---
description: 'Automotive Solution: Describes the Faceted Search Node
  Picker component.'
title: '\[%=Heading.Level1%\]'
---

Faceted Search Dialog
=====================

The Faceted Search Node Picker Dialog is a replacement for the regular
Node Picker dialog that is available to be used only in some components
of Web UI, and one common usage is within the Create Application Action
button that is configured in the Application Editor Screen or within the
Faceted Search Parameter that is configured in the Bulk Applications
Updates component. The faceted search field uses the sync between search
cards functionality to make it possible for the user to narrow down the
search result and only see relevant targets (assembly / vehicle or
part). This feature allows the Web UI users to quickly and easily build
custom searches involving valid combinations of IDs, Names, or different
attribute values of the objects (assembly / vehicle or part). In Web UI
Design mode, users can configure searches for vehicle / assembly or part
objects based on IDs, Names, or attribute values.

The Faceted Search dialog can be configured to define the most likely
used filter groups for the search in the Web UI. As an example, a user
has selected a part and needs to applicate that part to a vehicle. The
user would possibly need to find the vehicle based on Make, Model, Year,
or any attribute value that is valid for the vehicle object. For the
ease of access, if a facet is configured and made available for each of
these search criteria in the Faceted Search dialog, then users can
refine the list of objects based on one or more of the available
filters. Additionally, a configurable free text search bar is also
provided within the dialog so that the users can type in the IDs, Names,
or attribute values to search on.

Faceted Search Dialog Interface Overview
----------------------------------------

The top section of the Faceted Search dialog offers features related to
the free text search field. The section below the free text search field
is dedicated to search by using facets. Both of the types of searches
that are offered in the dialog can benefit users in their own way. The
Faceted Search Dialog is composed of the following:

![](../../Resources/Images/Application%20Editor/23.png)

1.  **Title:** Users can edit the Title in Design mode with any text
    string.
2.  **Free text search field:** Search for objects (assembly / vehicle)
    by manually typing in the ID / Name / attribute value in the free
    text field. Users can type in multiple lists of Names and IDs
    separated by a comma. When the comma-separated search is executed,
    the search result will be displayed with the IDs, Names, or
    attribute values that match the input from the free text search
    field. Users can copy (IDs / names / attribute values) from an Excel
    spreadsheet and paste directly to the free text search field to
    search for results.
3.  **Facets:** Use facets to narrow down the search result and only see
    relevant targets (assembly / vehicle or part). Users can configure
    the facets to use attributes, IDs, or Names. All of the configured
    facets are synchronized and the search criteria can be entered into
    the facets in any order, and the available search criteria will
    display in the typeahead dropdown based upon the criteria that have
    been entered within the other facets.
4.  **Results table:** Displays the list of search results. A Node List
    component is used to display the results of selections made within
    the dialog. Each column label can be edited as needed by accessing
    the Faceted Search Node List Properties Child Component Headers
    parameter.
5.  **Count of search results:**The total count of the search result is
    displayed.
6.  **Total number of search entries:** View the total number of object
    IDs / object names / attribute values that are typed in the free
    text field.
7.  **Search button:** When clicked, the Search button will use the
    criteria that have been provided within the facets / free text
    field, and then executes the search to provide any results in the
    results table.
8.  **Clear button:** Allows users to clear all search criteria,
    characters typed in the free text field, and results displayed in
    the results table. The Clear button remains disabled until at least
    one character is typed in the free text field or at least one
    criterion for one of the facets is populated. Once any unnecessary
    criteria are removed, the Search button must be used to update the
    results table.
9.  **Create application button:** Create an application record for the
    selected assembly / vehicle by clicking \'Create application\'
    button.

Users can execute the search either by clicking on the Search button or
by pressing the Enter key on the keyboard. Users can clear the
parameters by using the Clear button. The Clear button also clears the
search result. Users select the assembly / vehicle and can then create
the application by clicking the Create Application button.

Using The Faceted Search dialog
-------------------------------

