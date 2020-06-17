---
description: 'Automotive Solution: PMDM for Automotive 9.0 MP3 Patch
  Notes'
title: PMDM for Automotive 9.0 MP3 December 2018 Patch Notes
---

PMDM for Automotive 9.0 MP3 Patch Notes {#pmdm-for-automotive-9.0-mp3-patch-notes .MPN}
=======================================

Release Date: December 20, 2018 {#release-date-december-20-2018 style="text-align: center;"}
-------------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: MEDU PDO- 1464 New Data Onboarding solution

Within the automotive industry, it is often difficult to organize how
different parts and their information are used across different vehicles
and/or assemblies. This is especially true when trying to organize
supplier and/or competitor parts data across different automotive
standards and data models. The Data Onboarding solution helps to
streamline the process of importing supplier data and accepting it (or
automatically mapping it) into Standard and/or OWN data models.

Mapper is a functionality used in the Data Onboarding solution to move
the data from one STEP object to another STEP object. The Mapper can
also be used to move data from any Standard data model to their OWN data
model (typically used by suppliers) or to move data from the OWN data
model to any Standard data model (typically used by manufacturers).

The actual data mapping is executed via business rules (inside a
workflow or upon approvals) and/or through background processes (by
adding an extra state after the \'Import\' state in the import
workflow). After initial configuration, Web UI users can view, edit, and
create mappings to better handle the automation of data onboarding.

The Data Onboarding Automation solution can be used within an Onboarding
Mappings Detail Screen via the following plugins:

-   Attribute Mapping: Sets up mapping of attributes (with
    'Transformation' if needed) from a format into their OWN data model
    or vice versa.
-   Application Mapping: Sets up mapping of Applications from a standard
    data model into their OWN data model or vice versa.
-   Business Action Mapping
-   Object to Object Mapping: Sets up mapping of objects from a standard
    data model into their OWN data model or vice versa. The object
    mapping can create data on the target in the following ways.
-   As referenced object
-   As child object
-   Directly on the target object

PRODOC note: BOND RDCUST- 3221 and RDCUST- 3223New \'Country Handling
Value\' component and \'Application Country Handling Table Header\'
component allows inclusion of all countries by default

The new parameter \'Included By Default\' provides the user an option to
include all countries by default within the \'Country Handling Value\'
and \'Application Country Handling Table Header\' component. Previously,
it was a tedious process to add all the required countries into the
Country Inclusion list when there were more countries to be included
than excluded. Now, with the \'Included By Default\' parameter selected,
a user edits the applicable objects by deselecting the excluded
countries if required. For more information, see the Configuring Country
Handling Value Component ([here]{.mcFormatColor style="color: Blue;"})
and Configuring Application Country Handling Table Header
([here]{.mcFormatColor style="color: Blue;"}) topics in the Automotive
Reference Guide.

PRODOC note: BOND RDCUST- 3223Implemented new \'Reference Country
Handling Table Header\' component to select Country Inclusion /
Exclusion Handling for a Product Reference Type

A new component \'Reference Country Handling Table Header\' allows the
user to provide a Country Handling solution for a Product Reference
Type. The component can be configured as a header component in the
Application Manager screen and in the Node Editor component. For more
information, see the Country Handling Solution section of Automotive
Reference Guide[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: BOND RDCUST- 3084New \'Advanced Part Number References\'
and \'Advanced Part Number Suggestions\' components to display
referenced part numbers and suggested part numbers in Node Editor
component

New components \'Advanced Part Number References\' and \'Advanced Part
Number Suggestions\' are the extended features of \'Part Number
References\' and \'Part Number Suggestions\' allowing users to add /
delete / modify the Competitor Numbers / OE Numbers while still standing
on the Part object. These components include the same functionality as
the Node List component. For example, sorting by specific columns,
adding / removing one or more rows, switching the display modes, etc.
The components are useful when configured as new rows in OE Screen or
Competitor Screen. For more information, see the Competitor and OE
Numbers Solution section of Automotive Reference Guide[
here]{.mcFormatColor style="color: Blue;"}.

### AutoCare

PRODOC note: MEDU RDCUST- 3252 New ACES Exporter parameter allows
exclusion of BrandAAIAID

A new optional parameter (Include BrandAAIAID in Part) added to the
ACES Exporter allows for the exclusion of the BrandAAIAID. For more
information, see the AutoCare ACES Application Exporter topic in the
Automotive Reference Guide[ here]{.mcFormatColor style="color: Blue;"}.

This optional parameter is not available as a hotfix. However, the
ACES Exporter can be updated to always exclude the BrandAAIAID from the
part via the following hotfix that is available for STEP 8.2 MP3 +
Automotive 8.2 MP4:[
to:hotfix/328/issue-328558-HOTFIX-2766.spr]{.commandfont}

PRODOC note: RDCUST- 3109 Improved ACES and PIES exporter ZIP file names
within BGP Details screen

The ACES and PIES exporters now provide improved ZIP file names within
the Background Process (BGP) Details screen. Now, when an ACES or PIES
export is run, the ZIP file name is created using the following
template: \'Company Value\_Document Title Value\_current date\_FULL\'.
The Company and Document Title values are supplied via the \'Select
Format\' step of the AutoCare ACES Application Exporter.

In the screenshot below, the AutoCare ACES Application Exporter is
displayed with the \'Company\' and \'Document Title\' parameters
outlined in red. The values configured for these required parameters
help determine the ZIP file name displayed within a BGP Details screen.
Looking at the example below being exported on 31 October 2018, the ZIP
file name would display in the BGP Details screen as \'ACME\_BrandAAIAID
in Part\_2018-10-31\_FULL.zip\'.

![](../../Resources/Images/MPNotes/ACESExporter.png)

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/328/issue-328558-HOTFIX-2766.spr]{.commandfont}

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: MEDU RDCUST- 3072 Corrected Application Manager Saved
search tool functionality

Corrected the Saved search tool functionality so that both the Make and
Model criteria are now displayed within the Make / Model search box.

**Existing Implementations:** To avoid an error when patching, follow
the steps below:

1.  Have each user go to their Application Manager\'s Saved search
    functionality and make note of their search criteria for saved
    searches that contain Make / Model criteria.
2.  Delete the saved searches.
3.  Apply the patch.
4.  Recreate the deleted searches.

For more information, see the Saved Search Tool topic within the
Automotive Reference Guide[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: RDCUST- 3272 Corrected exception error during Easy Setup
action

Corrected an exception method error (NoSuchMethod) that displayed when
using the \'Configure \[standard\] Import Process\' Easy Setup action.

PRODOC note: MEDU RDCUST- 2935 Corrected Application Manager Results
Table filter

Corrected the Application Manager Results Table column header filter so
that the options added to the search boxes are considered and only valid
selections display within the filter dropdown.

PRODOC note: MEDU RDCUST- 3215 Corrected Application Condition Header\'s
Value editor display

Corrected the Application Condition Header component so that users can
no longer type in values, but must select a value from the dropdown.

PRODOC note: MEDU RDCUST- 3220 Updated the Application Country Handling
Table Header \'Exclude Attribute\' parameter

Updated the Application Country Handling Table Header \'Exclude
Attribute\' parameter to no longer be mandatory.

PRODOC note: BOND RDCUST- 3273Corrected Year search box dropdown results

Corrected the Year search box dropdown results within the Application
Manager screen so that when text is typed into the typeahead field, any
results that start with the supplied text are displayed.

PRODOC note: BOND RDCUST- 3237Corrected Part Number References component
to only display Part Number of same Part Type in the typeahead field

Corrected the Part Number References component within the OE Number /
Competitor Number Node Editor screen so that when text is typed in the
typeahead field, only results that belongs to the Part Type of the
selected Part are displayed.

PRODOC note: BOND RDCUST-3249Updated the Vehicle Type Search Panel in
Application Manager screen

Added the ability to configure a separate Node List for each Vehicle
Type Search Panel in Application Manager screen. Previously, it was not
possible to define an unique Node List for each search panel. Now, the
user has the flexibility to either configure each Vehicle Type Search
Panel with its own Node List or to configure a default Node List by
selecting the newly created parameter \'Default Node List\' in the
\'Application Manager Screen Properties\' component.

PRODOC note: BOND RDCUST-3236Added a new parameter \'Application Scope
Value\' to control the default setting of missing application coverage
functionality

Added a parameter \'Application Scope Value\' with the ability to
control the default setting of application coverage functionality in
Application Manager screen. Within this parameter in \'Application
Manager Screen Properties,\' users can configure to set values between
\'Existing Applications Only,\' \'Existing and Missing Applications,\'
or \'Missing Applications,\' which reflects as default values in
Application Manager screen. Though the default is set, the user still
has an option to manually choose from the options in Application Manager
screen. For more information see the Missing Application Coverage
Functionality topic[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: RDCUST- 3228 Corrected exception error in Application
Manager

Corrected an exception method error (RuntimeException) that displayed
when a user with restricted access (View / Edit) to any application is
trying to access the application in \'Application Manager screen.\'

PRODOC note: RDCUST- 3316 Corrected the Options search boxes in
Application Manager screen to display accurate results

Previously, when users searched for a pre-configured attribute and/or
reference type in the Options search boxes, some undesired results were
displayed in the results table. This happened because the LOV based
attributes were searched by ID and not by the value. Now, the search
results include LOV values thereby giving users accurate search results.

### AutoCare

PRODOC note: RDCUST- 2829Corrected AutoCare Easy Setup action

Corrected the need to run the \'1. Configure AutoCare Data Model\' Easy
Setup action more than once.

PRODOC note: MEDU RDCUST- 3219 Corrected ACES importer Delta calculation

Corrected Delta calculation in ACES importer so that the
\'deleteFile.xml\' file will only contain records that have the delete
status attribute populated with \'true.\'

PRODOC note: MEDU RDCUST- 3254Corrected effective date parameters for
ACES and PIES exporters

Previously, the \'Effective Date\' parameter within the ACES exporter
and the \'Blanket Effective Date\' parameter within the PIES exporter
were required. When the parameters were populated with a date value, and
then a saved configuration was used to run the export, the same date
values would display each time. Now, the parameters can be left blank,
and when a saved configuration is used, the dates will be generated from
when the export is scheduled to run.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/328/issue-328558-HOTFIX-2766.spr]{.commandfont}

**Existing Implementations:** [For this change to take effect, after
applying the hotfix, a user must access existing ACES and/or PIES export
configurations and remove the \'Effective Date\' or \'Blanket Effective
Date\' values prior to re-saving.]{style="font-weight: normal;"}

PRODOC note: MEDU RDCUST- 3312 Corrected MfrLabel parameter for ACES
exporter

Corrected an issue where the MfrLabel value was erroneously added to
applications within the exported data.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/330/issue-330477-HOTFIX-2808.spr]{.commandfont}

PRODOC note: MEDU RDCUST- 3191Corrected PIES export of supersession
parts

Corrected an issue where parts that were used in a supersession
reference and included in the PIES export collection were ignored and
not displayed within the export results. Now, referenced objects are not
exported unless the referenced objects have been specifically selected
to be included in the export.

The expected results after applying the hotfix are:

-   If Part A has supersession references to Part B and Part C, and
    during the PIES Export only Part A is selected for export, then the
    ItemCount = 1 in the exported file to include only Part A.
-   If Part A has supersession references to Part B and Part C, and
    during the PIES Export Part A, Part B, and Part C are selected for
    export, then the ItemCount = 3 in the exported file to include Part
    A, Part B, and Part C.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/330/issue-330182-HOTFIX-2801.spr]{.commandfont}

PRODOC note: BOND RDCUST- 3321Corrected PIES export of attributes within
multiple attribute groups

Corrected the PIES exporter so that attributes within multiple attribute
groups are properly exported.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/331/issue-331652-HOTFIX-2836.spr]{.commandfont}

PRODOC note: BOND RDCUST-3334Improved PIES exporter to export PAdb
attributes prefixed with \'PAdb\_\' along with \'AC\_PAdb\_\'

The PIES exporter now lets users export PAdb attributes prefixed with
both \'AC\_PAdb\_\' and \'PAdb\_\'. PAdb attributes are exported with
PADBAttribute=\"Y\" whenever the \'Part Terminology Attributes\'
parameter is selected in the \'Advanced\' step of the PIES Exporter
Manager.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/333/issue-333373-HOTFIX-2871.spr]{.commandfont}

