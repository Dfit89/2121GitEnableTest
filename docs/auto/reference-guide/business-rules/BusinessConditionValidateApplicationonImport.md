---
description: 'Automotive Solution: Describes the \''Validate application
  on import\'' Business Condition.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Condition: Validate Application on Import
==================================================

PRODOC note: BOND RDCUST-3365 and PRODOC-1759

The \'Validate Application\' operation is found within the STEP
Workbench Business Rule Editor under the Automotive menu and requires
selecting / deselecting of the \'Check configuration validity\'
parameter.

![](../../Resources/Images/BRs/Validate%20Application%20on%20Import/1.png)

The \'Validate Application\' operation is executed via the business
condition \'Validate Application on import.\' Running the Easy Setup of
the import process automatically creates the \'Validate Application on
import\' business condition and adds it to the Import state of the
relevant workflow.

![](../../Resources/Images/Release%20Notes/91MP15.png){.Inch6}

The \'Check configuration validity\' parameter determines whether the
applications with invalid configurations (applications that do not have
both a part type and vehicle / assembly that exists in the STEP
database, or invalid combinations of vehicle configurations that are
provided for the base vehicle, such as an invalid Engine Base or Drive
Type) are imported or not.

Checking the \'Check configuration validity\' parameter means
applications with invalid configurations are not imported. When an
application record is found that does not meet the condition, an error
is written to the execution report of the import process and the record
is not imported. The error contains the application ID from the ACES
file, as well as IDs of the objects that it failed on.

Below is an example of an error that is written to the execution report
when an assembly (Base Vehicle ID) mentioned in the ACES file does not
exist in the STEP database but the ACES file is trying to reference an
application record to the missing assembly.

![](../../Resources/Images/BRs/Validate%20Application%20on%20Import/2.png)

If the \'Check configuration validity\' parameter is not checked,
importing ACES applications that have invalid configurations will pass
the import and create the applications.

Selecting the \'Check configuration validity\' parameter prevents any
applications from being imported that do not have both a part type and
vehicle / assembly that exists in the STEP database. When an application
record is found that does not meet the condition, an error is written to
the execution report of the import process and the record is not
imported.
