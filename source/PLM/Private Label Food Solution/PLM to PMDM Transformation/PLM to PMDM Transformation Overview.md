---
description: 'PLM Solution: An important benefit of having PLM in the
  same STEP system where product master data management takes place is
  that pertinent details can be made available earlier to Data Stewards
  who need to enrich newly introduced items. '
title: '\[%=Heading.Level1%\]'
---

PLM to PMDM Transformation Overview
===================================

An important benefit of having PLM in the same STEP system where product
master data management takes place is that pertinent details can be made
available earlier to Data Stewards who need to enrich newly introduced
items. These newly enriched items will then be published on websites or
made available for other channels. A project in the Private Label Food
solution is complete when suppliers are awarded. One PMDM product is
created for each of the awarded labels in the finalized project.

The PMDM product will be linked to a recipe object containing all the
detailed information about the ingredients and nutritional data, and it
will also be linked to the finalized PLM project, enabling the PMDM user
to easily view additional information about the PLM project.

The following artifacts were created for this functionality:

-   Recipe Library Data model
-   A business rule for creating a library recipe for the awarded
    recipe(s)
-   A business rule for finalizing a PLM project, removing objects that
    are not awarded and moving the PLM project into a finalized library
-   A business rule for creating PMDM products for each of the awarded
    PLM labels and to start the PMDM product in a PMDM new product
    introduction workflow

PLM Private Label Food Solution to PMDM transformation will be done
using standard STEP platform capabilities, and no additional Web UI
components was developed as part of this functionality.
