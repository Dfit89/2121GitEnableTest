---
description: 'Customer MDM Solution: This topic shows how to set up the
  CMDM solution initial configuration on a local system.'
title: Customer MDM Configuration Guide
---

Customer MDM Configuration Guide
================================

The initial configurations for the enablement solution provide a generic
set of configurations for a basic Customer MDM (CMDM) system for the
purpose of providing quicker time to value.

This document provides an in-depth overview of the CMDM initial
configurations as a compliment to the CMDM Enablement Guidelines. The
target audience for this guide is any party interested in taking the
initial configurations as a starting point to a new CMDM implementation.

Enablement Initial Configuration Overview
-----------------------------------------

The initial configurations include basic data models, i.e., object
types, attributes, references, etc., component models, workflows for
clerical review of customer de-duplication, inbound integrations for
data consumption, and web user interfaces (Web UI) for data stewardship.

The initial configurations are largely based on the Merge Golden Record
solution and addresses various implementation styles. The implementation
styles that are addressed in this guide are:

-   Consolidation
-   Coexistence
-   Centralized

Based on the implementation style that is most relevant to your
requirements, the following configuration files may be provided:

Base Configuration

-   Mandatory (select one of):
-   Consolidation & Coexistence
-   Centralized
-   SAP Data Model
-   Optional Extension for B2B: D&B Web UI Configuration

It is recommended that the initial configurations are loaded into a STEP
environment with the appropriate STEP Base. STEP Base is a clean, fresh
install of the STEP application. For details on which STEP Base to take
which corresponds to the purchased STEP version, please contact Stibo
Systems' Technical Services team.

STEP System Components
----------------------

The following components are required to be activated in your STEP
system prior to loading the initial configurations:

-   Party Data Matching (partydatamatching)
-   Company Data Visualization (companydata-visualization)
-   CMDM Monitoring (cmdm-monitoring)
-   Profiling (profiling)

Deployment of STEP components require adequate working knowledge of
patching STEP environments. For deploying STEP components, it is
recommended to solicit the assistance of Stibo Systems Support or
Technical Services.

### Third-party services

Stibo CMDM provides native integrations with third-party services to
enhance the data quality and reliability of master data. For CMDM, these
third-party services include integrations with:

-   Dun & Bradstreet -- For entity matching and company profiling in B2B
    implementations
-   Loqate -- For address verification
-   Experian - For email validations

Should any of these third-party integrations be part of a solution,
please consult with your sales representative to ensure properly
licensing is procured.

Installation of third-party services that require dedicated system
components are not included in this guide. Information regarding the
CMDM third-party integrations is available in the STEP Online Help
Documentation. Further detailed deployment instructions may also be
available upon request.

CMDM Base Configuration
-----------------------

The CMDM Base Configurations includes a basic data model and other
configurations that are shared across the subsequent configurations.
Hence, the Base Configuration file should be loaded first.

Object types and corresponding attribute definitions that are included
are Organization Customer and Contact Person.

For more information on data modeling, please refer to the Data Modeling
section of the Enablement Guidelines.

### Data Model

Organization Customer

For B2B implementations, the initial configurations provide attributes,
references, a match algorithm, and clerical review workflow for
Organization Customer entity type.

Contact Persons

Contact Person are also relevant for B2B implementations. From an
attribution standpoint, Contact Person is similar to Individual Customer
with the exception being that a Contact Person has its own algorithm and
clerical review workflow.

Address Standardization

Included with the Base configuration is the Address Standardization
business rule using the Loqate integration. As noted previously, please
consult Loqate documentation for details on configuring and setting up
the integration.

Lookup Tables

Lookup tables may be used to compliment the match algorithms. A Word
Alias Table is included for organizations Organization (Word Alias
Table). An Unmatched Word Factor Table is also included for
organizations (Organization Unmatched Word Factor Table).

CMDM Consolidated & Coexistence Configuration
---------------------------------------------

The characteristics of the Consolidated and Coexistence styles are
rather similar, hence, only a single configuration file is required for
either implementation style. However, one major difference between the
two styles are with regards to the synchronization of master data back
to external systems. Data synchronization requirements must be carefully
vetted and designed for during the CMDM implementation.

