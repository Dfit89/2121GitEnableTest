---
description: 'Customer MDM Solution: This topic describes the relevant
  super types used in the CMDM data model.'
title: Entity Super Types
---

Entity Super Types
==================

STEP uses four types of object super types to model data: products,
classifications, assets, and entities. Entities are the suggested object
for modeling customer, contacts, and household data. Some benefits of
entity object types include:

-   May be configured as globally revisable, which requires no approvals
    or workspace revisions, and instantaneous updates.
-   References can be configured as parent-child relationships.
-   Support for Matching and Merging.
-   Support for Dun & Bradstreet integration.
-   Support for Experian Email Validation integration.
-   Support for Policy Data Monitoring

Some limitations on using entities are that they do not support
inheritance, translations, specification attributes, and specification
data container types.

For more information on entities in STEP, see the **Entity Maintenance**
topic in the **Getting Started** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Domain Folders
--------------

In STEP, any Entity must have a parent Entity. In a CMDM solution, this
relationship does not provide any semantic meaning. Therefore, very
little effort should be put in to organizing parent/child relationships.

The recommended approach is to create \'Domain Folders.\'

For the purpose of traceability in the Workbench tree and when searching
for records, it is recommended to split records governed by different
matching algorithms into separate domain folders.

### Source System Entities

Place all source systems into one folder as there are often very few to
consider.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/SourceSystemEntities.png)

Dimensions and Contexts
-----------------------

Dimension specific attribute values and references should not be used in
a CMDM solution. However, a language dimension can be used for the
purpose of translating data definitions as Attribute names, Reference
Type names, Object Type names, and Data Container Type names in Web UI
and workbench. This also means that the use of multiple Contexts only
allows for translation of data definitions in the UI.
