---
description: 'PLM Solution: An attribute can be configured as
  conditional mandatory when a dependent attribute has a specific value,
  and the Conditional Mandatory parameter is selected in the PLM Flex
  Value Attribute properties components.'
title: '\[%=Heading.Level1%\]'
---

Conditional Mandatory on a PLM Edit Reference Action
====================================================

An attribute can be configured as conditional mandatory when a dependent
attribute has a specific value, and the Conditional Mandatory parameter
is selected in the PLM Flex Value Attribute properties components.

Any attribute can be configured to be used as a conditional mandatory
attribute, but it must be a valid attribute on the Requirement or
Parameter reference.

In the PLM Private Label Food out of the box solution, the following
attributes can be configured to be **conditional mandatory**:

  For Requirements          For Parameters
  ------------------------- -----------------------
  Requirement               Requirement
  Requirement Description   Parameter Description
  Meets Requirement?        Meets Requirement?
  Response Detail           Response Detail
  Additional Comments       Method
  Help Text                 Help Text

Conditional attribute and conditional dependent attribute must be a
valid attribute in the Requirement or Parameter reference.

How to configure a Conditional Attribute - PLM Flex Attribute

A conditional attribute can be configured in the Web UI designer on
either the PLM Create Reference Action or PLM Edit Reference Action
using either the PLM Attribute Value or PLM Flex Value Attribute child
components.

Pre-requisites:

-   Identify conditional attribute and attribute value
-   Identify the conditional dependent attribute
-   Business Function Conditional Rule -- Optional

Conditional attribute and conditional dependent attribute must be a
valid attribute for the Requirement or Parameter reference.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional3.png)
