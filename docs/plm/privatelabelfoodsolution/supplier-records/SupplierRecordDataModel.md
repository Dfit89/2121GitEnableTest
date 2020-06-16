---
description: 'PLM Solution: The following object types are needed for
  the supplier record data model.'
title: '\[%=Heading.Level1%\]'
---

Supplier Record Data Model
==========================

The following object types are needed for the supplier record data
model.

Attribute Groups
----------------

The following attribute groups are used by the PLM Food Supplier Record
Library to determine which attributes to include in the supplier bid
record, and in which order they should display.

![](../../../../Resources/Images/Solution%20Enablement/PLM/SupplierRecord2.png)

  Attribute Group ID                          Attribute Group Name                            Description
  ------------------------------------------- ----------------------------------------------- -----------------------------------------------------------------------
  PLMSupplierResponseRecordInformation        Supplier Response Record Information            The root attribute group
  PLMSupplierRecordAsset                      Supplier Record Asset                           Attributes valid for the supplier response record asset
  PLMSupplierRecordHeader                     Supplier Record Header                          Attributes to include in the header section
  PLMSupplierRecordIngredient                 Supplier Record Ingredient                      Attributes to include in the ingredient section of recipes
  PLMSupplierRecordLabelDetails               Supplier Record Label Details                   Attributes to include in the label details section of labels
  PLMSupplierRecordLabelRequirement           Supplier Record Label Requirement               Attributes to include for label requirements
  PLMSupplierRecordNutrition                  Supplier Record Nutrition                       Attributes to include in the nutrition section
  PLMSupplierRecordNutritionDV                Supplier Record Nutrition DV                    Attributes to include in the nutrition daily values section
  PLMSupplierRecordOtherInformation           Supplier Record Other Information               Attributes to include in the other information section of recipes
  PLMSupplierRecordPackagingElement           Supplier Record Packaging Element               Attributes to include in the packaging element section of packaging
  PLMSupplierRecordPackagingRequirement       Supplier Record Packaging Requirement           Attributes to include for packaging requirements
  PLMSupplierRecordParameter                  Supplier Record Parameter                       Attributes to include in the parameter section
  PLMSupplierRecordProjectInformationLabel    Supplier Record Project Information Label       Attributes to include in the project information section of labels
  PLMSupplierRecordProjectInformationPack     Supplier Record Project Information Packaging   Attributes to include in the project information section of packaging
  PLMSupplierRecordProjectInformationRecipe   Supplier Record Project Information Recipe      Attributes to include in the project information section of recipe
  PLMSupplierRecordRequirement                Supplier Record Requirement                     Attributes to include in the recipe requirement section

Supplier Response Attributes
----------------------------

  Attribute Group ID      Attribute Group Name   Description
  ----------------------- ---------------------- -----------------------------------------------------------
  PLMSupplierRecordDate   Supplier Record Date   Storing the date and timestamp when the record is created
  PLMSupplierRecordType   Supplier Record Type   Storing the sample type, recipe, label, or packaging

Supplier Response Asset
-----------------------

  Attribute Group ID       Attribute Group Name       Description
  ------------------------ -------------------------- ---------------------------------------------------------------------------------
  SupplierResponseRecord   Supplier Response Record   An asset object type for storing the HTML document for a supplier's bid record.

Supplier Response Record Image and Document Reference
-----------------------------------------------------

  Attribute Group ID          Attribute Group Name       Description
  --------------------------- -------------------------- ------------------------------------------------------------
  PLMSupplierResponseRecord   Supplier Response Record   Reference from the sample to the supplier response record.
