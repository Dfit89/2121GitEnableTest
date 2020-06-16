---
description: 'PLM Solution: Specified ingredients are ingredients added
  by a customer to a recipe specification. It is used to list the
  ingredients that must be included or excluded in the supplier sample
  recipe.'
title: '\[%=Heading.Level1%\]'
---

Specified Ingredients
=====================

Specified ingredients are ingredients added by a customer to a recipe
specification. It is used to list the ingredients that must be included
or excluded in the product recipe provided by the suppler.

-   For any specified ingredient, the \'Allowance' must be filled out
    (is mandatory). \'Ingredient Precision,\' and \'Ingredient
    Quantity\' are needed for more precise validation but they are not
    required. Any other configurable attributes, such as \'Country of
    Origin\' or \'Organic\' (if applicable) are optional to specify.

![](../../../../Resources/Images/Solution%20Enablement/PLM/SpecifiedIngredients.png)

Specified Compound Ingredient
-----------------------------

When a user specifies ingredients for a recipe, they search the
ingredient library. When a compound ingredient is chosen, a copy of it
is made as a specified compound ingredient so that each instance can add
its own unique sub-ingredients to it, and parameters can be attached to
it without permanently attaching that parameter to the library compound
ingredient. Since parameters may be different based on how the compound
ingredient is used, this keeps the library ingredients neutral.

Specified Ingredient
--------------------

When a user specifies ingredients for a recipe, they search the
ingredient library. When an ingredient is chosen, a copy of it is made
as a specified ingredient so that parameters can be attached to it
without permanently attaching that parameter to the library ingredient.
Since parameters may be different based on how the ingredient is used,
this keeps the library ingredients neutral.

![](../../../../Resources/Images/Solution%20Enablement/PLM/SPUIComponent.png)
