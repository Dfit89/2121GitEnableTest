---
description: 'PLM Solution: A Quality Manager is responsible for
  preparing requirements and parameters for new products, which display
  in the Answer Requirements dialog that must be responded to by
  suppliers. '
title: '\[%=Heading.Level1%\]'
---

Use Case Conditional Attribute
==============================

A Quality Manager is responsible for preparing requirements and
parameters for new products, which display in the Answer Requirements
dialog that must be responded to by suppliers. The dialog can be
enhanced to improve the completeness of supplier responses based on set
conditions.

For example, to reduce the feedback loops of communication between the
Quality Department and the supplier, and to guarantee that a supplier\'s
responses are complete when submitted to the customers (buyer), the
quality team has decided to implement the following conditional
attributes.

The \'Response Detail\' attribute will be **conditional** based in the
value of the \'Meets Requirement\' attribute.

-   If the \'Meets Requirement,\' response value is **No**, then the
    \'Response Detail\' attribute will not display in the Answer
    Requirement dialog, and Save button will be **enabled**. The
    supplier is able to continue and save the response.

-   If the \'Meets Requirement,\' response value is **Yes**, then the
    \'Response Detail\' attribute will display in the Answer Requirement
    dialog. The supplier can choose to either complete or not complete
    the \'Response Detail\' parameter. Either way, there is no
    limitation set to save the response, and the Save button will be
    **enabled**.

After the mandatory conditional configuration for the \'Meets
Requirement\' attribute has been implemented, Laura, from supplier A,
receives an email notification that a new bid has been requested from
the customer, CIBUS.

Laura accesses the Supplier Web UI, opens the Chocolate Cookie Project
Dark Chocolate Chip A12345 recipe response, and starts the process of
completing the requested information for the recipe ingredients,
requirements, and parameters.

Laura selects the \'Fair Trade\' requirement and for the \'Meets
Requirement\' attribute responds with **Yes**. This affirmative response
then triggers the conditional mandatory \'Response Detail\' attribute to
immediately show having met the set condition.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-Conditional2.png)

Conditional attributes in the Answer Requirement or Answer Parameter
dialogs do not disable the Save action. A user can save the resposed
even when the conditional attribute value is empty.
