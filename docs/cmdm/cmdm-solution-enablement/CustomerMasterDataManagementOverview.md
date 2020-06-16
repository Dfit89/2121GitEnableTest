---
description: 'Customer MDM Solution: This topic is an overview
  explanation of the CMDM solution.'
title: '\[%=Heading.Level1%\]'
---

Customer MDM Overview
=====================

The Customer Master Data Management solution provides organizations with
the means to address complex customer data challenges and improve their
overall customer experience.

Improving Customer Experience {#improving-customer-experience conditions="Primary.Web"}
-----------------------------

Improving Customer Experience {#improving-customer-experience-1 .RNNoTOC conditions="Primary.Print"}
-----------------------------

Customer Experience is the holistic journey of a customer that begins
the moment they first become aware of a product and continues until the
customer is building their own loyalty platform with a product.

This documentation is focused on providing guidance to organizations in
how to improve their customer data so that they can make informed
decisions, and thus improve their customer experience.

![](../../../Resources/Images/CMDM/CX%20Journey.png)

Customer Data Management Challenges {#customer-data-management-challenges conditions="Primary.Web"}
-----------------------------------

Customer Data Management Challenges {#customer-data-management-challenges-1 .RNNoTOC conditions="Primary.Print"}
-----------------------------------

Organizations are faced with four primary challenges when managing
customer data:

-   Data Quality
-   Operational Inefficiencies
-   Reactive Strategic Decisions
-   Governance

Data Quality Challenges

Data quality issues typically arise when attempting to house and manage
customer data across multiple platforms. Doing so often times leads to
inaccurate, duplicated, and incomplete data.

Operational Inefficiencies

Operational inefficiencies can be characterized by an organization\'s
inability to share accurate and up-to-date data across the business,
severely impacting downstream systems, processes, and initiatives. For
example, some of these inefficiencies can lead to: returned mail,
increased costs, payment delays, and unacceptable response time.

Reactive Strategy Decisions

Many organizations struggle to achieve their Customer Relationship
Management (CRM) vision. Considering its impact on an organization\'s
success, a concrete CRM strategy is a high concern for business and
IT leaders.

Bad data is the most common reason many CRM initiatives fail.

Governance

The most important part of data governance is to consider the
availability, usability, integrity, and security of data within an
organization. Poor data governance can lead to financial, reputational,
and legal risks.

Implementation Methodologies {#implementation-methodologies conditions="Primary.Web"}
----------------------------

Implementation Methodologies {#implementation-methodologies-1 .RNNoTOC conditions="Primary.Print"}
----------------------------

CMDM comprises four paths to implementation. These paths are:

-   Consolidation Implementation
-   Coexistence Implementation
-   Registry Implementation
-   Centralized Implementation

Consolidation Implementation

This methodology refers to an implementation where STEP is a hub for
externally provided data that is funneled into single Golden Records,
which are then made available to external systems. These records are
created via matching and merging operations with validation checks
throughout the process. The STEP data created from this process is
read-only, which is often a necessity as the data originates outside of
STEP in an upstream system. A consolidation style implementation does
not synchronize data back to the contributing systems.

For example, a company wishes to combine all of their sales channel data
into one record bank so that data analytics may provide meaningful
information. Once all these records are consolidated, marketing
initiatives can use this information to target different channels as
well as different regions.

![](../../../Resources/Images/CMDM/ConsolidationMethodolgy.png)

Coexistence Implementation

This methodology refers to a scenario where multiple databases
containing the master data must operate at the same time. The customer
data is authored and stored in various external sources while being
synchronized to STEP. This process involves deduplication, conflict
resolution, and validation operations, resulting in the creation of
golden records. Finally, updates to the data can be done in the source
system and any external systems that master customer data. STEP
synchronizes the content of golden records back to the source systems,
keeping every source up to date with data contributed from any source.
This allows for a hybrid where DTA authoring may happen in the source
system as well as in the MDM system.

A common situation for coexistence is in companies where each department
has their own customer database. For example, a service department that
has data on customers is stored in a separate database than where
customer data is stored for the sales and marketing departments.
However, using a CMDM solution with the Coexistence model, if
information is changed in the marketing department, it is changed in all
other departments.

![](../../../Resources/Images/CMDM/CoexistenceMethodolgy.png)

Registry Implementation

The registry method uses a simple database to reconcile identifiers for
all customers across the enterprise. This method allows STEP to serve as
a referenced, read-only source of mastered customer data for external
systems with minimal data redundancy. STEP will only match on the bare
minimum of needed data to confirm a unique record. All externally
maintained data quality is the responsibility of the source systems.

For example, a company maintains different types of customer information
across various external systems. A registry is used to identify and
associate these different types of customer data with external systems.
STEP serves as this registry by storing unique records with identifiers
that are different from one external system to the next. STEP will ONLY
store these records and unique record identifiers, and deduplicate their
contact information.

![](../../../Resources/Images/CMDM/RegistryMethod.png)

Centralized Implementation

The centralized implementation is based around a well-managed and
governed central repository for all master data. This repository holds a
set of Golden Records that are read-only by the operational and
analytical systems throughout the enterprise. STEP is the centralized
owner of customer data, serving as the system of record. This system of
record is an organization's single version of truth for customer data.
Data is not only centralized in STEP but also created and stored there.
The most important aspect of a centralized implementation is that it is
a system of record instead of a system of reference.

For example, a company wants to use STEP as the system of record for
onboarding, deduplicating, and enriching new suppliers. Over time, STEP
could remove duplicate records of these suppliers, and then the golden
supplier records could be provided to external systems.

![](../../../Resources/Images/CMDM/CentralizedMethology.png)

This implementation guidelines focuses with a case that implements data
with the **consolidation** and the **coexistence** methodologies.
