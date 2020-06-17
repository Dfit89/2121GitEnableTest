---
description: 'Automotive Solution: This section describes an error that
  can occur when importing a TecDoc Reference Data file by listing an
  overview of the error, error message template, error message example,
  where the error messages can be viewed, and how best to address the
  error.'
title: Missing Country Code When Importing Vehicle Country
  Specifications
---

Missing Country Code When Importing Vehicle Country Specifications
==================================================================

Overview

Overview {#overview conditions="Primary.Web"}
--------

This type of error occurs when the import file tries to allocate Vehicle
Country Specifications to a particular Vehicle Type (PC or CV) through
the Reference Type 'Vehicle Country Deviation', but the target object
'Country Code' (known in STEP as \[Country\]) is missing.

When a user views the error message, this is apparent because the
message template states: Target \'Object ID\' of reference not found.

When viewing the example error message below, it is clear that the
object that is missing is the Country Code object with the Object ID
\'TD\_C\_IBE.'

Error Message Template

Error Message Template {#error-message-template conditions="Primary.Web"}
----------------------

Error in this import 39\_VehicleCountrySpecifications-table124.xml
setting completed with errors - Error: Target \'Object ID\' of reference
not found.

Error Message Example

Error Message Example {#error-message-example conditions="Primary.Web"}
---------------------

Error in this import 39\_VehicleCountrySpecifications-table124.xml
setting completed with errors - Error: Target \'TD\_C\_IBE\' of
reference not found.

Viewing the Error Message

Viewing the Error Message {#viewing-the-error-message conditions="Primary.Web"}
-------------------------

![](../../../../../Resources/Images/Importers/Errors/41.png)

Explanation

Explanation {#explanation conditions="Primary.Web"}
-----------

Because this error pertains to the Vehicle Type object, allocation of
Vehicle Country Specifications and Country Code and the Country Codes
are listed within the TecDoc Reference Data file Data Table 010, and the
allocation of Vehicle Country Specifications is listed within the Data
Table 124, it is important to understand Data Table 124.

For this explanation the following example data from Data Table 124 is
used. The Delta Keys that pertain to this error type are displayed with
red and green text.

![](../../../../../Resources/Images/Importers/Errors/44.png)

Understanding Data Table 010

Data Table 010 lists Country Codes featured in Delta Key **LKZ**.

Understanding Data Table 124

The following important Delta Keys are within this table:

**KTypNr:** Nine digit number representing the Vehicle Types.

In the example below, KTypNr 000001015 is displayed in Workbench as the
\'Vehicle Type (PC)\' Object Type, \'FORD Bus - TRANSIT Bus (V\_ \_) -
2.5 D\' (TD\_PC\_TYPE\_1015).

![](../../../../../Resources/Images/Importers/Errors/42.png)

**LKZ:** Maximum three letter alphabet representing Country Code
extracted from Data Table 010.

In the example below, the first image of the screenshot displays the
Vehicle type (PC) Object 'FORD Bus -- TRANSIT Bus (V\_\_) 2.5D'
referenced through the reference type 'Vehicle country deviation' to the
target Country 'France (F)', and the second image shows the Country
object 'France(F)' displayed within Workbench.

![](../../../../../Resources/Images/Importers/Errors/43.png)

In this example, because the Country object with ID: \'TD\_C\_IBE\'
(Data imported from Data Table 010) is missing from the appropriate STEP
classification hierarchy, and the file 124 includes instruction to
allocate the Vehicle Country Specification (Country Code) to that
object, STEP is displaying a missing object error.

In short, object \'TD\_C\_IBE' is missing from file 010, but the
information associating it is present in file 124.

If information on 'Country Code' is not present in Data Table 010 (LKZ)
or not loaded in STEP for some other reason, and the same is present in
the Data Table 124 (LKZ), then STEP will throw a missing information
error.

Resolution

Resolution {#resolution conditions="Primary.Web"}
----------

To resolve this, create the missing object and either import the
Reference Data import file again, or manually create the \'Vehicle Type
(PC or CV)\' object within the appropriate STEP classification
hierarchy.
