---
description: 'PLM Solution: A Quality Manager from CIBUS is reviewing
  the supplier responses they received for the Requirements and
  Parameters after the implementation of the conditional attribute
  functionality for \''Response Detail\'' attribute.'
title: '\[%=Heading.Level1%\]'
---

Use Case Conditional Mandatory Attribute
========================================

A Quality Manager from CIBUS is reviewing the supplier responses they
received for the Requirements and Parameters after the implementation of
the conditional attribute functionality for \'Response Detail\'
attribute. The quality manager from CIBUS noticed that even when the
conditional functionality has been implemented, suppliers tend to still
not provide an answer for the \'Response Detail\' parameter when the
\'Meets Requirement\' attribute value is set to **Yes**.

To ensure that the \'Response Detail\' attribute must be complete by a
supplier in their responses, the \'Response Detail\' attribute needs to
be conditional mandatory based in the value of the \'Meets Requirement\'
attribute.

-   If the \'Meets Requirement\' attribute response value is **No**,
    then the \'Response Detail\' attribute will not be displayed in the
    Answer Requirement dialog, and Save button will be enabled. The
    supplier will continue and Save the response.
-   If the \'Meets Requirement\' attribute response value is **Yes**,
    then the \'Response Detail\' attribute will be displayed in the
    Answer Requirement dialog. The Save button will be disabled. A
    supplier must complete the \'Response Detail\' to continue and Save
    the response.

After the mandatory conditional configuration for Meets Requirement
attribute has been implemented, Laura from supplier A receives an email
notification that a new bid has been requested from the customer, CIBUS.

Laura accesses the Supplier Web UI, opens the Chocolate Cookie Project
Dark Chocolate Chip A12345 Recipe Response, and starts the process of
completing the requested information for recipe ingredients,
requirements, and parameters.

Laura selects the \'Fair Trade\' Requirement and responds **Yes** to
Meets Requirement. Immediately, the \'Response Detail\' attribute is
displayed as mandatory and highlighted. A message displays underneath
the \'Response Detail\' attribute further telling the supplier that the
attribute is required to hold a value before the dialog can be Saved.

![](../../../../Resources/Images/Solution%20Enablement/PLM/COnditional-MRE4.png)

The conditional mandatory \'Response Detail\' displays as a required
field based on the dependent \'Meets Requirement?\' attribute. If the
value is **Yes**, then the Save button is disabled until the \'Response
Detail\' required field is populated.

If the dependent attribute \'Meets Requirement?\' has the value of
**No**, then the conditional attribute \'Response Detail\' displays but
is not required.

Example 1: Conditional Mandatory Attribute, Mandatory

The conditional attribute \'Additional Comments\' will always be shown
as a mandatory attribute indicated by a red asterisk (\*).

In this case, it is configured by entering the dependent attribute ID
into the Conditional Attribute field, PLMAdditionalSupplierComments. The
triggering value of **Y (LOV ID)** for PLMMeetsRequirement is entered
into the Conditional Attribute Value field. Aditionally, the checkbox
for making this mandatory is selected for the conditional attribute
Additional Supplier Comments and Conditional Mandatory for dependent
attribute PLMMeetsRequirement.

Both the Mandatory and conditional mandatory are selected, making the
attribute \'Additional Comments\' always shown as mandatory. The same
result can be achieved by making the attribute \'Additional Comments\'
mandatory and not specify any of the conditional fields.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional11.png)

This case is the same as indicating the \'Additional Comment\' attribute
to be mandatory with no conditional fields defined. Since the
\'Additional Comments\' attribute is mandatory, it will always be
displayed as mandatory, independent of the conditional value. However,
if instead the \'Additional Comment\' attribute was set to mandatory and
the conditional mandatory set to false, then the \'Additional Comment\'
attribute would only display if \'Meets Requirement\' is answered as
**Yes**. It would also display as mandatory.