The Faceted Search dialog can be used to search in two ways. First, by
using the free text field where users can type in multiple lists of
Names, IDs, and/or attribute values separated by a comma. Second, by
defining the search criteria using facets and narrowing down the search
results. The free text field and facets cannot be used simultaneously.
When the user types any character in free text field, the faceted search
field is disabled (grayed out).

Users need to type in the exact characters of the Name, ID, or attribute
value (not case sensitive) in the free text field. Failing to enter the
exact characters would not find the expected results.

The Faceted Search dialog can be configured to display any number of
facets. Within each facet, a typeahead field is used to view and select
valid search criteria. Because only valid criteria can be selected from
each dropdown list, the Faceted Search provides automated intelligence
for each search. Because of the synchronization of the search boxes,
valid criteria are considered upon each selection and within any of the
displayed facets, no matter the order of entry.

For example, if the Make / Model facet contains a vehicle that was only
produced from 1950-1969, then the dropdown within the VCdb Year facet
will only display those available years for selection.

![](../../Resources/Images/Application%20Editor/24.png)

Configuring Faceted Search Node Picker Dialog Properties
--------------------------------------------------------

Faceted Search dialog when configured provides a plethora of
possibilities to define a vast range of search criteria which the user
can use to narrow down the search results to meet various requirements.

Prerequisites
-------------

To configure this functionality, a user must already have the
Application Editor Screen (Parts / Vehicles) with the Create Application
Action button configured in it. For information on setting up the
required screens and buttons, see the **Application Editor Screen**
topic within this guide[ here]{.mcFormatColor style="color: Blue;"}.

Configuration
-------------

In the following example, the faceted search is configured on the Create
Application Action button in an Application Editor Screen. The
functionality of the Faceted Search dialog differs based on the type of
Application Editor Screen it is configured in. For the Application
Editor Screen configured on the Part object, the Faceted Search dialog
is to be configured to search for an assembly / vehicle as target. And
for the Application Editor Screen configured on the vehicle / assembly
object, the Faceted Search dialog must be configured to search for a
Part object as target. The AutoCare standard will be used as an example
throughout this document.

1.  In the Web UI Designer mode for Application Editor Screen,
    double-click the \'Create Application Action\' in the Actions field
    of the Child Components section.

![](../../../../Resources/Images/Solution%20Enablement/PMDM/Auto-SelectCreateApp.png)

1.  In the \'Create Application Action\' properties, the \'Faceted
    Search Configuration\' option is available in the \'Child
    Components\' section. Select the \'Faceted Search Node Picker
    Dialog\' option from the list, then select \'go to component.\'

![](../../../../Resources/Images/Solution%20Enablement/PMDM/Auto-CreateApplicationButton.png)

1.  Shown in the screenshot below is the Faceted Search Node Picker
    Dialog Properties. Populate the parameters that are listed below.

![](../../Resources/Images/Application%20Editor/28.png)

-   **Find attributes:** This parameter allows multiple attributes to be
    added so that the vehicle / assembly (or part) can be searched based
    on their attribute values in the free text search field available
    within the Faceted Search dialog. By default, the search criteria in
    the free text search field are defined to search based on the ID and
    Name of the object (vehicle / assembly or part). Adding the option
    to search based on the attribute values gives the user a broader
    criteria to search through the free text search field. Click the
    **Add** button to find and select the required attributes. The
    selected attributes must be valid for the object type of the objects
    that are intended to be searched.

```{=html}
<!-- -->
```
-   **Root Nodes:** Allows for root nodes to be added to restrict the
    vehicle / assembly or part search within the Faceted Search dialog.
    Click the **Add** button next to the parameter field to browse or
    search for the hierarchy to search below.

