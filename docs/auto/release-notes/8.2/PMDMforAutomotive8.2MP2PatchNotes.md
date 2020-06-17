---
description: 'Automotive Solution: PMDM for Automotive 8.2 MP2 August
  2017 Maintenance Patch Notes '
title: PMDM for Automotive 8.2 MP2 August 2017 Maintenance Patch Notes
---

PMDM for Automotive 8.2 MP2 Patch Notes {#pmdm-for-automotive-8.2-mp2-patch-notes .MPN}
=======================================

Release Date: August 24, 2017 {#release-date-august-24-2017 .MPN}
-----------------------------

Enablement of some new features and bugfixes requires that easy setup be
re-run. When this occurs, the setup steps in the Automotive Quick Start
guide should be re-checked as some manual changes may be reverted by
easy setup. Specifically, it is important to verify and/or repeat steps
4 - 10 of the Quick Start guide after re-running easy setup.

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST-2340PAdb Importer has been updated to no longer
require use of Single Update Mode

The PAdb Importer previously used Single Update Mode as part of the
import process. The importer has been updated to no longer use Single
Update Mode so that users should be able to run PAdb imports without
disrupting other system processes or activities.

PRODOC note: RDCUST-2336Added support for import of ACES 3.X files

The ACES 3.2 Importer has been updated to allow import of files with a
version of 3.0, 3.0.1, or 3.1. As long as the file matches the 3.2
schema, it will now be accepted, regardless of the specific 3.X version
number supplied in the header of the file. Note that the changes in
format between the various 3.X versions are minimal, so most files will
be accepted against the 3.2 schema validation. However, the format of
the ApprovedFor tag in the header changed between version 3.0 and 3.2.
Therefore, files using the ApprovedFor tag in the 3.0 schema will fail
validation and must be manually updated prior to import (either to
remove the tag, or to adjust it to the 3.2 schema).

PRODOC note: RDCUST-2140, 2332Added support for making the Application
Editor and related screens read-only

The Application Editor is designed for editing application records, and
was therefore originally provided only with full editing capabilities.
However, the editor also includes useful search features, independent of
the editing functionality, and implementations may wish to take
advantage of the lookup features without allowing application editing.
Previously it was not possible to provide a read-only version of the
editor as the headers used within the table did not honor standard
display mode settings. To enable use of the lookup functionality without
also enabling editing, several small updates have been made to align the
Automotive-specific table headers with the core Web UI functionality so
that standard display options to restrict editing could be employed. The
outcome of this is that the application editor can now be configured to
be read-only via use of the Compare Display Mode. Note that no changes
to easy setup have been made and all editors created by easy setup will
continue to be fully functioning editors by default.

To implement a read-only application editor, follow the steps below. The
modification can be done in an existing editor screen, or by duplicating
an existing editor screen in the designer, then following the steps
below (in the case that both a read-only and a fully editable option are
desired within the same Web UI). Note that it is not recommended to make
the configuration changes described below within the Web UI designer as
this will require re-configuration of all existing headers.

1.   Find the Web UI in workbench, right-click, and select Edit
    configuration. You may choose to use an internal or external editor,
    but external may be preferred so that search functionality is
    available.
2.  Find the segment with the appropriate screen ID in the format
    \'\[Standard\] Application Editor Search Screen,\' e.g.:

![](../../Resources/Images/QS/XML1.png)

1.  Within the identified screen, find the Display Mode setting within
    the Node List settings:

![](../../Resources/Images/QS/XML2.png)

1.  Change the display mode type to CompareDisplayMode:

![](../../Resources/Images/QS/XML3.png)

1.  Save the edited configuration.

The \'\[Standard\] Application Editor Screen (Parts)\' and
\'\[Standard\] Application Editor Screen (Vehicles)\' can both be made
read-only in the same way as described above (by updating the
configuration to use the Compare Display Mode).

PRODOC note: RDCUST-2143Added support to handle Qualifiers during ACES
import, export, and Easy Setup

Qualifiers are a standardized form of a Note that can be provided on
application records (via the ACES Importer). The standard Qualifiers are
provided in the Qdb database, and brought into STEP via the Qdb Importer
(integration endpoint). Previously, the ACES Importer and Exporter did
not handle Qualifiers in any way, the AutoCare data model had no support
for them outside of the Qdb classification model, and there was no data
model to support the handling of parameters within Qualifiers (even
within the Qdb classification hierarchy).

To handle Qualifiers for ACES import and export, **easy setup for the
Automotive - AutoCare Model (steps 1 & 2) must be re-run** to:

-   Create a new Classification Reference Type called
    AC\_ACESApplicationToQualifier
-   Create a new Description attribute called AC\_QdbParameter and make
    it valid for AC\_ACESApplicationToQualifier reference
-   Create a new Description attribute called AC\_QdbText and make it
    valid for AC\_ACESApplicationToQualifier reference
-   Make the existing DisplaySequence attribute valid for
    AC\_ACESApplicationToQualifier reference

The ACES importer has been updated to:

-   Match the \<Qual id\> provided in the ACES import file to the Qdb
    and create a Classification reference from the application to the
    Qualifier object using the new AC\_ACESApplicationToQualifier
    Classification Reference Type
-   The \<param value\> provided in the ACES import file will be written
    to the AC\_QdbParameter attribute on the reference
-   The \<text\> value provided in the ACES import file will be written
    to the AC\_QdbText attribute on the reference
-   If units are included, then the unit will be displayed in the
    AC\_QdbParameter attribute
-   A display sequence value will be set on the DisplaySequence
    attribute based on the order that the Qualifiers are provided in the
    ACES import file

The ACES exporter has been updated to export the Qualifier data from the
Parameter(s) and Text attributes on the reference in the order that is
set in the DisplaySequence attribute. And units are converted back to
the \<param uom\> tag.

PRODOC note: RDCUST-2144Added support for viewing qualifiers in Web UI
application editor screens

A new component header (ACESApplicationQualifiers) has been added to the
Application Editor Search Screen in order for users to be able to view
qualifier(s) that are applied to each application record. **To add this
header to an existing \'AutoCare Application EditorSearch Screen,\'
either run easy setup for the Automotive - AutoCare Model component \>
4. Configure AutoCare Web UI, or add the header manually via Web UI
designer.**Note that the header can also be added to \'AutoCare
Application Editor Screen (Parts)\' and \'AutoCare Application Editor
Screen (Vehicles)\' screens via manual addition.

This release is only for the functionality to view qualifiers within the
application record screens. Add, edit, and delete functionality for
qualifiers may be made available in a subsequent release.

PRODOC note: RDCUST-2139Added a new Reference Delegation Screen to
support viewing standard applications from the OWN model, as well as a
variety of other use cases

A new Reference Delegation Screen has been added to the Web UI and made
available for manual configuration as needed. There are no explicit
limits on how the screen can be used, but it was created specifically to
satisfy two use cases:

1.  View applications within a standard while the OWN part is selected
2.  View product data on a standard part while the OWN part is selected

The Reference Delegation Screen configuration requires Web UI designers
to select a reference type and a screen ID. The Reference Delegation
Screen can then be added to any existing screen and will follow the
specified reference to it\'s target, and display the configured screen.
In other words, it allows you to take any active selection, follow a
reference on that selection, and display any screen configured for the
target of the reference (noting that the selected screen may show data
from the target itself, data from the child of the target, data from
objects referenced by the target, etc).

For example, the screen can be configured to display applications from a
PIES Item when an OWN part is selected. To do this, the reference
parameter must specify a reference that has the OWN part as a source and
the PIES Item as a target, and a screen must be selected that displays
applications for a part. The \'AutoCare Application Editor Screen
(Parts)\' exists via easy setup creation and displays applications when
a part is selected, so this would be a good candidate. Note that if the
screen must be read-only, the same configuration as described above
regarding changing the display mode can be applied. Once configured
properly, the Reference Delegation Screen can then be added to any
existing screen that is mapped to display data from the OWN part, e.g.,
a Node Details screen using Tab Control where the Sub Screen Tab Page
configuration specifies the Reference Delegation Screen.

The above is just an example, and as stated, there are a variety of use
cases for which this screen can be applied. The only limitation to it\'s
use is that **the reference that is selected must allow for single
references only**. If a reference is selected that allows multiples, the
user will see an error.

Bugfixes {#bugfixes .MPNBugFix}
--------

PRODOC note: RDCUST-2341Corrected the display of the Bulk Update action
button in the Application Record Editor

Previously the Bulk Update action available in the Application Record
Editor displayed an unknown localization key as the label for the
action. This has been corrected so that a proper label (Bulk Updates) is
displayed. **To enable this, easy setup for the Automotive -
\[Standard\] Model component \> 4. Configure \[Standard\] Web UI must be
re-run.**

PRODOC note: RDCUST-2098Corrected inconsistent header names in Condition
Header popup window

Previously if a value was entered in the \'Editor Dialog Label\'
parameter for a Condition Header component, the value would be displayed
for other Condition Header components that it is not applicable for.
Therefore, the \'Editor Dialog Label\' parameter has now been removed
from \'Application Asset Reference\' and \'Application Comment\'
components so that the Condition Header popup window displays a more
consistent title of \"Value editor - 1 item selected.\"

PRODOC note: RDCUST-2312Fixed the ACES Partial Update scenario when an
UPDATE file is supplied via ACES Importer

Previously, when loading a file with SubmissionType=UPDATE and the
Update parameter for the brand set to \'Partial Update,\' more records
would be marked for deletion than expected as vehicle and part type were
not properly taken into account in the deletion calculation. This has
been corrected so that the Partial Update scenario now properly
evaluates the vehicle, part type, and brand combination of each record
to determine deletions.

PRODOC note: RDCUST-2361Fixed NPE generated in the Application Editor
related to invalid validation paths

Previously when working in the Application Editor, a null pointer error
would be generated if you attempted to search for applications when ALL
of the following conditions were met:

-   The selected part type has one or more criteria / option attributes
    linked to it with Display Condition set to \'true\'
-   The Automotive Validation Path metadata attribute is populated on
    the criteria / option attribute
-   The validation path included a reference, and the path had a typo of
    some sort and/or otherwise indicated a reference that does not exist
-   The \'Show missing applications\' option is checked (e.g., a missing
    coverage search is being run)

This has been corrected so that a proper runtime exception is thrown
that indicates the invalid reference.

PRODOC note: RDCUST-2248Fixed Automotive Importers to use Inbound
Endpoint User for revision history on newly created objects

Previously, objects that get created through the Automotive importers
are created with the executing User ID rather than with the User that is
defined in the Inbound Integration Endpoint (IIEP). This has been
corrected so that the User from the IIEP will be used in all processes
of the importflow and newly created objects will have the IIEP User in
the revision history. In addition, the data was being written to the
current context of the executing user, rather than to the context
indicated in the endpoint, so this has also been corrected. **Easy setup
of Automotive - Import Flow Process must be re-run to enable this change
and appropriate users must be assigned to the IIEPs as needed.**

PRODOC note: RDCUST-2263Fixed Application Condition Header component in
Application Editor to no longer require Options to be linked to the Part
Type

Previously in the Application Editor Search screen, the Options
(Application Condition Header) column would only display values for
attributes that were linked to the part type of the displayed
applications. This meant that data could be populated on the
applications that was not displayed to the user. This has been corrected
so that the attributes configured for display in the Application
Condition Header (via selection of attribute group) are no longer
required to be linked to the part type for data to be displayed. In
order for the attributes to be populated in the Application Condition
Header field, the attributes can either be linked to the part type, or
be included in an attribute group that is configured in the Application
Condition Header component.

PRODOC note: RDCUST-2385, 2386Updated AutoCare VCdb Importer to handle
changes in July 2017 file

The July 2017 VCdb file contained 2 issues that would prevent it from
successfully importing. The first was a data error where some models
were included that had no associated vehicles (or makes) and therefore
the system was unable to identify where to create them. This was
corrected by handling this type of exception by writing an error to the
conversion service so users are notified of the data error. The orphan
model records are then ignored and the import process can proceed. The
second issue was that a new date format was introduced in the Vehicle
file, which was causing files to error in validation. The importer has
been updated to accept the new date format so the import process can
proceed.

PRODOC note: RDCUST-1968Fixed handling of ApprovedFor in ACES 3.2
Exporter

Previously the ACES 3.2 exporter did not correctly handle the
ApprovedFor field in the header segment as all values were concatenated
into a single value entry rather than being supplied in individual
Country tags. This has been corrected so that the correct export format
is used. **To enable this, easy setup of the AutoCare data model must be
re-run.** This will create a new LOV with the ID=AC\_ACESApprovedFor.
Any country values that are valid selections for the ApprovedFor field
must be manually added to the LOV. Note that the value IDs must be 2
character country codes, and that it is the value IDs that are included
for export rather than the actual values. Within the exporter interface,
all values from the LOV are displayed so that users may select (via
checkboxes) those that should be included in any given export.

PRODOC note: RDCUST-1950Fixed handling of missing data in AutoCare PCdb
and VCdb Importers

Both the PCdb and VCdb files regularly include incomplete data in
specific places. Within the VCdb Power Output table, there is a row that
does not include values for HorsePower or KilowattPower. In the PCdb
PartsDescription table there are often multiple rows that do not contain
values for PartsDescription. In both cases, IDs are provided for the
rows, just no corresponding values. This means that users must manually
manipulate the files to removed the offending rows in order to get these
files to import as they would otherwise fail validation and be unable to
proceed through the import process. To avoid this manual manipulation,
the importers have been updated to allow the import process to proceed
when missing data is present, but only these two cases where it is
routinely observed. When this occurs, a warning is written to the
validation service to record any rows having the missing data and the
offending data is not imported, but the import processes are now able to
successfully continue.

PRODOC note: RDCUST-2257Updated AutoCare PCdb Importer to handle RevDate
Change

The new PCdb format contains a change to add the RevDate column in the
Parts.txt file, which would cause the file to fail validation. A change
has been made where **easy setup for Automotive - AutoCare Model (steps
1 & 2) must be re-run** in order to create a new attribute
(AC\_PCdbRevisionDate) and make it valid for object type
ID=AC\_PartTerminology. And the PCdb Importer has been updated to handle
the RevDate column to convert the value to \'ISO Date and Time\' format
= YYYY-MM-DD HH:MM:SS and write the value to the AC\_PCdbRevisionDate
attribute on the imported Part Terminology object.

PRODOC note: RDCUST-2400Corrected handling of VCdb Publication Stage
Date in VCdb Importer

VCdb Publication Stage date was previously written incorrectly,
introducing variances in the seconds. This has been corrected so that
the data is written exactly as provided in the Vehicle table.

PRODOC note: RDCUST-2379Updated application record importers to prevent
import of application records without a valid part type and vehicle /
assembly

Previously, any importers that imported application records had the
potential to create invalid applications as they would import data for
the record even if the part type or vehicle / assembly did not exist.
This has been corrected via addition of a business condition
(ID=ValidateApplication) to the Import state of the relevant workflows.
**Easy setup of the import process for the appropriate standards must be
re-run to enable this** (e.g., Automotive - \[Standard\] Model \> 2.
Configure \[Standard\] Import Process). This prevents any applications
from being imported that do not have both a part type and vehicle /
assembly that exists in the STEP database. When a record is found that
does not meet the condition, an error is written to the execution report
of the import process and the record is not imported.

The business rule can also be found independently under the Automotive
menu when editing a business condition (e.g., Edit Operation \>
Automotive \> Validate Application). The rule has no parameters as it
reads the data to identify the part type and vehicle / assembly objects
from the applicable component model.

PRODOC note: RDCUST-2339Corrected handling of special characters in TAF
files (applicable to TecDoc importers)

Previously TecDoc imports could fail when special characters appeared as
the wrong character set could be selected. This has been corrected by
improving the handling of special characters in these files.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

**to:automotive/7.0/automotive-7.0.4.spr**

Note that the above recipe is compatible only with the STEP 8.2 baseline
(to:step/trailblazer/step-8.2.spr).

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
