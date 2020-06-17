---
description: 'Automotive Solution: Describes how to use the intelligent
  search interface within the Application Manager.'
title: '\[%=Heading.AnyLevel%\]'
---

Using Intelligent Search Interface
==================================

PRODOC note: MEDU RDCUST-2671 BEJA Sprint demo (2/13/18) how the options
filter works on the results

The Application Manager intelligent search interface has been carefully
designed to allow users to quickly and easily select criteria for valid
combinations of different vehicle types, makes, models, years, options
(i.e., sub models, regions), and part types. This allows users to create
accurate search criteria on the fly and benefit from the customized
search results. This is accomplished by allowing users to select only
valid criteria across multiple search boxes per the configuration of the
Vehicle Type Search Panel.

Within an Application Manager screen, the Vehicle Type Search Panel can
be configured to display up to four search box types. Because the
Options Group search box type allows for up to two Options search boxes,
up to five search boxes can be displayed. Within each search box, a
typeahead field is used to view and select valid search criteria.
Because only valid criteria can be selected from each dropdown list, the
Application Manager provides automated intelligence for each search.
Thanks to the synchronization of the search boxes, the valid criteria is
considered upon each selection and within any of the displayed search
boxes, no matter the order of entry.

For example, if the Make/Model search box contains a vehicle that was
only produced from 1994-2010, then the dropdown within the Year search
box will only display those years for selection. Because Chrysler
established Ram trucks as a new brand (Make) beginning with the 2011
model year, the available years are displayed as 1994-2010 when
Make/Model 'Dodge Ram 3500' is selected (as shown below).

![](../../../Resources/Images/AppMgr/Dodge%20Ram%20Example%20Year%20list%20short.png)

The Vehicle Type Search Panel, and its search boxes, have many
configuration options. If your screen, or search criteria dropdown
options display differently than the examples within this section,
contact your Web UI administrator. For more information on configuring
an Application Manager, see the **Configuring Application Manager**
topic ([here]{.mcFormatColor style="color: Blue;"}) within this guide.
For information about the general layout and features of the Application
Manager, see the **Application Manager** topic ([here]{.mcFormatColor
style="color: Blue;"}) within this guide.

However, if the Ram 3500 is added to the Make/Model search box, then the
available years display as 1994-2018 (as shown below).

![](../../../Resources/Images/AppMgr/Dodge%20Ram%20Example%20Year%20list%20long.png)

Additionally, consider being able to easily view the engines used for
selected vehicles. In the screenshot below, a Dodge Ram 3500 is selected
for the Make/Model search box, and some available years have also been
selected. Therefore, when the Engine option is selected for the Options
search box, and the cursor is placed within the search box field, only
those engines used for those vehicles display for selection.

![](../../../Resources/Images/AppMgr/Search%20Make%20Model%20using%20Engine.png)

Taking this example a step further, after selecting Dodge Ram 3500 for
the Make/Model search box, and 6.7L L6, -CC, 408CID for the Engine
options search box, users can easily view the valid years the selected
engine has been was manufactured within the selected vehicle (as shown
below).

![](../../../Resources/Images/AppMgr/Engine.png)

This section addresses the following:

-   **Using Search Boxes** [ here]{.mcFormatColor style="color: Blue;"
    conditions="Primary.Web"}
-   **Search Box Synchronization** [ here]{.mcFormatColor
    style="color: Blue;"}
-   **Using Make/Model Search Box** [ here]{.mcFormatColor
    style="color: Blue;"}
-   **Using Year Search Box** [ here]{.mcFormatColor
    style="color: Blue;"}
-   **Using Options Search Boxes** [ here]{.mcFormatColor
    style="color: Blue;"}
-   **Using Part Type Search Box** [ here]{.mcFormatColor
    style="color: Blue;"}
