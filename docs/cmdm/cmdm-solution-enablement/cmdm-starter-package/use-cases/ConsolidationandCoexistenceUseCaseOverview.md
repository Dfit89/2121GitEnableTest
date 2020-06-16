---
description: 'Customer MDM Solution: This topic provides an overview for
  the coexistence data model use case.'
title: Coexistence Use Case Overview
---

Consolidation and Coexistence Use Case Overview
===============================================

ACME Company requires solutions for its Business-to-Customer and its
Business-to-Business use cases.

ACME Company\'s Business to Customer Use Case
---------------------------------------------

The ACME Company is a large clothing brand which markets and sells
largely to North America. ACME sells directly to their consumers via
various channels. As the company has grown, issues have developed due to
poor data quality. Because of this, customer contact information is
rarely in sync across business units. Furthermore, all customer shopping
patterns are inaccurate because the data is not distributed and updated
evenly. This asyncrhonization causes a missed opportunity to target
customers for the best sales, promotions, and loyalty programs. Finally,
due to these gaps in the data, the customer experience is quite poor as
actions performed in one department by a customer are not known in
another.

During an internal evaluation of the IT infrastructure, it was revealed
that the customer data is owned and maintained by separate and distinct
source systems. This setup causes data to not be updated across the
enterprise, creating a large amount of conflicting duplicate customer
records. Additionally, it was concluded that a lack of data governance
has made it impossible to determine what degree of overlap and
duplication is present within the customer database.

To improve customer data quality, ACME has targeted a few areas where
data quality becomes less consistent:

-   ACME\'s e-commerce system processing customers who self-register on
    the company website.
-   Customers placing phone orders to a call center representative who
    then enters their data into ACME\'s ERP system.
-   Customers signing up for the loyalty platform.
-   Marketing uses customer data residing in ACME\'s CRM system for
    seasonal marketing campaigns.
-   ACME uses loyalty points which can be redeemed for discounts and
    contain a monetary value. The financial data is owned by the CRM
    system which stores additional financial information.

### Considerations

-   North America is the primary market.
-   ACME sells directly to customers via various channels.
-   Multiple different source systems contain customer data.
-   The customer data violates ACME\'s own data policies.

### Difficulties and Problems

-   Contact information not in sync across business units.
-   Customer shopping patterns are of poor quality.
-   Very poor user experience due to out of sync data across the
    business units.
-   There is an excessive amount of duplicated customer records across
    the business.

For specific B2C use cases, see the **Business-to-Customer Coexistence
Use Case** section of the documentation[ here]{.mcFormatColor
style="color: Blue;"}.

ACME Company\'s Business to Business Use Case
---------------------------------------------

ACME Company is a major clothing brand that not only sells directly to
individual consumers, but also to both major and independent retailers
and distributors across North America. To manage these various
retailers, North America is divided up into several sales territories
which are each managed by their own sales managers. Each sales territory
contains several retailers, and information for each territory is
managed by different instances of CRM. Since the same retailers may
operate out of various different states or sales territories, ACME
Company requires CMDM to not only deduplicate retail entities but also
provide a trusted source of information for various source systems.

ACME also tracks and maintains contact persons' information for each
retailer. These contact persons are designated sales representatives,
account owners at each retailer, and purchasers in the procurement
departments. The CMDM system must be able to account for contact persons
that move from retailer to retailer, or those that get duplicated within
the same organization, to ensure that accurate information is
maintained.

Sales hierarchies are used to organize the customer portfolio in the
sales staff and to aggregate bonus schemes in the sales staff, based on
the revenue from each customer.

### Considerations

-   ACME sells to both major and independent retailers and distributors
    as well as to consumers.
-   The company mostly services clients in North America.
-   The North American region is divided into several sales territories
    with sales managers responsible for each territory.
-   Contact persons are maintained in CRM as well as the ERP
    applications.

### Difficulties and Problems

-   There is an excessive amount of duplicate customer records.

For specific B2B use cases, see the **Business-to-Business Coexistence
Use Case** section of the documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Data Management Improvement Plan
--------------------------------

The ACME Company has strategically planned the evolution of how their
customer data will mature over the course of the next few years. To
accomplish this long-term goal, an enterprise strategy plan is laid out
in three phases, with each phase progressively building on top of the
previous one.

Phase 1 -- ACME would like to ensure their customer data is governed and
can be trusted across the entire organization:

-   Use MDM technologies to achieve a single, trusted customer view
    which is accurate, complete, and up to date.
-   Establish baselines and improve analytical reporting accuracy for a
    better CRM and e-commerce experience.
-   Identify customers who live under the same household for more
    efficient mail distribution and for better profiling of the
    customer.
-   Reduce operational overhead cost by decreasing the amount of
    returned mail due to inaccurate mailing addresses.

Phase 2 -- ACME would like to combine core customer master data with
transactions, website activity and social profiles:

-   Enhance the customer experience by providing a personalized shopping
    experience.
-   Utilize purchasing behavior analytics for increasing cross sell / up
    sell opportunities.
-   Discover hidden associates and relationships to gather context for
    segmentation, targeted marketing, risk management, and regulatory
    reporting.

Phase 3 -- ACME would like to further enhance the personalized shopping
experience:

-   Create an enterprise-wide single view of customers to serve all
    operational systems and use big data to generate insight and
    foresight based on advanced learning models.
-   Contextualized customer data is then used to enhance customer
    experience through machine learning as well as digitally automating
    key business processes.
