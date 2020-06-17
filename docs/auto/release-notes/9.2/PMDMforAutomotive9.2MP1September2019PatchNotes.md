---
description: 'Automotive Solution: PMDM for Automotive 9.2 MP1 September
  2019 Patch Notes'
title: PMDM for Automotive 9.2 MP1 September 2019 Patch Notes
---

PMDM for Automotive 9.2 MP1 Patch Notes {#pmdm-for-automotive-9.2-mp1-patch-notes .MPN}
=======================================

Release Date: September 27, 2019 {#release-date-september-27-2019 style="text-align: center;"}
--------------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: BOND RDCUST 1941Added support to handle Market Copy during
PIES import, export, and Easy Setup

Market Copy is the segment in the PIES file that contains marketing
information. The Market Copy segment is provided in the PIES file and
brought into STEP via the PIES Importer. Previously, the PIES Importer
and Exporter did not handle the Market Copy segment in any way within
the STEP AutoCare data model.

To handle Market Copy for PIES import and export, Easy Setup for the
Automotive - AutoCare Model (steps 1 & 2) must be re-run to:

-   Create the following new object types:
-   PIES Marketing Copy (ID = AC\_PIESMarketingCopy)
-   PIES Market Copy Code (ID = AC\_PIESMarketCopyCode)
-   PIES Market Copy Reference (ID = AC\_PIESMarketCopyReference)
-   PIES Market Copy (ID = AC\_PIESMarketCopy)

![](../../Resources/Images/Release%20Notes/9.2MP1/8.png)

-   Create a new product object called PIES Marketing Copy (ID =
    AC\_PIESMarketingCopy).

![](../../Resources/Images/Release%20Notes/9.2MP1/13.png)

-   Create a new Asset Root classification called PIES Market Copy
    Assets (ID = AC\_PIESMarketingCopyAssetRoot) using the object type
    \'AC\_AssetRoot.\'

![](../../Resources/Images/Release%20Notes/9.2MP1/10.png)

-   Create a new attribute group called PIES Market Copy Segment MKTC
    (ID = AC\_PIESMarketCopySegmentMKTC).

![](../../Resources/Images/Release%20Notes/9.2MP1/9.png)

-   Create seven new Description attributes that are valid for
    AC\_PIESMarketCopy object type:

1.  PIES Market Copy Code (ID = AC\_PIES\_MKTC\_Code)
2.  PIES Market Copy Code Reference (ID = AC\_PIES\_MKTC\_CodeReference)
3.  PIES Market Copy Content (ID = AC\_PIES\_MKTC\_Copy)
4.  PIES Market Copy Record Sequence (ID =
    AC\_PIES\_MKTC\_RecordSequence)
5.  PIES Market Copy Sub Code (ID = AC\_PIES\_MKTC\_SubCode)
6.  PIES Market Copy Sub Code Reference (ID =
    AC\_PIES\_MKTC\_SubCodeReference)
7.  PIES Market Copy Type (ID = AC\_PIES\_MKTC\_Type)

-   Create two new LOVs called AC\_MarketCopyCode and AC\_MarketCopyType
-   Create a new Product Reference Type called AC\_PIEStoMarketCopy that
    is valid from AC\_PIESBrand and AC\_PIESPCdbPartTerminology object
    types to AC\_PIESMarketCopy target object type
-   Add AC\_PIESMarketCopy as a valid source type for all PIES asset
    references

The PIES importer has been updated to:

-   Create new objects for Market Copy and establish a reference to
    Digital asset and from objects in the product hierarchy. Market Copy
    Code PGC, PSG, BRD, BPR, BOW, SBR, and PCC will be referenced from
    the PIES Brand (AC\_PIESBrand) product object level. And Market Copy
    Code PTI will be referenced form the PIES PCdb Part Terminology
    (AC\_PIESPCdbPartTerminology) product object level.

![](../../Resources/Images/Release%20Notes/9.2MP1/14.png)

-   Handle Market Copy assets

The PIES Exporter has been updated to export Market Copy and Digital
assets within the \<MarketingCopy\> segment.

PIES Exporter has a new parameter called \'Market Copy\' to select for
whether to include or exclude the Market Copy segment.

![](../../Resources/Images/Release%20Notes/9.2MP1/12.png)

PRODOC note: RDCUST-3054Added option to exclude certain attributes and /
or references from the PIES Export

Previously, the \'AutoCare PIES Exporter\' format was hard-coded to
include all attributes / attribute groups related to the PIES Item in
the PIES exported file, which prevented users from selecting attributes
from the PIES Item to be included / excluded in the exported file. The
PIES Exporter has now been updated to include a new parameter \'Exclude
Attribute Group\' to allow users to select the attribute groups to be
excluded in the exported file. The \'Exclude Attribute Group\' parameter
is available within the \'Advanced\' tab of the Export Manager. The
parameter allows users to select attribute groups that can be excluded
from being exported. If no attribute group(s) is defined in the
parameter, the export continues to function as before and no attribute
groups will be excluded from export.

This parameter is available in all the versions of the PIES export. To
add the attributes / references in the exclusion list, users will need
to manually create a new attribute group and link attributes and / or
references to that attribute group that they want to exclude from the
PIES export before defining that attribute group in the \'Exclude
Attribute Group\' parameter.

Following are the features of this parameter:

-   The new parameter allows multi attribute group selection. If more
    than one attribute group need to be excluded from the export, users
    can define more than one attribute group in the parameter.
-   This new functionality also handles references that are added to the
    attribute group. If a reference is added to the attribute group that
    is selected to be excluded, then the attributes and references that
    are in the selected attribute group are excluded from the PIES
    export.
-   It also handles data containers.

At present, following are the limitations of this parameter that will be
implemented in a future release:

-   Excluding PIES Asset references is currently not supported.
-   This new feature DOES NOT support excluding specific Description
    Type within Data Containers or specific Asset Types within PIES
    Asset references. For example, If the user wants to only export
    Features and Benefits and Label Description types, but exclude all
    other Description types, then the user will not be able to do that.
-   If the user wants to specify that certain Asset Types such as
    Primary Photo (P04) and User Defined (ZZ1-ZZ9) should be exported,
    but exclude all other Asset Types, then the user will not be able to
    do that either. This will be implemented in a future release.

![](../../Resources/Images/Release%20Notes/9.2MP1/2019-09-24_12-42-23.png)

PRODOC note: RDCUST-3816New config property
Automotive.Aces.IgnoreSupplier to ignore the supplier information
populated in the Replacement Context attribute during the ACES file
import

To improve the performance of the Delta Calculation in the ACES
Importer, the \'context\' method of the Delta calculation can now be
configured to ignore the supplier information populated in the
Replacement Context attribute during the ACES import. There is a new
config property, **Automotive.Aces.IgnoreSupplier**, which is set to
false by default to always check the supplier information (meaning it
will include to populate the supplier information along with other
information in the Replacement Context attribute). If it is set to true,
then the supplier information is not checked in the ACES file import and
the attribute called Replacement Context (AC\_ACESReplacementContext)
will have a value populated that ignores the supplier information. In
the example below, \'ACES-Supplier0934-DKGX-30489-5696-JK36004\' is the
attribute value populated in the Replacement Context attribute that
includes \'Supplier0934\' as the supplier information. If the config
property **Automotive.Aces.IgnoreSupplier** is set to true, then the
import of ACES file will populate the Replacement Context attribute by
value \'ACES-DKGX-30489-5696-JK36004\' (meaning, it will not populate
the supplier information \'Supplier0934-\' in the Replacement Context
attribute).

![](../../Resources/Images/Release%20Notes/9.2MP1/3.png)

This solution is also available for STEP-8.2-mp3 via a hotfix.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/374/issue-374695-HOTFIX-3488.spr]{.commandfont}

