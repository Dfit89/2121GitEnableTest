---
description: 'Automotive Solution: Describes the PIES import validation
  rules.'
title: '\[%=Heading.AnyLevel%\]'
---

PIES Import Validation Rules
============================

When importing an AutoCare PIES (Product Information Exchange Standard)
file many STEP validation rules are performed. The table below describes
each of these validation rules, where the validation check occurs, what
happens when a validation fails, and an example of a failed validation
message (when applicable). However, it does not detail the file type\'s
data rules per the AutoCare Association. This information can be found
at [www.autocare.org](http://www.autocare.org/Default.aspx?gmssopc=1).
PRODOC note: 10/30/17 Link is live intentionally.

For best results, AutoCare imports should be executed in the order
specified within the **AutoCare Import Validation Rules** topic[
here]{.mcFormatColor style="color: Blue;"}.

**Accepted File Extension:** .xml

  Validation Rule              Occurs             When Validation Fails                     Failed Validation Message Example
  ---------------------------- ------------------ ----------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  PIES 6.5 XSD validation      Validation state   Validation fails                          Error while validating file against XSD: cvc-complex-type.2.4.a: Invalid content was found starting with element \'Headeasdfr.\' One of \'{\"http://www.aftermarket.org\":TestFile, \"http://www.aftermarket.org\":Header}\' is expected.
  Part terminology existence   Conversion state   Item will be skipped                      Part terminology with id 99999 does not exist in AutoCare reference data. All items under it will be skipped.
  Duplicated item              Conversion state   Warning is displayed.                     Item with id MyPart already imported.
  Duplicated package           Conversion state   Warning is displayed.                     Package with PackageLevelGTIN 1234567 was already imported for item MyPart.
  Missing GTIN on package      Conversion state   Package skipped                           Package with UOM PK does not have a PackageLevelGTIN specified for item MyPart. Package import will be skipped.
  PriceSheet existence         Import state       Standard step missing attribute errors.   Attribute \'AC\_PIES\_PRCS\_BADPricesheet\_CurrencyCode\' not found.

PRODOC note: All Failed Validation Messages provided by BEJA via
RDCUST-2384

Brand existence is not verified within STEP.
