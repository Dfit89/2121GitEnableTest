---
description: 'Automotive Solution: PMDM for Automotive 8.2 MP4 November
  2017 Maintenance Patch Notes'
title: PMDM for Automotive 8.2 MP4 November 2017 Maintenance Patch Notes
---

PMDM for Automotive 8.2 MP4 Patch Notes {#pmdm-for-automotive-8.2-mp4-patch-notes .MPN}
=======================================

Release Date: November 6, 2017 {#release-date-november-6-2017 .MPN}
------------------------------

Bugfixes {#bugfixes .MPNBugFix}
--------

PRODOC note: RDCUST-2420Fixed Application Condition Header - Group
component to display newly added conditions with filtered values based
on the validation path

Previously in Application Editor, when a new condition is added in the
condition editor, the list of values to select from would be empty. The
Application Condition Header - Group component has been fixed so that
when a new condition is added in the condition editor, values will be
displayed to select from. The values are filtered based on the
Automotive Validation Path that is configured on the condition
attribute.

PRODOC note: RDCUST-1573Fixed Automotive Validation Path error handling
in Application Editor

Previously, if an attribute that is linked to a part type contains an
invalid Automotive Validation Path, this would cause all condition
attributes in the Application Editor to display all available options in
the dropdown list instead of displaying only the valid filtered options.
Also, there wasn\'t an indication to the user in the Application Editor
that an error had been encountered with the validation path. This has
been fixed so that if an attribute contains an invalid Automotive
Validation Path, only the condition attribute with the invalid path will
display all available options, other condition attributes will still
retain the valid filtered options in the dropdown list. If the condition
attribute with the invalid path is displayed in its own column, then a
warning icon will be displayed and hovering over the icon will display a
message indicating which reference or attribute contains the error. If
the condition attribute with the invalid path is not displayed in its
own column, then opening the value editor window will display the error
message below the condition with the invalid path.

PRODOC note: RDCUST-2404Updated easy setup functionality for NAPA and
TecDoc so that existing objects are not re-set when easy setup is run
repeatedly

Previously, if easy setup had been run and the objects created by the
setup had been modified, running easy setup again would wipe out any
manual changes that had been made and would re-set the object to the
initial easy setup state. This was previously resolved for AutoCare and
now has been resolved for NAPA and TecDoc so that easy setup does not
modify existing objects unless the change is to expand on an existing
definition (e.g., increase max attribute length or add an additional
validation type). Note that as part of this change, the option to modify
initial configuration settings when running setup for the import
processes has been removed. Previously running option 2 of the easy
setup for NAPA or TecDoc would present the user with an interface to
specify IDs of workflows, integration endpoints, etc. These
user-specified options have been removed and all IDs are now included
within the setup code.

PRODOC note: RDCUST-2439Fixed PCdb Importer to handle N/A Position

Previously, the \'N/A\' value was not being added to AC\_Position LOV
through PCdb Importer, which would cause the Part Terminologies that
have N/A as the only valid position to not have a proper filter and
would allow all positions to be selected. PCdb Importer has been updated
so that the N/A value is written to the AC\_Position LOV and that the
AC\_ACESPosition attribute that is linked to the Part Terminology is
filtered correctly to display only the valid position(s) for that Part
Terminology to be selected.

PRODOC note: RDCUST-2172Fixed NullPointerException error when attempting
to delete missing applications in Application Editor

Previously, attempting to delete missing applications in Application
Editor would generate a NullPointerException error. This has been fixed
so that the NullPointerException is no longer displayed. When attempting
to delete missing applications, no action will be taken in the
Application Editor because missing records can\'t be deleted since they
don\'t exist.

PRODOC note: RDCUST-2264Updated Application Condition Header - Group
plugin in Application Editor to align value editor fields

For better visual display, Application Condition Header - Group plugin
in Application Editor has been updated so that all value editor fields
are now left-aligned properly and spacing has been added between the
fields so that they don\'t overlap one another.

PRODOC note: RDCUST-2087Updated easy setup to rename the ID and Name of
Import Flow Group Type objects

The ID and Name of Import Flow Group Type controller group objects have
been updated to be more consistent across standards. For example, STEP
Name = \'Application data imports\' has been changed to \'AutoCare
ACES.\' And STEP ID = \'application\_\_Application data imports\' has
been changed to \'AC\_ACESImport.\'

For new implementations, running **Automotive - \[Standard\] Model \> 2.
Configure \[Standard\] Import Process** easy setup will create new
Inbound Integration Endpoints (IIEP) with the new ID and Name pattern.
Once a file is imported, the Import Flow Group Type controller group
objects will be created with the new ID and Name pattern.

**Existing implementations should make these changes manually in order
see the new ID and Name pattern after files are imported:**

1.  In the Tree tab, delete the Import Flow Group Type objects below the
    Import Flow Root
2.  In System Setup tab, edit the Inbound Integration Endpoints
3.  In step 5.1 (Configure Processing Engine : Configuration) change the
    ID Prefix for each endpoint

```{=html}
<!-- -->
```
a.  AutoCare IIEP ID Prefix = **AC**
b.  NAPA IIEP ID Prefix = **NAPA**
c.  TecDoc IIEP ID Prefix = **TD**

PRODOC note: RDCUST-2174Updated Application Editor so that Options are
saved when creating new application records

Previously, when a user enters vehicle options to create an application
record and saves, the vehicle options would not be retained for the new
application. Application Editor has been updated so that when a user
creates new application records with vehicle options that all populated
options will be saved.

PRODOC note: RDCUST-2265Updated \'Application Condition Header - Group\'
component in Application Editor to have a fixed height and vertical
scroll bar

In the Application Editor screen, the \'Application Condition Header -
Group\' options value editor window has been updated with a fixed height
and contains a vertical scroll bar if the data to be displayed is
greater than the window size.

PRODOC note: RDCUST-2244Updated PAdb importer to handle attributes with
multiple Validation Base Type

The PAdb importer has been updated to set the attribute validation base
type to be \'Numeric Text\' when there are multiple Metadata validation
types for the same attribute. Previously, the validation base type was
incorrectly set as \'List Of Values.\'

PRODOC note: RDCUST-2357Updated easy setup for TecDoc to make attributes
TD\_ATTR\_BJvon and TD\_ATTR\_BJbis valid for Tractor Axle object type

Easy setup for TecDoc has been updated to make attributes
TD\_ATTR\_BJvon and TD\_ATTR\_BJbis valid for Tractor Axle object type
in order to fix some errors during TecDoc Reference data import. The
updates can be applied by running **Automotive - TecDoc Model \> 1.
Configure TecDoc Data Model** easy setup. Or existing implementations
can make these changes manually:

1.  Select the existing TD\_ATTR\_BJvon attribute and navigate to the
    \[Validity\] tab
2.  Below the \'Valid for Classification Types\' flipper, select the
    \'Tractor Axle\' object type
3.  Repeat steps 1 and 2 for TD\_ATTR\_BJbis attribute

PRODOC note: RDCUST-2503Updated easy setup to make ValidateApplication
Business Condition Global and valid for application object types

Easy setup has been updated to make the ValidateApplication Business
Condition Global and valid for application object types for each
standard so that error handling for invalid part type or invalid vehicle
is reported correctly. The update can be applied by running **Automotive
- \[Standard\] Model \> 2. Configure \[Standard\] Import Process** easy
setup. Existing implementations will need to delete the
ValidateApplication Business Condition first before rerunning step 2 of
easy setup in order to change the Business Condition to be Global.

PRODOC note: RDCUST-2513Updated ImportFlowExtension to handle String
messages correctly

Previously when using the reportInfo() method to write to the Execution
Report, the execution produces null values instead of the strings being
passed to it. Reporting from an ImportFlowExtension has been fixed to
handle String messages correctly.

PRODOC note: RDCUST-2381Fixed Application Editor popup windows to be
adjusted to browser height and width

Previously the Application Condition Header, Application Comment, and
Application Asset Reference header popup windows in Application Editor
were not resizeable, which would cause the windows to be cut off if the
browser width or height was too small. The max height and width for
these components have been adjusted to not exceed the browser height and
width so that the windows will always be visible.

PRODOC note: RDCUST-2516Updated Application Condition Header component
in Application Editor for displaying missing coverage options

Application Editor has been updated so that options that drive missing
coverage are displayed correctly in the value editor window with the
correct value when new applications are created. Previously the options
field would be empty in the value editor window even though a value
should be displayed.

PRODOC note: RDCUST-1955Updated Price Sheet attribute group name in PIES
Importer

In order to stay consistent with PIES attribute grouping model, PIES
Importer has been updated to create Price Sheet attribute groups with
the name in the following format: **PIES Price Segment PRCS \[Price
Sheet Name from input file\]** (e.g., \'PIES Price Segment PRCS 2017 WD
Prices\')

PRODOC note: RDCUST-2432Updated easy setup for TecDoc to add the name
for two entity objects

Easy setup for TecDoc has been updated to add a name for entity objects
TD\_TecDocManufacturerRoot to be \'TecDoc Manufacturers\' and
TD\_TecDocResourceRoot to be \'TecDoc Resources.\' The updates can be
applied by running **Automotive - TecDoc Model \> 1. Configure TecDoc
Data Model** easy setup.

PRODOC note: RDCUST-2459Updated Application Condition Header - Group
component in Application Editor to default cursor to the first value
field

Previously, when a user first opens the dialog window for the condition
editor, the cursor defaults to the field where a new condition is typed.
The Application Condition Header - Group component has been updated so
that the cursor is defaulted to the first value field. This has been
fixed when the condition editor window only contains single value
attributes. If there is a multi-valued attribute, the cursor will
default to the multi-valued attribute instead. The fix for multi-valued
attributes will come in future releases.

PRODOC note: RDCUST-2462Updated Application Condition Header -
Individual component in Application Editor be displayed in alphabetical
order if Display Sequence is not populated

Previously, if multiple conditions are added for individual column
display in the Application Editor, they would be displayed in random
order if the Display Sequence attribute is not populated. The
Application Condition Header - Individual component has been updated so
if the Display Sequence is not populated for any of the individual
conditions, then the individual conditions will be displayed in
alphabetical order. If some individual conditions have Display Sequence
populated and some do not, then the conditions with the Display Sequence
populated will be handled first in the order of the Display Sequence
number. Then the conditions without Display Sequence populated are
handled next and displayed in alphabetical order.

PRODOC note: RDCUST-2440Changed LOV filtering for ACES Position
attribute to display only the valid values that are filtered on the part
type that the application is referenced to

Previously, if an application object is referenced to a part type and
the PIES item is referenced to a different part type, then the Position
list of values to select from would contain values from both the part
type referenced by the PIES item and the part type referenced by the
application object. The LOV filtering on the ACES Position attribute has
been changed so that applications with a part type that differs from the
part type of the PIES item will no longer have the position attribute
filtered on the PIES items part type. It would only contain the filtered
values from the part type referenced by the applications.

PRODOC note: RDCUST-2460Updated the Delta file creation in the
importflow to create a delete file with only objects that has an object
type that is valid for the DeleteStatus attribute

Previously when importing a file, the Delta Calculation state would
generate errors if the change flag attributes was not made valid for all
object types. The Delta Calculation has been updated so that it will no
longer create delete file entries for objects that the DeleteStatus
attribute is not valid for.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

**to:automotive/7.0/automotive-7.0.6.spr**

Note that the above recipe is compatible only with the third maintenance
patch for the STEP 8.2 core baseline release
(**to:step/trailblazer/step-8.2-mp3.spr**).

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
