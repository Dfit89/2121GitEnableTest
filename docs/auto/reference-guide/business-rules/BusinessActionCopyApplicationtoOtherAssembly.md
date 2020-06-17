---
description: 'Automotive Solution: Describes the Copy Application to
  Other Assembly Business Action.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Action: Copy Application to Other Assembly
===================================================

This automotive business action allows users to use a Bulk Updates
action button within an Application Manager to copy one or more existing
applications to another assembly / vehicle. However, it will not copy an
assembly / vehicle that is missing an application, and thus any missing
applications selected when the bulk update is run will be ignored. For
more information, see the **Missing Application Coverage Functionality**
topic ([here]{.mcFormatColor style="color: Blue;"}) within this guide.
Setup is required within both STEP Workbench and Web UI for the action
to be available to users.

Once configured, a Bulk Updates button within an Application Manager can
be used to copy one or more existing applications to another assembly /
vehicle. Below are the steps for using the business action in Web UI.

![](../../Resources/Images/BRs/Copy%20Application%20to%20Other/2.png)

If only one bulk update is configured, then the Bulk Applications
Updates dialog will not display.

1.  Within the configured Application Manager, search for applications
    and select one or more applications to be copied.
2.  Click the **Bulk Updates** action button. If more than one bulk
    update is configured, then the Bulk Updates dialog will display (as
    shown above), otherwise this dialog is skipped and the Copy
    Application To Other Assembly dialog will display (skip to step 5
    below).
3.  Select the Copy Application To Other Assembly radio button from the
    list displayed within the Bulk Application Updates dialog. For this
    example, \'Copy Application To Other Assembly\' is used, but the
    business action name displayed within the list is dependent upon the
    business action\'s Name parameter.
4.  Click the **OK** button and the Copy Application To Other Assembly
    dialog will display. For this example, \'Copy Application To Other
    Assembly\' is used, but the title of this dialog is controlled by
    the business action\'s Name parameter.
5.  Select the desired assembly for the application(s).
6.  Click the **OK** button to close the dialog, and a background
    process notification will display.
7.  Once the background process has completed, click the **Find
    applications** button to display the newly created application(s)
    within the Application Manager results table.

![](../../Resources/Images/BRs/Copy%20Application%20to%20Other/Results.png)

-   Configuring the Copy Application to Other Assembly Business Action
    in Workbench ([here]{.mcFormatColor style="color: Blue;"})
-   Configuring the Copy Application to Other Assembly Business Action
    in Web UI ([here]{.mcFormatColor style="color: Blue;"})
