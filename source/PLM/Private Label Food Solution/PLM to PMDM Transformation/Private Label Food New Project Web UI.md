---
description: 'PLM Solution: In the existing solution for private label
  food, the business action PLM Food Award Bid (PLMFoodAwardBid) has
  been modified to include the business actions described below.'
title: '\[%=Heading.Level1%\]'
---

Private Label Food New Project Web UI
=====================================

In the existing solution for private label food, the business action PLM
Food Award Bid (PLMFoodAwardBid) has been modified to include the
business actions described below.

PLM Food Award Bid

-   **Business Rule ID**: PLMFoodAwardBid
-   **Scope**: Global (Action)
-   **Dependencies**: N/A
-   **Valid Object Types**: Design Specification
-   **Trigger**: On transition out of Award Bid state of the Private
    Label Food new Project workflow
-   **STEP Workflow using this Business Rule**:
    PLMPrivateLabelFoodNewProject
-   **Business Rules using this Business Rules**: N/A
-   **Description**: Validate the status of all Label Variant Sample
    objects related to the Label Variant Specification for the current
    project. If the value of attribute Status of This Response is
    (Declined by, No Response, or Canceled by), return true. Then
    validate if the value of attribute Awarded Bid in each Label Variant
    Sample is equal to \'Y,\' if it is not, return Submit error message:
-   **Referenced Other BA Business Action**: N/A

PLM Food Create Recipe Library

The business action PLM Food Create Recipe Library
(PLMFoodCreateRecipeLibrary) creates the library recipe(s) based on the
number of awarded recipes for a project.

It is valid for the Design Specification (PLMDesignSpecification) object
type, and it has two binds:

-   Node for the current object
-   Manager for the STEP manager

The main flow of the business action is:

-   Get a list of the awarded recipes
-   Get (if the project group already exists) or create the library
    group the library recipe will be created under. The hierarchy for
    the library recipe has two levels. As shown in the image below, the
    top level is the name of the parent of the project of the recipe,
    the Design Specification Level 1 (PLMDesignSpecificationLevel1)
    object. The next level is the name of the product category the
    project is linked to, the name of the target of the
    PLMProductCategory reference.

![](../../../../Resources/Images/Solution%20Enablement/PLM/RecipeLibraryHierarchy.png)

-   Link the library recipe to the recipe source sample,
    PLMRecipeSourceSample
-   Link the library recipe to the recipe source project,
    PLMRecipeSourceProject
-   Link the library recipe to the supplier, PLMRecipeSupplier
-   Set the recipe revision number
-   Copy values from the supplier recipe to the library recipe
-   Populate the data containers with nutritional values, nutritional
    daily values and all other values from the supplier recipe.
-   Generate an ingredients list from the supplier recipe and save it to
    the library recipe

PLM Food Finalize Project

The business action PLM Food Finalize Project (PLMFoodFinalizeProject)
reparents the PLM project and deletes any project related objects that
were not awarded.

It is valid for the Design Specification (PLMDesignSpecification) object
type, and it has two binds:

-   Node for the current object
-   Manager for the STEP manager

The main flow of the business action is:

-   Get (if the project group already exists), or create the finalized
    project group the project will be moved to. The hierarchy for the
    finalized projects has two levels. The top level is the name of the
    parent of the project of the recipe, the Design Specification Level
    1 (PLMDesignSpecificationLevel1) object. The next level is the name
    of the product category the project is linked to, the name of the
    target of the PLMProductCategory reference.

![](../../../../Resources/Images/Solution%20Enablement/PLM/FinalizedProductsHierarchy.png)

-   Reparent the project to the finalized project group
-   Delete none awarded labels
-   Deleted none awarded samples
-   Delete none awarded variants

When the samples and variants are deleted, all of the of the related
specified ingredients, supplier response ingredients, and packaging
elements are also deleted.

PLM Food Create PMDM Product

The business action PLM Food Create PMDM Product
(PLMFoodCreatePMDMProduct) creates a PMDM product for each of the
awarded PLM labels and copies a number of PLM values to it.

It is valid for the Design Specification (PLMDesignSpecification) object
type, and it has two binds:

-   Node for the current object
-   Manager for the STEP manager

The main flow is:

-   Get awarded labels
-   Get the GPC product category (based on PLM project)
-   Create PMDM product
-   Copy values from the PLM label to the PMDM product
-   Copy values from the PLM packaging to the PMDM product
-   Copy values from the PLM recipe to the PMDM product
-   Link the PMDM product to the library recipe
