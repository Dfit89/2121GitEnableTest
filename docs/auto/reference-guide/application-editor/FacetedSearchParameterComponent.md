---
description: 'Automotive Solution: The Faceted Search Parameter
  component allows the user to select the Target node using Faceted
  Search dialog.'
title: Faceted Search Parameter Component
---

Faceted Search Parameter Component
==================================

The Faceted Search Parameter component is configured within the Initiate
Business Action on Application(s) Properties dialog. This component
assists in executing the defined Business Action that requires an object
selection. Faceted Search Parameter component determines that the
objects are selectable through the Faceted Search dialog.

Below is a screenshot representing the Faceted Search Parameter
component that gets displayed when the Business Action that needs an
object selection is initiated for execution.

![](../../Resources/Images/Application%20Editor/54.png)

Configuring the Faceted Search Parameter Component
--------------------------------------------------

Follow the steps described below to add and configure the Faceted Search
Parameter component that gets displayed when the user executes the
Business Action (that needs an object selection) via **Business
action(s) for Bulk Update(s)** action button
![](../../Resources/Images/Application%20Editor/Auto-Bulk%20Application%20Updates%20Button.png).

The example below shows a configuration of the Faceted Search Parameter
component in an Application Editor Screen:

1.  In the Web UI design mode, select the Bulk Applications Updates
    action button configured within the Node List component of the
    required screen (Application Editor Screen / Application Manager
    Screen).
2.  Double click the Initiate Business Action on Application(s)
    component if it already exists, otherwise, create a new one by
    clicking the **Add** button within the Business action(s) for Bulk
    Update(s) parameter. For more information, see **Bulk Applications
    Updates Component** topic[ here]{.mcFormatColor
    style="color: Blue;"}.

![](../../Resources/Images/Application%20Editor/51.png)

1.  Under the Child Components section on the Initiate Business Action
    on Application(s) Properties, click the **Add** button under the
    field for Node Selector Dialog parameter. The Add Component dialog
    will display.

![](../../Resources/Images/Application%20Editor/47.png)

1.  Select Faceted Search Parameter component and click **Add**, and the
    Faceted Search Parameter Properties dialog will display. Define the
    following parameters:

![](../../Resources/Images/Application%20Editor/55.png)

-   **Key:** By default, this required parameter is blank. The value
    entered for this field is used to connect a business rule in the
    system to this Web UI component. Type in the exact characters (key)
    that is entered within the business rule configured within the
    Business Action parameter of Initiate Business Action on
    Application(s) Properties. Uniqueness is the only restriction for
    this key and it is case sensitive. For example, the business Action
    \'Copy application to other part\' has the value \'CopyApplication\'
    populated within the \'Copy application to other part parameter
    key\' parameter as shown in the image on the left. In order to
    identify this business action, the Key parameter within the Faceted
    Search Parameter Properties dialog has to be populated with the same
    value of \'CopyApplication\' as shown within the image on the right.

If this key is not entered exactly in both places, then the business
rule will not properly function when executed.

![](../../Resources/Images/Application%20Editor/58.png)

-   **Label:** Within the Label parameter, enter text that will prompt
    the user as to what they should select when using this business
    action. For example, when the Label parameter is blank the parameter
    within the dialog will display as \'null\' as shown in the image on
    the left. If the Label parameter is populated with \'Base vehicle\'
    the parameter within the dialog will display with \'Base vehicle\'
    as shown within the image on the right.

![](../../Resources/Images/BRs/Change%20Assembly/1.png)

-   **Mandatory:** Enabling this parameter will require the user to
    select a Target node when the Business Action is executed. The
    **OK** button will not be activated unless a valid node is selected
    for the execution of the business action.

```{=html}
<!-- -->
```
-   **Valid Object Types:** By default, this parameter is blank. Click
    the **Add** button beneath the Valid Object Types parameter and then
    select the desired valid object types. This ensures that only the
    defined object types are allowed for the selection.

5.  Click the **Add** button, and the Initiate Business Action on
    Application(s) Properties dialog will display with the Faceted
    Search Parameter component listed within the Node Selector Dialog
    parameter.

![](../../Resources/Images/Application%20Editor/56.png)

5.  To further define a search criteria, double click the **Faceted
    Search Parameter** component listed within the Node Selector Dialog
    parameter.

![](../../Resources/Images/Application%20Editor/57.png)

7.  Under the Child Component section go to \> Faceted Search
    Configuration \> Faceted Search Node Picker Dialog \> and click **go
    to component**. The \'Faceted Search Node Picker Dialog Properties\'
    dialog will display. Faceted Search Node Picker Dialog allows the
    user to define a search criteria that are presented for selection.
    For more information about the Faceted Search Node Picker Dialog,
    see the **Faceted Search Dialog** topic within this section[
    here]{.mcFormatColor style="color: Blue;"}.
8.  Click **Save** button to save the configuration.
