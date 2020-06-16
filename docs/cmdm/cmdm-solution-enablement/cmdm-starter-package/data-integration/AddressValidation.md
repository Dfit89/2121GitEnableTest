---
description: 'Customer MDM Solution: Describes the use of Loqate in the
  initial configuration.'
title: Address Validation
---

Address Validation
==================

Loqate validations can occur at three different points when dealing with
customer records:

-   During Import of Source Records
-   After surviving attribute values have been determined for a newly
    created Golden Record
-   When updating existing Golden Records

It is recommended to validate address values upon Import and after
Survivorship.

For more general information on Loqate, see the **Loqate Integration**
section of the **Data Integration** documentation[ here]{.mcFormatColor
style="color: Blue;" conditions="Primary.Web"}.

Validate on Import
------------------

By calling Loqate during Import, each Source Record will have its
address values standardized before matching takes place. Raw values
taken from Source Systems commonly include typos or inconsistent
formatting. By standardizing these values beforehand, the matching
algorithm is able to match records more accurately.

Validate on Survivorship
------------------------

Validating addresses after survivorship ensures that the surviving
address values are standardized. However, because address matching is
less reliable when matching raw values taken from Source Systems, it is
recommended to validate on Import as well.

Validate Updates to Existing Records
------------------------------------

A Data Steward can trigger Loqate for single records or when running a
bulk update for a collection. By using either of the maintenance methods
listed below, address values can be standardized when records are
updated.

Maintenance Validation Methods:

-   A \'Run Business Rule\' button on a Node Details screen
-   Running a Bulk Update configuration (an Address Validation business
    rule can be configured for bulk updates)
-   An Event processor can monitor for changes to the address inputs.
    When changes are detected, an event is generated to have Loqate
    re-standardize the updated address.

By using Bulk Update, existing records can have their address values
standardized whenever their data is updated.

Validate via Webservice Request
-------------------------------

Address standardization can be triggered from an external system which
will generate a request and receive a response containing the
standardized address information. This requires no direct interaction
with STEP and provides a better user experience in allowing external
systems to use Loqate\'s address standardization feature. In exposing
address validation to external applications, address data points may be
standardized prior to flowing into CMDM, which further ensures that data
is trusted and verified.

For an example use case for using address validation via webservice
request, refer to the **Scenario 2 - E-commerce** section of the
**Business-to-Customer Coexistence Use Case** topic in the **CMDM Data
Flow** documentation[ here]{.mcFormatColor style="color: Blue;"}.

All customers that have purchased a Loqate license, either cloud or
local, will have access to this service.
