---
description: 'PLM Solution: Each object type in the Product Lifecycle
  Management 9.1 hierarchy is listed below, along with the purpose of
  the object type.'
title: '\[%=Heading.Level1%\]'
---

Primary Product Classification
==============================

Each object type in the Product Lifecycle Management 10.0 hierarchy is
listed below, along with the purpose of the object type. PLM Private
Label Food solution specifically does not use a product categorization
to avoid coming into conflict with existing PMDM product categorization.

### Primary Product Classification

+----------------------+----------------------+----------------------+
| Object Type Name     | Object Type ID       | Purpose              |
+======================+======================+======================+
| Product Lifecycle    | ProductLifecycleM    | A root node of the   |
| Management           | anagementProductRoot | hierarchy that       |
|                      |                      | contains all PLM     |
|                      |                      | products.            |
+----------------------+----------------------+----------------------+
| Competitive Products | PLMCom               | A root level for     |
|                      | petitiveProductsRoot | organizing           |
|                      |                      | competitive product  |
|                      |                      | foods.               |
+----------------------+----------------------+----------------------+
| Competitive Product  | PLMCo                | Represent similar    |
| Food                 | mpetitiveProductFood | products to the      |
|                      |                      | product that a       |
|                      |                      | customer is          |
|                      |                      | evaluating to        |
|                      |                      | produce.             |
+----------------------+----------------------+----------------------+
| Design               | PLMDesi              | Root level for       |
| Specifications       | gnSpecificationsRoot | organizing           |
|                      |                      | specifications.      |
+----------------------+----------------------+----------------------+
| Design Specification | PLMDesig             | A broad              |
| Level 1              | nSpecificationLevel1 | categorization for   |
|                      |                      | design               |
|                      |                      | specifications so    |
|                      |                      | that attribution can |
|                      |                      | be controlled by the |
|                      |                      | type of product      |
|                      |                      | being produced.      |
+----------------------+----------------------+----------------------+
| Design Specification | PL                   | Represents a         |
|                      | MDesignSpecification | high-level place to  |
|                      |                      | gather input for new |
|                      |                      | products. Design     |
|                      |                      | Specification could  |
|                      |                      | represent multiple   |
|                      |                      | products. For food,  |
|                      |                      | it could represent   |
|                      |                      | multiple package     |
|                      |                      | size + flavor +      |
|                      |                      | label languages. For |
|                      |                      | detailed             |
|                      |                      | specifications,      |
|                      |                      | variants are created |
|                      |                      | for each option and  |
|                      |                      | specified there.     |
+----------------------+----------------------+----------------------+
| Design Specification | PLMDesignSpecifica   | Represents a flavor  |
| Composite Variant    | tionCompositeVariant | variation that       |
|                      |                      | includes more than   |
|                      |                      | one recipe, such as  |
|                      |                      | Macaroni & Cheese    |
+----------------------+----------------------+----------------------+
| Design Specification | PLMDesignSpeci       | They represent the   |
| Label Variant        | ficationLabelVariant | eventual item (GTIN, |
|                      |                      | EAN, UPC) and        |
|                      |                      | represents exactly   |
|                      |                      | one unique           |
|                      |                      | combination of       |
|                      |                      | flavor variation and |
|                      |                      | packaging variation. |
|                      |                      | They define which    |
|                      |                      | languages appear on  |
|                      |                      | the label.           |
|                      |                      |                      |
|                      |                      | While they do        |
|                      |                      | display some things  |
|                      |                      | from the variants,   |
|                      |                      | such as the recipe   |
|                      |                      | nutrition info, and  |
|                      |                      | the packaging        |
|                      |                      | variants net         |
|                      |                      | content, labels do   |
|                      |                      | not own that info.   |
+----------------------+----------------------+----------------------+
| Design Specification | PLMDesignSpecifica   | This specifies       |
| Packaging Variant    | tionPackagingVariant | packaging options    |
|                      |                      | and requirements.    |
|                      |                      | Packaging may have   |
|                      |                      | many elements such   |
|                      |                      | as: consumer         |
|                      |                      | packaging, tray      |
|                      |                      | inside the consumer  |
|                      |                      | packaging, shelf     |
|                      |                      | tray, etc\...        |
+----------------------+----------------------+----------------------+
| Design Specification | PLMDesign            | Represents a flavor  |
| Variant              | SpecificationVariant | variation for one or |
|                      |                      | more new products.   |
|                      |                      | Details about the    |
|                      |                      | recipe are collected |
|                      |                      | on this object.      |
+----------------------+----------------------+----------------------+
| Label Variant Sample | P                    | An object that is    |
|                      | LMLabelVariantSample | created for each     |
|                      |                      | supplier who should  |
|                      |                      | respond to package   |
|                      |                      | label                |
|                      |                      | specifications.      |
+----------------------+----------------------+----------------------+
| Packaging Variant    | PLMPa                | An object that is    |
| Sample               | ckagingVariantSample | created for each     |
|                      |                      | supplier which       |
|                      |                      | responds to a        |
|                      |                      | package label        |
|                      |                      | specifications.      |
+----------------------+----------------------+----------------------+
| Sample               | PLMSample            | The sample object    |
|                      |                      | represents the       |
|                      |                      | specified recipe in  |
|                      |                      | the private label    |
|                      |                      | food solution.       |
+----------------------+----------------------+----------------------+
| Composite Sample     | [PLMCo               | [Composite Sample    |
|                      | mpositeSample]{style | represents the       |
|                      | ="font-size: 11pt;"} | supplier response    |
|                      |                      | for a flavor         |
|                      |                      | variation that       |
|                      |                      | includes more than   |
|                      |                      | one                  |
|                      |                      | recipe]{style        |
|                      |                      | ="font-size: 11pt;"} |
+----------------------+----------------------+----------------------+
| Materials Root       | PLMMaterialsRoot     | A root level for     |
|                      |                      | organizing           |
|                      |                      | materials.           |
+----------------------+----------------------+----------------------+
| Additives Root       | PLMAdditivesRoot     | A root level for     |
|                      |                      | organizing           |
|                      |                      | additives.           |
+----------------------+----------------------+----------------------+
| Additives            | PLMAdditives         | A root level for     |
|                      |                      | organizing the       |
|                      |                      | additive library.    |
+----------------------+----------------------+----------------------+
| Additive             | PLMAdditive          | Represents an        |
|                      |                      | additive in the      |
|                      |                      | library. An additive |
|                      |                      | can be a natural or  |
|                      |                      | synthetic substance  |
|                      |                      | that is added to     |
|                      |                      | commercially         |
|                      |                      | prepared foods for a |
|                      |                      | specific purpose,    |
|                      |                      | such as a            |
|                      |                      | preservative,        |
|                      |                      | thickener, color     |
|                      |                      | retention agent,     |
|                      |                      | etc\...              |
+----------------------+----------------------+----------------------+
| Specified Additives  | P                    | Parent for storing   |
|                      | LMSpecifiedAdditives | specified additives. |
|                      |                      | In Tree, a parent    |
|                      |                      | level of the same ID |
|                      |                      | must exist.          |
|                      |                      |                      |
|                      |                      | Additive             |
|                      |                      | specifications are   |
|                      |                      | stored on the        |
|                      |                      | reference between a  |
|                      |                      | flavor variant and   |
|                      |                      | the additive.        |
|                      |                      | Because the additive |
|                      |                      | could be used        |
|                      |                      | multiple times in    |
|                      |                      | the same             |
|                      |                      | specification, a     |
|                      |                      | copy is created each |
|                      |                      | time it is           |
|                      |                      | specified. A version |
|                      |                      | for the suppliers\'  |
|                      |                      | responses is needed, |
|                      |                      | so a Supplier        |
|                      |                      | Response Additive is |
|                      |                      | created.             |
+----------------------+----------------------+----------------------+
| Specified Additive   | PLMSpecifiedAdditive | Used by the          |
|                      |                      | developed components |
|                      |                      | for specifying       |
|                      |                      | additives. A user    |
|                      |                      | searches an additive |
|                      |                      | library and chooses  |
|                      |                      | a class plus an      |
|                      |                      | additive. A copy of  |
|                      |                      | the additive is      |
|                      |                      | saved as a specified |
|                      |                      | additive.            |
+----------------------+----------------------+----------------------+
| Supplier Response    | PLMSuppl             | A root level for     |
| Additives            | ierResponseAdditives | organizing Suppliers |
|                      |                      | Response additives.  |
+----------------------+----------------------+----------------------+
| Supplier Response    | PLMSupp              | Represent an         |
| Additive             | lierResponseAdditive | additive used in a   |
|                      |                      | supplier's recipe.   |
+----------------------+----------------------+----------------------+
| Ingredients Root     | PLMIngredientsRoot   | A root level for     |
|                      |                      | organizing           |
|                      |                      | ingredients.         |
+----------------------+----------------------+----------------------+
| Ingredients          | PLMIngredients       | A level for          |
|                      |                      | organizing           |
|                      |                      | ingredients in the   |
|                      |                      | ingredient library.  |
+----------------------+----------------------+----------------------+
| Compound Ingredient  | P                    | This represents      |
|                      | LMCompoundIngredient | ingredients in the   |
|                      |                      | library that are     |
|                      |                      | made up of other     |
|                      |                      | ingredients, e.g.,   |
|                      |                      | enriched flour may   |
|                      |                      | be made from wheat   |
|                      |                      | flour, iron, and     |
|                      |                      | niacin, which are    |
|                      |                      | sub-ingredients.     |
+----------------------+----------------------+----------------------+
| Ingredient           | PLMIngredient        | Represents an        |
|                      |                      | ingredient in the    |
|                      |                      | ingredient library.  |
+----------------------+----------------------+----------------------+
| Specified            | PLM                  | A level for          |
| Ingredients          | SpecifiedIngredients | organizing           |
|                      |                      | ingredients added by |
|                      |                      | suppliers.           |
+----------------------+----------------------+----------------------+
| Specified Compound   | PLMSpecifi           | When a user          |
| Ingredient           | edCompoundIngredient | specifies            |
|                      |                      | ingredients for a    |
|                      |                      | recipe, they search  |
|                      |                      | the ingredient       |
|                      |                      | library. When a      |
|                      |                      | compound ingredient  |
|                      |                      | is chosen, a copy of |
|                      |                      | it is made as a      |
|                      |                      | specified compound   |
|                      |                      | ingredient so that   |
|                      |                      | parameters can be    |
|                      |                      | attached to it       |
|                      |                      | without permanently  |
|                      |                      | attaching that       |
|                      |                      | parameter to the     |
|                      |                      | library compound     |
|                      |                      | ingredient. Since    |
|                      |                      | parameters may be    |
|                      |                      | different based on   |
|                      |                      | how the compound     |
|                      |                      | ingredient is used,  |
|                      |                      | this keeps the       |
|                      |                      | library ingredients  |
|                      |                      | neutral.             |
+----------------------+----------------------+----------------------+
| Specified Ingredient | PL                   | When a user          |
|                      | MSpecifiedIngredient | specifies            |
|                      |                      | ingredients for a    |
|                      |                      | recipe, they search  |
|                      |                      | the ingredient       |
|                      |                      | library. When an     |
|                      |                      | ingredient is        |
|                      |                      | chosen, a copy of it |
|                      |                      | is made as a         |
|                      |                      | specified ingredient |
|                      |                      | so that parameters   |
|                      |                      | can be attached to   |
|                      |                      | it without           |
|                      |                      | permanently          |
|                      |                      | attaching that       |
|                      |                      | parameter to the     |
|                      |                      | library ingredient.  |
|                      |                      | Since parameters may |
|                      |                      | be different based   |
|                      |                      | on how the           |
|                      |                      | ingredient is used,  |
|                      |                      | this keeps the       |
|                      |                      | library ingredients  |
|                      |                      | neutral.             |
+----------------------+----------------------+----------------------+
| Supplier Response    | PLMSupplierRe        | A root level for     |
| Ingredients          | sponseIngredientRoot | organizing supplier  |
|                      |                      | response             |
|                      |                      | ingredients.         |
+----------------------+----------------------+----------------------+
| Supplier Response    | PLMSupplierRespon    | When a supplier adds |
| Compound Ingredient  | seCompoundIngredient | ingredients to a     |
|                      |                      | recipe, they search  |
|                      |                      | the ingredient       |
|                      |                      | library. When a      |
|                      |                      | compound ingredient  |
|                      |                      | is chosen, a copy of |
|                      |                      | it is made as a      |
|                      |                      | supplier response    |
|                      |                      | compound ingredient  |
|                      |                      | so that parameters   |
|                      |                      | can be attached to   |
|                      |                      | it without           |
|                      |                      | permanently          |
|                      |                      | attaching that       |
|                      |                      | parameter to the     |
|                      |                      | library compound     |
|                      |                      | ingredient. Since    |
|                      |                      | parameters may be    |
|                      |                      | different based on   |
|                      |                      | how the compound     |
|                      |                      | ingredient is used,  |
|                      |                      | this keeps the       |
|                      |                      | library ingredients  |
|                      |                      | neutral.             |
+----------------------+----------------------+----------------------+
| Supplier Response    | PLMSuppli            | When a supplier adds |
| Ingredient           | erResponseIngredient | ingredients to a     |
|                      |                      | recipe, they search  |
|                      |                      | the ingredient       |
|                      |                      | library. When an     |
|                      |                      | ingredient is        |
|                      |                      | chosen, a copy of it |
|                      |                      | is made as a         |
|                      |                      | supplier response    |
|                      |                      | ingredient so that   |
|                      |                      | parameters can be    |
|                      |                      | attached to it       |
|                      |                      | without permanently  |
|                      |                      | attaching that       |
|                      |                      | parameter to the     |
|                      |                      | library\'s           |
|                      |                      | ingredient. Since    |
|                      |                      | parameters may be    |
|                      |                      | different based on   |
|                      |                      | how the compound     |
|                      |                      | ingredient is used,  |
|                      |                      | this keeps the       |
|                      |                      | library ingredients  |
|                      |                      | neutral.             |
+----------------------+----------------------+----------------------+
| Packaging Elements   | PLMP                 | Root for packaging   |
| Root                 | ackagingElementsRoot | elements. Sub-roots  |
|                      |                      | for specified        |
|                      |                      | packaging elements   |
|                      |                      | and supplier         |
|                      |                      | response packaging   |
|                      |                      | elements.            |
+----------------------+----------------------+----------------------+
| Packaging Elements   | PLMPackagingElements | Root level for       |
|                      |                      | specified packaging  |
|                      |                      | elements.            |
+----------------------+----------------------+----------------------+
| Packaging Element    | PLMPackagingElement  | Used for capturing   |
|                      |                      | specifications of    |
|                      |                      | each packing         |
|                      |                      | element.             |
|                      |                      |                      |
|                      |                      | e.g., A foil wrapper |
|                      |                      | on a chocolate piece |
|                      |                      | is a packaging       |
|                      |                      | element, a tray to   |
|                      |                      | hold and protect the |
|                      |                      | chocolates is a      |
|                      |                      | separate element,    |
|                      |                      | and the box that the |
|                      |                      | tray goes into is    |
|                      |                      | another element.     |
+----------------------+----------------------+----------------------+
| Supplier Response    | PLMSupplierRespo     | Root level for all   |
| Packaging Elements   | nsePackagingElements | supplier response    |
|                      |                      | packaging elements.  |
+----------------------+----------------------+----------------------+
| Supplier Response    | PLMSupplierResp      | Represents the       |
| Packaging Element    | onsePackagingElement | supplier\'s version  |
|                      |                      | of a specified       |
|                      |                      | packaging element so |
|                      |                      | that the supplier    |
|                      |                      | can provide          |
|                      |                      | information about    |
|                      |                      | what they propose    |
|                      |                      | for each element.    |
+----------------------+----------------------+----------------------+
| Parameters           | PLMParametersRoot    | A root level for     |
|                      |                      | organizing           |
|                      |                      | Parameters.          |
+----------------------+----------------------+----------------------+
| Parameters Level 1   | PLMParametersLevel1  | A broad              |
|                      |                      | categorization for   |
|                      |                      | parameters used for  |
|                      |                      | organizing different |
|                      |                      | types of parameters. |
+----------------------+----------------------+----------------------+
| Parameter            | PLMParameter         | Used to specify the  |
|                      |                      | quality testing      |
|                      |                      | tolerances of each   |
|                      |                      | microbiological or   |
|                      |                      | chemical property    |
|                      |                      | that may be present  |
|                      |                      | in food.             |
|                      |                      |                      |
|                      |                      | e.g., Must be        |
|                      |                      | undetectable in 100  |
|                      |                      | mg.                  |
+----------------------+----------------------+----------------------+
| Requirements Root    | PLMRequirementsRoot  | A root level for     |
|                      |                      | organizing           |
|                      |                      | requirements.        |
+----------------------+----------------------+----------------------+
| Requirements Level 1 | P                    | A broad              |
|                      | LMRequirementsLevel1 | categorization for   |
|                      |                      | requirements used    |
|                      |                      | for organizing       |
|                      |                      | different types of   |
|                      |                      | requirements.        |
+----------------------+----------------------+----------------------+
| Requirements Level 2 | P                    | A broad              |
|                      | LMRequirementsLevel2 | categorization for   |
|                      |                      | requirements used    |
|                      |                      | for organizing       |
|                      |                      | different subtypes   |
|                      |                      | of requirements.     |
+----------------------+----------------------+----------------------+
| Requirement          | PLMRequirement       | [Holds information   |
|                      |                      | about requirements   |
|                      |                      | for a                |
|                      |                      | recipe.]{style       |
|                      |                      | ="font-size: 11pt;"} |
+----------------------+----------------------+----------------------+
| Label Requirement    | PLMLabelRequirement  | Holds information    |
|                      |                      | about requirements   |
|                      |                      | for labeling of a    |
|                      |                      | product variation.   |
+----------------------+----------------------+----------------------+
| Packaging            | PLM                  | Holds information of |
| Requirement          | PackagingRequirement | requirements for a   |
|                      |                      | packaging variation. |
+----------------------+----------------------+----------------------+

For more information on Snapshots and Snapshot Recorders, see the
**Snapshot Configurations** ([here]{.mcFormatColor
style="color: Blue;"}) and the **Snapshot Recorders**
([here]{.mcFormatColor style="color: Blue;"}) topics in the **Change
Reports** segment of the **PLM for Admins** section of the **Product
Lifecycle Management** documentation.
