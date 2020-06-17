---
description: 'Automotive Solution: This topic explains the Application
  Editor Screen that allows Web UI users to view, edit, create and
  delete application records when a vehicle / assembly or a part is
  selected.'
title: '\[%=Heading.Level1%\]'
---

Application Editor Screen
=========================

Running step 1 of Easy Setup for each standard (AutoCare / NAPA /
TecDoc) will create two Application Editor Screens:

-   One for when a Part is selected to display the applications
    belonging to that Part.
-   One for when a Vehicle / Assembly is selected to display the
    applications belonging to that Vehicle / Assembly.

Web UI users can view, edit, create, and delete application records
within these screens. Users can also further configure results table in
the screen to meet their requirements.

The Application Editor Screen require an object selection, so these
screens need to be mapped for a particular object type or added on a tab
within another screen that is mapped to the appropriate object. To map
the Parts or Vehicles screen directly so that when you are on a part or
vehicle, you will only see that screen, see the **Mappings** topic
within the **Main Properties Overview** section of **STEP Online**
**Help**[ here]{.mcFormatColor style="color: Blue;"}.

To add the Parts or Vehicles screen to an existing screen, use the Sub
Screen Tab Page configuration, described in the **Tab Pages** topic in
the **Web User Interfaces / Web UI Getting Started** documentation of
**STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

AutoCare will be used as an example throughout this topic.

Each of the automatically configured Application Editor Screens for the
different standards are described below:

AutoCare

Each of the automatically configured screens for the AutoCare solution
are described below:

-   **AutoCare Application Editor Screen (Parts):** A screen for viewing
    / editing application records when a part is selected. This screen
    is mapped to the AC\_PIESITEM object type.
-   **AutoCare Application Editor Screen (Vehicles):** A screen for
    viewing / editing application records when a vehicle is selected.
    This screen is mapped to the AC\_Basevehicle object type.

NAPA

-   **NAPA Application Editor Screen (Parts):** A screen for viewing /
    editing application records when a part is selected. This screen is
    mapped to the NAPA\_Product object type.
-   **NAPA Application Editor Screen (Vehicles):** A screen for viewing
    / editing application records when a vehicle is selected. This
    screen is mapped to the NAPA\_Year object type.

TecDoc

-   **TecDoc Application Editor Screen (Articles):** A screen for
    viewing / editing application records / linkages when an article is
    selected. This screen is mapped to the TD\_DS\_SupplierArticle
    object type.
-   **TecDoc Application Editor Screen (Assemblies):** A screen for
    viewing / editing application records / linkages when an assembly is
    selected. This screen is mapped to the TD\_VehicleType(PC) object
    type.

Prerequisites
-------------

It is expected that anyone configuring the Application Editor Screen
(Parts / Vehicle) is familiar with the Web UI Designer, as basic
concepts for working with the designer are not covered in this section.
In addition, the user must have appropriate privileges to access the
designer. Additional information can be found in the [Designer
Access]{.bold} section of the [Web User Interfaces]{.bold} / [Web UI
Getting Started]{.bold} documentation[ here]{.mcFormatColor
style="color: Blue;" conditions="Primary.Web"}.

Configuring Application Editor Screen Properties
------------------------------------------------

The Application Editor Screen Properties includes the **Data Provider**
parameter that is prepopulated with either the \'Part Application\' or
\'Assembly Application\' options. The \'Part Application\' option is
selected for the Application Editor Screen that is used to display the
application records while selecting a part. The \'Assembly Application\'
option is selected for the Application Editor Screen that is used to
display the application records while selecting a vehicle / assembly. No
further configuration is needed for the Data Provider parameter.

**Object Type Filter:** This parameter allows users to restrict the
Application Editor results by an object type. If left blank, application
records belonging to all object type will be displayed.

![](../../Resources/Images/Application%20Editor/2.png)

The Application Editor Screen Properties is pre-configured with a Node
List in Multi Edit Display Mode along with the \'Delete Application
Action\' and \'Create Application Action\' toolbar actions (as shown
above).

