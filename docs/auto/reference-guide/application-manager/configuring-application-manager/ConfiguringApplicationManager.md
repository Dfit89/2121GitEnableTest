---
description: This section describes the steps necessary to configure an
  Application Manager.
title: '\[%=Heading.AnyLevel%\]'
---

Configuring Application Manager
===============================

PRODOC note: MEDU Per a note from KRMA in section 5.1.12 of the Spec Doc
for the Rebuild of the Application finders project - we need to provide
good help text and limit the amount of documentation necessary for
configuration. Sadly the documentation was needed before the help text
could be prioritized. I tried to keep the OLH minimal knowing the help
text would be done soon.
https://stibo.sharepoint.com/:w:/r/sites/SYS-SC1/PDOGlobal/\_layouts/15/WopiFrame.aspx?sourcedoc=%7Bfd576409-28ab-44cf-9709-4086b83d6bb5%7D&action=default

The Easy Setup actions must be run for each standard that will be
accessed using an Application Manager, and by default each standard is
configured to use their own instance of an Application Manager.
Optionally, after Easy Setup actions have configured an Application
Manager, the Vehicle Type Search Panel and results table columns can be
manually modified. Before doing this, it is helpful to review how the
Vehicle Type Search Panel and results table are used per the **Using
Intelligent Search Interface** topic ([here]{.mcFormatColor
style="color: Blue;"}), the **Results Table and Toolbar** topic
([here]{.mcFormatColor style="color: Blue;"}), and then review the
search box configuration options within this topic. Additionally, for
information on adding columns to the results table, see the **Adding
Additional Headers to Application Screens** topic ([here]{.mcFormatColor
style="color: Blue;"}) within the **Automotive Quick Start Guide**.

When Easy Setup actions have been used to create a standard data model,
by default, much of the Application Manager is ready to be used,
including the addition of an easy to use link to the Application Manager
screen from the Quick Links widget on the Web UI Homepage. For more
information, see the **Application Manager** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Own Model Considerations
------------------------

An Application Manager screen can be configured for use with an Own
model. It is easiest to accomplish this after first using the Easy Setup
actions to configure the Automotive - Application Model for an
automotive standard.

For an Application Manager to function properly, some component model
types (i.e., Part Type) may need to be configured, even if otherwise not
needed.

To implement an Own model within an Application Manager screen, the
following must be in place:

1.  All components within the Automotive - Application Model must be
    populated with a value. For more information about each of the
    components, see the topic
2.  The Application, Assembly, Part, Part type, Part type list,
    Application to assembly, Leading part relation, Leading part type
    relation, Part type link type, and Part type list to part type
    aspects must be configured with Own object types and references in
    the Automotive - Application Model component.
3.  Create a new Product to Classification Link Type and define the own
    part and application object types as valid Product Types, and the
    own part type object type as a valid Classification Type. Then add
    this new Product to Classification Link Type to the \'Part type link
    type\' aspect within the Automotive - Application Model.
4.  The \'Part type list to part type\' aspect requires a Classification
    Reference Type to connect a part type list / group to a part type
    that is used in behind the scene code (not visible for a user to
    interact with). The object type that is used for the Valid Source
    Type in the reference must also be defined in the 'Part type list'
    aspect. The object type that is used for the Valid Target Type must
    also be defined in the 'Part type' aspect.

```{=html}
<!-- -->
```
1.  The Vehicle Type Search Panel within an Application Manager must be
    configured to use the Own application and vehicle object types, and
    Own vehicle root node.
2.  The own application must have the references established to the own
    vehicle and part type.

Configuring an Application Manager Screen in Web UI
---------------------------------------------------

Steps to configure an Application Manager screen in Web UI are below.

Easy Setup actions for at least one standard must be run before an
Application Manager Screen can be manually added to a Web UI and
configured for that standard.

1.  Log in to the Web UI where the Application Manager will be used, and
    access the Web UI Designer.
2.  Click the **New** button at the top of the Designer, and the Add
    Screen dialog will display.

![](../../../Resources/Images/AppMgr/Configuring/Add%20Screen.png)

1.  PRODOC note: RDCUST-2280 Screen name is ApplicationFinderScreen.
    Search for and select the \'Application Manager Screen,\' enter a
    Screen ID, click the **Add** button, and the Application Manager
    Screen Properties dialog will display as shown below.

![](../../../Resources/Images/AppMgr/Configuring/ApplicationFinderProp.png)

Within the Application Manager Screen Properties dialog, the following
parameter is required:

**Vehicle Type Search Panel:** Allows for up to six different Vehicle
Type Search Panels to be configured within each Application Manager.
Populating this required parameter allows for a Vehicle type icon and
Vehicle Type Search Panel to display within the Application Manager.
PRODOC note: MEDU RDCUST-2618 The number of allowed Vehicle Type Search
Panels is dependent upon the padding applied to the icons. If the
padding changes, the warning message automatically adjusts. If more than
five six vehicle type search panels are added, only the first five six
vehicle types listed will display for the Application Manager user.
Additionally, a warning dialog will display each time the Designer is
accessed informing the user that more vehicle type search panels are
configured than can be displayed. In the example below, six seven
vehicle type search panels have been configured.

