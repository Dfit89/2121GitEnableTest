---
description: 'Automotive Solution: Bulk Applications Updates component
  allows users to bulk update the application records. This component is
  available as a toolbar action for Node Lists.'
title: '\[%=Heading.Level1%\]'
---

Bulk Applications Updates Component
===================================

The Bulk Applications Updates component allows users to execute
configured Business Action(s) on selected application records. This
component is available as a toolbar action for Node Lists, and is
commonly used within the Application Editor Screen and Application
Manager Screen. One of the notable features of this component is that it
allows users to add any number of Business Actions. If more than one
Business Action is configured, then the Bulk Applications Updates dialog
will display the options for the user to select the desired Business
Action to be executed.

![](../../Resources/Images/Application%20Editor/10.png)

Configuring the Bulk Applications Updates Component
---------------------------------------------------

In the Application Editor Screen and Application Manager Screen, users
need to add and configure the Bulk Applications Updates component within
the Actions field of the Node List. The following process details how to
add and configure the Bulk Applications Updates component as a toolbar
action in a Node List.

1.  First, add the component. Under Child Components on the Node List
    Properties screen in the designer, click the **Add** button under
    the field for the Actions parameter.

![](../../Resources/Images/Application%20Editor/13.png)

1.  Then select **Bulk Applications Updates** from the component list.
    Click **Add**.

![](../../Resources/Images/Application%20Editor/37.png)

1.  Once added to the list of actions for the Node List, double-click
    the **Bulk Applications Updates** component to configure.

![](../../Resources/Images/Application%20Editor/36.png)

1.  In the Bulk Applications Updates Properties dialog, define the
    following parameters:

![](../../Resources/Images/Application%20Editor/38.png)

-   **Icon Style Class**: This parameter allows a custom icon to be
    displayed on the action button.
-   **Label**: To make changes to the default button label, add the
    custom text to the Label field. If nothing is added, the Label
    default will display as \'Business action(s) for Bulk Update(s).\'

This is how the button will display at the top of the Application Editor
Screen:

![](../../Resources/Images/Application%20Editor/Auto-Bulk%20Application%20Updates%20Button.png)

-   **Title**: To make changes to the default title of the dialog that
    appears when the user clicks on the Bulk Applications Updates
    button, add the custom text to the Title field. If nothing is added,
    the Title default will display as \'Bulk Applications Updates.\'

This is how the title will display at the top of the dialog when the
user clicks on the Business action(s) for Bulk Update(s) button:

![](../../Resources/Images/Application%20Editor/42.png)

The Bulk Applications Updates dialog will be displayed only when there
is more than one Business Action configured within the component. This
dialog prompts users to select the desired Business Action to be
executed. **The presence of only one bulk update will not display this
dialog and the configured sole Business Action gets executed (without
any confirmation dialog) when the user clicks on the Business action(s)
for Bulk Update(s) button.**

-   **Business action(s) for Bulk Update(s)**: This parameter lets users
    add one or multiple Business Actions that gets displayed as radio
    buttons to select when the user clicks the action button in the
    screen.

5.  Click the **Add** button under the field for **Business action(s)
    for Bulk Update(s)** parameter to add Business Action(s) that needs
    to be executed. Then the **Add Component** dialog will display.

[![](../../Resources/Images/Application%20Editor/44.png)](../../Resources/Images/Application%20Editor/44.png)

5.  Select the **Initiate Business Action on Application(s)** component
    from the component list and then click **Add**, and the Initiate
    Business Action on Application(s) Properties will display as shown
    below.

![](../../Resources/Images/Application%20Editor/45.png)

1.  In the Initiate Business Action on Application(s) Properties dialog,
    define the following parameter:

**Business Action**: This parameter allows the user to configure a
Business Action that is intended to be executed on the selected
application records in the Application Editor Screen or Application
Manager Screen. to find and select the required Business Action. Click
the **OK** button once the Business Action has been selected.

8.  Click the **Add** button and the Initiate Business Action on
    Application(s) component will be listed within the Business
    action(s) for Bulk Update(s) parameter as shown below.

![](../../Resources/Images/Application%20Editor/46.png)

9.  Double-click on the Initiate Business Action on Application(s)
    component listed within the Business action(s) for Bulk Update(s)
    parameter to define the type of node selector dialog that needs to
    be displayed if the business action configured within the Business
    Action parameter needs an object selection when executed.

If the configured business action requires an object selection, click
the **Add** button available under the field for **Node Selector
Dialog** parameter. Node Selector Dialog allows the user to determine
how the nodes are selected.

Configure the required Node Selector Dialog as detailed in the following
topics:

-   **Faceted Search Parameter Dialog** ([here]{.mcFormatColor
    style="color: Blue;"})
-   **Node Picker Parameter Dialog** ([here]{.mcFormatColor
    style="color: Blue;"})
-   **String Parameter Dialog**

![](../../Resources/Images/Application%20Editor/47.png)

Using Business Action(s) for Bulk Update(s) Action
--------------------------------------------------

The **Business action(s) for Bulk Update(s)** button
(![](../../Resources/Images/Application%20Editor/Auto-Bulk%20Application%20Updates%20Button.png))
is enabled when one or more application records are selected in the
search results table. If more than one Business Actions are configured
then the Bulk Applications Updates dialog will display, prompting users
to select the desired Business Action to be executed.

1.  Perform a search for applications.
2.  Select the application records that are to be updated.

```{=html}
<!-- -->
```
3.  Click the **Business action(s) for Bulk Update(s)** button
    (![](../../Resources/Images/Application%20Editor/Auto-Bulk%20Application%20Updates%20Button.png))
    that is available in the toolbar of the screen.

If only one Business Action has been configured, then the bulk update
will be done instantly without a dialog window being displayed. In this
case, it is suggested that the Label of the button be changed to
something that is more meaningful for the user to relay what the bulk
update will do (for example: \'Change Part\').

If more than one Business Actions are configured, then a dialog window
will be displayed with the available Business Actions for the user to
select. Below is an example of two Business Actions that have been
configured.

![](../../Resources/Images/Application%20Editor/10.png)

1.  Select the required Business Action that is to be executed by
    clicking the radio button, and then click **OK**.

If the Business Action requires an object selection, then the Node
Picker Dialog will display. Select the required object and click **OK**
to close the dialog.

The \'Started background process\' dialog (shown below) will be
displayed at the top of the screen. Optionally, click the Background
Process Link (BGP\_109137) to view the detailed execution of the
background process within the Background Process Details screen.

![](../../Resources/Images/Application%20Editor/48.png)

This action button can be configured to execute different Business
Actions. The following use cases are contained within the **Automotive
Business Rule Plugins** section ([here]{.mcFormatColor
style="color: Blue;"})

-   **Business Action: Change Assembly** [ here]{.mcFormatColor
    style="color: Blue;"}
-   **Business Action: Change Part Type** [ here]{.mcFormatColor
    style="color: Blue; font-weight: normal;"}
-   **Business Action: Change Part** [ here]{.mcFormatColor
    style="color: Blue; font-weight: normal;"}
-   **Business Action: Copy Application to Other Assembly** [
    here]{.mcFormatColor style="color: Blue; font-weight: normal;"}
-   **Business Action: Copy Application to Other Part** [
    here]{.mcFormatColor style="color: Blue;"}
-   **Business Action: Copy Applications to Related Parts** [
    here]{.mcFormatColor style="color: Blue;"}