### Data Model

Individual Customer

For B2C implementations, the initial configurations provide a match
algorithm and clerical review workflow for Individual Customer entity
type.

Household

The Household entity type is relevant to the Individual Customer use
case for B2C implementations. The initial configurations provide a match
algorithm and clerical review workflow for Household.

Workflows

Four clerical review workflows are provided with this configuration.

-   Individual Customer Clerical Review
-   Organization Customer Clerical Review
-   Contact Person Clerical Review
-   Household Clerical Review

Clerical review workflows provide the data steward with an interface to
view and resolve potential duplicate findings by the respective
algorithms of each object type.

For more information on configuring Match Algorithms and Clerical Review
Workflows, see the **Matching, Linking, and Merging** documentation[
here]{.mcFormatColor style="color: Blue;"}.

User Privileges

The Consolidated and Coexistence configurations provide a generic user
group for Data Stewards. No special privileges will be configured for
this group, and all users will have system super user privileges.

Event processor

The preconfigured event processor collects events for Individual and
Organization customer records to run through their respective match
algorithms

### Consolidation & Coexistence Web UI

A Web UI configuration is provided for the purpose of meeting the
operational needs of the MDM Data Steward. The Web UI affords the data
steward the ability to carry out their daily tasks such as clerical
review remediation, ad-hoc stewardship responsibilities, maintaining
internal hierarchies, monitoring of data governance, and running data
profiles.

For more information on configuring a Web UI, see the **Creating a New
Web UI** topic in the **Web User Interfaces / Web UI Getting Started**
documentation[ here]{.mcFormatColor style="color: Blue;"}. For more
information on Data Stewardship, see the **Data Stewardship** topic in
this documentation[ here]{.mcFormatColor style="color: Blue;"}.

### Inbound Integration Endpoint

An Inbound Integration Endpoint (IIEP) is provided and used in
conjunction with the Match and Merge Importer. For more information, see
the **Inbound Integration Endpoint** topic ([here]{.mcFormatColor
style="color: Blue;"}) and the **Match and Merge Importer** topic
([here]{.mcFormatColor style="color: Blue;"}) in the **Data Exchange**
documentation.

### Component Models

The following component models are included in the Consolidated and
Coexistence Configuration file:

-   Matching
-   Configured for
-   Individual Customer
-   Household
-   Organization Customer
-   Contact Person
-   Matching -- Merge Golden Record
-   Configured for
-   Individual Customer
-   Organization Customer
-   Contact Person
-   Matching -- Link Golden Record
-   Configured for
-   Household

For more information, see the **Component Models** topic in the **System
Setup / Super User** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

CMDM Centralized Configuration for B2B
--------------------------------------

In a centralized MDM style, all customer data originates within CMDM and
may be synchronized downstream / throughout the enterprise. In such a
scenario, operational oversight and data governance is of utmost
importance to an organization. The CMDM must be able to accommodate
complexities of data structures as well as business processes.

### Data Model

As the centralized style deals primarily with the B2B use case,
companies must be able to model B2B customers as well as their
respective of lines of businesses. As such, the centralized
configuration includes organization customers with line of business data
containers. These data containers contain attribution that are specific
to the line of business the customer does business with.

Corresponding attribution and match algorithm are also provided in the
configuration.

A Find Similar algorithm is also provided to support the Onboarding
workflow user experience. This allows users to determine whether the
customer record they intend to onboard already exists in the system.

### Workflows

As customer data origination / authorship resides within CMDM, a
customer creation, or onboarding, mechanism must be present to allow all
departments and personas that are part of the new customer onboarding
process a means to interact with the data and even collaborate with one
another.

The Centralized configurations includes an [Onboarding Workflow]{.bold}
that is designed for contribution by the following personas:

-   Local Loqate (local-loqate)
-   Experian Email Validation (experian)
-   Dun & Bradstreet Company Match and Profiling (dnb-integration)

The workflow allows each persona to fulfill their respective enrichment
activities, while providing a means for intra-departmental
collaboration.

Complimentary to the Onboarding workflow, an [Approval workflow]{.bold}
is also in place which is owned by the MDM Specialist. The purpose of
this workflow is to accommodate ad-hoc stewardship of customer data and
providing a means for the MDM Specialist to review changes and execute
any business validation on the changes.