PRODOC note: BOND RDCUST-3336Corrected PIES Importer \'context\' method

Previously, when the \'Delta calculation method\' parameter in PIES
import workflow was set to \'context,\' and a PIES file included the
attributes that did not exist in STEP, the import validation failed.
Now, the importer will create the new attributes, so that the importer
can complete successfully.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/333/issue-333177-HOTFIX-2864.spr]{.commandfont}

PRODOC note: BOND RDCUST- 3338 Updated Brand Owner DUNS / GLN parameter
in PIES exporter

The PIES exporter no longer requires users to enter a value in \'Brand
Owner DUNS\' and/or \'Brand Owner GLN\' parameters. Since these
parameters are optional, the \'Next\' button is active even if no values
exist. For more information, see the AutoCare PIES 6.5 Exporter topic in
the Automotive Reference Guide[ here]{.mcFormatColor
style="color: Blue;"}.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/333/issue-333181-HOTFIX-2865.spr]{.commandfont}

PRODOC note: BOND RDCUST- 3335 Updated the Conversion state in ACES
importer to include Engine Base / Transmission Base check

The ACES importer now checks the existence of Engine Base / Transmission
Base in STEP if the same Engine Base ID or Transmission Base ID is
listed in the ACES file. The Conversion state writes error messages in
the Execution Report listing the applications for which the Engine Base
/ Transmission Base is not found. The orphan applications are omitted
from the STEPXML file generated, and are not created when the file is
imported.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/333/issue-333215-HOTFIX-2866.spr]{.commandfont}