1.  Select the \'Node List\' option in the dropdown and click on the
    \'go to component\' link.
2.  Configure the Node List component. For more information, see the
    **Node List Component** topic within the **Web User Interfaces**
    section of **STEP Online Help**[ here]{.mcFormatColor
    style="color: Blue;"}.

The Headers parameter available within the Multi Edit Display Mode
allows for the display of various headers to be used to display needed
information. For more information on configuring the Multi Edit Display
Mode Properties, see the **Node List Component** topic within the **Web
User Interfaces** section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

Since the Application Editor Screen is based on the Node List component
and the Multi Edit Display Mode, sorting and filtering of the header
component values are supported. This allows for multiple information of
the application records to be shown in the same table with the column
filtering capabilities. Also, the \'Number of Items\' shown in the
Application Editor Screen is displayed towards the bottom of the results
table, allowing a user to see the total number of application records
without having to scroll through the data. In the example screenshot
shown below, the Application Editor Screen is configured as a tab page
within the Node details screen and eight application records are
displayed for the selected part.

![](../../Resources/Images/Application%20Editor/3.png)

Node List Properties
--------------------

Only the significant information applicable to the Application Editor
Screen is detailed below. Additional information about the Node List
Properties can be found in the **Node List Component** section of the
**Web User Interfaces** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

The following are the parameters available within the Child Components
section of the properties screen:

![](../../Resources/Images/Application%20Editor/11.png)

### Display Modes

The [Multi Edit Display Mode]{.bold} comes pre-configured in this Node
List. As the name implies, users can edit multiple application records
and multiple attributes in the same screen and save the changes
automatically (using the \'Use Immediate Save\' parameter) or manually.
For details, see the the **Auto-Save in the Web UI** topic within the
**Using Web UI** section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}. When the user double clicks the Multi Edit
Display Mode component available within the Display Mode parameter, the
Multi Edit Display Mode Properties dialog displays. The Multi Edit
Display Mode Properties dialog allows to further configure the component
based on the user requirements.

![](../../Resources/Images/Application%20Editor/12.png)

[Table Headers]{.bold}

The Headers parameter available within the Multi Edit Display Mode
Properties allow users to add multiple table header components that gets
listed as individual columns in the results table of the Application
Editor Screen.

Below are some header examples. The bullet under each header explains
what is displayed in that header column. Additional headers may be used
(e.g., Name, Attribute Value, Attribute Value Group). When adding
headers, you can read a description of each before adding them to the
Headers field.

It is suggested that the [Application ID Header]{.bold} be used in place
of the ID Header to display the ID of the application records.

-   [Application Condition Header - Individual]{.bold
    style="font-weight: bold;"} - Table header expanding to show all
    \'important\' conditions for an application. For details, see the
    **Application Condition Header Components** topic[
    here]{.mcFormatColor style="color: Blue;"}.
-   [Application Condition Header - Group]{.bold} - Table header showing
    attributes that serves as conditions for an application. The
    attributes could be on the application object, the child object to
    the application or on the reference from the application object to
    the assembly object. For details, see the **Application Condition
    Header Components** topic[ here]{.mcFormatColor
    style="color: Blue;"}.
-   [ACES Application Qualifiers]{.bold} - Table header that shows
    AutoCare application qualifiers.
-   [Application Approval Status]{.bold} - Table header that shows
    application approval status.
-   [Application Assembly Value]{.bold} - Table header that shows the
    value of an attribute of an assembly linked to an application.
-   [Application Asset Reference]{.bold} - Table header that shows the
    asset reference for an application.
-   [Application Comment]{.bold} - Table header that shows comments.
-   [Application Competitor or OE Part Numbers]{.bold} - Table Header
    used to display competitor or OEM part numbers and manufacturer
    names (optional) in the Application Manager results table.
    Additionally, when users click a part number value within the
    column, a read-only dialog will display the competitor or OEM
    applications.
-   [Application Country Handling Table Header]{.bold} - Component used
    to display and edit country handling data within the Application
    Editor Screen table.