### User Privileges

The Centralized configurations provide distinct system user privileges
for each user persona that interfaces with customer data. User
privileges are important to governance and provides are tighter control
in ensuring the right people deals with the right data.

Currently, the MDM Specialist may be considered as the *super user* of
the Centralized MDM and has privileges to access, edit, and approve all
data in the system, whereas Sales, Finance, and Logistics do not have
permission to approve customer data.

### Event Processor

The preconfigured event processor collects events for Organization
customer records to run against the Centralized match algorithm.

### Centralized Web UI

A Web UI configuration is provided which allows direct user interface to
onboard, maintain, and approve customer data as it pertains to the
company's operational processes. In the Web UI, users from Sales,
Finance, Logistics, as well as MDM Specialist are able to carry out
their day to day activities.

For more information on configuring a Web UI, see the **Creating a New
Web UI** topic in the **Web User Interfaces / Web UI Getting Started**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

### Inbound Integration Endpoint

No inbound integration endpoint will be provided with the Centralized
Configuration.

### Component Models

-   Matching
-   Configured for:
-   Organization Customer
-   Contact Person
-   Matching -- Merge Golden Record
-   Configured for:
-   Organization Customer
-   Contact Person
-   Matching -- Link Golden Record
-   Configured for:
-   Household

For more information, see the **Component Models** topic in the **System
Setup / Super User** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

CMDM SAP Data Model Configuration
---------------------------------

As a compliment to the Centralized Configuration, the enablement
configurations include a centralized approach for modeling SAP business
processes in a B2B scenario. As many companies utilize SAP as their
primary ERP solution, the goal of this configuration is to allow for a
more seamless bridge between customer master data and SAP data
structures.

For this release, the SAP configuration will include the SAP data model
and corresponding business conditions to enforce SAP data modeling
constraints.

### Data Model

The SAP data model configuration uses the same Organization Customer
entity type as the other configuration sets. The intent of this
configuration is to be able to model complex SAP data structures in
order to provide a more seamless user experience for companies that
utilize SAP as their primary ERP platform. As such, the usage of
relationships from in between data structures is highly emphasized as
part of this release.

### Data Model Constraints

The support of complex SAP data structures denotes the supporting of
data integrity complexities and maintain proper constraints between the
data structures. This configuration includes basic SAP data integrity
validation rules to sure data integrity is maintained in CMDM.

For more information on SAP data model constraints, it is recommended to
research SAP documentation for the Sales & Distribution module, as well
as the relevant sections in this enablement guideline as a complimentary
resource.

Extension: Dun & Bradstreet WebUI Configuration
-----------------------------------------------

A separate Dun & Bradstreet Web UI configuration is available for those
who are interested in implementing the third-party integration. The Web
UI configuration provides an interface for data stewards to run D&B
Match to obtain the DUNS number and other relevant match information.
Furthermore, data stewards may also level the Web UI configuration to
run the D&B Company Profile service to obtain a more detailed overview
of an organization.

### Component Model

For security reasons, D&B subscription credentials may not be loaded via
STEPXML so users are recommended to utilize the \'Easy Set-up\' feature
of the D&B component model within the CMDM application. Deployment of
\'Easy Set-up\' will automatically create the relevant D&B object types,
attribution, and references in the system.

For more information, see the **Dun & Bradstreet Integration** in the
**Data Exchange** documentation ([here]{.mcFormatColor
style="color: Blue;"}) as well as the relevant sections in this
enablement guideline.

Sample Data Load Files
----------------------

For the Consolidated and Coexistence and Centralized configurations,
three sample data Excel files are available for each of the three
customer entity types to be imported via the match and merge import
configuration (i.e., Individuals, Organizations, and Contact Persons).

The names of these sample data files are:

-   SampleContacts.xlsx
-   SampleIndividuals.xlsx
-   SampleOrganizations.xlxs

Users should import SampleOrganizations.xlsx before importing
SampleContacts.xlsx.

Sample data files may be imported with the Match and Merge Importer via
the Asset Importer Widgets available within the Web UI.