PRODOC note: BOND RDCUST- 3274 Corrected an empty \'Make\' attribute
value in \'Application Competitor and OE Part Numbers\' component

Previously, if an attribute was set to display Make / Manufacturer name
in the \'Application Competitor and OE Part Numbers\' component, the
empty cells displayed a \'null\' value. Now, the empty \'Make\'
attribute cells display empty.

### TecDoc

PRODOC note: MEDU RDCUST- 3302Added handling of Multi Valued attributes

Added the ability to read multi valued attribute data from TecDoc
importers. Now, STEP checks for issues with multi valued attribute data
and reports them as a Warning within a Background Process Report. This
allows for the Multi Valued Attribute Validation of a STEP attribute to
be manually changed, and the next import of the values from Supplier
data can be completed successfully.

PRODOC note: This hotfix is being applied to the latest release, so not
necessary to mention the hotfix.

PRODOC note: MEDU RDCUST- 3275Corrected PartsLists ID generation

Corrected the generation of PartsLists IDs so they use the following
pattern: \<supplierNr\>PL\<artNr\_hash\>

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/329/issue-329699-HOTFIX-2790.spr]{.commandfont}

**Existing Implementations:** [All previously created PartsLists that
used the same ID generation pattern as Articles must be deleted and then
recreated using the new ID while importing supplier
data.]{style="font-weight: normal;"}