**Existing Implementations:** For this change to take effect, after
applying the hotfix, the user must do the following:

1.  Add the new property to sharedconfig.properties file:
    Automotive.Aces.IgnoreSupplier=true
2.  Update the AC\_ACESReplacementContext attribute value in all
    existing applications to have the supplier information removed from
    the value. This can be done by creating a JavaScript action with
    JavaScript such as:

``` {.PreIndent space="preserve"}
var split = currentContext.split("-");
if (split.length != 6) {
    //throw some errors ....
}
var res = split[0]+"-"+split[2]+"-"+split[3]+"-"+split[4]+"-"+split[5];
node.setSimpleValue(contextAttr,res);
```

The above JavaScript uses the following three binds:

-   node = current object
-   currentContext = attribute value (AC\_ACESReplacementContext)
-   contextAttr = attribute (AC\_ACESReplacementContext)

Additionally, also consider whether to set the import delta context to
work on Brand or Part Terminology. For example, if you know that a
supplier will always provide all applications for a Brand, then the
system can be configured so it does not look up individual parts. Or if
you know a supplier will send all applications for a Part Terminology at
a time, then the system can be configured so that it only looks at the
Brand + Part Terminology.

This can be configured globally through the ACES import workflow, or per
Brand. For more information, see topic **9. Specify Complete Replacement
Handling (ACES Import Workflow Only)**[ here]{.mcFormatColor
style="color: Blue;"}.

