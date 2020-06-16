---
description: 'PLM Solution: Each reference used in the implementation is
  described in the table below.'
title: '\[%=Heading.Level1%\]'
---

Reference Object Types for PLM Private Label Food Solution
==========================================================

Each reference used in the implementation is described in the table
below.

Product References Types
------------------------

  Reference Name                    Reference ID                       Purpose
  --------------------------------- ---------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Additive                          PLMAdditive                        Used to relate additives, specified additive and supplier response additive to a recipe (design variants, sample).
  Competitive Product               PLMCompetitiveProduct              Used to relate a Competitive Product Food to a Design Specification.
  Composite Sample                  PLMCompositeSample                 Relates a supplier\'s composite response to their own recipe proposals that are used in the composite product.
  Composite Sample Packaging        PLMCompositeSamplePackaging        Relates supplier's composite recipe proposals to one or more packaging proposals that are valid options.
  Composite Variant Packaging       PLMCompositeVariantPackaging       Relates recipe specifications that are composite products to one or more packaging specifications that are valid options.
  Composite Variant Sample          PLMCompositeVariantSample          Relates a retailer's composite product specification to the supplier\'s composite product proposal.
  Composite Variant Specification   PLMCompositeVariantSpecification   Relates a retailer's composite specification to recipes that are used in the composite product.
  Ingredient                        PLMIngredient                      Relates a recipe (Design Specification Variant) to ingredients that are used to specify which ingredients can or cannot be used in a recipe. Also used to relate a supplier\'s sample (Sample) to ingredients in recipes that the supplier offers.
  Label Requirement                 PLMLabelRequirement                Used to relate a Design Specification Label Variant or Label Variant Sample to a Requirement. Allows for display and maintenance of specific types of requirements on Web UI screens.
  Label Variant Sample              PLMLabelVariantSample              Relates a Design Specification Label Variant to a supplier response object (Label Variant Sample).
  Packaging Element                 PLMPackagingElement                Relates a Design Specification Packaging Variant to elements that make up the packaging. Also relates a Packaging Variant Sample to supplier response objects for the packaging elements. Valid attributes are the same as for requirements.
  Packaging Requirement             PLMPackagingRequirement            Used to relate Design Specification Packaging Variant, Packaging Element, Packaging Variant Sample or Supplier Response Packaging Element to a Requirement. Allows for display and maintenance of specific types of requirements on Web UI screens.
  Packaging Variant Sample          PLMPackagingVariantSample          Relates the Design Specification Packaging Variant to supplier response objects for the packaging.
  Parameter                         PLMParameter                       Relates to recipe specifications (Design Specification Variant), Ingredients, Compound Ingredient, Specified Ingredient, Specified Compound Ingredient, Supplier Response Ingredient, Supplier Response Compound Ingredients, to Parameters so that requirements for quality testing thresholds can be set.
  PMDM Library Recipe               PMDMLibraryRecipe                  Relates a PMDM product to a finalized recipe in the retailer's recipe library.
  PMDM Source Project               PMDMSourceProject                  Relates a PMDM product to the Design Specification (project) that resulted in the PMDM product.
  Recipe Source Project             PLMRecipeSourceProject             Relates a finished recipe in the library to the Design Specification for the project.
  Recipe Source Sample              PLMRecipeSourceSample              Relates a finished recipe in the library to the original supplier\'s recipe proposal.
  Related Label Packaging           PLMRelatedLabelPackaging           Relates Design Specification Label Variant and Label Variant Sample objects to Design Specification Packaging Variant and Packaging Variant Sample objects.
  Related Packaging                 PLMRelatedPackaging                Relates a Design Specification Variant (Recipe Specification) to a Design Specification Packaging Variant (packaging specification). Also used to relate a Sample (Recipe Response) to valid Packaging Variant Samples.
  Related Recipe                    PLMRelatedRecipe                   Relates a Design Specification Label Variant (label specification) to one Design Specification Variant (Recipe Specification) or Design Specification Composite. It also relates the supplier's Label Variant Sample to one Sample or Composite Sample.
  Related Specification             PLMRelatedSpecification            Relates a Design Specification to Recipe Specification, Packaging and Label variant of the product.
  Requirement                       PLMRequirement                     Relates recipe specifications (Design Specification Variants) and recipe proposals (Samples) to recipe requirements.
  Sample                            PLMSample                          Relates a recipe specification (Design Specification Variant) to each supplier\'s response (sample) object for the product variation.
  Specified Additive                PLMSpecifiedAdditive               Relates an additive in the library to a specified additive.
  Specified Ingredient              PLMSpecifiedIngredient             Relates ingredients (Ingredient, Compound ingredient) in the ingredient library to the recipe\'s specified ingredients (Specified or Compound Ingredient).
  Sub-ingredient                    PLMSubIngredient                   Relates compound ingredient to sub-ingredients, which can be normal ingredients or compound ingredients. Indicates which ingredients are used in a Compound Ingredient in a recipe.
  Sub-Ingredient Additive           PLMSubIngredientAdditive           Relates a compound ingredient (Specified Compound, Supplier Response Compound) in a recipe with a sub-ingredient that is an additive (Specified Additive or Supplier Response Additive).
  Supplier\'s Equivalent            PLMSuppliersEquivalent             Relates ingredients, additives and packaging element in the library with copies of those ingredients, additives and packaging element that the supplier is using for their recipes. Allows traceability between the library ingredient and those ingredients that are used in the supplier recipes.
  Supplier Response                 PLMSupplierResponse                Relates a Design Specification to supplier response objects for the project. Used to store rankings on each of the samples so that there is a view from the Design Specification of all supplier responses.

