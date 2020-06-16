---
description: 'PLM Solution: The \''PMDM New Product Introduction\'' Web UI
  is intended to be used to enrich the PMDM product, making it ready for
  selling in multiple channels.'
title: '\[%=Heading.AnyLevel%\]'
---

Web UI PMDM New Product Introduction
====================================

The \'PMDM New Product Introduction\' Web UI is intended to be used to
enrich the PMDM product, making it ready for selling in multiple
channels.

The Web UI includes a simple workflow for demo purposes, PMDM New
Product Introduction, with two workflow states: Product Data Enrichment
and End.

Most Web UIs are configured to not show the last \'End\' state. The
image below reflects this common configuration.

![](../../../../Resources/Images/Solution%20Enablement/PLM/WorkflowExample.png)

No data exists for enrichment in the sample PMDM New Product
Introduction Web UI. This is an example that will be extended based on
the specific need for the user.

Use Case

In the images below, after supplier responses (Recipe, Packaging, and
Label) for the Chocolate Cookie product have been evaluated and ranked,
the purchasing (sourcing) team has decided to award the contract to
Supplier A.

![](../../../../Resources/Images/Solution%20Enablement/PLM/AwardCompleteImage.png)

A purchasing team member executes the action Award Complete, and with
this action, the Chocolate Cookie project has been finalized. The new
product needs to start the lifecycle in the PMDM system.

As shown below, Chocolate Chip Cookies Project is moved to the Finalized
Projects hierarchy.

![](../../../../Resources/Images/Solution%20Enablement/PLM/FinalizedHierarchyExample.png)

For suppliers other than Supplier A:

-   None awarded Recipe Response are deleted
-   None awarded Label Response are deleted
-   None awarded Packaging Response are deleted

When the Recipe Specifications, Label Specifications, and Packaging
Specifications that were not awarded are deleted, all the related
specified ingredients, supplier responses ingredients, and packaging
elements are also deleted.

One PMDM product was created for each awarded label for Supplier A.

![](../../../../Resources/Images/Solution%20Enablement/PLM/PMDMClassificationHierarchy.png)

The awarded supplier recipe is stored in a library so that users can
view the recipe. The library recipe is also linked to the PMDM product
in case additional information about the recipe needs to be reviewed.

![](../../../../Resources/Images/Solution%20Enablement/PLM/RecipeLibraryExample.png)