![](../../../Resources/Images/AppMgr/Configuring/Warning6.png)

![](../../../Resources/Images/AppMgr/Configuring/Warning7.png)

PRODOC note: MEDU Per my and NIFE findings when she removed the VCDB and
the default AC vehicle type disappeared: If a vehicle search type is
created, and the vehicle root node that has been configured for the
Vehicle Type is later removed from STEP, then the vehicle search type
created within the Application Manager will no longer display. If the
vehicle root node is re-created, then the Application Manager will
display as it did before the vehicle root node was deleted.

Within the Application Manager Screen Properties dialog, the following
parameters are optional:

PRODOC note: MEDU RDCUST-2741 It must be possible to search for
application records using Part classification (Product Lines) It must be
possible to search for application using a criterion that defines the
associated parts by classification hierarchy that they are located in.

**Application Scope Value:** This parameter sets the default drop down
value in the Missing Application Coverage functionality within
Application Manager Screen. Within this parameter, user can set default
values to either \'Existing Applications Only\' or \'Existing and
Missing Applications\' or \'Missing Applications.\' Typically, this
parameter is used to set the default value in the dropdown located below
the search boxes of Application Manager Screen, which can help users to
perform required search without changing the options every time. Despite
the default setting in the Application Scope Value parameter, user can
still swap amongst the options in Application Manager Screen to perform
required search. For information on missing application coverage
functionality, see the **Missing Application Coverage Functionality**
topic[ here]{.mcFormatColor style="color: Blue;"}.

**Hierarchy Restriction Label:** Type a label that best describes the
Hierarchy Restriction option to the Application Manager user. By
default, the label is populated with \'All data.\' If users are
filtering by brand, then \'Brand\' could be an appropriate label.

**Hierarchy Restriction Object Types:** Allows users to restrict the
Application Manager search results by an object type. Users can select
from a pre-configured dropdown list of product or classification object
types. This can be helpful when search results needs to be filtered by
Brand, Manufacturer, OEM, Product Line, etc. Once an object types is
added, it will display in the dropdown list. Use the Up and/or Down
buttons to edit the order of the dropdown list, as the objects will
display to the user in the order listed within the parameter. When the
parameter is blank, the Hierarchy Restriction dropdown will not display
within the Application Manager. Adding at least one object type to the
parameter will result in the Hierarchy Restriction dropdown displaying
below the search boxes of the Application Manager.

**Title:** If desired, type in a title which will display on the screen
in the top left corner. If no text is entered, no label is displayed.

**Default Node List:** This parameter functions as the generic Node List
component for all the Vehicle Type Search Panel listed within the
Vehicle Type Search Panels parameter unless a specific configuration is
done on each individual Vehicle Type Search Panel. Select \'Node List\'
option in the dropdown and click on the \'go to component\' to further
configure the Node List component. For more information, see the **Node
List Component** topic within the **Web User Interfaces** section of
**STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

1.  Click the **Add** button below the Vehicle Type Search Panels
    parameter, and the \'Add component\' dialog will display as shown
    below.

![](../../../Resources/Images/AppMgr/Configuring/Add%20Component1.png)

1.  Select the Vehicle Type Search Panel component, click **Add**, and
    the newly added component will display within the Vehicle Type
    Search Panel parameter.
2.  Double click the newly added component available in the Vehicle Type
    Search Panel parameter, and the Vehicle Type Search Panel Properties
    dialog will display (as shown below). Parameter options are
    explained below:

![](../../../Resources/Images/AppMgr/Configuring/Vehicle%20Type%20Panel%20Properties%20updated.png)

Within the Vehicle Type Search Panel Properties dialog, the following
parameters are required:

Whenever a new Vehicle Type Search Panel is added, all required
parameters that need to be populated are displayed in the main screen
(as shown below). To populate the required parameters, manually navigate
to the Vehicle Type Search Panel Properties dialog for the newly added
Vehicle Type Search Panel.

![](../../../Resources/Images/AppMgr/Configuring/Error.png)

**Application Object Types:** Allows for applications created within the
Application Manager to be restricted to the listed object type. Click
the Add button below the parameter field to browse or search for the
necessary object types.

-   Object type(s) selected for this parameter must be configured as an
    Application within the \'Automotive - Application Model.\' Easy
    Setup configures the Automotive - Application Model in this way.
-   Any object that is selected, and is configured as an Application in
    the Automotive - Application Model, will be displayed in the search
    results table. For example, a user can have their own application,
    as well as an AutoCare ACES application.
