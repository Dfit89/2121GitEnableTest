---
description: 'Within the Product Content Management module, the
  \''govern\'' activity includes defining and maintaining a mapping
  between the ERP and PMDM. The product is automatically classified in
  the primary product hierarchy using a value (\''ERP line\'') provided by
  the ERP. And it is also possible to classify products directly in
  STEP.'
title: '\[%=Heading.AnyLevel%\]'
---

Product Content Management \'Govern\' Activity
==============================================

![](../../../Resources/Images/PMDM%20for%20Retail/PMDMGovern.png)

Data Steward
------------

+----------------------------------+----------------------------------+
| ![                               | The data steward:                |
| ](../../../Resources/Images/PMDM |                                  |
| %20for%20Retail/datasteward.png) | -   maintains the mapping        |
|                                  |     between the ERP              |
|                                  |     classification and the MDM   |
|                                  |     classification.              |
|                                  | -   performs Data Governance     |
|                                  |     tasks to maintain            |
|                                  |     attributes, attribute        |
|                                  |     groups, and LOVs.            |
+----------------------------------+----------------------------------+

Each of these tasks are defined below.

Maintain the ERP and PMDM Classification Mapping
------------------------------------------------

Within the Product Content Management module, the \'govern\' activity
includes defining and maintaining a mapping between the ERP and PMDM.
This task is usually performed by the data steward.

The product is automatically classified in the primary product hierarchy
using a value (\'ERP line\') provided by the ERP. And it is also
possible to classify products directly in STEP.

Applying automatic classifications requires a mapping between the \'ERP
line\' code, provided by the ERP, and a unique identifier of a node (a
level) in the primary product hierarchy. This identifier is the
attribute \'External Identifier (ExternalIdentifier)\'.

This mapping is served by a Transformation Lookup Table
(PMDM.LUT.ERPToPMDMMapping) and must be maintained in the workbench.

![](../../../Resources/Images/PMDM%20for%20Retail/ERP-MDMClassification.png)

**Mapping between ERP and PMDM - Click to Play**

[ ]{.wistia_embed .wistia_async_zvnegy0isj .popover=true
.popoverAnimateThumbnail=true
style="display:inline-block;height:281px;position:relative;width:533px"}

Attributes and LOV Data Governance
----------------------------------

The data steward manages attributes, attribute groups, and LOVs in the
Web UI. Data Governance features are accessed via a Stack Panel Item on
the \-\--\[MAIN\]\-\-- page of your Web UI.

![](../../../Resources/Images/PMDM%20for%20Retail/attribandLOVGovernance.png)
