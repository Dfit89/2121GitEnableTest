---
description: 'PLM Solution: Any attribute can be configured to be used
  as conditional and/or conditional mandatory, but it must be a valid
  attribute on the Requirement or Parameter reference.'
title: '\[%=Heading.Level1%\]'
---

Conditional and Conditional Mandatory
=====================================

Any attribute can be configured to be used as conditional and/or
conditional mandatory, but it must be a valid attribute on the
Requirement or Parameter reference.

In the PLM Private Label Food out of the box solution, the following
attributes can be configured to be **conditional** or **conditional
mandatory**.

  For Requirements          For Parameters
  ------------------------- -----------------------
  Requirement               Requirement
  Requirement Description   Parameter Description
  Meets Requirement?        Meets Requirement?
  Response Detail           Response Detail
  Additional Comments       Method
  Help Text                 Help Text

A Web UI admin will be able to configure conditional attributes and
conditional mandatory attributes on the PLM Edit Reference Action.

![](../../../../Resources/Images/Solution%20Enablement/PLM/Conditional-MRE5.png)

Example 1: Conditional Attribute

The conditional attribute \'Additional Supplier Comments\' is shown to
the user when the dependent attribute \'Meets Requirement\' has a value
equal to **Yes**.

This is configured by entering the dependent attribute ID into the
Conditional Attribute field, PLMMeetsRequirement, and the triggering
value, Y (LOV ID), for PLMMeetsRequirement into the Conditional
Attribute Value field.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional7.png)

When supplier open the dialog to respond \'Meets Requirement?\' the
\'Additional Comments\' attribute is not displaying. It will only
display when the supplier responds with **Yes** to the \'Meets
Requirement?\' field. The Save action will be enabled.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional6.png)

Example 2: Conditional Mandatory Attribute

The conditional attribute \'Additional Supplier Comments\' displays when
the dependent attribute \'Meets Requirement\' has a value equal to
**Yes**.

This is configured by entering the dependent attribute ID into the
Conditional Attribute field, PLMMeetsRequirement, and the triggering
value, **Y (LOV ID)**, for PLMMeetsRequirement into the Conditional
Attribute Value field. Select the Mandatory Parameter for Conditional
attribute \'Additional Supplier Comments.\'

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional9.png)

When a supplier opens the dialog to respond to the \'Meets
Requirement?\' attribute, the \'Additional Comments\' is not displaying.
It will display when the supplier respond with **Yes** to the \'Meets
Requirement?\' field. The \'Additional Comments\' attribute becomes a
conditional mandatory field, and the Save action will be disabled until
a value is entered into the **Additional Comments** field.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional10.png)
