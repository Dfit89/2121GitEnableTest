---
description: PMDM for Automotive 9.1 MP2 June 2019 Patch Notes
title: PMDM for Automotive 9.1 MP2 June 2019 Patch Notes
---

PMDM for Automotive 9.1 MP2 Patch Notes {#pmdm-for-automotive-9.1-mp2-patch-notes .MPN}
=======================================

Release Date: June 20, 2019 {#release-date-june-20-2019 style="text-align: center;"}
---------------------------

New Features {#new-features .MPNNewFeatures}
------------

### All Standards

PRODOC note: RDCUST -3208,3580, 3270, 3209New Application Suggestion
solution

The Automotive functionality now includes an Application Suggestion
solution that makes it easy to maintain data related to applications of
a selected part. This not only helps users more easily view, edit, and
create applications for specific parts, but also suggests potential
matches. In other words, when configured, STEP can suggest potential
matches for applications based on existing competitor and/or OE part
number\'s applications and/or other defined part number\'s applications
within STEP. When a part is selected, STEP looks at the configured
Reference Types and displays their Target\'s applications.

![](../../Resources/Images/Release%20Notes/91MP22.png)

The components used for this solution are extremely flexible and can be
configured to display the existing applications along with the suggested
applications on the same screen. Also, additional column headers can be
added to the components to display more information than is shown in
this example.

When the solution is configured as shown above, Web UI users can:

1.  View existing applications and related data.
2.  View Target (competitor and/or OE part number) part\'s application
    suggestions and related data.
3.  View information about the suggested application.
4.  Add applications manually.
5.  Add applications from suggestions.
6.  Remove existing applications.
7.  Remove applications from suggestions.

For more information, see the **Application Suggestion Solution**
section of the **Automotive Reference Guide** documentation.

PRODOC note: RDCUST -3248, 3592, 3447Faceted Search: A new robust search
functionality for applicating Part to the Assembly / Vehicle

The PMDM for Automotive 9.1 MP2 now includes new Faceted Search
functionality. It is faster, easier, and provides many different aspects
of searching for Assembly / Vehicle. This function becomes very useful
while applicating a Part to the Assembly / Vehicle. This search function
can be configured in all the places where the \'Create Application
Action\' action button can be configured, one common usage is within the
Application Editor Screen.

Faceted Search window allows Web UI users to search either based on the
free text or by narrowing down the search result based on filtering
certain criteria. Users can also configure the search parameter so that
users can define their own relevant attributes or other parameters that
might be relevant for them.

![](../../Resources/Images/Release%20Notes/91MP214.png)

The following features are available in the new Faceted Search window

1.  Configurable title
2.  Configurable free text field to search Assembly / Vehicle by
    manually typing in the ID / Name / attribute value
3.  Number displaying the total number of Assembly IDs (Names) typed in
    the free text field
4.  Configurable faceted search field to narrow down the displayed
    search results
5.  Field displaying the list of search results
6.  Number displaying the total number of search results
7.  Create Application button to create an application record for the
    selected Assembly / Vehicle

Along with the ID and Name, the free text search field can be configured
to search for a list of attribute values. The free text search box
requires the user to type in the exact ID or Name or attribute value
that the user is looking for. If not, the user can use the faceted
search below. User can type in multiple lists of Names and IDs separated
by a comma. When the comma-separated search is executed, the search
result will display the search results with the IDs matching the input
in the result field. Users can copy (IDs / Names / attribute values)
from excel and paste directly to the free text search field and search
for results.

The faceted search field uses the facet / sync between search cards
functionality to make it possible for the user to narrow down the search
result and only see relevant targets (Assembly / Vehicle). Users can
configure the faceted search to use all available attributes, IDs, or
Names.

Users can execute the search either by clicking on the Search button or
by pressing the Enter key on the keyboard. Users can clear the
parameters by using the Clear button. The Clear button also clears the
search result. Users select the Assembly / Vehicle and can then create
the application by clicking the Create Application button.

When user types any character to free text field, the faceted search
field is disabled (grayed out) and vice versa.

PRODOC note: RDCUST -3208,3580, 3270, 3209New Part Application Editor
component

The new Part Application Editor component is a Node Editor component
used to display existing applications and their attribute values when a
part number is selected within the Tree navigator. For information about
how to use this component, and prerequisites, see the **Application
Suggestion Solution** topic within the **Automotive Reference Guide**
documentation.

PRODOC note: RDCUST -3208,3580, 3270, 3209New Application Suggestions
component

The new Application Suggestions component is a Node Editor component
used to extend the listed existing applications by displaying
application suggestions. Application suggestions are based on the
configured references and Suggestion Plugins when a part number is
selected within the Tree navigator. For information about how to
configure this component, and prerequisites, see the **Configuring the
Application Suggestions Component** topic within the **Automotive
Reference Guide**.

PRODOC note: RDCUST -3576New \'Use Default Application Editor\'
parameter in Vehicle Type Search Panel Properties dialog

The new Use Default Application Editor parameter is a checkbox added in
the Vehicle Type Search Panel Properties dialog. This new option allows
the user to toggle between the use of the default Node List configured
on the Application Manager Screen Properties dialog and the Node List
configured on the Vehicle Type Search Panel Properties dialog.
Previously, configuring the Node List component for any Vehicle Type
Search Panel would overwrite the configuration made in the Node List
component of Application Manager Screen Properties dialog. Once
overwritten, reverting back to the previous configuration was a manual
process that was also tedious. Now, the presence of Use Default
Application Editor parameter helps to easily switch between the Node
List configured on the Application Manager Screen Properties dialog and
the Node List configured on the Vehicle Type Search Panel Properties
dialog. For information about this parameter, see the **Configuring
Application Manager** topic within the **Automotive Reference Guide**[
here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/Release%20Notes/91MP23.png)

PRODOC note: BOND RDCUST-3481New \'Attribute Search Box\' card in
Application Manager screen provides broader search options

The introduction of the new search box component \'Attribute Search
Box\' allows users to search application records based on the values of
defined attributes. Previously, users only had the option to search
based on the \'Year\' attribute value (via Year Search Box component).
Now, users can define the desired attribute search criteria by
configuring this component. In the Vehicle Type Search Panel Properties
dialog, adding the desired attributes to the Search Box Types parameter
lists those attributes in the search box on Application Manager screen
(as shown below). For information about this component, see the
**Configuring Attribute Search Box** topic within the **Automotive
Reference Guide**.

![](../../Resources/Images/Release%20Notes/91MP25.png)

The Year Search Box component is superseded by the new Attribute Search
Box component. After patching to Automotive 9.1 MP2, existing saved
searches using the Year Search Box will no longer work.

To prepare for the Year Search Box being removed, users should do the
following before applying the MP2 Automotive patch:

1.  Go to the saved search and make note of the search criteria.
2.  Delete the saved search.
3.  Apply the Automotive 9.1 MP2 patch.
4.  Recreate the saved search.

If the above steps are not completed prior to patching, the following
error message will be displayed while trying to use the existing saved
search after applying the patch.

![](../../Resources/Images/Release%20Notes/91MP24.png)

PRODOC note: RDCUST -3590New option to not set a default name on
application records when created via the Application Manager

Two new parameters (\'Create Application Business Action\' and \'Do not
set name\') are now added to the Application Set Part column header to
provide control over the naming convention of the application records
being created via the Application Manager screen. Previously, when
application data was created using the Application Manager screen, the
name of the application record was created using the Part Type, Part
Name, Year, Make, and Model from the system wherein the ACES Importer
included a business action that specified the naming convention as
configured in the business action. Now, it is possible to execute a
business action on new applications and set the desired name via the
business action. Selecting the \'Do not set name\' parameter ensures
that the new applications will not have default names. Configuring
\'Create Application Business Action\' parameter with a Business Action
will make the Application Manager run the Business Action thereby
setting the name of the newly created application records as defined in
the Business Action. When using a Business Action to set the application
record name, make sure that the \'Do not set name\' parameter is
selected so that the name is only set through the Business Action.

![](../../Resources/Images/Release%20Notes/91MP29.png)

PRODOC note: RDCUST -3263, 3210New \'Suggested Part Number\' table
header component to suggest a potential product for a missing
application in the Application Manager

The new Suggested Part Number component is a table header component used
to display potential parts fitting the missing application. The
suggested parts are listed in a column for each result in the
Application Manager screen. Users can double click on the cell to open
up the Value editor window and can click the add
(![](../../Resources/Images/Competitor%20OE%20Number/43.png)) button to
add the suggested parts to the missing application. Parts are suggested
based on the references configured in design mode on the Part Suggestion
Plugins parameter. For information about how to configure this
component, and prerequisites, see the **Configuring the Suggested Part
Number Table Header Component** topic within the **Automotive Reference
Guide**.

![](../../Resources/Images/Release%20Notes/91MP210.png)

PRODOC note: RDCUST -3575New \'Application Approval Status\' table
header component to display the approval status of the application
records in the Application Manager

The new Application Approval Status component is a table header
component used to display the approval status of application records in
the Application Manager. The addition of this column will help filter
the applications based on their approval status in the Application
Manager screen. Users can click on the information icon
(![](../../Resources/Images/Release%20Notes/91MP212.png)) near the
\'Can\'t be approved\' status to check the reason for not being
approved. For information about how to configure this component, and
prerequisites, see the **Configuring the Application Approval Status
Table Header Component** topic within the **Automotive Reference
Guide**.

![](../../Resources/Images/Release%20Notes/91MP211.png)

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: RDCUST -3576Default Application Editor parameter replaces
the Default Node List parameter in Application Manager Screen Properties
dialog

Previously, the Default Node List parameter within Application Manager
Screen Properties dialog was being populated with an Automotive
exclusive Node List component (ApplicationFinderNodeList). Now, this
parameter is replaced with Default Application Editor parameter which
provides an option to populate the generic Node List component
(NodeListServerComponent). With this change enabled, the following
functionalities are accessible in the Application Manager solution.

-   Access to Multi Edit Display Mode added as a child component of the
    Node List component. This can provide a user-configurable view (via
    the Enable User Configurable View parameter) to easily switch
    between different Vehicle Type Search Panel views without accessing
    the Web UI designer. For more information, see the **User
    Configurable Views** topic in the **Using a Web UI** documentation[
    here]{.mcFormatColor style="color: Blue;"}.
-   Whenever a new Vehicle Type Search Panel is added, all required
    parameters that need to be populated are displayed in the main
    screen (as shown below). To populate the required parameters, users
    manually navigate to the Vehicle Type Search Panel Properties dialog
    for the newly added Vehicle Type Search Panel.

![](../../Resources/Images/Release%20Notes/91MP28.png)

PRODOC note: RDCUST-3568Improved Application Comment table header
component now includes Reference Metadata Value Header component

In the Application Manager screen, clicking on the Application Comment
edit icon (![](../../Resources/Images/Release%20Notes/icon.png)) opens
the \'Value editor\' window, where a user can add or delete a comment
reference. Previously, the \'Value editor\' window only showed an ID and
Name column for the comment reference. Now, a column for reference
metadata attribute (via Reference Metadata Value Header component) can
be configured to add, for example, the Display Sequence (a metadata
attribute).

![](../../Resources/Images/Release%20Notes/91MP26.png)

### AutoCare

PRODOC note: RDCUST- 3602Corrected stacktrace error while importing PAdb
files

In the last maintenance patch (Automotive 9.1 MP1), there was a
limitation where users were encountering a stacktrace error when
importing the latest version of the PAdb files. This error was
encountered only when the legacy PAdb LOVs were to be replaced with new
values during import and those LOVs were used in a PAdb attribute
referenced to a Classification with an existing LOV filter. This issue
is resolved with this maintenance patch and PAdb files are imported
without stacktrace error.

PRODOC note: BOND RDCUST- 3617Corrected the way PIES Items were created
while importing ACES files with \'Create PIES items\' parameter selected

With the introduction of the \'Create PIES items\' parameter in ACES
Importer, the previous release improved the ability of ACES Importer to
create applications even if the part number (PIES Item) is missing in
the system. The newly created PIES Item was not establishing reference
from the PIES Items to the Part Terminology. Now, a reference is
established through the ACES importer from the PIES Item to the Part
Terminology.

PRODOC note: RDCUST- 3641Corrected a problem with the import flow
conversion service, causing a wrong context to be used

Previously, the import of ACES file was creating the PIES PCdb Part
Terminology object names in the wrong context. Now, the background
process service (ACESToStepXMLConvertService / ImportFlowExtensions) of
the ACES importer creates PIES PCdb Part Terminology object names in the
right context.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/359/issue-359080-HOTFIX-3197.spr]{.commandfont}

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/357/issue-357676-HOTFIX-3185.spr]{.commandfont}

PRODOC note: RDCUST-3569Improved ACES Application Qualifiers Table
Header component to set order of the qualifiers by dragging and dropping
items in the list

In the Application Manager screen, clicking on the qualifier value cell
opens the \'Value editor\' window where the user can add or delete a
qualifier. Previously, the \'Value editor\' window only displayed the
list of qualifiers without an ability to set their order. Now, users can
set the order of the qualifiers (i.e., set values for the Display
Sequence metadata attribute) by dragging and dropping items in the list.

![](../../Resources/Images/Release%20Notes/91MP27.png)

PRODOC note: MEDU RDCUST- 3443Corrected exception error while exporting
PIES and ACES objects

Previously, when exporting the PIES and ACES objects, certain objects
with invalid input data would cause the following exception errors after
clicking on the Finish button directly from the Advanced tab.

-   Convert failed with exception: No enum constant
    com.stibo.automotive.autocare.domain.util.config.AutoCareProperties.PartNumberSourceType.
-   java.lang.IllegalArgumentException: No enum constant
    com.stibo.automotive.autocare.domain.util.config.AutoCareProperties.PartNumberSourceType

These errors caused the export to fail. Now, the exception error no
longer displays when the PIES / ACES objects are exported in the
workbench.

PRODOC note: CANTIRE-366Fixed the way the PCdb Importer handles Part
Relationship classification reference

One of the functions of the PCdb Importer is to set a reference for the
Part Terminology object through the Part Relationship classification
reference. Previously, when a PCdb file with the missing target object
was imported, the system would not remove the existing reference. Now,
the PCdb Importer removes the Part Relationship classification reference
when the target object no longer exists in the import file.

The STEP Automotive solution does not delete objects that are missing
from the import file and uniquely handles missing objects. With this
update, the system only removes the existing reference and does not
delete the target object from the system.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/362/issue-362454-HOTFIX-3235.spr]{.commandfont}

PRODOC note: CANTIRE-366Fixed the way the VCdb Importer handles
classification references of Vehicle objects

One of the functions of the VCdb Importer is to set a reference for the
Vehicle object through various classification references. Previously,
when a VCdb file with the missing target object was imported, the system
would not remove the existing reference. Now, the VCdb Importer removes
the applicable classification reference when the target object no longer
exists in the import file.

The STEP Automotive solution does not delete any objects that are
missing from the import file and uniquely handles missing objects. With
this update, the system only removes the existing reference and does not
delete the target object from the system.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/363/issue-363632-HOTFIX-3249.spr]{.commandfont}

