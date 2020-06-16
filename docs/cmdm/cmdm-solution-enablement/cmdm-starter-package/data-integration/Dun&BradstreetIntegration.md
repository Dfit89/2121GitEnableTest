---
description: 'Customer MDM Solution: This topic is around the Dun &
  Bradstreet plugin integrating with STEP.'
title: '\[%=Heading.Level1%\]'
---

Dun & Bradstreet Integration
============================

Dun & Bradstreet is a leading authority in augmenting and enhancing
customer and supplier data with industry leading company information
within CMDM.

Stibo Systems\' CMDM includes integration with D&B Match- and D&B
Company Profile services.

The D&B Match service integration, matches organization master data with
D&B's database of over 265 million organizational records world-wide and
return relevant match candidates. Information such as DUNS number,
address and contact information and more are provided using the Basic
match. For more information, see the **Dun & Bradstreet Matching** topic
in the **Data Integration** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

The D&B Company Profile service provides over 220 attributes of business
insight related to marketing and sales information, company structures,
financial information, key executive contact information and more. For
more information, see the **Dun & Bradstreet Company Profile
Enrichment** topic in the **Data Integration** documentation[
here]{.mcFormatColor style="color: Blue;"}.

Use Case
--------

ACME Company is a large, multi-national holding company with
subsidiaries that spans across various continents. ACME's customer
portfolio consists of many business-to-business (B2B) accounts which
operate across various industries.

In an initiative to improve overall reporting to benefit various
departments such as legal, marketing, and finance, ACME realizes a need
for a better understanding of their customers. To accomplish this, ACME
has commissioned CMDM to be the central repository for B2B customer data
by sending their customer information from various source systems to
CMDM for deduplication and further enrichment.

Czarina is a data steward for ACME company, whose responsibilities
include ensuring ACME's master customer data, which drives all reporting
and analytics, is accurate and up to date.

Using the Dun & Bradstreet integration offering, CMDM firstly obtains
the DUNS number for ACME customers using D&B Match by providing basic
information such as legal entity name of the organization or a main
organization address.

ACME Company's Stibo Systems\' CMDM implementation will automatically
use the information provided by D&B, to identify duplicate customers and
to improve various customer hierarchy structures.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/ACMECMDMImplementation.png)

Using the Dun & Bradstreet integration offering, the diagram above
depicts the flow of information for this particular use case:

1.  Source record information from ACME source system(s) (i.e., CRM) are
    sent to CMDM.
2.  As Organization Customer records are created, CMDM automatically
    obtains a DUNS number for the customer(s) by running a D&B Match.
    The request includes basic information such as legal entity name of
    the organization, address, phone number, tax identifiers, etc. In
    response, if D&B returns a match, then a DUNS number is provided and
    associated with the customer record.
    a.  If multiple potential matches are found, D&B will return the
        list of candidates and require a manual clerical review. It is
        part of Czarina's responsibility to review and select the most
        accurate match; once this is completed the correct DUNS number
        is associated with the customer record.

The DUNS number is a D&B unique identifier which directly correlates to
other government identification protocols such as EIN or Tax
Identification Number. This ensures the uniqueness of the customer
entity in question.

1.  Having obtained the DUNS number, ACME will further enrich their B2B
    customer data by automatically leveraging the D&B Detailed Company
    Profile integration.

As a global company that operates across multiple industries, ACME plans
to utilize this detailed information to build an industry segmentation
hierarchy for their customers, which allows the finance department to
properly report on, invoice, as well as be made aware of any relevant
tax breaks associated to customers within industries.

1.  A separate process within CMDM is created to automated the creation
    of industry hierarchies and categorization of customers within such
    hierarchies. This logic is based on D&B profile data and must
    execute after D&B enrichment.
2.  Once the relevant hierarchy(s) is created, data is then synchronized
    with external systems (i.e., Finance database) (see details below)
3.  From there, the Finance department now has the complete view of
    their customers with respect to their particular industry and
    available metadata.
