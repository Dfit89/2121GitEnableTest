---
description: 'Automotive Solution: This Web UI screen topic details how
  to build an Onboarding Mapping Details Screen as well as how to
  implement the screen with the Stack Panel component in Web UI.'
title: '\[%=Heading.Level1%\]'
---

Onboarding Mappings Details Screen
==================================

The Onboarding Mappings Details screen allows users to quickly display
mapping configurations. The **Onboarding mappings navigator** component
functions as a Stack Panel component. For more information, see the
**Tree Navigator Component** in the **Web User Interfaces / Web UI
Getting Started** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration Prerequisites
---------------------------

It is expected that anyone configuring the Onboarding Mappings Details
Screen component is familiar with the Web UI Designer as basic concepts
for working with the designer are not covered in this section. In
addition, the user must have appropriate privileges to access the
designer. Additional information can be found in the [Designer
Access]{.bold} section of the [Web User Interfaces / Web UI Getting
Started]{.bold} documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.

Configuration Process
---------------------

In the designer, create a new screen by selecting \'New.\' Select the
\'Onboarding Mappings Details Screen,\', and create a name for the
screen in the \'Screen ID\' field. In the example below, the Screen
ID is \'Onboarding Mappings Details Screen\'. Click \'Add.\'

![](../../Resources/Images/Data%20Onboarding/6.png)

Once this screen is created, the Onboarding Mappings Details Screen
Properties designer screen displays, which contains the following
parameters for configuration:

![](../../Resources/Images/Data%20Onboarding/7.png)

**Description Attribute:** This parameter allows users to configure an
attribute that holds the description text for the Mapper Configuration
setup entity. The configured attribute must be valid for the object type
belonging to the Mapper Configuration setup entity. Any text string
entered in the \'Description\' field available within the \'Setup\' tab
of the Onboarding Mappings Details screen for the selected Mapper
Configuration setup entity (an example shown below) will be held by the
attribute defined in this parameter.

![](../../Resources/Images/Data%20Onboarding/254.png)

**Mappings:** By default, this required parameter is blank. Click on the
\'Add\' button to add the mapping plugins that admin users should be
able to view and select when configuring the mappings. The following are
the available mapping plugins:

![](../../Resources/Images/Data%20Onboarding/34.png)

**Application Mappings Screen:** This mapping plugin, when configured in
the Mapper Configuration, will take data from the applications on the
Source object to create new applications in the Target object, as well
as establish references for the Target applications to Target vehicles
and Target part types. Double-click the added \'Application Mappings
Screen\' in the Mappings field to rename the plugin name if necessary by
changing the value in the \'Title\' parameter.

![](../../Resources/Images/Data%20Onboarding/35.png)

**Attribute Mappings Screen:** This plugin, when configured in the
Mapper Configuration, will copy attribute values from the Source object
to populate attributes in the Target object. In other words, If the
Source object has an attribute value of \'X,\' then this value can be
copied into a valid attribute of the Target object (with
transformations, if required).For example, if the Source object has an
attribute \'Length\' with a value \'15 mm,\' then this value can be
moved into a target attribute, say \'Distance\' as \'1.5 cm.\'
Double-click the added \'Attribute Mappings Screen\' in the Mappings
field to rename the plugin name if necessary by changing the value in
the Title parameter.

![](../../Resources/Images/Data%20Onboarding/36.png)

**Business Action Mappings Screen:** This plugin, when configured in the
Mapper Configuration, provides an extended flexibility for users to
configure and solve unique mapping cases which cannot be achieved by the
other Mapping plugins (Attribute Mapping, Application Mapping, and
Object to Object Mapping). The Business Action Mapping plugin takes a
business action as a configuration and when executed, executes the
business action on the target object.

![](../../Resources/Images/Data%20Onboarding/253.png)

**Concatenator Mappings Screen:** This plugin, when configured in the
Mapper Configuration, it allows the user to copy and combine multiple
source values into a single target attribute. This plugin is mostly used
while applying different pre, separator and post texts.

![](../../Resources/Images/Data%20Onboarding/252.png)

**Object to Object Mappings Screen:** This plugin, when configured in
the Mapper Configuration, copies any data from the Source object by
using the STEP path to either create child objects on the Target object,
or store the data as attribute values, or as references on the Target
objects. Double-click the added \'Object to Object Mappings Screen\' in
the Mappings field to rename the plugin name if necessary by changing
the value in the Title parameter.

**Buttons:** A number of action buttons can be added to the \'Onboarding
Mappings Details Screen\' to be used with the Mapper Configuration list.
These action buttons are added and configured within the \'Actions\'
field on the Buttons parameter. The \'Save Action\' is required to be
configured. Other actions should be added only when necessary.

