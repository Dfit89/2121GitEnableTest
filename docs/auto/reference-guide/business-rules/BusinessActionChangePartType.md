---
description: 'Automotive Solution: Describes the Change Part Type
  Business Action.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Action: Change Part Type
=================================

This automotive business action allows users to change the part type of
one or more existing applications by clicking a Bulk Updates action
button within an Application Manager. However, it cannot change the part
type of a missing application, and thus any missing applications
selected when the bulk update is run will be ignored. For more
information, see the **Missing Application Coverage Functionality**
topic[ here]{.mcFormatColor style="color: Blue;"}. Setup is required
within both STEP Workbench and Web UI for the action to be available to
users.

Once configured, a Bulk Updates button within an Application Manager can
be used to change the part type for an existing application. Below are
the steps for using the business action in Web UI.

![](../../Resources/Images/BRs/Change%20Part%20Type/ButtonMultiple.png)

If only one bulk update is configured, then the Bulk Applications
Updates dialog will not display.

1.  Within the configured Application Manager, search for applications
    and select one or more applications to be changed.
2.  Click the **Bulk Updates** action button. If more than one bulk
    update is configured, the Bulk Applications Updates dialog will
    display (as shown above), otherwise this dialog is skipped and the
    Change Part Type dialog will display (skip to step 5 below).
3.  Select the Change Part Type radio button from the list displayed
    within the Bulk Application Updates dialog. For this example,
    \'Change Part Type\' is used, but the business action name displayed
    within the list is dependent upon the business action\'s Name
    parameter.
4.  Click the **OK** button and the Change Part Type dialog will
    display. For this example, \'Change Part Type\' is used, but the
    title of this dialog is controlled by the business action\'s Name
    parameter.
5.  Select the desired part type for the application(s).
6.  Click the **OK** button to close the dialog, and a background
    process notification will display.

```{=html}
<!-- -->
```
1.  Click the BGP link to view the Background Process Details screen, or
    look for the gray background process (BGP) notification icon to
    display with a green dot
    ![](../../../../Resources/Images/WebUserInterfaces/BackgroundProcess/BGP%20Notification%20Icon%20Success.png)
    or orange dot
    ![](../../../../Resources/Images/WebUserInterfaces/BackgroundProcess/BGP%20Notification%20Icon%20Errors.png)
    Notification icon. Once the business action has completed
    successfully, the gray background process (BGP) notification icon
    will display with a green dot
    ![](../../../../Resources/Images/WebUserInterfaces/BackgroundProcess/BGP%20Notification%20Icon%20Success.png).
    If the business action has failed or completed with errors, the BGP
    notification icon will display with an orange dot
    ![](../../../../Resources/Images/WebUserInterfaces/BackgroundProcess/BGP%20Notification%20Icon%20Errors.png).
    For more information, see the **Background Process Notification
    Component** topic[ here]{.mcFormatColor style="color: Blue;"}.

If the business action BGP fails, access the Background Process Details
page for more information.

Before completing this business action, by default, STEP confirms that
the application\'s part type matches one or more part types assigned to
the part. If one or more part types associated with the application\'s
part do not match the application\'s part type, then an error can occur.
However, this functionality can be overridden by using the \'Ignore Part
Type\' parameter within the business action. For more information, see
the **Configuring the Change Part Type Business Action in Workbench**
topic[ here]{.mcFormatColor style="color: Blue;"}.

In the example below, the Background Process Details screen displays the
failed BGP with the following error message: Selected part did not match
part type from application \[application ID\].

![](../../Resources/Images/BRs/Change%20Part/4.png)

1.  Once the background process has completed, click the **Find
    applications** button to display the newly created application(s)
    within the Application Manager results table.

![](../../Resources/Images/BRs/Change%20Part%20Type/ChangePartTypeResults.png)

-   Configuring the Change Part Type Business Action in Workbench
    ([here]{.mcFormatColor style="color: Blue;"})
-   Configuring the Change Part Type Business Action in Web UI
    ([here]{.mcFormatColor style="color: Blue;"})