-   When applications are created, their object type is determined based
    on the part number that is applied to the Vehicle. For example, if
    part number 123 is a PIES Item, and part number 456 is a Own part
    number, then when a user applies part number 123 to a Vehicle, then
    the application record is created using an ACES application object
    type.

**Search Box Types:** Allows one to four search boxes to be added to the
Vehicle Type Search Panel. Only one search box is required, and each
search box type can be added only once. The order listed determines the
order of display within the Application Manager search panel. The Part
Type search box type does not require additional configuration, whereas
the other search box types do. Clicking the Add button below the Search
Box Types parameter displays an Add Component dialog with the option to
add one of the following search box types: Make/Model, Options Group,
Part Type, and Year. Steps for configuring each search box type can be
found in their respective sections below:

-   Configuring Make/Model Search Box [ here]{.mcFormatColor
    style="color: Blue;"}
-   Configuring Attribute Search Box [ here]{.mcFormatColor
    style="color: Blue;"}
-   Configuring Options Group Search Box [ here]{.mcFormatColor
    style="color: Blue;"}
-   Configuring Part Type Search Box [ here]{.mcFormatColor
    style="color: Blue;"}
-   Configuring Year Search Box [ here]{.mcFormatColor
    style="color: Blue;"}

PRODOC note: MEDU RDCUST-2622 As a Web UI designer I want to be
prevented from adding the same criterion configuration more than once so
I don\'t make silly configurations. This can only be done within a list
and not between lists, but this could be checked on the server. Only one
Make/Model, Year, Part Type card, and Options Group cards can be added.
Otherwise a warning displays.

**Name:** Allows for a custom name for the Vehicle Type Search Panel to
display when a user hovers over the Vehicle type icon. Type in the
desired name.

**Root Nodes:** Allows for the restriction of root nodes to be used
within the Application Manager when searching for a vehicle. The root
node(s) listed should correspond to the Icon and Name parameters because
the search input field displays only suggestions for Make/Model objects
that belong in the root node defined within this parameter.
Additionally, when the Node Picker is used, its dialog will display the
only those classification folders that pertain to the root nodes defined
within this parameter. Click the Add button below the parameter field to
browse or search for the necessary vehicle root node object(s).

**UUID:**

**Use Default Application Editor:** Allows the user to toggle between
the use of the default Node List configured on the Application Manager
Screen Properties dialog and the Node List configured on the Vehicle
Type Search Panel Properties dialog.

**Vehicle Object Types:** Allows vehicles within the Application Manager
to be of the listed object type. Object type(s) selected for this
parameter must be configured as an Assembly aspect within the
\'Automotive - Application Model.\' Easy Setup configures the Automotive
- Application Model in this way. Click the Add button below the
parameter field to browse or search for the necessary object types.

Within the Vehicle Type Search Panel Properties dialog, the following
parameters are optional:

**Vehicle Type Icon:** The Vehicle type icon is a visual representation
of the Vehicle Type Search Panel. Clicking a Vehicle type icon displays
the Vehicle Type Search Panel configured specifically for that vehicle
type (i.e., Personal Cars, Buses, Marine, Street Bikes). Hovering over
the icon will display the name configured for the Vehicle Type Search
Panel. Each Application Manager must have at least one Vehicle type
icon. However, only up to five six icons can be displayed within the
same Application Manager. Therefore up to five six Vehicle Type Search
Panels can be specifically configured to best meet the needs of
different search types. The following Vehicle Type icons are available
for selection:

![](../../../Resources/Images/AppMgr/Configuring/Icon%20List.png)

PRODOC note: MEDU RDCUST-2617 ACES Vehicle Type Selector Also a Vehicle
type icon, title and root node can be configured to match each other and
corresponds to the vehicle type being configured for users. The values
populated for the required fields should all correspond to one or more
vehicle types being configured for the Application Manager.

Double click on the newly added Vehicle Type Search Panel in the
Application Manager screen Properties dialog to configure the following
optional parameter:

**Node List:** Allows configuration of the Node List component for the
selected Vehicle Type Search Panel. Node List configured under this
parameter will only be applicable for the selected Vehicle Type Search
Panel and shall overwrite all the configuration made within Default Node
List parameter in the Application Manager screen properties dialog.
Select \'Node List\' option in the dropdown and click on the \'go to
component\' to configure the Node List component for the selected
Vehicle Type Search Panel. For more information, see the **Node List
Component** topic within the **Web User Interfaces** section of **STEP
Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

Below is an example of a configured Vehicle Type Search Panel Properties
dialog for an AutoCare Application Manager.

![](../../../Resources/Images/AppMgr/Vehicle%20Type%20Panel%20Properties.png)

7.  Once the required parameters are populated, click the **Save** and
    **Close** buttons to exit the Designer.

Many optional parameters are available within the Application Manager
Screen Properties \> Child Components \> Node List. Each of them are
described within the Configuring Application Manager Screen Node List
Properties topic.