Images and Documents Reference
------------------------------

  Object Type Name        Object Type ID        Purpose
  ----------------------- --------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Primary Product Image   PrimaryProductImage   Links Product and Supplier Items to Product Image objects. Upper levels of the Products hierarchy can also be linked as the reference is inherited. Multiples are not allowed as each product or Supplier Item may have only a single primary image assigned to it.
  Product Image           ProductImage          Used for the additional product images for a product.
  Punch Template          PLMPunchTemplate      Links Packaging Variant objects and Recipe to a Punch Template asset.

Classification References
-------------------------

  Object Type Name                 Object Type ID                    Purpose
  -------------------------------- --------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Additive Class                   PLMAdditiveClass                  Used by the PLM developed component for specifying recipes. This reference specifies an entire class of additives that may or may not be used in recipes.
  Ingredient Options               PLMIngredientOptions              Used by the PLM developed component for specifying and building recipes. Creates a reference from a category of Design Specifications to the root of an ingredient classification so that the list of ingredient options can be controlled via classification. For example, pet food contains ingredients that should not be options for human-grade food.
  Ingredient Specification Group   PLMIngredientSpecificationGroup   Used to group similar ingredients that can then be specified to must be, must not be or may be contained in a recipe.
  Selected Supplier                PLMSelectedSupplier               Used to connect a Design Specification directly to one or more suppliers that are selected to bid on a new private label food product.
  Snapshot                         Snapshot                          Relates the object that has a snapshot to its snapshot.
  Snapshot Configuration           SnapshotConfiguration             Links the Snapshot Configuration with the snapshot.

Product to Classification Link
------------------------------

+----------------------+----------------------+----------------------+
| Object Type Name     | Object Type ID       | Purpose              |
+======================+======================+======================+
| Additive             | PLMAd                | Relates an additive  |
| Classification       | ditiveClassification | to the Additive      |
|                      |                      | Class classification |
|                      |                      | according to the     |
|                      |                      | additive function in |
|                      |                      | the recipe.          |
+----------------------+----------------------+----------------------+
| Ingredient           | PLMIngr              | A root level for     |
| Classification       | edientClassification | ingredient           |
|                      |                      | classification that  |
|                      |                      | breaks down the      |
|                      |                      | purpose for          |
|                      |                      | ingredients (e.g.,   |
|                      |                      | food or pet food)    |
|                      |                      | and allows           |
|                      |                      | ingredients to be    |
|                      |                      | classified in one or |
|                      |                      | more ways.           |
+----------------------+----------------------+----------------------+
| Label Country and    | PLMLabe              | Relates a label      |
| Languages            | lCountryAndLanguages | variant to the Label |
|                      |                      | Country and          |
|                      |                      | Languages            |
|                      |                      | classification that  |
|                      |                      | the variant          |
|                      |                      | represents.          |
+----------------------+----------------------+----------------------+
| PLM Product Category | PLMProductCategory   | A product-centric    |
|                      |                      | classification used  |
|                      |                      | for classifying      |
|                      |                      | Design               |
|                      |                      | Specifications so    |
|                      |                      | that attribution can |
|                      |                      | be controlled. Also  |
|                      |                      | used for             |
|                      |                      | product-centric      |
|                      |                      | Design Specification |
|                      |                      | templates with       |
|                      |                      | Requirements and     |
|                      |                      | Parameters already   |
|                      |                      | linked to the        |
|                      |                      | templates to reduce  |
|                      |                      | effort by users when |
|                      |                      | new Design           |
|                      |                      | Specifications are   |
|                      |                      | made.                |
|                      |                      |                      |
|                      |                      | Relates a Design     |
|                      |                      | Specification to a   |
|                      |                      | product category for |
|                      |                      | the product. Also    |
|                      |                      | relates requirements |
|                      |                      | and parameters to    |
|                      |                      | product categories   |
|                      |                      | so that the default  |
|                      |                      | requirement or       |
|                      |                      | parameter\'s         |
|                      |                      | descriptions and     |
|                      |                      | help text can be     |
|                      |                      | tailored for the     |
|                      |                      | category.            |
+----------------------+----------------------+----------------------+
| Required for         | PLM                  | Relates a Design     |
| Geography            | RequiredForGeography | Specification to one |
|                      |                      | or more countries    |
|                      |                      | where the product(s) |
|                      |                      | are intended to be   |
|                      |                      | sold. Also relates   |
|                      |                      | requirements and     |
|                      |                      | parameters to a      |
|                      |                      | country so that the  |
|                      |                      | default requirement  |
|                      |                      | or parameter\'s      |
|                      |                      | descriptions and     |
|                      |                      | help text can be     |
|                      |                      | tailored for         |
|                      |                      | regulations in each  |
|                      |                      | country.             |
+----------------------+----------------------+----------------------+
| Supplier Link        | SupplierLink         | Classifies           |
|                      |                      | suppliers\'          |
|                      |                      | materials, samples,  |
|                      |                      | and other product    |
|                      |                      | objects into a       |
|                      |                      | folder which is used |
|                      |                      | to control user      |
|                      |                      | privileges.          |
+----------------------+----------------------+----------------------+

 