PRODOC note: RDCUST-3795The Mapper has been extended with a new element
referencedBy\[type:\'\[id\]\'\] to be available within Step Path Editor
window

A new element **referencedBy\[type:\'\[id\]\'\]** is available within
the Step Path Editor window for the Mapping Validation Path
functionality in \'Application Mapping\' and \'Object to Object
Mapping\' plugins. Now, there is an option to access data of the objects
available within the 'Referenced By' tab for the defined object. This
element retrieves the data from the source object when the defined
object is the target object of the configured reference. For the
\'Application Mapping\' plugin this new element can be selected as part
of the Source Validation Path Editor, and Target Validation Path Editor.
And for the \'Object to Object Mapping\' plugin this new element can be
selected as part of the STEP Path Editor. This element can always be
accompanied by id / name / attribute\[id:\'\[id\]\'\] /
reference\[type:\'\[id\]\'\] elements. For more information, see the
**Mapping Validation Path Functionality** topic of **Automotive
Reference Guide**[ here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/Release%20Notes/9.2MP1/4.png)

PRODOC note: RDCUST-3767,3766New XXX Search screen

With a strong desire to add more strength to the existing Data
Onboarding solution, a new search functionality is made available to
users with this release.

XXXX Search screen allows Web UI users to search either based on the
free text or by narrowing down the search result based on filtering
certain criteria. Users can also configure the search parameter so that
users can define their own relevant attributes or other parameters that
might be relevant for them.

This search functionality helps to keep track of all the changes
implemented when a Mapper Configuration setup entity is executed (See
**Executing Mapper Configuration Setup Entity** topic
([here]{.mcFormatColor style="color: Blue;"})). xxxx

PRODOC note: BOND RDCUST-3724Updated ACES Exporter to also include the
inherited application notes in the exported ACES file

The existing solution of the ACES Exporter is to only include the
application note information that is directly referenced by the ACES
application record. There are some special cases where the application
notes are linked to the parent of the application records and are
inherited by the application records. Now, the ACES Exporter is updated
to also include the inherited application note information in the
exported ACES file. To include the inherited application note
information, the user has to manually add the Valid Source Types to the
AC\_ACESApplicationToApplicationNote product reference that the user
wants the Application Note reference to inherit from. Also, for the
Application Note product reference, users should change the
\'Inheritance\' parameter to be either \'Inherited\' or \'Accumulative\'
depending on what the user wants to get exported.

To avail this solution, along with the upgrade to this latest patch,
users need to patch the following Hotfix recipe:

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**
[to:hotfix/376/issue-376272-HOTFIX-3510.spr]{.commandfont}

PRODOC note: RDCUST-3767,3766Added support to import and export PIES
data in 7.1 format

In order to send data to downstream systems in PIES 7.1 format, the
AutoCare PIES Exporter now includes the option 7.1 to select either PIES
6.5, PIES 6.7, PIES 7.0, or PIES 7.1 format. The version will default to
7.0, and when version 7.1 is selected, then the exported file will
contain the following:

-   \<PIESVersion\>7.1\</PIESVersion\>
-   The export is validated against PIES 7.1 XSD.
-    

The AutoCare PIES Application Exporter now provides an option to select
between PIES 6.5, 6.7, 7.0, and 7.1 versions in the \'Version\'
parameter within \'Select Format\' dialog as displayed below. For more
information, see the AutoCare PIES Exporter topic of Automotive
Reference Guide[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: RDCUST-3573New Mappings Manager bind available for business
rules

A new Mappings Manager bind has been added for mapping business rules.
This bind is used by business rules to give access to define the
following mapping definitions:

-   **ObjectMappingChange**: bind object to make new objects from
    JavaScript in the Mapper framework. More information can be found
    within the STEP Extension API documentation in the
    com.stibo.onboarding.domain.mapper.mapping.objectmanager class.
-   **ValueMappingChange**: bind object to set values on objects from
    JavaScript. More information can be found within the STEP Extension
    API documentation in the
    com.stibo.onboarding.domain.mapper.mapping.valuemanager class.

More information can be found in the **Mappings Manager Binds** topic
within the **Resource Materials** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: RDCUST-3792Removed support of three old Automotive specific
binds from Easy Setup

Previously, the Easy Setup action created the following three Automotive
specific binds:

-   AutoCare mapping help
-   NAPA mapping help
-   TecDoc mapping help

They were used by the old mapper and are no longer needed. As they are
not fully supported, they have been removed from Easy Setup so as not to
cause confusion.

PRODOC note: RDCUST- 3717Updated Suggested Part Number header component
in Application Manager screen to no longer display the OK and Cancel
button in the \'Value editor\' field

In the Application Manager screen, the Suggested Part Number header
component value editor window has been updated so that the value editor
window no longer displays the OK and Cancel buttons. A new Close button
is added to directly close the value editor window.

![](../../Resources/Images/Release%20Notes/9.2MP1/1.png)

PRODOC note: RDCUST- 3808Fixed Unexpected error generated in the Part
Application Editor component while deleting an existing application

Previously, an Unexpected error was generated in the Part Application
Editor component when users tried to delete an existing application
through the Delete button. This has been corrected so that applications
can be deleted in the Part Application Editor component.

PRODOC note: RDCUST- 3810Fixed Unexpected error generated in the
Application Manager while adding a root node in the Part Type Search Box
Properties window

Previously, an Unexpected error was generated in the Part Type Search
Box Properties window when users tried to delete the existing root node
and add a new root node within the Root Nodes parameter. This has been
corrected so that users can add any root node in the Part Type Search
Box Properties window.

![](../../Resources/Images/Release%20Notes/9.2MP1/5.png)

PRODOC note: RDCUST- 3328Updated Part Type Search card in Application
Manager screen to no longer display any irrelevant part type when the
user types in the typeahead field

The Root Nodes parameter available within the Part Type Search Box
Properties allows for the restriction of root nodes to be used within
the Part Type search box when searching / filtering for a Part Type.
Previously, despite the root node(s) being defined in the Root Node
parameter, the typeahead field in the Part Type search box would suggest
part types that would exist even outside the root node. This was
intentionally designed to perform this way considering the performance
factor of the Application Manager screen. Now, considering the factors
like the user need and system performance, a new parameter \'Use Root
Nodes In Typeahead\' is introduced within the Part type Search Box
Properties to provide an option that suggests the part types in the
typeahead field either within or beyond the defined root node.

![](../../Resources/Images/Release%20Notes/9.2MP1/6.png)

PRODOC note: RDCUST- 3753Corrected the Faceted Search screen to display
the correct count of search results

Previously, the Faceted Search screen had a problem with displaying the
correct count of search results. Any search results exceeding 200 counts
would list all the search results but would not show the correct count
displayed in the bottom left of the screen. Now, the Faceted Search
screen is corrected to display correct number of search counts. The
default value that is set to display for the search count is 1000. If
this number needs to be increased, it can be changed in sharedconfig
property **Onboarding.FacetedSearchDialogServerComponent.FindMax**

For example: Onboarding.FacetedSearchDialogServerComponent.FindMax=5000

PRODOC note: RDCUST- 3760Fixed the way the Application Mapping plugin
handles a unique mapping solution where multiple Source objects are
referenced to the same Target object

Previously, the presence of more than one Source object to the same
Target object restricted the Application Mapping plugin from creating
the applications in the Target object. This has been fixed so that now
the presence of multiple source objects can create applications in the
Target object.

PRODOC note: RDCUST-3750Updated the Automotive import framework to be
able to retrieve the user ID that is importing the file

Checking the parameter \'Swap User\' available within the File Loading
Widget Properties runs the file import as the logged in user instead of
the IIEP user. Previously, this parameter had no significance in the
Automotive import framework because the Automotive import workflows
always used the user from the IIEP for the controller entities. Now,
this issue is fixed so that the automotive import workflows are able to
retrieve the user ID that is importing the file and have that user ID to
be associated with the controller entity instead of the user from the
IIEP so that tasks within the import workflow states are correctly
associated with the user ID that dropped the file into the File Loading
Widget. The user ID is now stored on the import controller object in a
new attribute called Overwriting User. If the ID of the user that is
importing the file (Ready for Import state) should be used instead of
the user who dropped the file into the File Loading Widget, this can be
done by a business action to update the user ID to the one of the
current user just before the import is started.

In order to use the new functionalities, the following must be done
after the patch has been applied:

1.  Run **Automotive - Import Flow Process** Easy Setup

![](../../Resources/Images/Release%20Notes/9.2MP1/15.png)

1.  Change the Inbound Integration endpoint Receiver to use the WebUI
    File Loading Receiver

![](../../Resources/Images/Release%20Notes/9.2MP1/16.png)

1.  Select the Swap User parameter in the File Loading Widget properties
    in Web UI Designer

![](../../Resources/Images/Release%20Notes/9.2MP1/17.png)

PRODOC note: RDCUST-3779Fixed the performance issue occurred in the
Delta Calculation state of the import workflow

To improve the performance of the importers, the \'file\' method of the
Delta calculation has been updated. The sharedconfig property,
Delta.MaxFilesCreated, is now set to 100000 by default to ensure that
the delta calculation will never generate more than 100000 files for the
delta calculation.

PRODOC note: BOND RDCUST- 3752 Corrected an error when using \'Select
all\' Action button in Faceted Search dialog

Faceted Search dialog can search and display the parts / vehicles based
on the defined search criteria and provides an option to the user to
select a part / vehicle from the search list and create an application
using the \'Create application\' button. Previously in the Faceted
Search dialog, in a case when the search result list was exceeding the
configured page size, using the \'Select all\' button would select all
the search results but failed to enable the \'Create application\'
action button (meaning the button still being grayed out). Now, the
\'Select all\' button is corrected so that users can create applications
selecting all the search results using the \'Select all\' button.

In addition, it is also updated to display a warning message notifying
users about creating an excess of applications.

![](../../Resources/Images/Release%20Notes/9.2MP1/7.png)

PRODOC note: BOND RDCUST- 3768 Corrected error when using \'Select all\'
Action button in the Application Editor screen

Previously in the Application Editor screen, in a case when the number
of application records listed in the screen was exceeding the configured
page size, using the \'Select all\' button would select all the
available applications but failed to delete any applications when the
user tried to delete using \'Delete application\' action button. Now,
the \'Select all\' button is corrected so that users are able to select
all the listed applications using \'Select all\' button and then to
delete all the selected applications using the \'Delete application\'
button.

### AutoCare

PRODOC note: RDCUST- 3762Fixed error when calculating possible option
values in the Application Manager

Previously, when an AutoCare Vehicle is linked to a Drive Type other
than AutoCare Drive Type object, the Application Manager fails to
display the vehicle configurations that exist as an attribute value on
the AutoCare Drive Type target object. Now, the Options Search Box has
been updated so that it will display the AutoCare attribute values on a
referenced target object, even if other non-AutoCare object types are
being referenced to the vehicle.

PRODOC note: BOND RDCUST-3761Updated the Engine Base object name to
include the value from the attribute Engine Block Type
(AC\_VCdbEngineBlockType) with the Cylinders

Previously, the Engine Base object STEP name contained the Engine Liter
+ \'L\', Cylinders + \'L\', CC, and CID values. Now, the naming
convention is updated to contain the Engine Block Type + Cylinders,
Engine Liter + \'L\', CC, and CID values. For example, the Engine Base
ID \'AC\_EngineBase\_15\' that had the name as 3.0L 6L, 2999CC, -CID is
updated to display as H6 3.0L, 2999CC, -CID.

PRODOC note: BOND RDCUST-3761Updated the Engine Config object name to
include the LOV value retrieved from attribute VCdb Fuel Type

Previously, the Engine Config object STEP name concatenated the Engine
Base Name + the Fuel Delivery Config Name (both are references from the
Engine Config object). Now, the naming convention is updated to also
include LOV value retrieved from attribute VCdb Fuel Type
(AC\_VCdbFuelType). For example, the Engine Config ID
\'AC\_EngineConfig\_3047\' that had the name as \'3.0L L6, 2999CC, -CID,
FI, MFI, Mechanical, Bosch K-Jetronic\' is updated to display as \'3.0L
L6, 2999CC, -CID, GAS, FI, MFI, Mechanical, Bosch K-Jetronic\'.

PRODOC note: BOND RDCUST-3781Corrected the way the assemblies are
suggested in the node picker when the user tries to create an
application in the Application Editor screen

In the Application Editor screen, users are provided with an option to
create new application records using the \'Create application\' action
button. This action button lets the user select a valid assembly through
a node picker to create an application. Previously, there was some error
that restricted users from selecting non-AutoCare assemblies. Now, the
node picker is corrected to be able to select all types of valid
assemblies.

![](../../Resources/Images/Release%20Notes/9.2MP1/11.png)

PRODOC note: RDCUST-3659Updated PIES Exporter and ACES Exporter to
handle attribute values that are language dependent

Previously, PIES Exporter and ACES Exporter were not handling attribute
values that were language dependent. Now, the PIES and ACES exporter is
updated to export the correct LanguageCode for values that are language
dependent. PIES and ACES exporter is updated so that if a context other
than English is selected when exporting PIES or ACES, that the
LanguageCode that is defined for the context that has been selected will
be evaluated to use in the LanguageCode attribute for values that are
language dimension dependent.

To handle PIES and ACES exporter to export the correct LanguageCode for
values that are language dependent, easy setup for the Automotive -
AutoCare Model (steps 1 & 2) must be re-run to:

-   Create a new Description attribute called \'Language Code\' (ID =
    AC\_LanguageCode) under \'AutoCare Attributes\' group (ID =
    AC\_TopLevelAttrGroup) and make it valid for \'Dimension Point\'
    object type (ID = Real qualifier). This attribute will be set to
    LOVs as the Validation Base Type using LOV ID =
    AC\_PIESLanguageCode.

Corrected PIES export of Interchange parts

Corrected an issue where Interchange parts that were included in the
PIES export were wrongly exported and displayed more than once within
the export results. Now, the PIES Exporter is corrected to properly
handle the Interchange parts and are displayed correctly in the exported
PIES file.

This issue is fixed to be available from Automotive 9.2 MP2 release. To
make this fix available in the current release, the user needs to patch
the following Hotfix recipe in the current release.

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**
[to:hotfix/376/issue-376215-HOTFIX-3509.spr]{.commandfont}

Corrected PIES export of Packaging Segment

Corrected an issue where Packaging information that were included in the
PIES export were either ignored or not displayed in the right place
within the export results. Exporting with two or more PIES Item
displayed packaging information of different PIES Item under one PIES
Item segment within the export results. Now, the PIES Exporter is
corrected to properly handle the Packaging information and are displayed
correctly in the exported PIES file.

This issue is fixed to be available from Automotive 9.2 MP2 release. To
make this fix available in the current release, the user needs to patch
the following Hotfix recipe in the current release.

**Hotfix recipe compatible with STEP 9.2 MP2 + Automotive 9.2 MP1:**
[to:hotfix/376/issue-376277-HOTFIX-3511.spr]{.commandfont}

### TecDoc

PRODOC note: RDCUST- 3777Fixed error generated in the Part Application
Suggestions component while adding an application from the suggested
application list

Previously, an Unexpected error generated in the Application Suggestions
component when users tried to add an application through the Add button
(![](../../Resources/Images/Competitor%20OE%20Number/43.png){.img_intext})
from the suggested applications list. This has been corrected so that
applications can be added from the suggested applications list.

Performance Enhancements {#performance-enhancements .MPNPerformance}
------------------------

PRODOC note: RDCUST- 3759 and NGK-555Corrected performance issue when
opening the Application Manager screen

The performance of opening the Application Manager screen has been
improved.

**Hotfix recipe compatible with STEP 9.1 MP5 or 9.1 MP6 + Automotive 9.1
MP2:**[ to:hotfix/373/issue-373513-HOTFIX-3474.spr]{.commandfont}

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

PRODOC note: PRODOC-xxxx Business Action Mapping Plugin topic

The **Business Action Mapping Plugin** topic ([here]{.mcFormatColor
style="color: Blue;"}) has been added to the new **Data Onboarding
Solution** section of the **Automotive Reference Guide**.

PRODOC note: PRODOC-xxxx Business Action: Validate Application
Conditions and Start in Workflow topic

The **Business Action: Validate Application Conditions and Start in
Workflow** topic ([here]{.mcFormatColor style="color: Blue;"}) has been
added to the **Automotive Business Rule Plugins** section of the
**Automotive Reference Guide**.

PRODOC note: PRODOC-xxxx Business Condition: Validate Application on
Import topic

The **Business Condition: Validate Application on Import** topic
([here]{.mcFormatColor style="color: Blue;"}) has been added to the
**Automotive Business Rule Plugins** section of the **Automotive
Reference Guide**.

PRODOC note: PRODOC-xxxx Automotive bind topics update

Three new Automotive specific bind **Source Object Bind**
([here]{.mcFormatColor style="color: Blue;"}), **Source Application
Bind** ([here]{.mcFormatColor style="color: Blue;"}), and **Mappings
Manager Bind** ([here]{.mcFormatColor style="color: Blue;"}) topics has
been added to the **Resource Materials** section of the **STEP Online
Help**.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.22.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible only with the following STEP 9.2 MP2
baseline recipe:

[to:step/trailblazer/step-9.2-mp2.spr]{.commandfont}

**PRODOC note: MEDU PRODOC- 1572** Once an Automotive add-on is
installed to a base STEP system, the base system cannot be upgraded
without upgrading the Automotive add-on at the same time. Additionally,
when upgrading any base STEP system that has any Automotive add-on
installed, both install recipes must be prepared at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