PRODOC note: MEDU RDCUST- 3275Corrected TD\_AccessoryListToManufacturer
Link Type validity

Updated Easy Setup actions to set the validity for
\'TD\_AccessoryListToManufacturer\' Link Type to include LCV and CV.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/329/issue-329699-HOTFIX-2790.spr]{.commandfont}

**Existing Implementations:** [The changes must be completed manually,
as the actions are too small for Easy Setup to properly recognize their
need. ]{style="font-weight: normal;"}

PRODOC note: BOND RDCUST- 3275Corrected STEPXML Tag in Conversion State

Corrected an error that would occur while importing TecDoc Supplier Data
file (Error: ReferenceType with ID \'TD\_AccessoryListToManufacturer\'
for classification references not found). Now, while importing the
Supplier Data file, STEP will consider
\'TD\_AccessoryListToManufacturer\' Link Type as STEPXML tag
\<ClassificationReference\> instead of \<ClassificationCrossReference\>.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/329/issue-329699-HOTFIX-2790.spr]{.commandfont}

PRODOC note: BOND RDCUST- 3213Corrected TAF import error

Corrected an error that would occur in the Conversion state when the
\'Generic article filter\' parameter was used. Now, with the \'Generic
article filter\' parameter selected, STEP continues the import even if
it does not find the GA filter entries (in Data Table 222) in the
Supplier Data file.

