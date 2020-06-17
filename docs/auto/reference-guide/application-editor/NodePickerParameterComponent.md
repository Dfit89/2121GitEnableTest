---
description: 'Automotive Solution: The Node Picker Parameter component
  allows the user to select the Target node using Node Picker dialog'
title: Node Picker Parameter Component
---

Node Picker Parameter Component
===============================

The **Node Picker Parameter** component is configured within the
Initiate Business Action on Application(s) Properties dialog. This
component assists in executing the defined Business Action that requires
an object selection. Node Picker Parameter component determines which
objects are selectable through the Node Picker dialog.

Below is a screenshot representing the Node Picker Parameter component
that gets displayed when the Business Action that needs an object
selection is initiated for execution.

![](../../Resources/Images/Application%20Editor/50.png)

Configuring the Node Picker Parameter Component
-----------------------------------------------

Follow the steps described below to add and configure the Node Picker
Parameter component that gets displayed when the user executes the
Business Action that needs an object selection via **Business action(s)
for Bulk Update(s)** action button
![](../../Resources/Images/Application%20Editor/Auto-Bulk%20Application%20Updates%20Button.png).

The example below shows a configuration of Node Picker Parameter
component in an Application Editor Screen:

1.  In the Web UI design mode, select the Bulk Applications Updates
    action button configured within the Node List component of the
    required screen (Application Editor Screen / Application Manager
    Screen).
2.  Double click the **Initiate Business Action on Application(s)**
    component if it already exists, if not create a new one by clicking
    the **Add** button within the Business action(s) for Bulk Update(s)
    parameter. For more information, see **Bulk Applications Updates
    Component** topic[ here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/Application%20Editor/51.png)

1.  Under the Child Components section on the Initiate Business Action
    on Application(s) Properties, click the **Add** button under the
    field for Node Selector Dialog parameter. The Add Component dialog
    will display.

![](../../Resources/Images/Application%20Editor/47.png)

1.  Select the Node Picker Parameter component and click **Add**, and
    the \'Add component - configure required properties\' for the \'Node
    Picker Parameter Properties\' dialog will display (as shown below).
    Define the following parameters:

![](../../Resources/Images/Application%20Editor/49.png)

-   **Key:** By default, this required parameter is blank. The value
    entered for this field is used to connect a business rule in the
    system to this Web UI component. Type in the exact characters (key)
    that is entered within the business rule configured within the
    Business Action parameter of Initiate Business Action on
    Application(s) Properties. Uniqueness is the only restriction for
    this key and it is case sensitive. For example, the Business Action
    \'Copy application to other part\' has the value \'CopyApplication\'
    populated within the \'Copy application to other part parameter
    key\' parameter as shown in the image on the left. In order to
    identify this business action, the Key parameter within the Node
    Picker Parameter Properties dialog has to be populated with the same
    value of \'CopyApplication\' as shown within the image on the right.

If the exact key is not entered, then the business rule will not
properly function when executed.

![](../../Resources/Images/Application%20Editor/59.png)

-   **Label:** Within the Label parameter, enter the text that will
    prompt the user as to what they should select when using this
    business action. For example, when the Label parameter is blank the
    parameter within the dialog will display as \'null\' as shown in the
    image on the left. If the Label parameter is populated with \'Base
    vehicle\' the parameter within the dialog will display with \'Base
    vehicle\' as shown within the image on the right.

![](../../Resources/Images/BRs/Change%20Assembly/1.png)

-   **Mandatory:** Enabling this parameter will require the user to
    select a Target node when the Business Action is executed. The
    **OK** button will not be activated unless a valid node is selected
    for the execution of the business action.

```{=html}
<!-- -->
```
-   **Node Picker Configuration:** In the dropdown next to the Node
    Picker Configuration parameter, select Node Picker Dialog option and
    click **Edit**. The \'Edit component\' for the \'Node Picker Dialog
    Properties\' dialog will display. Node Picker Dialog allows the user
    to define the nodes that are presented for selection in the dialog
    and also allows the user to determine how the nodes are selectable.
    For more information about the Node Picker Dialog, see the **Node
    Picker Dialog** topic within the **Web User Interfaces** section of
    **STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.
-   **Valid Node Types:** By default, this parameter is populated with
    the value \'UNKNOWN\_TYPE\', meaning that all node types are valid
    for selection. Click the dropdown located beneath the Valid Node
    Types parameter to select the required node type, and then click the
    Add button so that the required node type is displayed within the
    Valid Node Types parameter.
-   **Valid Object Types:** By default, this parameter is blank. Click
    the Add button beneath the Valid Object Types parameter and then
    select the desired valid object types. This ensures that only the
    defined object types are allowed for the selection.

5.  Click the **Add** button, and the Initiate Business Action on
    Application(s) Properties dialog will display with the Node Picker
    Parameter component listed within the Node Selector Dialog
    parameter.

![](../../Resources/Images/Application%20Editor/52.png)

5.  Click **Save** button to save the configuration.
