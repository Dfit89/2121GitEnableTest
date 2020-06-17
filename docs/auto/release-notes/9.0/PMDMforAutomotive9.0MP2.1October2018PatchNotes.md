---
description: 'Automotive Solution: PMDM for Automotive 9.0 MP2.1 Patch
  Notes'
title: PMDM for Automotive 9.0 MP2.1 October 2018 Patch Notes
---

PMDM for Automotive 9.0 MP2.1 Patch Notes {#pmdm-for-automotive-9.0-mp2.1-patch-notes .MPN}
=========================================

Release Date: October 15, 2018 {#release-date-october-15-2018 style="text-align: center;"}
------------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: PDO-2536 Enhancements to Application Record Generation for
Print Tables

New functionality simplifies the extraction of Application Records and
population of table(s) when the Vehicle Table structure is simple (e.g.,
a Make / Model / Year construction). The previous functionality that
allows the use of Product Nodes is still available for complex and some
non-standard \'Vehicle Table\' classification structures. In addition,
the enhancements will allow unwanted Application Records (and there may
be many) to be ignored and filtered out of the table so that complex
transformations to get rid of them do not have to be deployed.

The system will recognize whether the currently selected node is a
Product Node or a Classification Node and will populate the table with
Application Records. Three mandatory Description Attributes must reside
on the Publication. The Description attributes are
PRINT\_AppToAssyReferenceTypeID, PRINT\_AssemblyYearObjectTypeID, and
PRINT\_PartTypeLinkReferenceTypeID.

When iterating through the classification folders to locate the Object
Types that match the entry in PRINT\_AssemblyYearObjectTypeID
attributes, there may be many valid Object Types that are not required
for Print purposes. It is desirable not to scan down these unwanted
Nodes and thus not populate the table with Application Records that will
never be used in Print. An optional Description attribute on the
Classification Node will define whether to include or exclude that
folder structure in the extraction of Application Records. A value of
\'N\' will exclude that folder structure. A null value or a value of Y
will include the folder structure. This new filtering Description
attribute is called \'PRINT\_IncludeClassificationNode.\'

When a product node is currently selected, the existing functionality
looks for a reference of the reference type = PrintMakeToVehicleMake.
But, after analysis, the only real function of this reference was to
identify the currently selected product node as being a vehicle
\'Make.\' In order to avoid the necessity of having to generate
\'dummy\' references to classification nodes, the new solution will be
to place a Description attribute on the Publication that identifies
which Object Type in the Print Structure is a vehicle \'Make.\' That
removes the need for all former PrintMakeToVehicleMake references. The
new Description attribute is called PRINT\_StructureMakeID.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive 9.0 MP2.1 add-on can be installed with the following
recipe:

[to:automotive/7.0/automotive-7.0.13.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible only with the following STEP 9.0 MP4
baseline recipe:

[to:step/trailblazer/step-9.0-mp4.spr]{.commandfont}

**PRODOC note: MEDU PRODOC- 1572** Once an Automotive add-on is
installed to a base STEP system, the base system cannot be upgraded
without upgrading the Automotive add-on at the same time. Additionally,
when upgrading any base STEP system that has any Automotive add-on
installed, both install recipes must be prepared at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
