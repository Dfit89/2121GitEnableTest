---
description: 'Automotive Solution: PMDM for Automotive 9.0 MP1 September
  2018 Maintenance Patch Notes'
title: PMDM for Automotive 9.0 MP1 September 2018 Patch Notes
---

PMDM for Automotive 9.0 MP1 Patch Notes {#pmdm-for-automotive-9.0-mp1-patch-notes .MPN}
=======================================

Release Date: September 10, 2018 {#release-date-september-10-2018 style="text-align: center;"}
--------------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: PRODOC -1395 New Part Number References component

The new Part Number References component is a Node Editor component used
to display referenced part numbers and their attribute and/or metadata
values when a part number is selected within the Tree navigator. For
information about how to use this component, and prerequisites, see the
**Competitor and OE Numbers Solution** topic within the **Automotive
Reference Guide** found within the **Solution Enablement** section of
**STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: PRODOC -1395 New Part Number Suggestions component

The new Part Number Suggestions component is a Node Editor component
used to extend the Part Number References component by displaying part
number suggestions. Part number suggestions are based upon the
configured references and Suggestion Plugins when a part number is
selected within the Tree navigator. For information about how to
configure this component, and prerequisites, see the **Configuring the
Part Number Suggestions Component** topic within the **Automotive
Reference Guide**[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: MEDU RDCUST- 3099 New component names for Application
Manager specific Action buttons

With the release of Automotive 8.3 MP1, two new Action button components
were added for use with the restricted node list within the Application
Manager. Because these components were copied from the STEP core Action
button components \'Export Action\' and \'Create Collection Action,\'
they were given the same component name and description. This posed a
problem as users were not able to decipher which listing of the
component would work with the Application Manager. If the STEP core
Action button components were added to an Application Manager then
errors would occur. Now, the Action button names are updated to \'Export
Action Automotive\' and \'Create Collection Action Automotive,\' and
their descriptions clearly communicate they are to be used within the
Application Manager Screen.

PRODOC note: MEDU RDCUST -3064 New Application Manager \'Clear All\'
link

The Application Manager screen is now updated with a \'Clear All\' link
that, when clicked, will reset or clear all search criteria, as well as
any displayed search results. Previously, a \'Clear Criteria\' link was
provided that, when clicked, would clear only the criteria fields, and
not the displayed results. This link has been replaced with the \'Clear
All\' link.

PRODOC note: MEDU RDCUST- 3023 Easily clear filters applied to
Application Manager Results Table

Previously, when a filter was applied to the Application Manager Results
Table and the Clear Criteria link was selected, the filter settings were
not cleared. This meant that the next time a search was run, the Results
Table would display the filtered search results. Now, when the new Clear
All link is clicked, all search criteria and search results are cleared,
as well as any filters applied to the results table.

PRODOC note: MEDU RDCUST -2968 New customizable title for Application
Manager

Previously, the Application Manager screen did not provide a \'Title\'
parameter. This posed a problem for those using more than one
Application Manager screen, as they could not easily determine which
Application Manager screen they were currently using. Now, a \'Title\'
parameter is available on the Application Manager Screen component,
allowing for Web UI Designer users to customize the title of each
Application Manager screen. In the example below, the Application
Manager configured for the TecDoc solution via Easy Setup actions is
displayed with the Title parameter populated as \'TecDoc Application
Manager.\'

![](../../Resources/Images/Release%20Notes/AMT.png)

PRODOC note: MEDU RDCUST- 2956 Updated Competitor and/or OE Numbers cell
contents from read-only to clickable

Previously, when using the \'Application Competitor or OE Part Numbers\'
Table Header component within the Application Manager, the Interchange
Manufacturer Name and Interchange Part Name were displayed within the
cell, and nothing further displayed when users double clicked the cell.
Now, when the cell is double clicked a custom labeled read only dialog
displays the current application part number name and the
interchangeable competitor or OEM part number names, as well as the
valid attributes and their values.

In the example below, the \'Application Competitor or OE Part Numbers\'
Table Header component is displayed within an Application Manager with
the column label of \'Application Comp/OE Suppliers with Manuf. Name.\'
A populated cell value within the column was double clicked, and the
\'Application Competitor or OE Part Numbers\' Table Header component
dialog displays with the label \'Competitor or OEM Applications.\'
Within the dialog, the current application number \'351080051\' displays
along with four interchangeable part numbers and their values for the
valid attributes (ACES Drive Type, ACES Mfr Body Code, ACES Region).

![](../../Resources/Images/Release%20Notes/2956.png)

PRODOC note: MEDU RDCUST -3048 Improvement to how Application Manager
\'Vehicle type icon\' handles dropdown defaults

Previously, when a user selected a Vehicle type icon, the dropdown
selections for the \'Existing and Missing Applications\' and \'Hierarchy
Restriction\' dropdowns would remain. This has now been improved so that
each time a different Vehicle type icon is selected, the two dropdowns
reset to their respective defaults (\'Existing Applications Only\' and
\'All Brands\').

PRODOC note: MEDU RDCUST- 3098 3100 Improved Results Table appearance
and ease-of-use

Previously, the Application Set Part and Application Set Assembly header
components (used within the Application Manager) would use a link icon
instead of hyperlinked text. Clicking the link icon would navigate users
to the Application Editor Part screen. Clicking the text did nothing.
Now, when the \'Enable Link\' parameter is enabled, the link icon no
longer displays and clicking the text within the cell opens the
Application Editor Part screen. When the Enable Link parameter is
disabled, the link icon no longer displays and the text within the cell
does not display as hyperlinked. This option is useful when linking to
the Application Editor Part screen is not necessary.

In the example below, the \'Enable Link\' parameter configuration within
the \'Application Set Assembly\' component is displayed above the
\'Before change:\' (displaying the link icon) and \'After change:\'
(displaying the hyperlinked text) Web UI display examples.

![](../../Resources/Images/Release%20Notes/ASA.png)

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: MEDU RDCUST- 3106 Corrected error when using \'Export
Action Automotive\' Action button

Previously, when using the \'Export Action Automotive\' Action button
and clicking the \'Start export\' button within the Export dialog, a
\'Failed asynchronous call\' error message would display. This error
message stopped users from being able to successfully export data. Now,
this is corrected so that users are able to successfully export data
from the Application Manager Results table.

PRODOC note: MEDU RDCUST -3006 Updated Easy Setup to create Part Type
object types with Reference Target Lock Policy property set to
\'Relaxed\'

Previously, Easy Setup created the following Part Type object types with
the Reference Target Lock Policy property set to \'Strict:\'
AC\_PartTerminology, NAPA\_MPCC, TD\_StandardAssemblyGA, and
TD\_UniversalAssemblyGA. This could potentially cause locking errors on
Reference Target objects when multiple imports were run in parallel.
Now, Easy Setup has been updated so that the Part Type object types are
created with the Reference Target Lock Policy property set to
\'Relaxed.\'

**Existing Implementations:** Run step 1 of Easy Setup for each standard
and, in a matter of seconds, the necessary object type(s) will be
updated to have the \'Relaxed\' setting. This option is ideal because it
does not put the system into single update mode. Otherwise the changes
can be made by manually updating the Reference Target Lock Policy
property value to \'Relaxed.\' However, this manual action puts the
system into Single Update Mode. Thus, it is suggested to make this
manual change outside of business hours as to not impact performance,
nor interfere with other users\' work.

PRODOC note: MEDU RDCUST -3080 Corrected automotive importer handling of
special characters

Previously, when importing an XML file containing special characters
(i.e., &, \', \"), the automotive importer would convert the special
characters in a way that would add more characters to the text. This
caused the import to fail validation when character count restrictions
were applied. This is now fixed, so that the special characters are not
mishandled, the character count validation does not fail, and the import
can proceed as expected.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/322/issue-322092-HOTFIX-2640.spr]{.commandfont}

PRODOC note: MEDU RDCUST -2984 Corrected display of Competitor / OE
Number after selection

Previously, though a Competitor or OE Number was currently selected and
displayed within the Competitor / OE Number screen, it would also
display within the suggestion list when a user tried to add New
Reference Number. If a user tried to select the already listed number,
an error dialog would display. Now, the previously selected numbers do
not display within the dropdown list.

PRODOC note: MEDU RDCUST -3032 Corrected display of node picker icon
when using the bulk update function

Previously, when using the bulk update function within the Application
Manager, the node picker icon would not display. Thus, users could not
select the desired node(s) for bulk update. Now, the node picker icon is
properly displayed, so that the bulk update function can be used within
the Application Manager.

PRODOC note: MEDU RDCUST- 3037 Corrected display of Name and ID when
using Bulk Update within Application Manager

Previously, when a user clicked the Application Manager Bulk Update
action button and then needed to use the Node picker to select a
necessary target vehicle, many of the vehicle Names displayed in a way
that the user could not properly make their selection (i.e., shortened
names, no ID). Now, the Bulk Update Node picker displays the vehicle
Name appended with the vehicle ID, and does not cut off the ID. If the
Name appended with the ID is too long, then \'\...\' will display
between the Name and the ID. However, the entire ID is displayed, and
only a portion of the Name is not displayed.

PRODOC note: MEDU RDCUST -2981 3085Corrected Application Condition
Header component

Previously, when the Value editor dialog for the Application Condition
Header component (configured for use within an Application Manager) was
accessed and an attribute configured for use within the header component
did not contain values, an \"Include: (TypeError): Cannot read property
\'length\' of null for callback\" error message would display. Now, this
has been corrected so that users are able to access the Value editor for
the Application Condition Header component without an error message
displaying.

PRODOC note: MEDU RDCUST- 3120 Corrected Application Asset Reference
Header component

Previously, when adding an asset through the Application Asset Reference
Header component from the suggestion list, the following error would
display and not allow users to link the asset: \'(TypeError): a is
undefined.\' Now, this error is corrected and assets can be properly
linked to applications.

PRODOC note: MEDU RDCUST- 3035 Improved value display height within
Make/Model search box

Previously, when multiple values were added to a Make/Model search box
and the browser zoom was set below 100%, the value tiles would display
double the usual height. This is now improved so that the value tile
display height does not change, regardless of the browser zoom settings.
In the screenshot below on the left, the value tiles are displayed using
double height, whereas on the right, the same values tiles are displayed
using the normal height.

![](../../Resources/Images/AppMgr/doubleheight.png)

PRODOC note: MEDU RDCUST -3040 and 3039 Corrected Application Manager\'s
requirement of Make/Model value

With the Automotive 9.0 release, the Make/Model search box within the
Application Manager was updated to require a value prior to allowing a
search to be run. This posed an issue for those needing to search by an
option like \'Engine Code\' across multiple makes and/or models because
the same engine can be available across several manufacturers. Now, this
is corrected so that a value is no longer required within the Make/Model
search box. However, when users attempt to run a search without
populating the Make/Model search box, a dialog will display warning the
user that the search may be time consuming, and suggesting the Report
button option. Below is an example of the warning dialog.

![](../../Resources/Images/AppMgr/Warn1.png)

PRODOC note: MEDU RDCUST -3020 Corrected ability to edit multiple values
within Application Manager

Previously, users were not able to select more than one cell within the
results table and then successfully edit the cells with a single value.
This forced users to update the cell values one at a time. Now, this is
corrected, so that users can multi-select cells and edit the contents
all at once. However, selected cells must have an existing value that is
different from the updated value, or no changes will be made to any of
the selected cells.

PRODOC note: MEDU RDCUST -3088 Corrected ability to applicate same part
number more than once

Previously, when the Application Manager results displayed an
application using a part number, and a user needed to applicate that
same part number to a different vehicle, the new application would not
save, and an error message would display. Now, this is corrected so that
more than one application can be created using the same part number
within the results table.

PRODOC note: MEDU RDCUST -2791 Corrected results of using Create
Collection action button when missing applications are selected

Previously, when the Application Manger was used to display missing
applications, and a user selected those applications prior to clicking
the \'Create Collection\' action button, an error message would display
within the BGP. Though existing applications were selected, and
therefore expected to be within the newly created collection, the error
message would inform the user that the \'File contains 0 rows\'. Now,
this is corrected so that users can use the \'Select All\' button when
both existing and missing applications are displayed, along with the
\'Create Collection\' button, and the existing applications will be
successfully added to the collection. Though missing applications can be
selected, they cannot be added to a collection because they do not
actually exist in STEP.

PRODOC note: MEDU RDCUST -3081 Corrected display of Application Manager
when accessed from Corner Bar link

Previously, when accessing an Application Manager screen from a link
configured within the Corner Bar component, the screen would not load
completely, causing an error dialog to display. This forced users to
reload the page before being able to successfully use it. Now, this is
corrected so that an Application Manager screen can be used when
accessed from a link configured within the Corner Bar.

PRODOC note: MEDU RDCUST -3027 Removed Application Manager error message
when searching for invalid criteria

Previously, when adding search criteria to an Application Manager,
additional criteria could cause previously added criteria to no longer
be valid. The newly invalid criteria would display as grayed out, an
error message would display (\"Cannot read property \'removeChild\' of
null\"), and users could not complete the search. Now, the error message
is removed, invalid values are grayed out, and users are able to conduct
the search for only those values that are valid.

PRODOC note: MEDU RDCUST -3074 Corrected graying out of valid Part Types
within Application Manager

Previously, some Part Type values were grayed out after additional
criteria was added to the Application Manager screen, even though the
Part Type was valid for the provided criteria. Now, this is corrected so
that Part Types are not erroneously grayed out.

PRODOC note: MEDU RDCUST- 3050 Corrected error when using \'Application
Asset Reference\' header component

Previously, when users selected an asset within the Reference Target
parameter of the Add Reference dialog (shown below), an error message
would display and the selected asset would not be linked. Now, this is
corrected and users can successfully add a reference to an asset.

PRODOC note: MEDU RDCUST- 3095 Updated \'Asset Search Below Plugin\'
within \'Application Asset Reference\' header component to only display
the configured \'Asset Static Root Nodes\'

Previously, when a user clicked the node browser icon to add a Reference
Target using the \'Application Asset Reference\' component, the Select
Node(s) dialog would display all the Classification Root Nodes within
STEP, despite the Asset Static Root Nodes component Root Node URLs
parameter being configured to only display specific Root Nodes. This
caused confusion for users, as they would see more Classification Root
Nodes than configured for display within the Web UI. Now, this is
corrected so that only the Root Nodes configured within the component
are displayed. In the screenshot below, both the Web UI end results and
configuration of the \'Asset Static Root Nodes\' are displayed. Steps
one through four display:

1.  Clicking on the Edit icon within the Assets column of the
    Application Manager to display the Value editor.
2.  Clicking on the Add Reference button to access the Add Reference
    dialog.
3.  Clicking the node browser icon to display the Select Node(s) dialog.
4.  Only the \'Classification Root Node\' configured within the \'Root
    Node URLs\' parameter of the \'Asset Static Root Nodes\' plugin
    display in the Select Node(s) dialog.

![](../../Resources/Images/Release%20Notes/RTRN.png)

![](../../Resources/Images/Release%20Notes/RTRN.png)

AutoCare

PRODOC note: RDCUST -3076 ACES Application Exporter Part Number Source
attribute retention correction

Previously, when an attribute was selected for the \'Part Number
Source\' parameter, and a different attribute was selected for the \'Use
Attribute for Mfr Label\' parameter, then the system would use the \'Use
Attribute for Mfr Label\' attribute value instead of the \'Part Number
Source\' attribute value. This caused the exported file to have the same
value for both fields. Now, this is fixed so that the Part Number Source
parameter in AutoCare ACES Application Exporter will retain the
attribute that is selected for the Attribute Value option.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/322/issue-322235-HOTFIX-2641.spr]{.commandfont}

PRODOC note: MEDU RDCUST- 3110 Corrected unclosed Product tags in
ACES Importer

Previously, when using the ACES Importer and viewing the XML file
generated after Delta Calculation, many Product tags were left open in a
cascading fashion and were never properly closed. This occurred whenever
a multivalued object had the same value twice, and the Delta Calculation
missed the end tags. This caused a SAXParser exception when a user
clicked the Import button to initiate the import. Now, this is
corrected.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**[
to:hotfix/323/issue-323547-HOTFIX-2667.spr]{.commandfont}

PRODOC note: MEDU RDCUST- 3093 Corrected ACES Importer skipping
applications with unique Qdb parameter values

Previously, Qualifier parameters were not checked as part of the
uniqueness when generating the ID for ACES applications. This caused
applications with unique Qdb parameter values to not be properly
imported because the Conversion state in the AutoCare ACES Import
workflow did not read into the XML children of the \<Qual\> tag during
the conversion state of the import workflow. Because the importer was
not reading into the XML children of the tag, the data was thought to be
duplicate, and was being skipped. Now, Qualifier parameters are part of
the uniqueness check, the importer is correctly reading into the XML
children, and the imports are able to be successfully processed.
However, this correction requires existing applications with qualifier
parameters to be assigned a new STEP ID when the next ACES import is
completed.

**Existing Implementations:** Identify existing records with qualifiers
and prepare them for replacement. Then, complete a FULL load of all
applications with qualifier parameters. Be aware that all applications
with qualifier parameters will be assigned a new STEP ID. In other
words, applications that have a qualifier with parameters that existed
prior to the import will be marked or flagged as deleted and the new
version will display (with a different STEP ID), and will be marked or
flagged as new.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/322/issue-322570-HOTFIX-2648.spr]{.commandfont}

NAPA

PRODOC note: RDCUST -3091 Added Product Line as a suffix to the Part
Type Name

Previously, when using the NAPA Application Manager MPCC search box, the
dropdown would display what appeared to be duplicate Part Types. This
occurred because the Product Line is used to differentiate between Part
Types within the NAPA solution. Now, the Product Line is added as a
suffix to the Part Type Name, so that when users access the MPCC search
box, the different Part Types display suffixes with their relative
Product Line. In the image below on the left, the previous version of
the MPCC search box dropdown displays the ambiguous Part Type list,
while on the right, the new version of the MPCC search box dropdown
displays the Part Types now including the Product Line suffix.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**[
to:hotfix/322/issue-322567-HOTFIX-2647.spr]{.commandfont}

![](../../Resources/Images/Release%20Notes/MPCCWoPL.jpg)

TecDoc

PRODOC note: MEDU RDCUST -2947 Reference Data Importer corrections

Previously, when using the Reference Data Importer, the following error
types would occur:

-   \"Error in this import 07\_VehicleModelSeries.xml setting completed
    with errors - Error: Trying to import new classification without
    specifying usertype. UserTypeID must be specified in order to
    autogenerate ID using configured autoname for usertype.\"
-   \"Error in this import 39\_VehicleCountrySpecifications-table124.xml
    setting completed with errors - Error: Target \'TD\_C\_IBE\' of
    reference not found\"
-   \"Error in this import 33\_BodyType-Table145.xml setting completed
    with errors - Error: Target \'TD\_C\_EG\' of reference not found\"

Now, the Reference Data Importer has been updated to properly handle the
Reference Data file, and the errors no longer display erroneously.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/319/issue-319667-HOTFIX-2596.spr]{.commandfont}

PRODOC note: MEDU RDCUST -2920 Supplier Data Importer VPE field
validation correction

Previously, when using a Supplier Data importer, validation would fail
and trigger warning messages when the VPE field was blank. This occurred
because the VPE field had been incorrectly specified as mandatory. This
was misconstrued because the field is mandatory when the MengeProVPE
field is populated. Now, the code has been updated to handle the VPE
field correctly.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/319/issue-319667-HOTFIX-2596.spr]{.commandfont}

PRODOC note: RDCUST -2986Supplier Data Importer delta calculation
correction

Previously, when using the Supplier Data Importer, the status file would
only be stored when the importer failed. This caused an issue with
subsequent Supplier Data imports not benefiting from the delta
calculation process. Now, whether the Supplier Data import fails or
succeeds, the import file is properly saved. For more information, see
the **Delta Calculation State** within the **Automotive Reference
Guide**[ here]{.mcFormatColor style="color: Blue;"}.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/316/issue-316697-HOTFIX-2526.spr]{.commandfont}

PRODOC note: RDCUST -2982Updated Application Competitor or OE Part
Numbers table header component results

Previously, when the Application Competitor or OE Part Numbers component
was used within the TecDoc Application Manager to create applications,
the applicated numbers were not being stored below the value provided
within the Object Type parameter of the component. This also caused for
the applicated numbers not to display within the Application Manager
results table. Now, this is resolved so that the applicated numbers are
stored below the specified Object Type parameter, and properly display
within the results table.

PRODOC note: RDCUST -2952Out Of Memory Exception during TAF import
corrected

Previously, when importing a TAF file an Out of Memory Exception error
could occur, which was caused by the tables being loaded into memory
instead of being partially read. This is now resolved so that the tables
are properly processed, and the error does not occur.

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

PRODOC note: PRODOC- 1241TecDoc Reference Data Importer documentation
update

The new **TecDoc Reference Data Importer** section addresses using and
configuring the TecDoc Reference Data Importer, and can be found within
the **Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.11.spr]{.commandfont}

The above recipe is only compatible with the STEP 9.0 MP3 baseline
([to:step/trailblazer/step-9.0-mp3.]{.commandfont}[spr]{.commandfont}).

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
