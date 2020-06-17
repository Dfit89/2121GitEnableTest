---
description: 'Automotive Solution: Describes the Change Assembly
  Business Action.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Action: Change Assembly
================================

This automotive business action allows users to use a Bulk Updates
action button within an Application Manager to change the assembly /
vehicle of one or more existing applications. However, it will not
change the assembly / vehicle of a missing application, and thus any
missing applications selected when the bulk update is run will be
ignored. For more information about missing coverage, see the **Missing
Application Coverage Functionality** topic ([here]{.mcFormatColor
style="color: Blue;"}) within this guide.

Once configured, a Bulk Updates button within an Application Manager can
be used to change the assembly for one or more existing application.
Below are the steps for using the business action in Web UI.

![](../../Resources/Images/BRs/Change%20Assembly/7.png)

If only one bulk update is configured, then the Bulk Applications
Updates dialog will not display.

1.  Within the configured Application Manager, search for applications
    and select one or more applications to be changed.
2.  Click the **Bulk Updates** action button. If more than one bulk
    update is configured then the Bulk Updates dialog will display (as
    shown above), otherwise this dialog is skipped and the change
    assembly dialog will display (skip to step 5 below).
3.  Select the Change Base Vehicle Assembly radio button from the list
    displayed within the Bulk Applications Updates dialog. For this
    example, \'Change Base Vehicle Assembly\' is used, but the business
    action name displayed within the list is dependent upon the business
    action\'s Name parameter.

```{=html}
<!-- -->
```
1.  Click the **OK** button and the change assembly dialog will display.
    For this example, \'Change Base Vehicle Assembly\' is used, but the
    title of this dialog is controlled by the business action\'s Name
    parameter.
2.  Select the desired assembly / vehicle for the application(s).
3.  Click the **OK** button to close the dialog, and a background
    process notification will display.
4.  Once the background process has completed, click the **Find
    applications** button to display the newly created application(s)
    within the Application Manager results table.

![](../../Resources/Images/BRs/Change%20Assembly/Results.png)

-   Configuring the Change Assembly Business Action in Workbench
    ([here]{.mcFormatColor style="color: Blue;"})
-   Configuring the Change Assembly Business Action in Web UI
    ([here]{.mcFormatColor style="color: Blue;"})
