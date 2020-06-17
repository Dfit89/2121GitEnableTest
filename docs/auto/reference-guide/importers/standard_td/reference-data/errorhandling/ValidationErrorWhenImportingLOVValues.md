---
description: 'Automotive Solution: Describes an error that can occur
  when importing a TecDoc Reference Data file by listing an overview of
  the error, error message template, error message example, where the
  error messages can be viewed, and how to resolve the error.'
title: '\[%=Heading.AnyLevel%\]'
---

Validation Error When Importing LOV Values
==========================================

PRODOC note: Peer Reviewed by JOPI on MEDU per NIFE: The character
conversion issue has been resolved in RDCUST-3080, so the description
isn\'t valid anymore regarding the &amp;. There will still be an error
if the max length for an LOV is \'60\' and the import file contains \>60
characters (that are not special characters). But the example of &amp;
in this case is no longer valid.

Overview

Overview {#overview conditions="Primary.Web"}
--------

This type of error occurs when an import file attempts to import values
for a particular LOV but the values in the import file do not match the
validation rules set by STEP. For more information about STEP validation
rules, see the **Validation Rules** section of OLH[ here]{.mcFormatColor
style="color: Blue;"}.

When a user views the error message, this can be understood because the
message template states: The value \'Value' isn\'t valid for LOV \'LOV
ID\': Length: 60 does not fit: 'Value'.

Error Message Template

Error Message Template {#error-message-template conditions="Primary.Web"}
----------------------

Error in this import \[import file name\] setting completed with errors
- Error: The value \[imported LOV value\] isn\'t valid for LOV \[LOV
ID\]: Length: \[Maximum Length value\] does not fit: \[imported LOV
value\].

Error Message Example

Error Message Example {#error-message-example conditions="Primary.Web"}
---------------------

Error in this import 04\_LOVDefinitions.xml setting completed with
errors - Error: The value \'With Support Wheel Holder, pointing
rearwards & also crossways\' isn\'t valid for LOV \'TD\_LOV-713\':
Length: 60 does not fit: With Support Wheel Holder, pointing rearwards &
also crossways

Viewing the Error Message

Viewing the Error Message {#viewing-the-error-message conditions="Primary.Web"}
-------------------------

![](../../../../../Resources/Images/Importers/Errors/21.png)

Explanation

Explanation {#explanation conditions="Primary.Web"}
-----------

Because this error pertains to LOV validation in STEP, and LOV Values
are listed within the TecDoc Reference Data file Data Table 030, it is
important to understand Data Table 030.

For this explanation, the following example data from a Reference Data
file Data Table 030 is used. The Delta Key within the Reference Data
file that pertains to this error type (Bez) is displayed with red text.

![](../../../../../Resources/Images/Importers/Errors/22.png)

Understanding Data Table 030

This section describes the important Delta Key within this Data Table.

**Bez:** Maximum 60 character text representing an LOV Value (also known
as \'Descriptions\' in the \'TecAlliance: TecDoc Data Format\' file).

In the example below, LOV 'Overrun Brake Design' (TD\_LOV-713) is
configured to have a \'Maximum Length\' of 60. Because the import file
contains the value 'With Support Wheel Holder, pointing rearwards & also
crossways' which has 62 characters, STEP displays a validation error,
and the LOV Value is not imported into STEP. Therefore, it does not
display within the \'Values\' flipper.

![](../../../../../Resources/Images/Importers/Errors/23.png)

Resolution

Resolution {#resolution conditions="Primary.Web"}
----------

To resolve the error, edit the text within the description to be less
than the defined character limit, or adjust the character limit in STEP.
