---
description: 'Automotive Solution: Describes how to configure the
  Application Approval Status Table Header component for the Application
  Manager Screen and Application Editor Screen. This Header is used to
  display approval status of the applications.'
title: '\[%=Heading.AnyLevel%\]'
---

Application Approval Status Table Header
========================================

PRODOC note: BOND PRODOC-1856 When configured, the \'Application
Approval Status\' component can be used to display the approval status
of the application records within an Application Manager Results Table
and/or Application Editor Screen. The addition of this column will help
filter the applications based on their approval status. Additionally,
within a cell, an Information icon
(![](../../../../Resources/Images/AppMgr/ResultsTable/2.png)) will be
visible that provides detailed information on the approval status.

Prerequisites

It is expected that anyone configuring the Application Approval Status
component is familiar with the Web UI Designer as basic concepts for
working with the designer are not covered in this section. In addition,
the user must have appropriate privileges to access the designer.
Additional information can be found in the **Designer Access** section
of the **Web User Interfaces / Web UI Getting Started** documentation[
here]{.mcFormatColor style="color: Blue;"}.

For information about accessing and configuring the Node List component,
see the **Node List Component** topic within the **Web User Interfaces**
section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration Steps

The Application Approval Status component can be added within any of the
display modes available in the Node list Properties for the selected
Application Manager Screen (or Application Editor Screen). Each of the
parameters for the Application Approval Status Properties are described
below.Below are the steps to configure the Application Approval Status
component.

1.  Using the Web UI designer as shown in the image below, go to Node
    List Properties \> Multi Edit Display Mode Headers parameter for the
    Application Manager Screen (or Application Editor Screen) that needs
    to display application approval status.
2.  Click the **Add** button for the Headers parameter, and the Add
    Component dialog will display.
3.  Find and select the **Application Approval Status** component.
4.  Click the **Add** button, and the Application Approval Status
    Properties dialog will display (as shown below).

![](../../../../Resources/Images/AppMgr/ResultsTable/3.png)

5.  Optionally, populate the parameters listed below.

-   **Dimensions:** By default, the parameter is blank. Optionally, to
    configure the column width and height, select \'Table Header
    Dimensions.

```{=html}
<!-- -->
```
-   **Label:** By default, the parameter is blank. But after clicking
    the **Add** button, the default column header label (Approval
    Status) will be stored. Optionally, enter the desired label to be
    displayed as the column header within the Application Manager
    results table.
-   **Table Sorting:** By default, the parameter is blank. Optionally,
    select from the dropdown values to specify the default sorting order
    of the column data.

6.  Once the required parameters are populated, the Add button will
    activate. Click the **SAVE** button to save the newly added
    component to the Headers parameter.
7.  Optionally, on the Node List Properties Headers parameter, use the
    **Up** and/or **Down** buttons to configure the order in which the
    newly added column should display within the results table.
8.  Click the **Save** and **Close** buttons for the designer.

When a search is performed in the Application Manager Screen, the
Application Manager results table will display the application records
with the approval status of each application as shown below.

![](../../../../Resources/Images/AppMgr/ResultsTable/4.png)

There are three Approval statuses that can be displayed:

-   **Approved:** This status is displayed when the object and all of
    its parent nodes and referenced target objects are fully approved.
-   **Can\'t be approved:** This status is displayed when the object has
    either never been approved, or that the object cannot be fully
    approved because there are parent nodes or referenced target objects
    that have not been fully approved yet.
-   **Not approved:** This status is displayed when the target has been
    previously fully approved but now a change has been made in the
    object that requires it to be approved again (such as changing an
    attribute value).

And when users click on the Information icon
(![](../../../../Resources/Images/AppMgr/ResultsTable/2.png)), the
reason(s) for the application record for not being approved or cannot be
approved is displayed as shown below.

![](../../../../Resources/Images/AppMgr/ResultsTable/5.png)
