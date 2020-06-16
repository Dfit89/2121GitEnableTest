---
description: 'CMDM Solution Enablement: This topic looks at the
  relationships, constraints, and terminology that is used in this
  implementation guide.'
title: SAP Customer and Enterprise Structure and Definitions
---

SAP Customers and Enterprise Structure Definitions
==================================================

This documentation assumes an understanding of generic SAP structures.
The following diagram shows an example of the data structure within SAP
in a CMDM implementation.

![](../../../../../../Resources/Images/SystemSetup/SAPCustomerEnterpriseStruct.png)

This topic uses a number of SAP terminology. All readers are recommended
to be familiar with this terminology to better understand SAP data
structures.

For the following terms, please refer to this SAP Online Documentation
for further details:

https://help.sap.com/viewer/e43f5774d00640d9adbf39734fe5933c/6.00.29/en-US/9a95c7536e8e2a4be10000000a174cb4.html

<https://help.sap.com/viewer/e79854f090014378a89d74024923dbab/6.00.29/en-US/8b6fbd534f22b44ce10000000a174cb4.html>

-   Company Code
-   Sales Organization
-   Distribution Channel
-   Division
-   Sales Area
-   Partner Functions
-   Account Group

For Partner Functions and Account Groups, please refer to this SAP
Online Documentation for further details:

https://help.sap.com/viewer/e79854f090014378a89d74024923dbab/6.00.29/en-US/8b6fbd534f22b44ce10000000a174cb4.html

<https://help.sap.com/viewer/e79854f090014378a89d74024923dbab/6.00.29/en-US/8b6fbd534f22b44ce10000000a174cb4.html>

Relations and Constraints
-------------------------

The following sections are expansions on the logical data model which
details the relationships between entities and elements that include SAP
customer and enterprise structures.

Uniqueness Constraints

The following is a summary of the uniqueness constraints presented in
the Logical Model diagram:

-   The following types are unique by ID:

```{=html}
<!-- -->
```
-   CompanyCode
-   SalesOrganization
-   DistributionChannel
-   Division
-   Customer

```{=html}
<!-- -->
```
-   SalesArea is unique by the combination of SalesOrganization,
    DistributionChannel and Division
-   CustomerSalesAreaData is unique by Customer and SalesArea
-   CustomerCompanyCodeData is unique by Customer and CompanyCode

Sales Area Constraints

![](../../../../../../Resources/Images/SystemSetup/SalesAreaConstraint.png)

'SAP Customer Sales area data,' a data container, is valid for a
customer only if the sales area is currently associated to a sales
organization that is, in turn, also associated with the same company
code for which that the customer has data.

Partner Functions Constraints

![](../../../../../../Resources/Images/SystemSetup/PartnerFunctionConstraints.png)

A Customer has one, and only one, account group. An account group has
one-to-many valid partner functions. Not all customers can act in all
partner functions.

Each customer has exactly one account group and, by extension, must also
have one or multiple partner function relations.

Common Distribution Channel and Division Constraints

To avoid redundant sales area master data across distribution channels
and divisions, distribution channels and division may have a common
\'parent,\' which is logically resolved into what may be termed as
\'common sales areas.\' This concept means that sales areas associated
to a particular distribution channel and division may not also be the
\'parent\' of a different distribution channel and division that is
already associated with another sales area. This hierarchy is nested.

If a customer is active in a sales area that is common for other sales
areas, this customer cannot have master data in these other sales areas.
