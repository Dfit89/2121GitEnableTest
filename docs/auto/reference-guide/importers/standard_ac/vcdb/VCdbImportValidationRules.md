---
description: 'Automotive Solution: Describes the VCdb import validation
  rules.'
title: '\[%=Heading.AnyLevel%\]'
---

VCdb Import Validation Rules
============================

When importing an AutoCare VCdb (Vehicle Configuration Database) file
many STEP validation rules are performed. The table below describes each
of these validation rules, where the validation check occurs, what
happens when a validation fails, and an example of a failed validation
message (when applicable). However, it does not detail the file type\'s
data rules per the AutoCare Association. This information can be found
at [www.autocare.org](http://www.autocare.org/Default.aspx?gmssopc=1).
PRODOC note: 10/30/17 Link is live intentionally.

For best results, AutoCare imports should be executed in the order
specified within the **AutoCare Import Validation Rules** topic[
here]{.mcFormatColor style="color: Blue;"}.

**Accepted File Extension:** .zip

  Validation Rule                                                                                                             Occurs             When Validation Fails                                                  Failed Validation Message Example
  --------------------------------------------------------------------------------------------------------------------------- ------------------ ---------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  All tables present                                                                                                          Validation state   BGP ends in an error triggering the import to enter the Error state.   The required table \'BaseVehicle\' is missing in the ZIP archive or is empty.
  Mandatory values present                                                                                                    Validation state   BGP ends in an error triggering the import to enter the Error state.   Table \'BaseVehicle\' contains a row that misses value for the required column \'YearID\' at line 3.
  Correct number of columns (If last column is optional, then the last column can be missing without affecting validation.)   Validation state   BGP ends in an error triggering the import to enter the Error state.   Table \'BaseVehicle\' contains a row with wrong number of columns at line 2.
  References between tables                                                                                                   Validation state   BGP ends in an error triggering the import to enter the Error state.   Table \'Vehicle\' contains a row where the \'RegionID\' column value \'1000\' does not exist in referenced \'Region\' file at line 13.
  Correct type of values: date / numbers / max length                                                                         Validation state   BGP ends in an error triggering the import to enter the Error state.   Table \'Vehicle\' contains a row where the \'PublicationStageDate\' column value \'33-10-2013 14:38:00\' is not a proper instance of type \'Date with time\' at line 35.
  Loading of older version                                                                                                    Validation state   Warning is displayed.                                                  Existing version \'2015-09-25\' is newer that provided \'2014-11-28.\'
  Empty line                                                                                                                  Validation state   Warning is displayed.                                                  Table \'VehicleToBedConfig\' contains an empty row at line 3.

PRODOC note: All Failed Validation Messages provided by BEJA via
RDCUST-2384
