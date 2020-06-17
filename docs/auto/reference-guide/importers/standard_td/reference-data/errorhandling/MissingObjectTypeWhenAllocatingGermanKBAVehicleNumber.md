---
description: 'Automotive Solution: Describes an error that can occur
  when importing a TecDoc Reference Data file by listing an overview of
  the error, error message template, error message example, where the
  error messages can be viewed, and how to resolve the error.'
title: Missing Object Type When Allocating German KBA Vehicle Number
---

Missing Object Type When Allocating German KBA Vehicle Number
=============================================================

Written by BOND. Peer Review requested of JOPI on 11/21

Overview

Overview {#overview conditions="Primary.Web"}
--------

This type of error occurs when the import file tries to allocate a
German KBA Number to a particular Passenger Car (PC) but the data within
the table that imports the Passenger Car object (known in STEP as
\[Vehicle (PC)\]) is missing.

When a user views the error message, this is apparent because the
message template states: Missing object type for new object: \<Object
ID\> of type: com.stibo.core.domain.Classification

When viewing the example error message below, it is clear that the
Object that is missing is the Passenger car object with the Object ID
'TD\_PC\_TYPE\_128235'.

Error Message Template

Error Message Template {#error-message-template conditions="Primary.Web"}
----------------------

Error in this import \[import file name\] setting completed with errors
- Error: Missing object type for new object: \[\<Object ID\>\] of type:
com.stibo.core.domain.Classification

Error Message Example

Error Message Example {#error-message-example conditions="Primary.Web"}
---------------------

Error in this import 22\_KbaVehicleNumbers.xml setting completed with
errors - Error: Missing object type for new object: TD\_PC\_TYPE\_128235
of type: com.stibo.core.domain.Classification

Viewing the Error Message

Viewing the Error Message {#viewing-the-error-message conditions="Primary.Web"}
-------------------------

![](../../../../../Resources/Images/Importers/Errors/51.png)

Explanation

Explanation {#explanation conditions="Primary.Web"}
-----------

Because this error pertains to the Vehicle Type (PC) Object Type and
allocation of KBA Numbers, the Passenger Car Types are listed within the
TecDoc Reference Data file Data Table 120, and the allocation of KBA
Numbers are listed within the data table 121, it is important to first
understand Data Table 121.

For this explanation, the following example data from Data Table 121 is
used. The Delta Keys that pertain to this error type are displayed with
green or red text.

![](../../../../../Resources/Images/Importers/Errors/54.png)

Understanding Data Table 120

Data Table 120 lists Passenger Car Types that are featured in Delta Key
**KTypNr**.

Understanding Data Table 121

The following important Delta Keys are within Data Table 121:

**KTypNr:** Nine digit number representing the PC Vehicle Type number.
Shown above in red text.

In the example below, KTypNr 000013972 displays in Workbench as the
\'Vehicle Type (PC)\' Object Type, \'LAND ROVER Open Off-Road Vehicle -
DEFENDER Cabrio (L316) - 2.2\' (TD\_PC\_Type\_13972). Because KTypNr
0000128235 is not present in Data Table 121 the Vehicle Type (PC) with
Object ID: TD\_PC\_Type\_13972 is not created in STEP. The screenshot
below is solely for the representational purpose of how an object with
object type Vehicle Type (PC) displays in the workbench.

![](../../../../../Resources/Images/Importers/Errors/52.png)

**KBANr:** Seven digit number representing the German KBA Number. Shown
above in green text.

In the example below, the first image within the screenshot displays an
example of what a Passenger Car type Object would look like if it were
present in Workbench. For this example, the 'LAND ROVER open off-road
vehicle' object is referenced to the German KBA number '2143ABZ.' The
second image in the screenshot displays the referenced German KBA Number
'2143ABZ' within Workbench.

![](../../../../../Resources/Images/Importers/Errors/53.png)

In this example, because the Passenger Car object with ID:
'TD\_PC\_TYPE\_128235' (Data imported from Data Table 120) is missing
from the appropriate STEP classification hierarchy, and the Data Table
121 has instruction to allocate the KBA Number to that object, STEP is
displaying a missing object error.

If information on 'Passenger Car Vehicle primary type Number' is not
present in Data Table 120 (KTypNr), but is present in Data Table
121(KTypNr), then STEP will throw a missing information error. In short,
object 'TD\_PC\_TYPE\_128235' is missing from Data Table 120 but the
information associating it is present in file 121.

Resolution

Resolution {#resolution conditions="Primary.Web"}
----------

To resolve this, create the missing object within the appropriate STEP
classification hierarchy and import the Reference Data file again.