```{=html}
<!-- -->
```
-   **Search Fields:** This parameter allows adding multiple search
    fields that are displayed as facets within the Faceted Search
    dialog. Of the available options, Name Search Field and Hierarchy
    Search Field components can be added only once and Attribute Search
    Field can be added multiple times. The order that the search fields
    are listed determines the order that they will be displayed within
    the Faceted Search dialog. All of the search fields require
    additional configuration. Clicking the Add button next to the Search
    Fields parameter displays an Add Component dialog with the option to
    add one of the following search fields: Attribute Search Field,
    Hierarchy Search Field, and Name Search Field. Steps for configuring
    each search fields can be found in their respective sections below:

```{=html}
<!-- -->
```
-   Configuring Name Search Field ([here]{.mcFormatColor
    style="color: Blue;"})
-   Configuring Hierarchy Search Field ([here]{.mcFormatColor
    style="color: Blue;"})
-   Configuring Attribute Search Field ([here]{.mcFormatColor
    style="color: Blue;"})

Because Name Search Field and Hierarchy Search Field components can be
only be configured once for each Faceted Search dialog, if a second
search field of the same type is added, an Error dialog will display as
shown below, and the Search Fields parameter will remain unchanged.

![](../../Resources/Images/Application%20Editor/25.png)

-   **Search Placeholder:** This parameter defines the text to be
    displayed within the free text search field when no character is
    typed in the free text search field. To make changes to the default
    text in the free text search field, add the custom text to the
    Search Placeholder field. If nothing is added, the Search
    Placeholder default will display \'Search for names, ids, and
    attributes.\'

This is how the default free text search field will display at the top
of the Faceted Search dialog:

![](../../Resources/Images/Application%20Editor/26.png)

-   **Title:** To make changes to the default title in the Faceted
    Search dialog that appears when the user clicks on the Create
    Application Action button, add the custom text to the Title field.
    If nothing is added, the Title default will display as \'Select
    node(s).\'

This is how the Title displays at the top of the Faceted Search dialog:

![](../../Resources/Images/Application%20Editor/27.png)

-   **Node List:** The Faceted Search Node Picker Dialog Properties is
    pre-configured with a Node List in Multi Edit Display Mode. Select
    the \'Node List\' option in the dropdown and click on the \'go to
    component\' to add more table header components in the Node List
    component. For more information, see the **Node List Component**
    topic within the **Web User Interfaces** section of **STEP Online
    Help**[ here]{.mcFormatColor style="color: Blue;"}.

Improving Part Type Accuracy
----------------------------

PRODOC note: BOND RDCUST-3743 The application data model (Automotive -
Application Model) includes a relationship between conditions on
applications and different configurations of vehicles. This is possible
due to the automotive validation path functionality. However, sometimes
the conditions on specific part types need to be considered to ensure
that targets (assembly / vehicle or part) are displayed more accurately.

For example, when searching for a 2013 Audi A3 vehicle for a selected
spark plug, the results table would list both Gas and Diesel engines,
even though Diesel engines do not use spark plugs, and are invalid in
the search results. However, when the validation path functionality is
implemented in conjunction with the \'Missing Application Conditions\'
attribute and the \'Check path for missing application\' business
condition, the search results will display more accurately because the
target search coverage will consider both the Condition and Part Type
values.

To implement this improvement, the automotive validation path
functionality and Check Path for Missing Application Business Condition
must be implemented. For more information, see the **Automotive
Validation Path Functionality** ([here]{.mcFormatColor
style="color: Blue;"}) and the **Business Condition: Check Path for
Missing Application** topics ([here]{.mcFormatColor
style="color: Blue;"}) within this guide.

It should be noted that searching for a large number of objects can
create performance issues. The system gives admins the ability to
display a warning when the number of nodes selected exceeds a configured
maximum by adding the property
Onboarding.FacetedSearchDialogServerComponent.FindMax=1000 in the
sharedconfig.properties file. This property directs the system to
display a warning message to the user if more than 1,000 nodes are set
to display in the search results displayed in the Faceted Search dialog.
The \'=1000\' is the maximum that aligns with Stibo Systems\'
recommended practices, but can be set higher or lower, depending on
customer requirements.
