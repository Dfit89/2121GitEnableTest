---
description: 'PLM Solution: When a PLM project has been awarded to one
  or more suppliers, a PMDM product is created for each of the awarded
  labels.'
title: '\[%=Heading.Level1%\]'
---

Creating a PMDM Product
=======================

When a PLM project has been awarded to one or more suppliers, a PMDM
product is created for each of the awarded labels. This configuration is
an example of how the PLM to PMDM product transformation can be done.
Project implementations should be tailored to classify the new product
in the existing PMDM product hierarchy.

When a PLM project is created it is linked to a product category which
is a GS1 global product classification. For PMDM products a similar
hierarchy is created, and the PMDM product is placed in the same
location in the GPC hierarchy as the PLM project.

A PMDM product will be populated with a number of values from the PLM
project.

Data Model

Products are created in a GPC hierarchy (PMDM Product Classifications).
This classification can be replaced with the existing PMDM product
hierarchy by modifying a business action.

  --------------------------------------------------------------------------
  Object Type ID                   Object Type Name  Description
  -------------------------------- ----------------- -----------------------
  PMDMProductClassificationsRoot   PMDM Product      Root object type for
                                   Classifications   GPC classification

  PMDMProductSegment               PMDM Product      Following GPC standard
                                   Segment           

  PMDMProductFamily                PMDM Product      Following GPC standard
                                   Family            

  PMDMProductClass                 PMDM Product      Following GPC standard
                                   Class             

  PMDMProductGroup                 PMDM Product      Following GPC standard
                                   Group             

  PMDMProduct                      PMDM Product      The PMDM product
  --------------------------------------------------------------------------

Attributes for the PMDM product are all located in the attribute group
PMDM Product Information.

![](../../../../Resources/Images/Solution%20Enablement/PLM/AttributeGroupsHierarchy.png)
