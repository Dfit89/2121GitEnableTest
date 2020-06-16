---
description: 'CMDM Solution Enablement: This topic revolves around the
  STEP implementation with SAP and using STEP structures as examples.'
title: SAP Customer and Enterprise Structures
---

SAP Customer and Enterprise Structures in CMDM
==============================================

The following sections provide an overview of the CMDM implementation of
SAP data structures. For information on the SAP implementation, see the
**SAP Organizational Data Structures** topic in this documentation[
here]{.mcFormatColor style="color: Blue;"}. For information on the
general relationships, constraints, and terms used, see **SAP Customer
and Enterprise Structure and Definitions** topic in this documentation[
here]{.mcFormatColor style="color: Blue;"}.

SAP Customer

The SAP Customer is the direct customer of the CPG company. For example,
BlueBox Retailer is a customer of CleanGoods Manufacturer.

The SAP Customer will be represented by the Organization Customer entity
type in CMDM.

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/CustomerRootExample-SAP.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/OrganizationCustomerHierarchy.png)

Customer Company Code Data & Customer Sales Area Data

Customer Company Code Data & Customer Sales Area Data are data
containers on the Organization Customer entity.

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/CustCompanyCode-DC.png)

Data-Container-to-Entity References

For each 'Customer Company Code Data' data container, a reference will
point to the target Company Code entity, such as \'-Company Code.\'

For each 'Customer Sales Area Data' data container, a reference will
point to the target Sales Area entity, such as \'-Sales Area.\'

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/Data-Container-to-EntityReferences.png)

For each 'Customer Sales Area Data' data container, a reference will
point to an Organization Customer record, while for each 'Customer Sales
Area Data' data container, a reference will point to an Account Group
entity.

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SalesAreaReferencedBy.png)

Conversely, each Organization Customer record may be referenced-by a
'Customer Sales Area Data' data container.

### SAP Enterprise Structure

A JavaScript business condition is used for governing the Customer
Entity data integrity constraints. For more information on these
constraints, see the **SAP Customer and Enterprise Structure and
Definitions** topic in this documentation[ here]{.mcFormatColor
style="color: Blue;"}.

The business condition assesses whether the Customer Entity is valid for
the configured Enterprise Structure. The execution of this business
condition should happen in a Workflow as part of a transition state and
on approval of customer data.

The CMDM enablement pre-configurations for SAP data structures will
include the basic SAP data model for object types, attributes, and
references.

Account Group

System setup

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPAccountsSetup.png)

Example

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/ExampleOfAccountGroups.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/RecordExample.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/ExampleofReferences.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/ExampleOfreferencedby.png)

Partner Function

The CMDM representations of SAP partner functions will be via a
dedicated entity type.

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPPartnerStructuresSetup.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPPartnerFunction-Objects.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPPartnerFunctionRecord.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPEntityReferenceExamples.png)

References from 'Customer Sales Area Data' data container on
Organization Customer entity to other Organization Customer entity or
reference to itself.

SAP Company Code

As a global company, CleanGoods has separate operating entities
determined by geography. Each operating entity is responsible for its
own sales and financial reporting, hence the need for separate
organization representation as Company Codes.

In CMDM, Company Code is its own entity type and is a reference from:

-   Customer Company Code Data' data container via 'SAP Company Code
    Data -- Company Code' reference type.
-   Sales Organization entity via 'SAP Sales Organization -- Company
    Code' reference type.

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPCompanyCodes.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPCompanyCodeRecord.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPReferencedByCompanyCodeExample.png)

Sales Area

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPSalesAreaCompanies.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPSalesAreaRecordExample.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPSalesAreaReferencesExample.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPSalesAreaReferencedByExample.png)

SAP Sales Area Data -- Sales Area is a reference from a Sales Area data
container.

Sales Organization

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPSalesOrgStructure.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPSalesOrgRecordExample.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPSalesOrgReferencesExample.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPSalesOrgReferencedByExample.png)

Distribution Channel

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPDistributionChannelStructureSetup.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPDistributionChannelRecordExample.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPDistriutionChannelReferencedByExample.png)

Division

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPDivisionStructureSetup.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPDivisionRecordExample.png)

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/SAPDivisionsReferencedByExample.png)
