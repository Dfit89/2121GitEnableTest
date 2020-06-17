---
description: 'Automotive Solution: This section describes an error that
  can occur when importing a TecDoc Reference Data file by listing an
  overview of the error, error message template, error message example,
  where the error messages can be viewed, and how best to address the
  error.'
title: '\[%=Heading.AnyLevel%\]'
---

Missing Object Type When Allocating Engine Number
=================================================

Overview

Overview {#overview conditions="Primary.Web"}
--------

This type of error occurs when the import file attempts to allocate an
Engine Number to a particular TecDoc Commercial Vehicle Type
(TD\_CV\_TYPE), but the data within the table that imports the
Commercial Vehicle object, known in STEP as \[Vehicle Type (CV)\], is
missing.

When a user views the error message, this can be understood because the
message template states: Missing object type for new object: \<Object
ID\> of type: com.stibo.core.domain.Classification.

When viewing the example error message below, it is clear that the
Object that is missing is the Commercial Vehicle object with the Object
ID 'TD\_CV\_TYPE\_23420.'

Error Message Template

Error Message Template {#error-message-template conditions="Primary.Web"}
----------------------

Error in this import 25\_CVTypesAndEngineAllocation.xml setting
completed with errors - Error: Missing object type for new object:
\<Object ID\> of type: com.stibo.core.domain.Classification

Error Message Example

Error Message Example {#error-message-example conditions="Primary.Web"}
---------------------

Error in this import 25\_CVTypesAndEngineAllocation.xml setting
completed with errors - Error: Missing object type for new object:
TD\_CV\_TYPE\_23420 of type: com.stibo.core.domain.Classification

Viewing the Error Message

Viewing the Error Message {#viewing-the-error-message conditions="Primary.Web"}
-------------------------

![](../../../../../Resources/Images/Importers/Errors/11.png)

Explanation

Explanation {#explanation conditions="Primary.Web"}
-----------

Because this error is about a Commercial Vehicle Type object and
allocation of Engine Numbers, and the Commercial Vehicle Types are
handled within the TecDoc Reference Data file data table 532, and the
allocation of Engine Numbers are handled within data table 537, it is
important to first understand data table 537.

For this explanation the following example data from Data Table 537 is
used. The Delta Keys that pertain to this error type are displayed with
red text.

![](../../../../../Resources/Images/Importers/Errors/12.png)

Understanding Data Table 537

The following important Delta Keys are within this table:

**NTypNr:** Nine digit number representing a Commercial Vehicle Type.

In the example below, NTypNr 000023420 is displayed in Workbench as the
\'Vehicle Type (CV)\' Object Type, \'HICOM Closed - MTB - MTB 145
1994-01-01-2004-12-31, kW, HP, cmTech 2771\' (TD\_CV\_Type\_23420).

![](../../../../../Resources/Images/Importers/Errors/13.png)

**MotNr:** Five digit number representing an Engine Number.

In the example below, MotNr 01670 is displayed in Workbench as the
\'Engine Code\' Object Type, \'4JB1\' (TD\_ENGINE\_CODE\_1670).

![](../../../../../Resources/Images/Importers/Errors/14.png)

In this example, because the Commercial Vehicle object with ID:
'TD\_CV\_TYPE\_23420' is missing from the appropriate STEP
classification hierarchy, and file 537 includes instruction to link the
Engine Number to that object using the TD\_Vehicle(CV)ToEngine link
type, STEP displays a missing object error.

In short, object 'TD\_CV\_TYPE\_23420' is missing from file 532 but the
information associating it is present in file 537.

To resolve this, create the missing object and either import the
Reference Data import file again, or manually link the object(s) to the
engine code.
