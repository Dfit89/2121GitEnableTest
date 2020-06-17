---
description: 'Automotive Solution: Describes the features available
  within the Application Manager Results table and toolbar.'
title: '\[%=Heading.AnyLevel%\]'
---

Results Table and Toolbar
=========================

PRODOC note: MEDU Peer reviewed by ERPO The bottom half of the
Application Manager screen offers features related to the results table
and its toolbar. The top half of the screen is dedicated to the
intelligent search interface. For more information about the intelligent
search interface, see the **Intelligent Search Interface** topic[
here]{.mcFormatColor style="color: Blue;"}.

This section provides an overview of the results table and toolbar and
addresses the following:

-   Results Table Default Columns ([here]{.mcFormatColor
    style="color: Blue;"})
-   Controlling Display of Conditions in Application Manager
    ([here]{.mcFormatColor style="color: Blue;"})
-   Creating Applications ([here]{.mcFormatColor style="color: Blue;"})

Results Table and Toolbar Overview

Results Table and Toolbar Overview {#results-table-and-toolbar-overview conditions="Primary.Web"}
----------------------------------

The results table and toolbar of an Application Manager screen are
composed of the following:

![](../../../Resources/Images/AppMgr/ResultsTable/Results%20Table%20Overview.png)

1.  **Results table toolbar**

![](../../../../../Resources/Images/Data%20Governance/ResultToolbar.png)

Contains action buttons relative to the Application Manager results
table. Action buttons can be configured using the Web UI Designer. For
more information about action buttons, see the **Action Buttons**
section of the **Web User Interfaces** guide within **STEP Online
Help**[ here]{.mcFormatColor style="color: Blue;"}.

-   **Button labels:** When the \'Include Labels\' parameter within the
    Node List Properties is disabled, the labels for each icon within
    the toolbar will not display. However, when a user hovers over an
    icon, help text will display.
-   **Clear all / Select all:** The \'Clear all\' button displays when
    one or more rows are selected using the \'row selection boxes.\'
    When no rows are selected, the \'Select all\' button will display.
    Clicking the \'Clear all\' button will remove the selections within
    the \'row selection boxes.\' Clicking this button will not clear the
    actual table results, but rather disables the selection of \'row
    selection boxes.\' Clicking the \'Select all\' button enables the
    \'row selection boxes\' for each row within the results table.
-   **Clear filter:** The \'Clear filter\' button displays when one or
    more filters are applied to columns in the Results table. Clicking
    the \'Clear filter\' button will remove any filter selections within
    the Results table columns but will not clear the actual table
    results. Within the filter dialog for each column is a \'Reset
    filter\' button that can be used to reset the filter setting for
    each column. Additionally, the \'Clear All\' link above the Results
    table (not to be confused with the \'Clear all\' action button
    within the Results table toolbar) can be used to clear all filters
    and search criteria. For more information, see the **Clear All
    link** section of the **Intelligent Search Interface** topic[
    here]{.mcFormatColor style="color: Blue;"}.
-   **Compressed / Normal view:** By default, the table results display
    using the \'Normal view.\' Clicking the 'Compressed view' button
    will compress the values displayed in the Options column by removing
    the attribute labels and displaying only the attribute values. When
    the table displays as compressed, the \'Normal view\' button will
    display within the toolbar instead of the \'Compressed view\'
    button.
-   **Delete:** For the Delete button to display, one or more rows must
    be selected by enabling \'row selection boxes.\' No warning nor
    confirmation dialog will display, and the application (and its data)
    will be permanently deleted.
-   **Bulk Updates:** For the Bulk Updates button to display, one or
    more rows must be selected by enabling the \'row selection boxes.\'
    The Bulk Updates action button is not configured automatically by
    Easy Setup Actions, and must be configured for use with Automotive
    Business Rule Plugins. For more information, see the **Automotive
    Business Rule Plugins** section within the **Automotive Reference
    Guide**[ here]{.mcFormatColor style="color: Blue;"}.
-   **Export:** For the Export button to display, one or more rows must
    be selected by enabling \'row selection boxes.\' The Export action
    button is not configured automatically by Easy Setup Actions. To
    properly function, a Web UI Designer User must add an export
    configuration to the \'Narrowed Export Configurations\' parameter of
    the Export action button. If the Export button has not yet been
    configured, and the button is selected, a \'No export configurations
    found\' warning message will display (as shown below).

![](../../../Resources/Images/AppMgr/ResultsTable/ExportWarning.jpg)

-   **Create Collection:** For the Create Collection button to display,
    one or more rows must be selected by enabling \'row selection
    boxes.\' Clicking the Create Collection button displays a \'Create
    New Collection\' dialog where users can provide a Name of the new
    collection, and select a Collection Group to store the collection
    in. For more information, see the **Collections** topic within the
    **Getting Started Section** of the **STEP Online Help**[
    here]{.mcFormatColor style="color: Blue;"}.

2.  **Flip table icon**

![](../../../Resources/Images/AppMgr/ResultsTable/Flip%20table%20icon.png)

Allows users to change or flip the orientation of the table.

2.  **Row selection boxes**

![](../../../Resources/Images/AppMgr/ResultsTable/Row%20selection%20boxes.png)

Allows for selection of one or more rows within the table. Selecting at
least one row can change the action buttons that display within the
toolbar.

2.  **Number of items**

![](../../../Resources/Images/AppMgr/ResultsTable/Number%20of%20items.png)

List the total number of rows available for display within the results
table.

```{=html}
<!-- -->
```
5.  **Column Headers**

![](../../../Resources/Images/AppMgr/ResultsTable/Column%20Headers.png)

Displays the column headings as configured within the Headers parameter
for the Node List Properties Child Component of the Application Manager.

-   **Sorting and filtering columns:** Each column displays a black dot
    to the right of the Heading. Clicking the black dot will display the
    sort and filter options for the column. By default, search results
    are sorted by the Vehicle column. When a sort selection is made an
    up or down arrow displays in place of the black dot, indicating the
    search is respectively ascending or descending. When a filter
    selection is made, a black filter displays in place of the black
    dot. This makes it easy for users to identify any sorting and/or
    filtering applied to the results table. When one or more filters are
    applied, the \'Clear filter\' button within the toolbar can be used
    to clear all the filters. Otherwise, any sort and filter selections
    made will remain (even after conducting a new search) until the
    Application Manager page is exited.

By default, the following components are configured within the Headers
parameter for the Node List Properties Child Component of the
Application Manager:

-   Application Set Assembly (labeled as \'Vehicle\')
-   Application Part Type Title Header (labeled as \'Part Terminology\')
-   Application Set Part (labeled as \'Part Number\')
-   Application Condition Header - Individual (labeled as \'Additional
    Options,\' but displays the relative attribute name.) In the example
    above, ACES Fuel Type and ACES Position are displayed because the
    attributes are linked to a part type with the display condition set
    to 'true.' For more information on how to display linked attributes,
    see the **Business Action : Set condition Links on Part Types**
    topic within the **Automotive Business Rule Plugins** section[
    here]{.mcFormatColor style="color: Blue;"}.
-   Application Condition Header - Group (labeled as \'Options\')
-   Application Comment (labeled as \'Notes\')
-   Application Asset Reference (labeled as \'Assets\')

For information on adding columns to the results table, see the **Adding
Additional Headers to Application Screens** topic within the
**Automotive Quick Start Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

When the Easy Setup actions for the AutoCare solution are completed, the
\'ACES Application Qualifiers\' component is automatically configured
(labeled as \'Qualifiers\') in addition to the components listed above.

6.  **Edited items panel**

![](../../../Resources/Images/AppMgr/ResultsTable/Edit%20Items%20panel.png)

Contains an expand / collapse arrow, Save, and Reset buttons. When the
panel is expanded and changes are made to the results table, the changes
are displayed as a list in the panel. In the example above, it is easy
to see that the 2008 Acura application has been edited. By default, the
\'Use Immediate Save\' parameter within the Node List Properties is
disabled. When enabled, the Save button will not display, and the list
of edited items will briefly display.

6.  **Edit icons**

![](../../../Resources/Images/IconEdit.jpg)

Clicking on any one of the Edit icons within the results table will
display a Value editor dialog where the value ID and/or Name are
displayed. From a Value editor dialog, users can add and/or remove
References.

6.  **Hyperlinks**

![](../../../Resources/Images/AppMgr/ResultsTable/hyperlinks.jpg)

When text within the results table displays as a hyperlink, users are
able to click the text and a screen specific to that text will display.
The most common use of this is with the Part Terminology
(classifications) and Vehicle columns.

-   **Classification Hyperlinks:** For classification hyperlinks to
    display within a results table, a Node Details component should be
    used to create a \'Classification Details\' screen that is
    configured to display details about the classification object types.
    To make sure this screen displays when a classification is selected
    within the results table, be sure to add the necessary Mappings to
    the Web UI MAIN screen. For more information, see the **Mappings**
    topic within the **Main Properties Overview** of the **STEP Online
    Help**[ here]{.mcFormatColor style="color: Blue;"}.
-   **Part Number Hyperlinks:** For Part Number hyperlinks to display
    within a results table, the \'Enable Link\' parameter must be
    enabled within the \'Application Set Part\' component. By default,
    this is enabled. When a user clicks a part number hyperlink, an
    Application Editor screen will display. Values within cells can be
    edited by double-clicking in a cell. Once a cell is active, a
    typeahead or Node Picker can be used to select a new value. For more
    information, see the Application Editor Screen topic.
-   **Vehicle Hyperlinks:** For Vehicle hyperlinks to display within a
    results table, the \'Enable Link\' parameter must be enabled within
    the \'Application Set Assembly\' component. By default, this is
    enabled. When a user clicks a vehicle hyperlink, an Application
    Editor screen will display. Values within cells can be edited by
    double-clicking in a cell. Once a cell is active, a typeahead or
    Node Picker can be used to select a new value. For more information
    about an Application Editor Screen, see the Application Editor
    topic. For more information about this component, see the
    Application Set Assembly topic.

9.  **Results table**

![](../../../Resources/Images/AppMgr/ResultsTable/Results%20Table%20grid.png)

The example above is from an AutoCare Application Manager. However,
NAPA and TecDoc Application Managers use the same results table
settings, but the AutoCare specific headers are removed. The vehicle
names and part numbers shown above display as plain text because the
\'Enable Link\' parameter for the \'Application Set Assembly\' and
\'Application Set Part\' components are disabled.

A Node List component is used to display the results of selections made
within the intelligent search interface. This includes criteria selected
within the Vehicle Type Search Panel, and selections made within the
Existing and Missing Applications and Hierarchy Restriction dropdowns.
For more information on the intelligent search interface, see the
**Intelligent Search Interface** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Once the Search button is clicked, valid results display within the
results table. However, it is possible to click the Search button and
have zero results display. For example, if the \'Existing Applications
Only\' dropdown option is selected, and the search criteria is limited
to vehicles types that do not have any applications, then a \'No
Result\' dialog will display, and the results table will only display
column headings. When results are displayed within the results table,
users have the option to create, edit, or delete part application data.

For more information on column headers, and editing data using the
different Header components, see the **Results Table Default Columns**
topic[ here]{.mcFormatColor style="color: Blue;"}.

Each column label can be edited as needed by accessing the Application
Manager Node List Properties Child Component Headers parameter.

Additionally the results table can be configured as read-only, as
described in the **Making Application Editor Screens Read-Only** topic
within the **Automotive Reference Guide** found within the **Solution
Enablement** section of **STEP Online Help**.