PRODOC note: CANTIRE - 398Improved the performance of \' Validate
Application conditions and start in workflow\' business condition

The \'Validate Application conditions and start in workflow\' business
condition is used in the ACES Importer to create applications with
invalid configurations and initiate them into a workflow. The
performance of this business condition has been improved.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/358/issue-358044-HOTFIX-3191.spr]{.commandfont}

### TecDoc

PRODOC note: BOND RDCUST- 3643 Corrected exception error when importing
TecDoc 7-Zip file types

Previously, when importing the TecDoc 7-Zip file types, an exception
error would display. Now, this has been corrected.

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

PRODOC note: PRODOC- 1244New AutoCare PIES Importer documentation

The new **AutoCare PIES Importer** section addresses using and
configuring the AutoCare PIES Importer and can be found within the
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

PRODOC note: PRODOC- 1742 New set of Use Cases on Business Action: Set
Import Status Attributes

The business action \'Set Import Status Attributes\' when configured
with valid attributes provides many use cases which the user can use to
track the deleted, changed, and newly added objects during the import.
The **Use Case Appendix** section under Business Action: Set Import
Status Attributes topic addresses various use cases on business action
\'Set Import Status Attributes\' and can be found within the
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.18.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible with the following STEP 9.1 MP5 and STEP
9.1 MP6 baseline recipe:

[to:step/trailblazer/step-9.1-mp5.spr]{.commandfont}

[to:step/trailblazer/step-9.1-mp6.spr]{.commandfont}

**PRODOC note: PRODOC- 1572** Once an Automotive add-on is installed to
a base STEP system, the base system cannot be upgraded without upgrading
the Automotive add-on at the same time. Additionally, when upgrading any
base STEP system that has any Automotive add-on installed, both install
recipes must be prepared at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
