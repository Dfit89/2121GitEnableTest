---
description: 'Automotive Solution: 8.3 MP2 May 2018 Maintenance Patch
  Notes'
title: PMDM for Automotive 8.3 MP2 May 2018 Maintenance Patch Notes
---

PMDM for Automotive 8.3 MP2 Patch Notes {#pmdm-for-automotive-8.3-mp2-patch-notes .MPN}
=======================================

Release Date: May 29, 2018 {#release-date-may-29-2018 .MPN}
--------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST-2675Saved Search tool added to Application Manager

Now available within an Application Manager screen, the Saved Search
Tool allows users to quickly populate previously saved search criteria
by selecting the name of a saved search from the saved search dropdown.
Saved searches can consist of many different combinations of intelligent
search interface selections, including criteria within one or more
search boxes, existing and/or missing application coverage selection,
and/or brand selection. For more information, see the **Saved Search
Tool** topic ([here]{.mcFormatColor style="color: Blue;"}) within the
**Application Manger** section of the **Automotive Reference Guide**.

PRODOC note: RDCUST-2471Hierarchy Restriction functionality added to
Application Manager

Now available within an Application Manager screen, the Hierarchy
Restriction dropdown allows users to restrict the Application Manager
search results by object type. Users can select from a pre-configured
dropdown list of object types. This can be helpful when search results
need to be filtered by Brand, Manufacturer, OEM, Product Line, etc. This
option can be removed from the Application Manager screen by removing
all object types from the Hierarchy Restriction Object Types parameter.
For more information, see the **Hierarchy Restriction dropdown**
functionality section of the **Intelligent Search Interface** topic
([here]{.mcFormatColor style="color: Blue;"}) within the **Automotive
Reference Guide**.

PRODOC note: MEDU RDCUST-2677 Easy Setup actions create Application
Manager screen

Now, when Easy Setup actions are completed for each standard, a
respective Application Manager screen is automatically created.
Additionally, a quick link to the Application Manager screen is added to
the Quick Links Widget on the home page. Additional steps are required
to insure the quick link functions correctly. For more information, see
the **Application Manager** topic ([here]{.mcFormatColor
style="color: Blue;"}) within the **Automotive Reference Guide**.

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

Application Manager bugfixes

Many bugfixes have been made to the Application Manager, but are not
listed in detail within this release.

PRODOC note: MEDU RDCUST-2872 Updated Easy Setup to no longer create
some links within the Quick Links Widget

Previously, Easy Setup for all three standards (AutoCare, NAPA, TecDoc)
created the following Navigation screens in the Quick Links widget on
the homepage: Advanced Search, Browse, Basket. However, because these
screens require additional configuration, they would display as blank.
Now, Easy Setup only creates the link to the Application Manager screen
created for the standard. The link name displays using the following
syntax: \'\[Standard Name\] Application Manager.\'

**Existing Implementations**: Easy Setup actions can be re-run to
properly configure the Application Manager screen. The quick link to
that Application Manager screen will be added to the bottom of the Quick
Links list.

PRODOC note: RDCUST-2822 Updated label for Missing Applications Only
search

Within the Application Manager, the \'Show missing applications only\'
option has been updated to \'Missing Applications Only.\'

### AutoCare Standard

PRODOC note: RDCUST-2825 Corrected SAX Parse Exception error during
delta calculation import state when context mode is used

Previously, when using the following importers, a SAX Parse Exception
error would occur during the delta calculation import state if the
\'context\' mode was configured: PCdb, PAdb, or VCdb. The error has been
corrected so that the importers can pass the Delta Calculation Import
state successfully when either the context or file calculation mode is
configured.

PRODOC note: MEDU RDCUST-2911 Corrected the use of \'BrandAAIAID\' when
creating PIES Item objects

Previously, the AutoCareMappingBackgroundService used in a \'Run
background process action\' business rule created PIES Item objects with
the Brand Name instead of the BrandAAIAID. This caused ACES exports to
fail because the exporter could not recognize the ID for the PIES Items.
Now, the AutoCareMappingBackgroundService creates the PIES Item ID using
the following ID structure:
AC\_PIESItem\_\[BrandAAIAID\]\_\[PartNumber\].

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

Automotive guides now clearly display version, patch recipe, and core
compatibility

The **Automotive Reference Guide** and the **Automotive Quick Start**
**Guide** now display their version information on the PDF cover page
and footers. Additionally, a **Patch Recipe and Compatibility** section
([here]{.mcFormatColor style="color: Blue;"}) has been added to clearly
communicate the Automotive add-on recipe and the STEP baseline recipe
with which it is compatible.

Automotive Reference Guide is updated with detailed content

With this release, much of the Application Manager functionality
documentation has been completed within the **Automotive Reference
Guide**. Be sure to read the **Application Manager** section
([here]{.mcFormatColor style="color: Blue;"}) and provide feedback.

PRODOC note: PRODOC-1295 File Loading and Status Selector Widget topic
updates

The File Loading and Status Selector Widget topics have been updated.
The latest information is included within the **Web UI Status Selectors
& Import Control Panel Screens** topic ([here]{.mcFormatColor
style="color: Blue;"}) found in the **Using Automotive Importers**
section of the **Automotive User Quick Start Guide**.

PRODOC note: PRODOC-1342 Application Coverage Report topic

The **Application Coverage Report** topic ([here]{.mcFormatColor
style="color: Blue;"}) has been added to the new **Application Manager**
section ([here]{.mcFormatColor style="color: Blue;"}) of the
**Automotive Reference Guide** ([here]{.mcFormatColor
style="color: Blue;"}).

The Application Manager screen type has now superseded the Application
Editor, and with the release of PMDM for Automotive 9.0, the Application
Editor will be deprecated. Thus, the screen type will no longer be
available when creating a new screen within the Web UI Designer.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

**to:automotive/7.0/automotive-7.0.9.spr**

The above recipe is only compatible with the core 8.3 MP3 baseline
(to:step/trailblazer/step-8.3-mp3.spr).

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
