---
description: 'Customer MDM Solution: In a CMDM system, the contained b2b
  use cases explain the data flow.'
title: '\[%=Heading.Level1%\]'
---

Business-to-Business Coexistence Use Case
=========================================

#### Scenario 1 - Consolidation

Benny, a representative from the sales team, is responsible for
retailers and distributors that have contracts to resell ACME's
products.

Benny needs to be able to maintain sales terms and conditions, as well
as maintain relationships with appropriate contact person(s) for each
retailer / distributor (sales reps, account owners, purchasers, etc.).

He requires his retailer / distributor information to be accurate in
order to intelligently negotiate appropriate terms and conditions.

Susie from Financing reaches out to Benny to request the retailers /
distributors contact information.

Benny primarily interfaces with ACME's CRM system to track and edit all
relationships and conditions.

As field representatives enter contact information for their retailers /
distributors, they may enter the same contact person multiple times.
Since different CRM instances track sales and relationships across
different regions of the country, this requires deduplicating across the
various CRM platforms. This can be a complex process for Benny to look
up the proper contact person for a retailer who's parent company
information is maintained in a different CRM instance. This can be
frustrating to Benny as he must first identify what the parent-child
subsidiary relationship is and then has to determine which CRM instance
to search in. Even so, there is no guarantee that the retailer
information is stored in a single CRM instance nor is there any
governance to ensure the data is up to date.

To account for these challenges, ACME requires a solution which assists
in determining which Primary Contact is accurate, up to date, and
appropriate to the inquiring department (Marketing contact for Marketing
Analyst, Technical Contact for IT, etc.)

**Current Data Flow**

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%202a.png)

Within the current system landscape Contacts are created and stored
across many CRM systems. These systems do not interact frequently
enough. This means Benny may find duplicated records across the systems,
which makes it difficult to determine who the primary contact is. Susie
works out of ERP and must notify Benny via email to have contacts or
payment terms updated.

**To-Be Data Flow**

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%202b.png)

With a CMDM solution in place, all data is fed into STEP. It is then
synchronized back to the various source systems in a timely manner. The
solution consolidates all contact persons from the various CRM
systems and also deduplicates them within each organization.

This ensures that Benny has the most accurate and complete data
available regardless of which CRM he is accessing.

Additionally, Susie is able to rely on the data in ERP because it is in
constant communication with CMDM.

#### Scenario 2 - Synchronization

Doris is also part of the sales team but works primarily in the field.

Her role requires her to meet with ACME's retailers / distributors to
identify and provide relevant product offerings based on climate,
demographics, and demand that are specific to individual sales regions
and territories.  In doing this, ACME's strategy is to increase brand
awareness and up-sell / cross-sell opportunities by empowering their
retailers / distributors to cater to the demand of the end-consumers.

As a saleswoman, Doris must have the most up to date information on
which contacts representing retailers and distributors to invoice.  To
do this, Doris relies on her access to ACME's ERP system to track all
transactions.

While Doris' job depends heavily on Benny's work, ACME's ERP system does
not synch with their various CRM systems in a timely manner. Because of
this, Doris may place orders without realizing that
payment conditions have changed, leading to her and the customer
operating under out-dated terms. This miscommunication leads
to frustrating ACME's retailers / distributors when they sign up for one
payment term but are invoiced according to another. End customers'
shopping experience may also be negatively impacted when retailers pass
along the cost differential to them.

In summary, these issues lead to: low governance, payment risks,
diminished customer experience, and increased costs and potentially lost
revenue.

**Current Data Flow**

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%201a.png)

With the current System landscape Doris does not have the most up to
date information available to her. This may lead to Doris setting
payment terms based on outdated data.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%201b.png)

With CMDM in place Doris can be sure that she is working with the best
possible data. This allows her to set appropriate payment terms and
avoid duplicating contacts no matter what CRM she interacts with.

#### Scenario 3 - Mastered Data

In this scenario, Jack works with business analytics and is responsible
for creating business reports. He succeeds when he can create accurate
reports and insights into the state of the business.

More specifically, Jack needs to provide other departments (marketing,
e-commerce, finance, and management) with information such as:

-   How many customers do we actually have?
-   Who are the best customers?
-   How much and which products do they buy?
-   Are my customers standalone or do they belong to a group?

Jack creates all reports in the Business Intelligence system.

Unfortunately, ACME's current solution does not provide a good way for
marketing (and other departments) to maintain and build their specific
hierarchies, nor is it possible to ensure the availability, usability,
and integrity of the data. When there is no consolidated, trusted view,
Jack is unable to provide for them an accurate overview of the customer.

The low-quality data this solution generates is sent to the BI system
from various sources. The chief issues with the data include:
duplicates, incomplete records, conflicting data, no source of truth,
and differing data formats.

These issues result in reactive or wrong strategic decisions, and
potential revenue in cross-sell is not realized.

**Current Data Flow**

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%203a.png)

Jack must interact with Benny to receive data from the CRMs since he
does not have access to them. This leads to conflicting or inaccurate
data for the reports. With bad data, the reports do not generate the
value they should.

**To-Be Data Flow**

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%203b.png)

With the CMDM solution in place, all source systems are being read when
generating the master data. This allows Jack to pull whatever data he
needs from the CMDM system rather than multiple siloed source systems.
This ensures that reports can be trusted because they are generated off
the most accurate and up-to-date information. This includes golden
customer records and golden company hierarchies. The golden data reports
that Jack provides allows marketing to efficiently run campaigns. The
golden company hierarchy allows Finance to more accurately run quarterly
roll-up reports.
