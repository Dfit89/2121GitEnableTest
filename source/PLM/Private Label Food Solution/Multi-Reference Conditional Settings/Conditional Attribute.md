---
description: 'PLM Solution: A conditional attribute is controlled by a
  specific value of a dependent attribute. Any attribute can be
  configured as a conditional attribute, but it must be made valid for
  either the \''Requirement\'' or \''Parameter\'' reference.'
title: '\[%=Heading.Level1%\]'
---

Conditional Attribute
=====================

A conditional attribute is controlled by a specific value of a dependent
attribute. Any attribute can be configured as a conditional attribute,
but it must be made valid for either the \'Requirement\' or
\'Parameter\' reference.

For out of the box PLM Private Label Food solution, the following
attributes can configure to be conditional:

  For Requirements          For Parameters
  ------------------------- -----------------------
  Requirement               Requirement
  Requirement Description   Parameter Description
  Meets Requirement?        Meets Requirement?
  Response Detail           Response Detail
  Additional Comments       Method
  Help Text                 Help Text

How to Configure a Conditional Attribute in the Multi-Reference Editor

A conditional attribute in the Multi-Reference Editor can be configured
in the Web UI designer on either the PLM Create Reference Action or PLM
Edit Reference Action using either the PLM Attribute Value or PLM Flex
Value Attribute child components.

**Pre-requisites**:

-   Identify conditional attribute and attribute value
-   Identify the conditional dependent attribute
-   Business Function Conditional Rule -- Optional

Conditional Attribute - PLM Flex Value Attribute

A conditional attribute is immediately shown after meeting the specified
condition. There is no need to save the entered value into the
conditional dependent attribute.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional1.png)

If the conditional attribute is an LOV with IDs, then the conditional
attribute value is the LOV ID not the value.
