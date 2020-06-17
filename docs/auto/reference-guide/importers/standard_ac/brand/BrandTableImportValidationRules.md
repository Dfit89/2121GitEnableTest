---
description: 'Automotive Solution: Describes the Brand Table import
  validation rules.'
title: '\[%=Heading.AnyLevel%\]'
---

Brand Table Import Validation Rules
===================================

When importing an AutoCare Brand Table file, many STEP validation rules
are performed. The table below describes each of these validation rules,
where the validation check occurs, what happens when a validation fails,
and an example of a failed validation message (when applicable).
However, it does not detail the file type\'s data rules per the AutoCare
Association. This information can be found at
[www.autocare.org.](http://www.autocare.org/Default.aspx?gmssopc=1)
PRODOC note: 10/30/17 Link is live intentionally.

For best results, AutoCare imports should be executed in the order
specified within the **AutoCare Import Validation Rules** topic[
here]{.mcFormatColor style="color: Blue;"}.

**Accepted File Extension:** .txt

  Validation Rule                                                                                                              Occurs             When Validation Fails                                                  Failed Validation Message Example
  ---------------------------------------------------------------------------------------------------------------------------- ------------------ ---------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------
  All tables present                                                                                                           Validation state   BGP ends in an error triggering the import to enter the Error state.   The required table \'\[Required Table Name\]\' is missing in the archive or is empty.
  Mandatory values present                                                                                                     Validation state   BGP ends in an error triggering the import to enter the Error state.   Table \'\[Table Name\]\' contains a row that misses value for the required column \'\[Column Name\]\' at line 3.
  Correct number of columns. (If last column is optional, then the last column can be missing without affecting validation.)   Validation state   BGP ends in an error triggering the import to enter the Error state.   Table \'\[Table Name\]\' contains a row with wrong number of columns at line 2.
  Loading of older version                                                                                                     Validation state   Warning is displayed.                                                  Existing version \'2015-09-25\' is newer that provided \'2014-11-28.\'
  Empty line                                                                                                                   Validation state   Warning is displayed.                                                  Table \'\[Table Name\]\' contains an empty row at line 3.

PRODOC note: None of the Failed Validation Messages were provided by
RDCUST-2384 Copied from other examples and need to be tested / confirm
the table and column names in the example are viable.