The **Delete**, **Duplicate**, and **Reset**) buttons configured within
the Buttons field will delete / duplicate / reset the Mapper
Configuration, NOT the individual mapping plugin rows within the
configuration. If the user does not want to be able to delete the Mapper
Configuration in Web UI, then do not configure the **Delete** Action.

If the Mapper Configuration is deleted in Web UI, then it will get moved
to the Recycle Bin in System Setup. Users can revive the Mapper
Configuration via the \'Maintain\' dropdown \> Revive.

Implementing the Onboarding Mappings Details Screen
---------------------------------------------------

Once the \'Onboarding Mappings Details Screen\' is created,
implementation of the screen requires the following setup:

-   A Global Navigation Panel needs to be configured to access the
    Mapper Configurations
-   A Mapper Configuration object type must be configured to display the
    \'Onboarding Mappings Details Screen\' when a Mapper Configuration
    is selected

### Configuring the Stack Panel {#configuring-the-stack-panel conditions="Primary.Under Construction"}

1.  From the **Main Properties** screen, add a \'Stack Panel\' to the
    \'Left\' section of the child components. Once added, double-click
    the Stack Panel component.

![](../../../../Resources/Images/WebUserInterfaces/MAIN/SelectStackPanel.png)

1.  From the Stack Panel Properties, select \'Add\' in the Items field
    of the Child Components section. Select \'Stack Panel Item\' from
    this dialog.

![](../../Resources/Images/Data%20Onboarding/10.png)

1.  Double-click the Stack Panel Item component to access the
    configuration. In the Stack Panel Item Properties, select the
    \'Onboarding mappings navigator\' in the Content field dropdown of
    the Child Components section.

![](../../Resources/Images/Data%20Onboarding/8.png)

1.  Click on the **go to component** link and, in the \'Onboarding
    mappings navigator Properties,\' next to the \'Setup group root\'
    parameter. Then select the **Mappings** node to define the setup
    group root for mapping configurations. Click \'OK\' to add.

![](../../Resources/Images/Data%20Onboarding/9.png)

When finished, click [Save]{.bold} in the designer to save the current
settings. Do not close the designer unless you have finished configuring
all the other parameters (outlined in the rest of this topic).

### Configuring the Global Navigation Panel

1.  From the **Main Properties** screen, add a \'Global Navigation
    Panel\' to the \'Left\' section of the child components. Once added,
    double-click the Global Navigation Panel component. For Information
    on how to add the Global Navigation Panel, see the **Global
    Navigation Panel** topic in the **Web User Interfaces** / **Web UI
    Getting Started** documentation of the **STEP Online Help**[
    here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/Data%20Onboarding/241.png)

1.  From the Global Navigation Panel Properties, select \'Add\' in the
    Menu Items field of the Child Components section. Select
    \'Onboarding mappings navigator\' from this dialog and then click
    \'Add.\' The \'Onboarding mappings navigator Properties\' designer
    screen will be displayed.

![](../../Resources/Images/Data%20Onboarding/242.png)

1.  In the \'Onboarding mappings navigator Properties,\' next to the
    \'Setup group root\' parameter. Then select the **Mappings** node to
    define the setup group root for mapping configurations. Click \'OK\'
    to add.

![](../../Resources/Images/Data%20Onboarding/9.png)

When finished, click [Save]{.bold} in the designer to save the current
settings. Do not close the designer unless you have finished configuring
all the other parameters (outlined in the rest of this topic).

### Configuring the Mapper Configurations to Display Onboarding Mappings Details Screen

1.  From the Main Properties, click the \'Add\...\' button for the
    Mappings parameter, and the Screen Mapping Properties will display.

![](../../Resources/Images/Data%20Onboarding/11.png)

2.  Add a condition by clicking the **Add\...** button next to the
    \'Conditions\' parameter, and the Add Component dialog will display.

![](../../Resources/Images/Data%20Onboarding/12.png)

1.  Within the Add Component dialog, select the Object Type Condition
    component and then click [Add]{.bold}. In the Object Type Condition
    Properties, next to the Object Type parameter, expand Basic Object
    Types, and select the Mapper Configuration (MapperConfiguration)
    object type to define that this object type should use the
    Onboarding Mappings Details Screen. Click **OK** to add the object
    type. Then click **Add** to add the Object Type Condition.

![](../../Resources/Images/Data%20Onboarding/13.png)

1.  In the Screen Mapping Properties, select the previously created
    Onboarding Mappings Detail Screen using the dropdown selector next
    to the \'Screen\' parameter.

![](../../Resources/Images/Data%20Onboarding/14.png)

1.  Click [Add]{.bold}. The new mapping is added in the \'Mappings\'
    field (as shown below). Click [Save]{.bold} in the designer to save
    the current settings.

![](../../Resources/Images/Data%20Onboarding/15.png)

For more information, see the **Mappings** topic in the **Web User
Interfaces / Web UI Getting Started** documentation[
here]{.mcFormatColor style="color: Blue;"}.
