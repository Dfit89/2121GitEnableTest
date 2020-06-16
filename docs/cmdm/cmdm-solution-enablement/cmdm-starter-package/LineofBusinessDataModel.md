---
description: 'Customer MDM Solution: This Enablement documentation
  explains the Line of Business data model in a CMDM system.'
title: Line of Business Data Model
---

Line of Business Data Model
===========================

Introduction
------------

The term \'Line of Business\' is defined by Gartner as \'a corporate
subdivision focused on a single product or family of products.\' It is
quite common for Business-to-Business (B2B) organizations to be able to
manage their operational master data across multiple lines of businesses
(LOB).

For example, CleanGoods Manufacturer, operates across a number of
different LOBs:

-   Household Cleaning Supplies -- Cleaners and chemical cleaning agents
    manufactured and marketed towards typical household consumers.
-   Consumer Charcoal -- Consumer-grade charcoal of varying types.
    Manufactured and marketed for us with barbecue grills.
-   Professional Cleaning Supplies -- Cleaners and chemical cleaning
    agents manufactured and marketed towards businesses and institutions
    such as schools, professional contractors, government entities, etc.

Generally, one LOB may be a subdivision focused on perishable goods that
are manufactured, marketed, and sold to average household consumers,
whereas another LOB may be focused on selling to professional businesses
such as hospitals, corporations, or government entities.

To further illustrate this concept, BlueBox Retailer is a fictitious
retail business that is a direct customer to CleanGoods, specifically
for CleanGoods Household Cleaning Supplies and CleanGoods Consumer
Charcoal.

For the sake of ease, ClleanGoods should master the customer data of a
particular BlueBox retail store, as one Organization Customer Entity,
which is shared amongst the different LOBs. This model makes it possible
to keep an overview of all interactions with BlueBox, across the LOBs
and optimizes the process of having one accurate and complete version of
information about BlueBox, across the enterprise.

While this implementation works for these use cases, CleanGoods
Household Cleaning Supplies and CleanGoods Consumer Charcoal do not
handle all interactions with BlueBox the same way. Instead, they use
different invoice schedules and ship-to destinations. This information
is treated as customer master data while being LOB specific.

Data Model Explained
--------------------

LOB-specific customer data should be modeled as data containers on an
Organization Customer Entity.

In the example of CleanGoods and BlueBox, exactly one Entity would exist
for one particular BlueBox retail store. That Entity would have two data
container objects of type \'LineOfBusinessData,\' as outlined below.

![](../../../../Resources/Images/Solution%20Enablement/CMDM/LOBDataContainerType.png)

The initial pre-configurations will include the following attributes
associated with LOB data containers:

![](../../../../Resources/Images/Solution%20Enablement/CMDM/LOBDataContainerAttributes.png)

Data containers are used to model LOB data as associated to a customer
record. Each LOB will be its own data container object with
corresponding attributes and references. The initial configuration for
the LineOfBusiness attribute is a data container key. This configuration
allows only one entry of each LineOfBusiness per customer.

PRODOC note: \--\[IMAGE UPDATED LATER; WAITING FOR DATA CONTAINER
UPDATES\]\--