-   [Application ID]{.bold} - Table header that shows the ID of an
    application.
-   [Application Part Type Title Header]{.bold} - Table header that
    shows the name of the part type that is linked to the applications
    in the table.
-   [Application Part Type Value]{.bold} - Table header that shows the
    value of an attribute of a part type that is linked to an
    application.
-   [Application Set Assembly]{.bold} - Table header that shows the name
    of the assemblies linked to the applications in the table.
-   [Application Set Part]{.bold} - Table header that shows the name of
    the parts linked to the applications in the table.
-   [Application Suggestion Info]{.bold} - Table header component used
    to display information for why the application record is being
    suggested.

While configuring the headers in Display Mode properties, a user can
choose to set up the table sort order based on a specific header. By
editing a particular header\'s properties, sorting order (ascending or
descending) can be designated using the dropdown next to Table Sorting.
Once the properties are saved, the table will sort itself based on the
new header settings, and the Display Mode properties will be retained
until configured differently.

The Table Sorting designation can only apply to one header at a time. It
has to be removed from one header before setting up on another.
Additionally, if \'Enable Default Sorting\' is enabled / selected in the
Node List properties, selecting a header to sort by overwrites this
setting.

### Actions {#actions style="margin-top: 6mm;"}

Many action buttons can be added to a screen to be used with a Node
List. These are all added and configured within the [Actions]{.bold}
field on the Node List Properties screen. The [Create Application
Action]{.bold} and the [Delete Application Action]{.bold} come
pre-configured. These actions and the Bulk Application Updates action
are described below. Other actions can be configured based on the user
requirements.

After clicking the **Add** button, the \'Add component\' dialog is
displayed. Selecting a component in the left area will display the
description for that component in the right area.

![](../../Resources/Images/Application%20Editor/4.png)

#### [Create Application Action]{.bold}

The [Create Application Action ]{.bold}button (
![](../../Resources/Images/Application%20Editor/5.png) ) opens a
\'Create Application\' dialog with Select Assembly (or Select Part
depending on the type of Application Editor Screen) option.

![](../../Resources/Images/Application%20Editor/6.png)

When a user clicks on a node picker icon (as shown in the screenshot
above), they are presented with standard Browse and Search tabs to
select an existing vehicle / assembly or part. The \'Select Assembly\'
and \'Select Part\' value fields support typeahead functionality, which
allows users to easily add a vehicle / assembly or part without having
to click through various hierarchies and/or folders.

![](../../Resources/Images/Application%20Editor/7.png)

Additional functionality can be configured that allows users to set a
name of the newly created application records with a unique name format,
search for vehicles / assemblies or parts in an effort to only select
below the defined hierarchy, or narrow the search result in the Faceted
Search window to aid efficient vehicles / assemblies or parts selection.
For more details regarding how to fully configure the properties for the
Create Application Action component, see the [Create Application
Action]{.bold} section of the [Automotive Reference Guide]{.bold}
documentation[ here]{.mcFormatColor style="color: Blue;"}.

#### [Delete Application Action]{.bold}

The [Delete Application Action]{.bold} (
![](../../Resources/Images/Application%20Editor/8.png) ) is enabled when
an application record is selected in the table. When clicked, it will
delete the selected application record from the table without showing
any warning dialog.

#### Bulk Applications Updates

The **Business action(s) for Bulk Update(s)**
![](../../Resources/Images/Application%20Editor/Auto-Bulk%20Application%20Updates%20Button.png)
button is enabled when one or more application records are selected in
the table. When clicked, it will update multiple application records in
a single operation. Users have the flexibility to add any number of bulk
updates. If more than one bulk update is configured then the Bulk
Applications Updates dialog will display (as shown below), prompting
users to select the desired bulk update to be executed. For more details
regarding how to fully configure the properties for the Create
Application Action component, see the [Bulk Applications Updates]{.bold}
topic of the [Automotive Reference Guide]{.bold} documentation[
here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/Application%20Editor/10.png)