PRODOC note: This hotfix is being applied to the latest release, so not
necessary to mention the hotfix.

PRODOC note: BOND RDCUST- 3323Implemented single-update mode for
\'04\_LOVDefinitions.xml\'

Corrected an error that could occur while importing
\'04\_LOVDefinitions.xml\' (a STEPXML file generated during Conversion
state). Now, when the \'04\_LOVDefinitions.xml\' file is imported into
the system, STEP enters into single-update mode. For more information,
see the Single-Update Mode topic within STEP Online Help[
here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: BOND RDCUST- 3396Corrected TAF import error

Corrected an error in Conversion state that would occur while importing
TecDoc Supplier Data file. Previously, creating
\'59\_ProductCrossReferencesFrom402and432\_FOR\_TAF\_400-Number.xml\'
file in Conversion state was wrongly creating references to \'Text
Blocks\' object in product hierarchy.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/335/issue-335110-HOTFIX-2912.spr]{.commandfont}

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

Automotive Quick Start Guide

The Automotive Quick Start Guide ([here]{.mcFormatColor
style="color: Blue;"}) contains introductory information for all
automotive solution users.

PRODOC note: PRODOC- 1251, 1252 Improved ACES and PIES Exporter topics

The following ACES and PIES exporters topics have been improved:
AutoCare ACES Application Exporter ([here]{.mcFormatColor
style="color: Blue;"}), AutoCare PIES 6.5 Exporter
([here]{.mcFormatColor style="color: Blue;"}).

PRODOC note: PRODOC- 1341 Improved the Application Editor and Manager
screens documentation

Multiple screens are created when Easy Setup actions are used. Although
the screen types have similar names, the functionality is very
different. See the newly updated Accessing Application Editor and
Manager Screens topic within the Automotive Quick Start Guide[
here]{.mcFormatColor style="color: Blue;"}.

Conversion State topic update

The Conversion State topic within the Automotive Reference Guide
([here]{.mcFormatColor style="color: Blue;"}) now includes more details
about the options available based on the selected Background Process
Services.

PRODOC note: PRODOC- 1290, 1291 New Error Handling instructions for
TecDoc Reference Data imports

Importing TecDoc Reference data can result in many \'acceptable\' error
messages. More topics have been added to the TecDoc Reference Data
Importer Error Handling section to provide assistance in handling the
errors that occur. See the Error Handling for Reference Data Imports
section of the Automotive Reference Guide[ here]{.mcFormatColor
style="color: Blue;"}.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.14.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible only with the following STEP 9.0 MP5
baseline recipe:

[to:step/trailblazer/step-9.0-mp5.spr]{.commandfont}

**PRODOC note: MEDU PRODOC- 1572** Once an Automotive add-on is
installed to a base STEP system, the base system cannot be upgraded
without upgrading the Automotive add-on at the same time. Additionally,
when upgrading any base STEP system that has any Automotive add-on
installed, both install recipes must be prepared at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
