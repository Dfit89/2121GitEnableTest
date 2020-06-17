---
description: 'Automotive Solution: PMDM for Automotive 8.2 MP3 September
  2017 Maintenance Patch Notes '
title: PMDM for Automotive 8.2 MP3 September 2017 Maintenance Patch
  Notes
---

PMDM for Automotive 8.2 MP3 Patch Notes {#pmdm-for-automotive-8.2-mp3-patch-notes .MPN}
=======================================

Release Date: September 21, 2017 {#release-date-september-21-2017 .MPN}
--------------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST-2309, RDCUST-2252, RDCUST-2416Updated easy setup of
the Automotive Validation Path attribute to be pre-populated with
validation path data

An attribute with ID=AutomotiveValidationPath was already created as
part of easy setup, but easy setup has now been modified to create the
attribute with a longer maximum length (200) and to be made valid on the
Reference-Type basic object type as both changes are required for full
use of the attribute. Easy setup has also been updated to populate the
validation paths as the value for all attributes and references used to
model vehicle options for application records. *Additional information
on the use of validation paths can be found in the Automotive Reference
Guide.*

Validation paths are only populated when the relevant attributes and
references are first created by easy setup. Therefore, existing
implementations have two options to add validation path data:

1.  Populate the validation paths manually, as described in the
    Automotive Reference Guide.
2.  Delete the relevant attributes and references and run easy setup to
    enable recreation and auto-population of the validation paths
    (System Setup \> Component Models \> Automotive - AutoCare
    Model \> 1. Configure AutoCare Data Model).

In either case, the impacted attributes are those included in the
AutoCare ACES Attributes group that correspond to vehicle options. In
systems where no additional attributes have been added to the group
beyond those created by easy setup, this will equate to all attributes
in the group *except* the three ACES Import Handling attributes, the
ACES Replacement Context attribute, and the Application Note attribute.
The references impacted are the ACES Application to Transmission Base
and ACES Application to Engine Base classification references.

PRODOC note: RDCUST-2376Added a new business rule plugin to move ACES
Applications for PIES Part

A new business rule plugin has been added to be able to **move** ACES
applications from one PIES part to another referenced PIES part. This
rule is a business action found under the **Automotive** menu, called
**Move ACES Applications for PIES Part**. The rule has a single
parameter to select a Reference Type, which is used by the business
action to evaluate which PIES part to execute the applications move from
and to. Note that this rule cannot be used to move applications outside
of the AutoCare model. *More details can be found in the Automotive
Reference Guide.*

PRODOC note: RDCUST-2377Added a new business rule plugin to sync ACES
Applications between PIES Parts

A new business rule plugin has been added to be able to **sync** ACES
applications between two referenced PIES parts. This rule is a business
action found under the **Automotive** menu, called **Sync ACES
Applications between PIES Parts**. The rule has a single parameter to
select a Reference Type, which is used by the business action to
evaluate which PIES items the records should be synced between. Note
that this rule cannot be used to move applications outside of the
AutoCare model. *More details can be found in the Automotive Reference
Guide.*

PRODOC note: RDCUST-2389Added support to include ID or Name as options
for PartNumber in PIES Exporter

Previously, the PIES Exporter only had the option to use \'Attribute
Value\' as the \<PartNumber\> in PIES exports. The PIES Exporter has now
been updated to include ID and Name options as well in the Part Number
Source area. If no selection is made, the value from the Part Number
attribute (ID=AC\_PIES\_ITEMPartNumber) is applied in the \<PartNumber\>
field of the export.

-   Selecting the \'ID\' option inserts the STEP ID of the exported
    object(s) into the \<PartNumber\> field of the exported file.
-   Selecting the \'Name\' option inserts the STEP Name of the exported
    object(s) into the \<PartNumber\> field of the exported file.
-   Selecting the \'Attribute Value\' option inserts the selected
    attribute\'s value of the exported object(s) into the \<PartNumber\>
    field of the exported file.

PRODOC note: RDCUST-2364Added support to PIES Exporter to be able to
export objects (Own parts) other than PIES Items

Previously, the \'AutoCare PIES 6.5 Exporter\' format was hard-coded to
look specifically for object type ID=AC\_PIESItem objects (and child
AC\_PIESPackage and AC\_PIESHazMat if applicable) to include in the PIES
exported file, which prevented users from selecting parts from their own
hierarchy to be included in the exported file. The PIES Exporter has now
been updated to include four new parameters to allow users to select
their own object types to be included in the exported file. If the Own
Model Settings are used, the selected object types must utilize standard
PIES attributes and references as the content that the exporter must
find on the objects has not changed - the parameters allow for users to
select non-standard object types and hierarchies that include the
standard PIES data. If the own model configuration is not used, the
export continues to function as before and no object type selections are
needed when running from a standard PIES hierarchy. More information on
the exporter can be found in the Automotive Quick Start Guide.

![](../../Resources/Images/Exporters/PIES%20Own%20Model.jpg)

PRODOC note: RDCUST-1932Added support to include Part Number Source
options in ACES Exporter

Previously, the ACES Exporter did not have the Part Number Source
options available and would always apply the value from the Part Number
attribute (ID=AC\_PIES\_ITEMPartNumber) on the parental PIES item as the
\<Part\> value in the application record. The ACES Exporter has now been
updated to include ID, Name, and Attribute Value, as part number
selection options. In addition, an option has been added to select any
attribute from the parental PIES part or from the ACES application to be
used as the value in the \<MfrLabel\> field of the application record.

-   Selecting the \'ID\' option inserts the STEP ID of the parental PIES
    part into the \<Part\> field of the exported file.
-   Selecting the \'Name\' option inserts the STEP Name of the parental
    PIES part into the \<Part\> field of the exported file.
-   Selecting the \'Attribute Value\' option inserts the selected
    attribute\'s value from the parental PIES part into the \<Part\>
    field of the exported file.
-   Selecting the \'Use Attribute for Mfr Label\' option inserts the
    selected attribute\'s value from the parental PIES part or the
    exported applications into the \<MfrLabel\> field of the exported
    file.

PRODOC note: RDCUST-2154Added support to export ACES application data in
3.0 format

In order to send data to downstream systems in both ACES 3.0 and 3.2
formats, the AutoCare ACES Application Exporter now has a Version
parameter to select either 3.0 or 3.2 format. The version will default
to 3.2, but if 3.0 is selected, then the exported file will contain the
following:

-   UTF-8 encoding
-   \<ACES version=\"3.0\"\>
-   The ApprovedFor tag in the Header is in the 3.0 format:
    \<ApprovedFor\>DK,US\</ApprovedFor\> *(Note that this tag must be
    removed from the file before importing through ACES Importer so that
    it doesn\'t fail validation against 3.2 XSD.)*
-   The DigitalAsset segment is excluded from ACES 3.0 export. For ACES
    3.2 export, if an application has an asset linked to it, only the
    AssetName will get exported with the application. (The value for
    AssetName comes from attribute ID=AC\_PIES\_ASSTAssetID.) Note that
    ACES standard only supports one asset linked to each application,
    but STEP supports multiple assets linked per application. If more
    than one asset is linked to the application in STEP, only one asset
    is exported (which is randomly selected). An entry is written to the
    execution report of the export for any skipped assets. The asset
    included in an export must be linked to the application record using
    any of these Image and Document Reference Types:
    AC\_ACESApplicationToInstallation,
    AC\_ACESApplicationToOwnersManual,
    AC\_ACESApplicationToPrimaryProductImage,
    AC\_ACESApplicationToProductImage.

PRODOC note: RDCUST-2256Added business action to aid in configuration of
Application Editor display options

A new \'Set Condition Links on Part Types\' business action has been
added, which can be found under the Automotive menu when editing
business action operations. The rule serves to link application
conditions / options to part types to assist in configuring display
options in the Web UI Application Record Editor (application search
screen). When run, the rule will evaluate all selected applications and
identify which conditions are populated on the applications, per part
type. It will then link the attributes or references representing the
conditions to the part types, using standard attribute links or the
Reference Part Type Links metadata attribute as appropriate. Additional
information on the display settings can be found in the Application
Editor section of the Automotive Reference Guide (specifically, the
section titled Controlling Display of Conditions in the Editor).
Additional information on the rule itself can be found in the Business
Rules section of the Automotive Reference Guide.

Bugfixes {#bugfixes .MPNBugFix}
--------

PRODOC note: RDCUST-2310Added Reference Part Type Links attribute to
easy setup

The Reference Part Type Links attribute (ID=ReferencePartTypeLinks) is
used to manage display of application conditions in the Web UI
application record editor. Accordingly, this attribute has been added to
the data model easy setup step of all standards. **Easy setup must be
run to enable this change in both new and existing implementations**
(Automotive - \[Standard\] Model \> 1. Configure \[Standard\] Data
Model). As the attribute was not previously part of easy setup, running
setup will newly create it on both new and existing implementations.

PRODOC note: RDCUST-2392Updated easy setup of the ACES Replacement
Context attribute

An attribute with ID=AC\_ACESReplacementContext was already created as
part of easy setup and placed under attribute group
ID=AC\_ACESAttributes, which would expose the attribute in the
application record editor.

Easy setup has now been modified to create the attribute under attribute
group ID=Metadata. The changes made impact initial easy setup only as
the attribute already exists on existing implementations and will not be
changed by re-running the setup. However, the change should also be put
in place on existing systems as described below.

**Existing implementations should make these changes manually:**

1.  Select the existing AC\_ACESReplacementContext attribute and
    navigate to the \[References\] tab.
2.  Click on the \'Add Attribute Group\' link and select attribute group
    ID=Metadata.
3.  Right-click on the \[\>\] arrow in front of the AC\_ACESAttributes
    attribute group and select \'Remove Attribute Group.\'

PRODOC note: RDCUST-1965Changed ID pattern for PIES Interchange objects

Previously, PIES Interchange objects were created with the ID pattern:
AC\_PIESInterchangeItem\_\[BrandCode\]\_\[PartNumber\], which could
cause some objects to not get created because the ID would pass a
maximum limit of 40 characters. The PIES Importer has been updated to
generate the PIES Interchange ID based on a hash function so that the 40
character limit will not be encountered (e.g.,
AC\_PIESInterchangeItem\_\[hash function\]).

As this changed the algorithm of the PIES Interchange ID generator,
**all previously imported PIES Interchange objects should be deleted and
re-imported to match the new ID generation pattern.**

PRODOC note: RDCUST-2387Updated error reporting for ACES importer to
include the application record ID

Previously, when application records would fail to get created through
the ACES importer, the error report would display the STEP ID of the
object that failed to get created. This STEP ID is not useful as the
user cannot identify the problem record since the record was not created
in STEP. The error messaging has now been improved in ACES importer to
include the application record ID from the input file anytime that an
application record is not created. This will allow users to find the
actual record with the error by going back to the ACES file and
referencing the ID.

PRODOC note: RDCUST-1860Updated Application Condition Header component
names for Application Editor

The Application Condition Header component names have been updated in
Application Editor Search screen for Web UI in order to avoid confusion
for users. The new names are:

-   **Application Condition Header - Individual**: This is used to allow
    table headers to be expanded to display conditions in individual
    columns. Condition attributes that have metadata
    DisplayCondition=true will be displayed in their own column using
    this header. This was previously named the Application Condition
    Group Header.
-   **Application Condition Header - Group**: This is used to group
    multiple conditions into a single column. Attributes that are linked
    on the Part type that the application is referenced to, or
    attributes that are included in the attribute group that is
    configured within the component and that have data for the
    application will be displayed in a single column using this header.
    This was previously named the Application Condition Header.

PRODOC note: RDCUST-2415Updated Application Condition Header component
to display attribute name when there is only one attribute value to
display

Previously, if there was only one attribute value to be displayed in the
Application Condition Header - Group header for the application record,
only the attribute value would be displayed and not the attribute name.
This has been fixed so that the attribute name is displayed along with
the attribute value, regardless of the number of options being
displayed.

PRODOC note: RDCUST-2396Updated AutoCare easy setup for ACES Engine and
Transmission references

Classification Reference Types with ID=AC\_ACESApplicationToEngineBase
and AC\_ACESApplicationToTransmissionBase were already created as part
of easy setup. These references are considered part of the basic
AutoCare application conditions, and much handling of the conditions in
the application editor and other functionalities is dependent on all
criteria (attributes and references) being included in the ACES
Attributes group. Therefore we needed easy setup to create these
references and also link them to the attribute group.

Easy setup has now been updated to link the references under attribute
group ID=AC\_ACESAttributes. The changes made impact initial easy setup
only as the references already exists on existing implementations and
will not be changed by re-running the setup. However, the change should
also be put in place on existing systems as described below.

**Existing implementations should make these changes manually:**

1.  Select the existing AC\_ACESApplicationToEngineBase Classification
    Reference Type and make sure that the \[Reference Type\] tab is
    selected.
2.  Click on the \'Add Attribute Group\' link and select attribute group
    ID=AC\_ACESAttributes.
3.  Repeat steps 1 and 2 for AC\_ACESApplicationToTransmissionBase
    Classification Reference Type.

PRODOC note: RDCUST-2215Fixed PAdb import Execution Report to no longer
display stacktrace errors for non-zipped files

Previously, when a non-zipped file is placed in the PAdb importer, the
log would display a stacktrace error that is not user friendly. The
logging has been improved to now indicate that the \"File is not in a
recognized format or could not be unzipped.\"

PRODOC note: RDCUST-2404Updated easy setup functionality for AutoCare so
that existing objects are not re-set when easy setup is run repeatedly

Previously, if easy setup had been run and the objects created by the
setup had been modified, running easy setup again would wipe out any
manual changes that had been made and would re-set the object to the
initial easy setup state. This has been updated so that easy setup does
not modify existing objects unless the change is to expand on an
existing definition (e.g., increase max attribute length or add an
additional validation type). Changes such as workflow assignees,
business rule parameters, etc are all left intact and unchanged if the
object already exists when setup is run. Note that as part of this
change, the option to modify initial configuration settings when running
setup for the import processes has been removed. Previously running
option 2 of the easy setup for AutoCare would present the user with an
interface to specify IDs of workflows, integration endpoints, etc. These
user-specified options have been removed and all IDs are now included
within the setup code. This change was implemented for the AutoCare
model only at this time, but will be applied to NAPA and TecDoc models
as well in a subsequent patch.

PRODOC note: RDCUST-2398Fixed error in Application Editor Search screen
when creating a Collection

Previously, it was not possible to create a Collection for the
application search results in the Application Editor Search screen
because an error was generated. The error has now been fixed in order to
be able to create a Collection from the Application Editor Search
screen.

PRODOC note: RDCUST-2399Fixed error in Application Editor Search screen
when exporting to Excel

Previously, it was not possible to export the application search results
in the Application Editor Search screen to Excel because an error was
generated. The error has now been fixed in order to be able to export
the application records to Excel. An export configuration needs to be
created to define the attribute and reference values that should be
exported. And then this export configuration will be used in the Export
Action component in Web UI designer to get the application data to
export.

PRODOC note: RDCUST-2407Added support for Compressed View for Qualifiers
in Application Editor Search screen

The compressed view in Application Editor Search screen now works
properly for Qualifiers. The full text of the Qualifier is displayed and
separated by a comma when there are multiple Qualifiers.

PRODOC note: RDCUST-2311Fixed bug in filtering condition values on valid
vehicles in Application Editor to not require that conditions are linked
to a part type

Previously, it was required that condition / options attributes on
application records are linked to the part type in order for valid
values to be filtered correctly. This has been fixed so that it is no
longer required to link the condition / options attributes to the part
type. The attribute value filtering will be done using the validation
path that is defined in the AutomotiveValidationPath attribute so that
users will only see values that are valid for the application to select
from.

PRODOC note: RDCUST-2347Fixed bug in filtering condition values on valid
vehicles in Application Editor when attribute and reference options are
combined

Previously, if an application record has both condition attributes and
reference options, the valid values for the condition attribute would
not be filtered correctly. This has been fixed so that having both the
reference and the attribute options will have the correct valid
attribute value filtering in the same Application Editor.

PRODOC note: RDCUST-2361Fixed NullPointerException error generated in
the Application Editor related to Qualifiers table header

Previously, when searching for missing applications in the Application
Editor Search screen, the Qualifiers table header (ACES Application
Qualifiers component) would cause a NullPointerException error. This has
been corrected so that the NPE error is no longer displayed and the
missing application(s) is displayed in the search results instead.

PRODOC note: RDCUST-2345Added Tool Tip for missing coverage in
Application Editor screen

Currently the missing coverage option in the Web UI Application Editor
can only be selected when both a vehicle and part type selection have
been made and it isn\'t clear to the user that those two parameters are
required to be selected before the checkbox is enabled.

A Tool Tip has been added when hovering over the \'Show missing
applications\' checkbox area to display \"Part type and vehicle
selections are required to enable missing coverage.\"

PRODOC note: RDCUST-2308Corrected a bug in the display of options in the
Application Editor screen

Corrected a bug in the application editor where previously some
conditions modeled using references would display values for selection
from another condition (e.g., a transmission option displaying values
for both transmission and engine) when editing within the value editor.
This has been corrected so that only the selection values for the
particular condition are displayed.

PRODOC note: RDCUST-2375Updated NAPA ID for two object types and one
Classification Reference Type

Previously, easy setup created two NAPA object types with
ID=NAPA\_Option1Root and NAPA\_Option1; and Classification Reference
Type ID=NAPA\_ApplicationToOption1, which doesn\'t conform to other ID
names for NAPA objects and references.

The NAPA object and classification reference type IDs have been updated
to the following:

-   NAPA\_Option1Root \> NAPA\_AxleRoot
-   NAPA\_Option1 \> NAPA\_Axle
-   NAPA\_ApplicationToOption1 \> NAPA\_ApplicationToAxle

**Existing NAPA standard implementations should make the following
changes manually in order to create the new object and classification
reference types with the new IDs:**

1.  In the Tree tab in the Classification Hierarchy under NAPA Reference
    Data \> Vehicle Options \> delete the \'Axles\' folder along with
    all of its children
2.  In the System Setup tab under Reference Types \> Classification
    Reference Types \> delete the \'NAPA Application To Axle\' reference
3.  In the System Setup tab under Reference Types \> Classification
    Reference Types \> delete the \'NAPA Vehicle To Axle\' reference
4.  In the System Setup tab under Object Types & Structures \> Alternate
    Classifications \> NAPA Root \> NAPA Vehicle Option Root \> delete
    both the NAPA Axles and NAPA Axle object types
5.  In the System Setup tab under Component Models \> Automotive - NAPA
    Model \> right-click and run step 1. Configure NAPA Data Model in
    order to recreate the object and classification types with the new
    IDs
6.  Re-import vehicle options so that they are assigned the new object
    types

PRODOC note: RDCUST-2353Updated easy setup for DisplaySequence and
DisplayCondition attributes

Previously, the Display Sequence and Display Condition attributes were
created improperly through easy setup in the \'TecDoc\' attribute group.
As these attributes are general metadata that is needed by all
standards, easy setup has been updated to create attributes
ID=DisplaySequence and DisplayCondition under attribute group
ID=Metadata if the attributes don\'t already exist when running step 1
to configure any \[Standard\] Data Model.

Running easy setup for Component Models \> Automotive - TecDoc Model \>
1. Configure TecDoc Data Model will in addition create attribute
ID=Display\_Sequence as this attribute is heavily used for the TecDoc
solution.

PRODOC note: RDCUST-2419Fixed condition being displayed incorrectly in
Application Editor

Previously, if a condition (attribute) was linked to two part types and
part type A had DisplayCondition=true and part type B had
DisplayCondtion=false, then the application for part type B would still
show the condition in its own column. This has been fixed so that
conditions will only show in their own column if DisplayCondition=true
on the attribute that is linked to the part type of the application,
regardless of how many part types the condition is linked to.

PRODOC note: RDCUST-2373Remove TecDoc Impact Reports from easy setup

Previously the TecDoc import workflows (TecDoc Reference Import + TecDoc
Supplier Import) included an Impact Report state and associated business
rules. The impact reports had some known issues that caused them to be
unreliable and were intended as samples only. As they are not fully
supported, they have been removed from easy setup so as not to cause
confusion.

PRODOC note: RDCUST-2426Fixed easy setup to set AutoCare ACES and VCdb
LOVs to have maximum length of 100

Previously running easy setup or VCdb Import would change the maximum
length for AutoCare ACES and VCdb LOVs (e.g., AC\_Aspiration,
AC\_BedLength, etc.) to be \'50\' or \'60,\' with the max lengths from
easy setup and the importer being in conflict and periodically changing.
Easy setup and VCdb import settings have now been aligned so that the
maximum length for the LOVs are set to and remains as \'100.\'

PRODOC note: RDCUST-2434Fixed easy setup to make AC\_QdbVersionDate
attribute valid only on Qualifiers (Qdb) root node

Previously easy setup would create AC\_QdbVersionDate attribute and make
it valid for both Qualifiers and Qualifiers (Qdb) root node. Easy setup
has been fixed to make AC\_QdbVersionDate attribute valid only on the
Qualifiers (Qdb) root node, as this is the only place where the data is
applicable.

PRODOC note: RDCUST-2112Updated PAdb Importer to no longer set a Minimum
Value on attributes that are created by the import

The PAdb importer has been updated to no longer set a Minimum Value on
attributes that are created by the import. \'Number\' validated PAdb
attributes that previously had a Minimum Value = 0 is now null after the
fix. The Minimum Value for \'Text\' and \'List Of Values\' attributes
stayed the same as it did before with a value of \'N/A.\'

For existing implementations to see this change, import the latest PAdb
file and the Minimum Value will get updated on the attributes.

PRODOC note: RDCUST-2342Updated Qdb Importer to write WhenModified data
from the Qualifier.txt file

The Qualifier.txt file of the Qdb includes a WhenModified value for each
qualifier, which was recently added to the format. The modified date was
being written properly to the attribute with ID = AC\_QdbModifiedDate
when new qualifiers were created, but was not being updated on existing
qualifiers (and as it was a newly added field to the Qdb, existing
implementations would have many existing qualifiers without the value).
This has been corrected so that the data is written appropriately on
both new and existing qualifiers.

PRODOC note: RDCUST-2425Fixed Application Editor where type ahead for an
assembly / vehicle that is not a number no longer generates a
NumberFormatException error

Previously in the Application Editor Search results, if a user tries to
modify the assembly /vehicle on an application by entering a non-number
in the typeahead, a java.lang.NumberFormatException error would be
displayed when the user clicks outside of the assembly column. This has
been fixed where the error is no longer displayed.

PRODOC note: RDCUST-2431Added visibility for invalid conditions in the
Application Editor value editor for Macs

An invalid option selection occurs when a vehicle option is valid for
the selected vehicle, but considered invalid due to other selections.
For example, a vehicle could have 2 doors or 4 doors, but the 2 door
option is only available with a Coupe body style, and the 4 door option
is only available with a Sedan body style. So if Sedan is selected, the
2 door option is considered invalid. On a PC, these invalid options are
displayed in the value editor of the application editor as dimmed in
color and in italics. However, there was no visible difference between
valid and invalid options on a Mac. As standard styling options are not
rendered properly on a Mac, a prefix of 3 dashes (\-\--) is used to
distinguish invalid options from valid ones (which have no prefix). This
change applies to Mac users only and PC users will continue to see the
dimmed and italicized invalid options as they have previously.

PRODOC note: RDCUST-2352, 2422Updated missing coverage functionality in
Application Editor

Previously, the application editor did not properly identify missing
application records and would produce unexpected results, including not
displaying valid options for which coverage is missing. This has been
corrected by adjusting the behavior so that the query looks for the
options populated on the existing records to determine which options
need to be taken into account for determining missing coverage, and
displaying them correctly on the missing records. For example, consider
a vehicle that exists with 2 options for engine. When searching for
missing coverage on that vehicle, if an application exists with no value
populated for the engine and no other options populated, then no missing
records are identified as the unpopulated record is considered to work
for both available engines. If a record exists with one engine populated
and no record exists for the other engine, a missing record is generated
and pre-populated with the second engine. If there is no existing record
for the vehicle and part type combination, a single missing record is
generated with no options populated.

PRODOC note: RDCUST-1963Corrected the population of STEP Name and ID for
ACES and PIES Controller objects

Previously, controller entities for ACES and PIES imports were created
without STEP Names. This has been corrected so that a name is now
applied to these objects when they are created. This change is
applicable to both new and existing implementations as all will observe
the STEP Name applied when the relevant importer creates the controller
entity.

The ID for controller entity objects is the same as the STEP Name, but
with a prefix applied. The prefix can be manually adjusted in the
relevant inbound integration endpoints (IIEPs) using the ID Prefix
parameter in step 5.1 of the IIEP wizard. Easy setup previously created
the IIEPs with an \'application\_\' or \'pies\_\' prefix, as
appropriate. Easy setup has been updated to now create the endpoints
with \'AC\_ACES\' and \'AC\_PIES\' prefixes, to be aligned with other
AutoCare objects in the system. This change will only be in effect for
new implementations running initial setup, but existing implementations
can change their ID structure if desired by manually adjusting the ID
Prefix parameter in the IIEPs.

PRODOC note: RDCUST-2241Updated AutoCare easy setup to create PAdb units

Running easy setup for Component Models \> Automotive - AutoCare Model
\> 1. Configure AutoCare Data Model will now create units that are
needed for PAdb attributes along with setting the metadata for
AC\_PAdb\_UOMCode, AC\_PAdb\_UOMDescription, and AC\_PAdb\_UOMLabel on
those attributes.

PRODOC note: RDCUST-2242Updated how units are matched through PAdb
Importer

Previously, the PAdb Importer looks at the MetaUOMCodes.txt subfile in
the imported zip file and tries to match the value that is in the
UOMCode column to the value for attribute ID=AC\_PAdb\_UOMLabel on an
existing STEP unit of measure. This method did not find many matches
because the UoM Label is often different than the UoM Code.

PAdb Importer has been updated to match the UOMCode value in the
MetaUOMCodes.txt subfile to the metadata that is stored in attribute
ID=AC\_PAdb\_UOMCode on the unit in order to find more matches.

PRODOC note: RDCUST-2243Fixed PAdb import Execution Report to indicate
UoM that can\'t be matched

Previously, if a unit from the MetaUOMCodes.txt file could not be
matched to an existing STEP unit, the Execution Report did not indicate
that the UoM did not exist. The logging has been improved to now
indicate that \"The unit \'ID\_of\_Missing\_UoM\' couldn\'t be created
as the unit group is unknown.\"

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

**to:automotive/7.0/automotive-7.0.5.spr**

Note that the above recipe is compatible only with the first maintenance
patch for the STEP 8.2 core baseline release
(to:step/trailblazer/step-8.2-mp1.spr).

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