4.  The Finance department now is able to confidently send appropriate
    invoices and other business transactions.

Creation of Hierarchies
-----------------------

Once organization customer records have been enriched with D&B data, a
separate process is initiated to evaluate SIC and NAICS industry codes
to automate the building of an industry hierarchy as well as
categorization of customers into this hierarchy.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/HierarchyExample.png)

### Identifying More Duplicates

As ACME's Stibo Systems\' CMDM solution is configured to match customer
records on various data provided by D&B, whenever it is available, event
triggering of matching algorithms, will automatically identify and merge
duplicate customer records that could not previously be identified, due
to a lack of common identifiers on the duplicate customer records.

For further information on CMDM's matching capabilities, refer to the
matching documentation.

D&B Data Flow within CMDM Application
-------------------------------------

The progression of data flow for B2B organization records as it is
de-duplicated within CMDM and also further enriched via Dun & Bradstreet
is shown below.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/DandBFlow.png)

### Transaction 1: Inbound Integration Endpoint

An inbound integration endpoint will receive a message and transform it
into STEPXML.

Once transformed, the Match & Merge Importer will:

-   Execute standardizations and other associated business rules to
    cleanse the data. Cleansed data allows for the Match algorithm to
    more accurately identify duplicate records.
-   Determine the target Golden Record. For more information, see the
    **IIEP - Configure Match and Merge Importer** topic of the **Data
    Exchange** documentation[ here]{.mcFormatColor
    style="color: Blue;"}.
-   Survivorship rules will write any updates from the incoming data to
    the golden record. For more information, see the **Golden Records
    Survivorship Rules** section of the **Matching, Linking, and
    Merging** documentation[ here]{.mcFormatColor style="color: Blue;"}.
-   To the extent that a Golden Record was created or an existing Golden
    Record was updated, events will be written to event queues
    triggering on those changes. In this case, a Matching event
    processor as well as an Outbound Integration Endpoint.

### Transaction 2: Matching Event Processor

When new golden records are created or an existing golden record is
updated, this will trigger a matching event, with the purpose of
comparing golden records to each other. Prior to matching, the golden
record under treatment will have its match codes updated.

Matching golden records may result in a clerical review workflow
initiation or a merge, depending on the score. Additionally,
survivorship rules should trigger a D&B Match event

For more information, see the **Clerical Review** topic of the
**Matching, Linking, and Merging** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

### Transaction 3: D&B Match Event Processor

Golden record events are then triggered for the D&B Match event
processor. This triggers a webservice call to D&B to obtain a
corresponding match to existing entities within D&B database. The D&B
response will invoke one of two types of behaviors within CMDM.

If a direct match is found, a corresponding D&B entity record is created
within CMDM and referenced to the golden organization record. Attribute
information from the D&B response are then parsed into D&B attributes.

Once a DUNS number is obtained, a D&B Profile event should be triggered
for the D&B Detailed Profile Event Processor.

If potential match candidates are returned by D&B, then corresponding
D&B entities are created and submitted to the \'Select Candidate\'
workflow state.

### Transaction 4: D&B Profile Event Processor

Once a D&B match has been found, a second D&B event processor sends the
D&B record with its corresponding DUNS number back to D&B for retrieval
of detailed company profile information.

The D&B response from this call is then parsed into corresponding D&B
attributes on the D&B record.

Once a D&B response is received and parsed, two events should be
triggered:

-   Match Event -- in the case that the detailed profile provides more
    information that may affect matching results, the Matching Event
    Processor is invoked to re-run the match algorithm.
-   Export Event -- to synchronize the golden record information with
    external systems, an export event is triggered for an Outbound
    Integration Endpoint(s)

### Transaction 5: Outbound Integration Endpoint

Whenever Golden Records are created or changed, an export event will
trigger. This allows the mastered data to be synced back to the various
source systems.

For more information, see the **Outbound Integration Endpoints** topic
of the **Data Exchange** documentation[ here]{.mcFormatColor
style="color: Blue;"}.
