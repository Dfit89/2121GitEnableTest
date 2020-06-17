---
description: 'Automotive Solution: Describes how to configure the
  Suggested Part Number Table Header component for the Application
  Manager Screen. This Header is used to display the potential parts
  fitting the missing applications.'
title: '\[%=Heading.AnyLevel%\]'
---

Suggested Part Number Table Header
==================================

PRODOC note: BOND PRODOC-XXXX When configured within an Application
Manager Results Table, the \'Suggested Part Number\' component can be
used to display the potential parts fitting the missing application. The
suggested parts are listed in a column against each result in the
Application Manager screen. Users can double click on the cell to open
up the Value Editor window and can add the suggested parts to the
missing application.

Prerequisites

It is expected that anyone configuring the Suggested Part Number
component is familiar with the Web UI Designer, as basic concepts for
working with the designer are not covered in this section. In addition,
the user must have appropriate privileges to access the designer.
Additional information can be found in the **Designer Access** section
of the **Web User Interfaces / Web UI Getting Started** documentation[
here]{.mcFormatColor style="color: Blue;"}.

For information about accessing and configuring the Node List component,
see the **Node List Component** topic within the **Web User Interfaces**
section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

For information about how the Application Manager results table displays
the missing application for a search criteria, see the **Missing
Application Coverage Functionality** topic within the **Application
Manager** section of this guide[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration Steps

The Suggested Part Number component is added within any of the display
modes available in the Node list Properties for the selected Application
Manager screen. Each of the parameters for the Application Approval
Status Properties are described below. Follow the steps below to
configure the Suggested Part Number component.

1.  Using the Web UI designer as shown in the image below, go to Node
    List Properties \> Display Modes parameter for the Application
    Manager Screen that needs to display potential product.

![](../../../../Resources/Images/AppMgr/ResultsTable/11.png)

2.  Add a display mode (or edit the one that exists) by clicking the
    **Add** button available next to the Display Modes parameter.
3.  Double click to enter the added (or available) display mode, click
    the **Add** button for the Headers parameter, and the Add Component
    dialog will display.
4.  Find and select the **Suggested Part Numbers** component.
5.  Click the **Add** button, and the Suggested Part Number Properties
    designer screen will display (as shown below).

![](../../../../Resources/Images/AppMgr/ResultsTable/6.png)

1.  Populate the parameters listed below:

-   **Display ID:** Determines if the ID or name or the attribute value
    of the suggested part number to be displayed within the table cell.
    By default, the parameter uses the \'NODE\_ID\' value that allows
    the ID of the suggested part number to display within the cell.
    Optionally, the \'NAME\_VALUE\' or \'ATTRIBUTE\_VALUE\' value can be
    selected using the dropdown. While the \'NAME\_VALUE\' displays the
    name of the suggested part number, the \'ATTRIBUTE\_VALUE\' allows
    the values of the attribute selected within the \'Attribute\'
    parameter to display within the cell.
-   **Attribute:** This parameter must be populated with an attribute
    that is valid for the suggested part number.

The Attribute parameter should only be populated when the
\'ATTRIBUTE\_VALUE\' value is selected. Otherwise, the defined attribute
value will not be displayed in the cell.

-   **Label:** By default, the parameter is blank, but after clicking
    the **Add** button, the default column header label (Suggested Part
    Number) will be stored. Optionally, enter the desired label to be
    displayed as the column header within the Application Manager
    result\'s table.
-   **Part Suggestions Plugins:** Currently, this parameter allows to
    configure the \'Referenced Parts Suggestion Plugin.\' This plugin is
    used to suggest the part number where the part number is referencing
    the current part that has similar application records defined in the
    Application Manager search criteria. Clicking on the Add button will
    directly display the Referenced Parts Suggestion Plugin Properties
    designer screen. It is mandatory to have at least one reference type
    within the Referenced Parts Suggestion Plugin Properties designer
    screen, so that when a missing application is displayed in the
    Application Manager results table, information about the suggested
    part number (if available) can be displayed. The configured
    reference types must be the associated reference types linked
    between the suggested part number and the current part number.

 

In the example chart below, App-V1P1X1 and App-V2P1X2 are the existing
application records for Part B (that is of Part Type-P1).While the
existing application record App-V1P1X1 is referenced to Vehicle-V1, Part
Type-P1, and Engine Base-X1.

![](../../../../Resources/Images/AppMgr/ResultsTable/7.png)

When the Application Manager performs a search for missing application
records based on the vehicle (V1) and the part type (P1) values, since
there are existing application records for the vehicle (V1) and part
type (P1) defined in the search, the Application Manager checks for the
application records covering all the different configurations of the
vehicle (V1) and displays some missing application records. For
understanding the logic of how the missing applications are calculated
and displayed in the search results, see the **Missing Application
Coverage Functionality** topic within the **Application Manager**
section of this guide[ here]{.mcFormatColor style="color: Blue;"}.

In this scenario, since the Part A is referenced to Part B by the
reference type (Part Relation) configured within the Part Suggestion
Plugins, Part A will be displayed as suggested part number.

-   **Table Headers:** By default, no table headers are listed in this
    parameter. It is required to add at least the ID and the Name
    headers within this parameter. Table headers configured in this
    parameter display the associating information of the suggested part
    number when the user accesses the Value Editor dialog by
    double-clicking the suggested part number cell.

```{=html}
<!-- -->
```
-   **Dimensions:** By default, the parameter is blank. Optionally, to
    configure column width and height, select \'Table Header
    Dimensions.\'

```{=html}
<!-- -->
```
-   **Table Sorting:** By default, the parameter is blank. Optionally,
    select from the dropdown values to specify the default sorting order
    of the column data.

7.  Once the required parameters are populated, the Add button will
    activate. Click the **Add** button (or **Save** button if editing an
    existing component) to save the newly added component to the Headers
    parameter.
8.  Optionally, on the Node List Properties Headers parameter, use the
    **Up** and/or **Down** buttons to configure the order in which the
    newly added column should display within the Results Table.
9.  Click the **Save** and **Close** buttons for the designer.

 

When a search is performed in the Application Manager screen, the
Application Manager Results Table will display the missing application
records with the suggested part number(s) for application as shown
below.

![](../../../../Resources/Images/AppMgr/ResultsTable/8.png)

When users click on the cell, the Value Editor window listing all the
suggested part numbers will be displayed, as shown below.

![](../../../../Resources/Images/AppMgr/ResultsTable/9.png)

Clicking on the add button
(![](../../../../Resources/Images/Competitor%20OE%20Number/43.png){.img_intext})
that is available alongside each part number will applicate the missing
application to the suggested part number.

Clicking the remove button
(![](../../../../Resources/Images/Competitor%20OE%20Number/51.png){.img_intext})
that is available alongside each part number will remove the suggested
part number from the list.

Clicking the info button
(![](../../../../Resources/Images/Release%20Notes/9.3mp2/help%20text%20icon.png))
opens a dialog explaining the reason for suggesting that part number.

![](../../../../Resources/Images/AppMgr/ResultsTable/10.png)
