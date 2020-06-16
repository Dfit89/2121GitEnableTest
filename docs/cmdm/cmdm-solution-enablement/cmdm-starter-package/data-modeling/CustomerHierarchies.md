---
description: 'Customer MDM Solution: This topic covers how to construct
  customer Hierarchies.'
title: Customer Hierarchies
---

Customer Hierarchies
====================

The primary purpose for a customer hierarchy in CMDM is for proper
grouping of customers. There are two avenues for application: internal
view and external view.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/HierarchyViews.png)

With internal view, organizational ownership shows business owners as
the customers and allocate customers to actual locations when doing
businesses with your company. This affords a view from your own
company's perspective as well as the ability to group customers
according to your internal structure.

With external view, the customer has a legal ownership structure, works
as a standard industry classification, and it shows the customer
location, without regard to the company\'s location. This affords a view
on customers from their company's perspective.

Constructing Hierarchies
------------------------

There are three primary methods of constructing a customer hierarchy in
STEP:

-   **Manually** - This is the approach delivered with the
    implementations package configurations.
-   **Import** - Relevant reference types and parent ID\'s can be loaded
    via an import to construct hierarchies based on external data.
-   **Business logic** - D&B could potentially be leveraged to construct
    hierarchies based on linking of DUNS number and parent DUNS.

Hierarchy Benchmark
-------------------

When considering recommended practices in constructing customer
hierarchies, customers must pass the \'is grouped by\' test. This is a
general analysis of grouping based on common characteristics. Some
examples of characteristic groupings are as described in the following
sections.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/OrgChart.png)

Organizational Characteristics
------------------------------

Organizational hierarchies may be characterized by customers that are
owned by the same organizational unit, such as with a Financial or Sales
organization. Organizational hierarchies are typically used by the
business to organize customers according to the organizational setup of
their company (division, sales organization etc.) and may also be used
in sales transactions, revenue reporting, and/or commissioning. The same
customer may also be referenced in different locations within this
hierarchical structure.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/OrgCharacteristics.png)

A division is regarded as an organizational unit for sales and
distribution with a specific product portfolio to a customer. For every
division, customer-specific agreements can be made like for partial
deliveries, pricing, and terms of payment. A division can create an
exclusion list of products for other divisions which can only be sold to
a customer from that particular division.

In large organizations, one or more divisions may be responsible for a
customer, such as if the company is selling cleaning equipment such as
disinfectant dispensers (healthcare division) and laundry machines
(textile care division) to the same hospital.

Legal Characteristics
---------------------

Legal hierarchies may be characterized by customers that are owned by
the same legal entity. Legal hierarchies are typically used by the
business to categorize customers according to legal ownership, i.e.,
between holdings and subsidiaries and/or shareholders. A common usage is
for legal reporting and analytics such as whitespace, risk analysis and
credit checks (ex. roll up from subsidiary to holding). The same
customer is not typically placed under different locations.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/LegalHierarchy.png)

The above example illustrates a legal hierarchy for ACME Inc.

Industry Characteristics
------------------------

Industry-specific hierarchies may be characterized by customers that are
conducting the same type of business. Industry hierarchies are typically
used by the business to categorize customers by type of business using
the Standard Industry Classification (SIC). This hierarchy may be used
for analytics, i.e., customer/ market segmentation (customer allocated
to industry, organizational unit allocated to industry).

The same customer is not typically placed under different locations.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/CompaniesStructure.png)

Companies of the same industry are assigned the same SIC code. For
example, General Motors, Ford Motor Corporation, Honda, and Toyota were
all assigned the SIC code of 3711.

Entities have limited functionality when using in combination with
Classifications:\

-   Entities are not shown as \'sub-products\' (or children) of the
    Classification node
-   Attribute values cannot be inherited from the Classification node to
    the Entity object.
-   Classification references to Entities are not inherited from parent
    Classification to child Classification.

Spatial Location
----------------

Location-based hierarchies may be characterized by customers that are
allocated at the same spatial location. Location hierarchies are
typically used by the business in sales transactions (ordering address),
delivery planning (routing), regional revenue reporting, whitespace
analysis, segmentation (demographics). This hierarchy may mix different
customers under the same location.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/SpatialLocation.png)

In this example, the hierarchy is purely spatial:

-   The Region contains lower categories called \'EMEA\' and \'ASIA\'
-   Below \'EMEA\' you'd find countries of Europe and Middle East
-   Below \'ASIA,\' you would have countries like \'CN,\' \'JPN,\' etc.
-   Below \'CN\' you could have provinces like \'Beijing\' and cities
    like \'Yizhuang,\' etc.
-   Below the \'Yizhuang\' node, you have all customers which are
    allocated on this location

When grouping customers, consider what the usage of the hierarchy is
(organizational, legal, spatial or other). Furthermore, hierarchy names
should be designed to organize customers used in that specific context.

Customer hierarchies are a way of structuring customer data so that the
data is related to and connected to other objects. This isn\'t the same
structuring as with classifications for products, nor will it be the
same structure as a web hierarchy where each sales channel has their own
web sites. Finally, customer hierarchies are not structured for
searching, sorting, and browsing data, though these can be built to
apply to customer hierarchies.

Customer Hierarchy Use Cases
----------------------------

### Use Case 1 - ACME Group Company Financial Hierarchy

Acme Group consists of fourteen daughter companies across the Americas
region. Among these, the relationships across sister companies may or
may not exist. In each of these companies there may also exist
subsidiaries which operate independently of the each other and of the
parent company. These subsidiaries are a combination of acquisitions and
spin-offs of individual divisions / business units:

-   **ACME Group** - Parent holding company with multiple subsidiary
-   **ACME Inc** - Apparel Manufacturer and Distributor
-   **ACME Healthcare** - Manufacturer and Distributor of healthcare
    equipment and supplies
-   **Imaging & IT** -- Focus on healthcare imaging systems
-   **Workflow Solutions** -- Focus on business workflow solutions
    either as a standalone solution or to compliment an ERP system.
-   **Diagnostics** -- Focus on healthcare chemical diagnostic supplies
-   **ACME Healthcare Supplies LTDA, Brazil** - Healthcare Supply
    Division headquartered in Brazil and caters to South America
-   **Obits Technologies** -- Subsidiary focusing on enterprise software
-   **Obits Financial Services** -- Focus on financial sector: banking,
    insurance, wealth management
-   **Obits Energy Innovations** -- Think tank for innovations with a
    focus on energy generation, usage, and consumption
-   **Wind Power** -- Leader in wind turbine technology
-   **Solar & Hydroelectric** -- Leader in alternative energy solutions
    for businesses and municipalities
-   **Oil & Gas** -- Focus on technology to safely transport crude oil
    and natural gas
-   **Energy Service** -- Energy Solutions Professional Service
    offerings
-   **Obits Energy LTDA, Brazil** -- Energy division headquartered in
    Brazil and caters to South America

Walter is an Level I analyst for Acme Group, the primary holding company
of Acme Inc and all daughter companies and subsidiaries. In alignment
with a new initiative, one of Walter's tasks is to assist with the
quarterly reporting for Acme Group. To do so, Walter requires running
consolidated (roll-up) reports to provide an aggregate view of all of
Acme Group's holdings and investments.

The challenge that Walter faces today is due to the growing number of
holdings and subsidiaries over time, each individual company may have
implemented their own accounting solutions to track various performance
metrics and KPIs. As such, each company has different views of the truth
this makes it very difficult to track and report on the relationships
between daughter-to-subsidiary, daughter-to-daughter,
subsidiary-to-subsidiary companies.

![](../../../../../Resources/Images/Data%20Governance/HierarchiesForACME.png)

Every quarter, Walter is tasked with generating a quarterly financial
report broken down by industry and subsidiaries. However, with no
centralized view of the corporate hierarchy and since finances are
maintained in separate, isolated ERPs based on industry and divisions.
Walter is operationally challenged due to lack of governance.

![](../../../../../Resources/Images/Data%20Governance/ACMETools.png)

However in using CMDM, Walter is now able to utilize the hierarchy
maintenance tools to visualize and maintain a golden hierarchy which
models the complete company hierarchy for Acme Group. By taking in
consolidating the various information provided by each company's source
system, CMDM may now establish the proper relationships between
companies within Acme Group.

This golden hierarchy information may be synchronized with Acme Group's
accounting application so Walter now has an accurate and complete view
of all holdings and daughter companies. Walter is able to confidently
select which subsidiaries to be included for various roll-up reports to
drive Acme Group's quarterly analysis.

![](../../../../../Resources/Images/Data%20Governance/RoadRunnerHierarchy.png)

### Use Case 2 - ACME Group Company Sales Hierarchy

Whitney, a data steward, is responsible for maintaining internal
customer hierarchies at ACME. A new sales manager has been hired to
replace a retiree, and Whitney has been asked to update the sales
hierarchy. She will need to locate the appropriate territory for the
retiree and remove him before adding the new sales manager.

Without a structured internal view, however, ACME struggles with the
ability to accurately view and maintain their internal sales structure.
To overcome this obstacle, Whitney can use STEP\'s customer hierarchy
capabilities to easily identify the correct region for the new sales
manager and create a new entity to represent the sales manager directly
below.

With STEP, ACME can now easily view their internal hierarchies, and data
stewards are empowered to maintain them.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Sales%20Hierarchy.png)

Recommended Practices for Hierarchies
-------------------------------------

### Navigation

The Web UI should be optimized for navigating hierarchies:

1.  The Homepage Left Primary Navigation Panel should include
    \'Hierarchies\' as a Tree Navigator menu item.

```{=html}
<!-- -->
```
1.  All hierarchy roots should be included in the within the Hierarchies
    menu item. Customer entities should be visualized within the company
    hierarchy screen, but should not be included in the Hierarchies Tree
    in the navigation panel.
2.  A hierarchy tab page should be available on all details pages for
    valid hierarchy object types.

### Referenced Based Hierarchy

Referenced based hierarchies are structured to where customers reference
other customers. Customers that are assigned to higher customer levels
specified by the reference type used to appropriate attribution. One
benefit of this hierarchy over the parent-child hierarchy is that
reassigning a customer doesn't not require related customers to have to
be moved, though the relationship change does apply to them.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/ReferencedHierarchy.png)

### Web Hierarchy

It is recommended to keep the web or sales hierarchy for products clean
from customer data. A web or sales hierarchy for products is not
intended to be customer specific but rather to represent the product
portfolio intended for a specific sales channel.

Customers are typically assigned to a distribution channel in ERP in
sales transactions. The distribution channel is an entity through which
sales items (products or services) reach customers. They may include
wholesale, retail and direct sales. Sales organization is the legal
entity that structures the company according to its sales requirements
(selling unit) and defines the basic sales and distribution structure. A
sales organization is responsible for selling products and services.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/WebHierarchy.png)

### Search Hierarchy

Customer hierarchies is not structured a searching, sorting, or browsing
hierarchy. If necessary these structures may be built in addition to
customer hierarchies.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/SearchHierarchy.png)
