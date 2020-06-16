---
description: 'PLM Solution: For more complex scenarios, a business
  function can control whether or not attributes are conditional,
  conditional mandatory, mandatory, or read only. An admin user will be
  able to specify a business function that will provide the conditional
  rules.'
title: '\[%=Heading.Level1%\]'
---

Conditional Rules - Business Functions
======================================

For more complex scenarios, a business function can control whether or
not attributes are conditional, conditional mandatory, mandatory, or
read only. An admin user will be able to specify a business function
that will provide the conditional rules.

The Conditional Rules-Business Function will have two input parameters:
an input parameters of the type Node for the source object and an input
parameter of the type Node for the target object. It will have a return
type of String.

The business function will be called every time a reference is being
edited in the Multi-Reference Editor dialog, including going back and
forth to edit multiple references.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional11.1.png)

If a Conditional Rules-Business Function is defined, any values in the
fields for any of the PLM Attribute Value components are ignored. This
includes properties for Mandatory and Read Only.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional12.png)

 
