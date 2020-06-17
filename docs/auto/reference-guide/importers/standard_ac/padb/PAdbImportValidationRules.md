---
description: 'Automotive Solution: Describes the PAdb import validation
  rules.'
title: '\[%=Heading.AnyLevel%\]'
---

PAdb Import Validation Rules
============================

When importing an AutoCare PAdb (Product Attribute Database) file many
STEP validation rules are performed. The table below describes each of
these validation rules, where the validation check occurs, what happens
when a validation fails, and an example of a failed validation message
(when applicable). However, it does not detail the file type\'s data
rules per the AutoCare Association. This information can be found at
[www.autocare.org](http://www.autocare.org/Default.aspx?gmssopc=1).
PRODOC note: 10/30/17 Link is live intentionally.

For best results, AutoCare imports should be executed in the order
specified within the **AutoCare Import Validation Rules** topic[
here]{.mcFormatColor style="color: Blue;"}.

**Accepted File Extension:** .zip

  Validation Rule                                                                                                                       Occurs             When Validation Fails                                                   Failed Validation Message Example
  ------------------------------------------------------------------------------------------------------------------------------------- ------------------ ----------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Cannot be unzipped or is not in a recognized format.                                                                                  Validation state   BGP ends in an error, triggering the import to enter the Error state.   File is not in a recognized format or could not be unzipped.
  Unit group existence.                                                                                                                 Import state       Unit skipped.                                                           The unit \'DK\' could not be created as the unit group is unknown.
  All tables / subfiles present. (PartAttributes.txt, MetaUoMCodes.txt, Version.txt, PartAttributeAssignment.txt, Metadata.txt)         Validation state   BGP ends in an error, triggering the import to enter the Error state.   The required table \'\[Required Table Name\]\' is missing in the \[Name of zipped file\] ZIP archive or is empty.
  Mandatory values present                                                                                                              Validation state   BGP ends in an error triggering the import to enter the Error state.    Table \'\[Table Name\]\' contains a row that misses value for the required column \'\[Column Name\]\' at line 3.
  Correct number of columns / headers (If last column is optional, then the last column can be missing without affecting validation.)   Validation state   BGP ends in an error triggering the import to enter the Error state.    Table \'\[Table Name\]\' contains a row with wrong number of columns at line 2. or \[Name of subfile\] does not include \[missing Header\].
  Loading of older version                                                                                                              Validation state   Warning is displayed.                                                   Existing version \'2015-09-25\' is newer that provided \'2014-11-28.\'
  Empty line                                                                                                                            Validation state   Warning is displayed.                                                   Table \'VehicleToBedConfig\' contains an empty row at line 3.
  Part Type existence                                                                                                                   Import state       All attribute links to PT skipped.                                      Line 10, Classification 2: No parent specified for new classification with ID \'AC\_PartTerminology\_99999\' Line 10, Classification 2: The classification with ID \'AC\_PartTerminology\_99999\' was skipped.

PRODOC note: Unit group existence and PartType existance Failed
Validation Messages were provided by RDCUST-2384. All others were copied
from other examples and need to be tested / confirm the table and column
names in the example are viable.
