---
description: 'Automotive Solution: PMDM for Automotive 9.3 Release
  Notes'
title: PMDM for Automotive 9.3 Release Notes
---

PMDM for Automotive 9.3 Release Notes {#pmdm-for-automotive-9.3-release-notes .MPN}
=====================================

Release Date: December 06, 2019 {#release-date-december-06-2019 style="text-align: center;"}
-------------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST-3815Updated the MapperBackgroundService to include
\'Clear change attribute\' parameter

The MapperBackgroundService used in the \'Run background process
action\' business rule now has the \'Clear change attribute\' parameter.
When checked, this parameter will clear the flag set in the attribute
configured within the \'Changed attribute\' parameter after the Mapper
Configuration setup entity is executed. This parameter prevents the
Mapper Configuration setup entity to be executed multiple times on the
same Source object over subsequent imports.

![](../../Resources/Images/Release%20Notes/9.3/1.png)

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: NGK-666Fixed Runtime Exception error generated in the
Application Manager related to bulk application updates

Previously, when working in the Application Manager Screen, a Runtime
Exception error would be generated if all of the application records
listed in the search result table were selected by the **Select all**
button and then the Bulk Applications Updates action was executed on all
of the selected application records. The Application Manager Screen is
now updated, therefore executing the Bulk Applications Updates action on
application records after clicking the **Select all** button will no
longer display the \'Failed - Java Lang Runtime.Exception: Cannot find
object type \'null\'\' message.

### AutoCare

PRODOC note: GPC-477Added Replacement Rules for PIES Importer Conversion
to remove existing attribute values when the value no longer exists in
the import file

Previously, the PIES importer did not handle existing STEP attribute
values that have been deleted in the current PIES import file. The PIES
importer would ignore the deleted value in the import file and left the
existing attribute value untouched. In addition, the PIES importer did
not handle overwriting existing Description data containers that had
changed, but instead created a new description. Now, PIES importer has
been updated to include replacement rules that checks the previously
imported file to compare to the current file that is getting imported.
If the previous import populated an attribute value and the current
import does not contain the same attribute, then the import will update
the existing attribute value to be null. Also, if the current imported
file has a change to an existing Description data container, the
existing data container will get overwritten instead of getting a new
description created.

The PIES importer Delta calculation method parameter must be set to
\'file\' in order for this update work properly. Also, the previously
imported file must be retained in the system in order for the current
import file to use for comparison.

**Hotfix recipe compatible with STEP 9.1 MP6 + Automotive 9.1 MP2:**
[to:hotfix/382/issue-382986-HOTFIX-3697.spr]{.commandfont}

PRODOC note: RDCUST-3743Improved accuracy when searching for relevant
targets (assembly / vehicle or part) in Faceted Search dialog

Target (assembly / vehicle or part) search accuracy has been improved by
taking both the Condition and Part Type values into consideration.
Previously, when searching for relevant targets (assembly / vehicle or
part) in Faceted Search dialog, conditions for specific part types were
not considered, resulting in the display of invalid targets (assembly /
vehicle or part). For example, when searching for a 2013 Audi A3 vehicle
for a selected spark plug, the results table would list both Gas and
Diesel engines, even though Diesel engines do not use spark plugs, and
are invalid in the search results. Now, we have improved the targets
search by introducing an existing Business Condition plugin (\'Check
path for missing application\') in the Faceted Search dialog where a
validation path can be configured so that the invalid targets for a
specific part type are filtered away, and only valid values are
returned.

PRODOC note: NGK-570Fixed Application Manager Screen with multiple
Application Manager Options search box to correctly display the search
results

In the Application Manager Screen, the Options Group Search Box within
the Vehicle Type Search Panel allows users to add attributes and/or
references as option search criteria. The Options Group Search Box uses
an \'And\' or \'Or\' operator as a filter when searching between
multiple options. Previously, the Application Manager Options search box
required both Options boxes to be populated in order to display the
correct results. If only one Option box was populated, there would be
more results that would be displayed than what was entered for the
search criteria. Now, the Application Manager Options search box is
corrected to properly sync to form the desired search criteria and
display the results accordingly.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive 9.2 MP2:**
[to:hotfix/382/issue-382862-HOTFIX-3694.spr]{.commandfont}

### TecDoc

PRODOC note: GPC-477Added Replacement Rules for TecDoc Supplier Data
Importer Conversion to remove existing attribute values when the value
no longer exists in the import file

When a file is loaded for an import in the system, the Delta Calculation
state of the importer will assess and compare the loaded file against
the existing data in the system. Depending on the data provided in the
importing file, an attribute value / reference value is either added,
changed, or deleted from the system. Previously, the TecDoc Supplier
Data Importer Delta Calculation exhibited problems in removing the
existing attribute value of an object in the system if the attribute
value of an object was removed in the import file over a subsequent
Import. The TecDoc Supplier Data Importer Delta Calculation has been
fixed so that the existing attribute value of an object is erased in the
system if the attribute value is not present on the TecDoc Supplier Data
file.

Previously, the PIES importer did not handle existing STEP attribute
values that have been deleted in the current PIES import file. The PIES
importer would ignore the deleted value in the import file and left the
existing attribute value untouched. In addition, the PIES importer did
not handle overwriting existing Description data containers that had
changed, but instead created a new description. Now, PIES importer has
been updated to include replacement rules that checks the previously
imported file to compare to the current file that is getting imported.
If the previous import populated an attribute value and the current
import does not contain the same attribute, then the import will update
the existing attribute value to be null. Also, if the current imported
file has a change to an existing Description data container, the
existing data container will get overwritten instead of getting a new
description created.

The PIES importer Delta calculation method parameter must be set to
\'file\' in order for this update work properly. Also, the previously
imported file must be retained in the system in order for the current
import file to use for comparison.

**Hotfix recipe compatible with STEP 9.1 MP6 + Automotive 9.1 MP2:**
[to:hotfix/382/issue-382986-HOTFIX-3697.spr]{.commandfont}

PRODOC note: NGK-654Corrected TAF stacktrace that would occur while
importing TecDoc Reference Data file

Corrected an error in Validation state that would occur while importing
TecDoc Reference Data file. Previously, the presence of TAF table 115
would cause a stacktrace error to occur during conversion. TAF table 115
has now been removed from validation, therefore the validation state no
longer displays the \'Wrong file name or missing in code. Code has not
table 115 to file\' message.

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**
[to:hotfix/381/issue-381839-HOTFIX-3668.spr]{.commandfont}

**Hotfix recipe compatible with STEP 9.1 MP6 + Automotive 9.1 MP2:**
[to:hotfix/381/issue-381839-HOTFIX-3668.spr]{.commandfont}

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.24.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible with the following STEP 9.3 baseline
recipe:

[to:step/trailblazer/step-9.3.spr]{.commandfont}

Once an Automotive add-on is installed to a base STEP system, the base
system cannot be upgraded without upgrading the Automotive add-on at the
same time. Additionally, when upgrading any base STEP system that has
any Automotive add-on installed, both install recipes must be prepared
at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
