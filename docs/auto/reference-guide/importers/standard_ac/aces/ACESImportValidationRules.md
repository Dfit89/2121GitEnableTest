---
description: 'Automotive Solution: Describes the ACES import validation
  rules.'
title: '\[%=Heading.AnyLevel%\]'
---

ACES Import Validation Rules
============================

When importing an AutoCare ACES (Aftermarket Catalog Exchange Standard)
file, many STEP validation rules are performed. The table below
describes each of these validation rules, where the validation check
occurs, what happens when a validation fails, and an example of a failed
validation message (when applicable). However, it does not detail the
file type\'s data rules per the AutoCare Association. This information
can be found at
[www.autocare.org](http://www.autocare.org/Default.aspx?gmssopc=1).
PRODOC note: 10/30/17 Link is live intentionally.

For information on the supported versions, see the **Supported Versions
and Formats** topic within this guide[ here]{.mcFormatColor
style="color: Blue;"}.

For best results, AutoCare imports should be executed in the order
specified within the **AutoCare Import Validation Rules** topic[
here]{.mcFormatColor style="color: Blue;"}.

**Accepted File Extension:** .xml and .ZIP

  Validation Rule                          Occurs                                When Validation Fails                                                                                                             Failed Validation Message Example
  ---------------------------------------- ------------------------------------- --------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ACES 3.2 XSD validation                  Validation state                      Import fails Validation state.                                                                                                    cvc-pattern-valid: Value \'somethingWrongBrand\' is not facet-valid with respect to pattern \'\[B-Z-\[EIOU\]\]\[B-Z-\[EIO\]\]\[B-Z-\[OU\]\]\[A-Z\]\' for type \'brandType.\'
  Base vehicle existence                   Import state via Business Action      Record skipped.                                                                                                                   An application (id=13) for part: VC36004 has no assembly target.
  Engine and transmission base existence   Import state                          Application is imported, but Condition is NOT imported.                                                                           Target \'AC\_EngineBase\_2127123321\' of reference not found.
  File name matches configuration          Conversion state                      BGP ends in an error triggering the import to enter the Error state.                                                              Conversion stopped due to en error: Current import handling configuration for brand DKGX requires Supplier information that failed to be obtained from the filename.
  Import mode Full and action = D          Conversion state                      Record is skipped and a warning will display in the BGP report.                                                                   Application 16 will be skipped as the import mode FULL only processes the applications with A (Add) action.
  Part existence                           Import state via Business Condition   Record skipped.                                                                                                                   AC\_PIESItem\_DKGX\_BADNumber does not exist for application (id=15).
  Part terminology existence               Import state via Business Condition   Record skipped.                                                                                                                   An application (id=14) for part: VC36004 has no parttype.
  Qualifier existence                      Import state                          Record is imported but a standard STEP reference target not found error will display.                                             Target \'AC\_Qualifier\_129461111111111111\' of reference not found.
  Text in number conditions                Conversion state                      BGP ends in an error, triggering the import to enter the Error state, and an exception to display within the conversion report.    

PRODOC note: All Failed Validation Messages except \"Text in number
conditions\" provided by BEJA via RDCUST-2384

The ACES importer does not validate that the VCdb, PCdb, and/or Qdb
versions within STEP are the same versions within the ACES file.
