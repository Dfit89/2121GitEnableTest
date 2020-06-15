---
description: 'PLM Solution: The private label food solution
  implementation utilizes six alternate classifications. Each is
  described in the subsequent sections.'
title: '\[%=Heading.Level1%\]'
---

Alternate Classification Hierarchies
====================================

The private label food solution implementation uses six alternate
classifications. Each is described in the subsequent sections.

![](../../../../Resources/Images/Solution%20Enablement/PLM/AdditiveClasses.png)

  Object Type Name               Object Type ID                          Purpose
  ------------------------------ --------------------------------------- --------------------------------------------------
  Product Lifecycle Management   ProductLifecycleManagementClassifRoot   The root node of the Product Lifecycle Products.

Additive Classes
----------------

Organizes additives into one or more classes, based on classifications
of GSFA (General Standard for Food Additives), an international standard
administered by the Codex Alimentarius Commission.

For example, the same additive can be used as an acidifier or a color
retention agent. On product labels, the purpose of the additive must be
declared along with the additive.

![](../../../../Resources/Images/Solution%20Enablement/PLM/AdditiveClasses02.png)

+---------------------+----------------------+----------------------+
| Object Type Name    | Object Type ID       | Purpose              |
+=====================+======================+======================+
| Additive Class Root | PLMAdditiveClassRoot | A top-level          |
|                     |                      | organization level   |
|                     |                      | for additive         |
|                     |                      | classes.             |
+---------------------+----------------------+----------------------+
| Additive Class      | PLMAdditiveClass     | Organizes additives  |
|                     |                      | into one or more     |
|                     |                      | classes, based on    |
|                     |                      | classifications of   |
|                     |                      | GSFA (General        |
|                     |                      | Standard for Food    |
|                     |                      | Additives), an       |
|                     |                      | international        |
|                     |                      | standard             |
|                     |                      | administrated by the |
|                     |                      | Codex Alimentarius   |
|                     |                      | Commission.          |
|                     |                      |                      |
|                     |                      | An additive is       |
|                     |                      | classified according |
|                     |                      | to the purpose       |
|                     |                      | function.            |
|                     |                      |                      |
|                     |                      | For example, the     |
|                     |                      | same additive can be |
|                     |                      | used as an acidifier |
|                     |                      | or a color retention |
|                     |                      | agent. On a product  |
|                     |                      | label, the purpose   |
|                     |                      | of the additive must |
|                     |                      | be declared along    |
|                     |                      | with the additive.   |
+---------------------+----------------------+----------------------+

Geographical Areas
------------------

Organization for geographic areas of the world where the customer may
sell their products. It includes regions and countries.

Countries classification is used to relate projects to countries where
the product is intended to be sold. Also used to relate requirements and
parameters so specific values of a basic requirement or parameter can be
tailored for the country where it will be sold. The requirement or
parameters can vary based on regulations or standards for that country.

![](../../../../Resources/Images/Solution%20Enablement/PLM/GeorgraphicArea.png)

  Object Type Name          Object Type ID             Purpose
  ------------------------- -------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Geographical Areas Root   PLMGeographicalAreasRoot   A top-level organization level for geographic areas of the world where the customer may sell their products.
  Country                   PLMCountry                 A classification for countries. This classification is used to relate Design Specifications to countries where the product is intended to be sold. Also used to relate requirements and parameters to countries so that the requirement or parameters can vary based on regulations or standards for that country.
  Region                    PLMRegion                  An organization level for countries. (optional)

Ingredients Classification
--------------------------

Ingredients classifications organize ingredients in groups based on
their allowable purpose, like whether food is intended for animals or
humans. This allows ingredient searches used in the Web UI to specify
ingredient component result in only relevant ingredients. It categorizes
ingredients into relevant groupings for maintenance purposes and for
specifying a group of ingredients that may be allowable.

![](../../../../Resources/Images/Solution%20Enablement/PLM/Ingredients%20Classification.png)

  Object Type Name                  Object Type ID                      Purpose
  --------------------------------- ----------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------
  Ingredients Classification Root   PLMIngredientsClassificationRoot    Classification for ingredients; supports finding different ingredients under Food or Pet Food.
  Ingredient Maintenance Groups     PLMIngredientMaintenanceGroups      Categorizes ingredients into relevant groupings for maintenance.
  Ingredient Purpose                PLMIngredientPurpose                Organizes groups of ingredients by their allowable purpose, e.g., Food vs Pet Food so that ingredient searches result in only relevant ingredients.
  Ingredient Group                  PLMIngredientGroup                  Categorizes ingredients into relevant groupings for maintenance purposes and also for specifying a group of ingredients that may be allowable.
  Ingredient Specification Groups   PLMIngredientSpecificationsGroups   Organizes groups of Specification ingredients.
  Ingredient Specification Group    PLMIngredientSpecificationGroup     Categorizes ingredients into relevant groupings for specifying a group of ingredients that may be allowable.

Label and Country Language
--------------------------

The label and country language hierarchy is an object that will hold
attributes containing country code and language code for a label
variation. It is recommended classification names to represent country
name plus language code(s).

![](../../../../Resources/Images/Solution%20Enablement/PLM/LabelCountryLang.png)

  Object Type Name                   Object Type ID                    Purpose
  ---------------------------------- --------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Label Country and Languages Root   PLMLabelCountryAndLanguagesRoot   Root level for storing the language bundle library.
  Label Country and Languages        PLMLabelCountryAndLanguages       An object that will hold attributes containing country code and language code for a label variation. Recommended classification names to represent country name plus language code(s).

PLM Digital Asset
-----------------

The PLM digital asset hierarchy organizes product lifecycle digital
images uploaded or inserted by the customer. Food images will be located
at:

![](../../../../Resources/Images/Solution%20Enablement/PLM/Digital%20Assets.png)

  Object Type Name                     Object Type ID                           Purpose
  ------------------------------------ ---------------------------------------- ---------------------------------------------------------------------
  Digital Assets Root                  PLMDigitalAssetsRoot                     A top-level organization level for digital assets.
  Competitive Product Digital Assets   PLMCompetitiveProductDigitalAssetsRoot   A top-level organization level for competitive digital assets.
  Packaging Images                     PLMPackagingImagesRoot                   A top-level organization level for packaging digital assets.
  PLM Illustrations Root               PLMIllustrationsRoot                     A top-level organization level for PLM illustration digital assets.
  PLM Images Root                      PLMImagesRoot                            A top-level organization level for PLM digital assets.

PLM Product Classification
--------------------------

The PLM product classification hierarchy organizes products based on
GS1's Global Product Classification. The lowest level is used to
organize projects, requirements, and parameters. This allows specific
values of parameters and requirements to vary by the type of product
being produced.

![](../../../../Resources/Images/Solution%20Enablement/PLM/PLM%20ProductClass.png)

  Object Type Name              Object Type ID                  Purpose
  ----------------------------- ------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  PLM Product Classifications   PLMProductClassificationsRoot   An organization level for products based on GS1's Global Product Classification.
  PLM Product Segment           PLMProductSegment               An organization level for products.
  PLM Product Family            PLMProductFamily                An organization level for products.
  PLM Product Class             PLMProductClass                 An organization level for products.
  PLM Product Group             PLMProductGroup                 An organization level for Design Specifications, Requirements, and Parameters. Allows specific values of Requirements and Parameters to vary by the type of product being produced.
