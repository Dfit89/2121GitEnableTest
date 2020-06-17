---
description: 'Automotive Solution: This section describes an error that
  can occur when importing a TecDoc Reference Data file by listing an
  overview of the error, error message template, error message example,
  where the error messages can be viewed, and how best to address the
  error.'
title: Missing Object Type When Adding Additional Descriptions to
  Vehicle Model Series
---

Missing Object Type When Adding Additional Descriptions to Vehicle Model Series
===============================================================================

Overview

Overview {#overview conditions="Primary.Web"}
--------

This type of error occurs when the import file attempts to add
\'Additional Descriptions\' (populated within STEP as value to the
attribute(s) \'Country Dependent Model Designation\' and / or \'Model
Generation\') to a particular Vehicle Model Series but the data within
the table that imports Vehicle Model Series objects (known in STEP as
\[Vehicle Model Series (CV)\]) is missing.

When a user views the error message, this is apparent because the
message template states: Missing object type for new Object: \<Object
ID\> of type: com.stibo.core.domain.Classification.

When viewing the example error message below, it is clear that the
Object that is missing is the Vehicle Model Series (CV) Object with the
Object ID 'TD\_CVMDL\_38367'.

Error Message Template

Error Message Template {#error-message-template conditions="Primary.Web"}
----------------------

Error in this import \[import file name\] setting completed with errors
- Error: Missing object type for new Object: \[Object ID\] of type:
com.stibo.core.domain.Classification.

Error Message Example

Error Message Example {#error-message-example conditions="Primary.Web"}
---------------------

Error in this import 31\_DescriptionsToVehicleModelSeries-Table140.xml
setting completed with errors - Error: Missing object type for new
object: TD\_CVMDL\_38367 of type: com.stibo.core.domain.Classification.

Viewing the Error Message

Viewing the Error Message {#viewing-the-error-message conditions="Primary.Web"}
-------------------------

![](../../../../../Resources/Images/Importers/Errors/31.png)

Explanation

Explanation {#explanation conditions="Primary.Web"}
-----------

Because this error pertains to the 'Vehicle Model Series (CV)' Object
(featured in Data Table 110) and adding Additional Descriptions to
Vehicle Model Series (featured in Data Table 140), it is important to
understand Data Tables 110 and 140.

Understanding Data Table 110

Data Table 110 lists Vehicle Model Series (CV) Objects featured in Delta
Key **KModNr**.

Understanding Data Table 140

For this explanation the following example data from Data Table 140 is
used. The Delta Keys that pertain to this error type are displayed with
red and green text.

![](../../../../../Resources/Images/Importers/Errors/33.png)

The following important Delta Keys are within this table:

**KModNr:** Five digit number representing the Vehicle Model Series
\[Vehicle Model Series (CV)\].

**LbezNr1:** Nine digit number representing the Description Number of
the sales description (also known in STEP by Attribute \'Country
Dependent Model Designation\' (STEP ID: TD\_ATTR\_LBezNr1)).

**LbezNr2:** Nine digit number representing the Description Number of
the model generation (also known in STEP by Attribute \'Model
Generation\' (STEP ID: TD\_ATTR\_LBezNr2)).

In the example below, KModNr 38364 is displayed in Workbench as the
\'Vehicle Model Series (CV)\' Object Type \'RG Series 01.96-\'
(TD\_CVMDL\_38364). Because KModNr 38367 is not present in Data Table
110 the Vehicle Model Series (CV) with Object ID: TD\_CVMDL\_38367 is
not created in STEP. The screenshot below is solely for representational
purpose of how an object with object type Vehicle Model Series (CV)
displays in the workbench.

![](../../../../../Resources/Images/Importers/Errors/32.png)

In this example, because the \'Vehicle Model Series (CV)\' with ID
'TD\_CVMDL\_38367' is missing from the appropriate STEP classification
hierarchy, and Data Table 140 includes instruction to add values to the
attribute(s) \'Country Dependent Model Designation\' and/or \'Model
Generation,\' STEP is displaying a missing object error.

If information on 'Vehicle Model Series Number' is not present in STEP
(KModNr), but is present in Data Table 140 (KModNr), then STEP will
display a missing information error.

Resolution

Resolution {#resolution conditions="Primary.Web"}
----------

To resolve this, manually create the missing object within the
appropriate STEP classification hierarchy and import the Reference Data
file again.
