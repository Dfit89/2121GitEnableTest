---
description: 'Automotive Solution: Describes how to configure an Options
  Search Box type.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring Options Group Search Box
====================================

PRODOC note: MEDU RDCUST-2646 Maximum of 2 Options Search Boxes can be
added to a search group. This helps ensure no more than 5 vehicle types
are selected.

Attributes or References within STEP can be displayed as Options within
an Application Manager Options Search Box. The Option values (attribute
and/or reference values) can then be selected as criteria for a search.

Though many options (attributes and/or references) can be added to an
Options Search Box, only one Options Group search box type can be
configured for each \'Vehicle Type Search Panel.\' However, either one
or two Options Search Boxes can be configured within the Options Group
search box type. In other words, one Options Search Box can be
configured to list multiple options or two Options Search Boxes can be
configured. When two Options Search Boxes are configured, then an AND/OR
toggle button displays between the two Options Search Boxes.

In the example below, an Options Group search box type is configured
with two Options Search Boxes. Each Options Search Box is configured to
display multiple attributes and/or References available for selection.
In the screenshot below, the dropdown selections for both Options Search
Boxes are displayed for the purposes of this example.

![](../../../Resources/Images/AppMgr/Configuring/OptionsListDisplayed.png)

It is possible to instead list all of the options within one Options
Search Box, however users would loose the ability to apply the \'AND\'
function to their search. Additionally, each Options Search Box can be
configured to list the same options as the other Options Search Box.

Prerequisites

Prior to configuring an Options Group Search Box, it is helpful to know
one or more attributes and/or References that will be displayed as an
option, along with the exact validation path for each. Setup requires an
exact validation path for each of the attributes and/or References used.
Though this topic provides example for each validation path type, more
information about validation paths, can be found within the **Automotive
Validation Path** topic ([here]{.mcFormatColor style="color: Blue;"}) of
this guide.

Configuring Options Group Search Box

Steps for adding and configuring the Options Group search box type for a
Vehicle Type Search Panel are below.

1.  From the Vehicle Type Search Panel Properties dialog, click the
    **Add** button below the Search Box Types parameter field, and the
    Add Component dialog will display.

![](../../../Resources/Images/AppMgr/Configuring/Add%20Component.png)

1.  Click **Options Group Search Box** from the list of components.
2.  Click the **Add** button, and the Options Group Search Box
    Properties will display as shown below.

![](../../../Resources/Images/AppMgr/Configuring/Options%20Group%20Properties.png)

PRODOC note: MEDU RDCUST-2663 The Options Group Search Box component
contains the settings for the Search Box Types.

Within the Options Group Search Box Properties dialog, the following
parameters are required:

**Options Search Boxes:** Allows either one or two Options search boxes
to display within the Vehicle Type Search Panel. Each Options search box
can be configured to allow users to choose from a dropdown list of
options. At a maximum, only two Options Search Boxes can be added to an
Options Group Search Box.

PRODOC note: MEDU RDCUST-2291 The default value of the AND / OR option
combination can be configured.

**Operator Default:** Allows the default AND / OR operator to be
configured for two Options search boxes. By default, AND is selected.

Below is an example of an Options Group Search Box Properties dialog
configured for the AutoCare standard.

![](../../../Resources/Images/AppMgr/Options%20Group%20Search%20Box%20Properties.png)

PRODOC note: MEDU RDCUST-2646 Options Group Search Box is limited to 2
Search Boxes maximum. If a 3rd Search Box is added, a warning will
display, \'A maximum of 2 option Search Boxes can be configured on an
options group\'

Because only two Options Search Boxes can be configured for each Option
Group search box type, if a user tries to add a third Options Search
Box, a Warning dialog will display as shown below.

![](../../../Resources/Images/AppMgr/Configuring/WarningOpt.png)

1.  Click the **Add** button beneath the Options Search Boxes parameter,
    and the Options Search Box Properties will display as shown below.

![](../../../Resources/Images/AppMgr/Configuring/Options%20Card%20Properties.png)

Within the Options Search Box Properties dialog, the following
parameters are required:

**Default Option:** Allows for a default option to display when users
access the Application Manager. The value within this parameter must
match the \'Label\' parameter configured within the Options parameter
listed below this parameter.

**Options:** Allows for one or more attributes or References to be
displayed as Options within the Options Search Box. Once an Option is
selected, the typeahead dropdown field will display only values that
pertain to the selected option. When more than one Options search box is
used, the attributes and/or reference Options configured within one
Options search box can optionally be configured to display in the second
Options search box.

Below is an example of an Options Search Box Properties dialog
configured for the AutoCare standard.

![](../../../Resources/Images/AppMgr/Options%20Card%20Properties.png)

1.  Click the **Add** button to add an option to an Options Search Box,
    and the Option Properties dialog will display two required
    parameters:

![](../../../Resources/Images/AppMgr/Configuring/Criterion%20Options%20Card.png)

Within the Option Properties dialog, the following parameters are
required:

**Label:** Provide a label that best describes the option being added to
the Options Search Box. The value can be used within the \'Default
Option\' parameter on the previous dialog.

**Validation Path:** Provide a validation path for the option being
configured. The option should correlate to an attribute or reference. It
is recommended to copy the \'Automotive Validation Path\' value for the
attribute or reference from the workbench, and paste it into the
Validation Path parameter field. Examples for each type of validation
path can be found below.

-   Attribute Validation Path Example:

Below is an example of a Option Properties dialog configured for the
ACES attribute, Sub Model.

![](../../../Resources/Images/AppMgr/Criterion%20Option%20Properties.png)

The Validation Path is configured by the Easy Setup and displayed in the
workbench. For this example, the Validation Path for the ACES Sub Model
can be found by navigating to System Setup \> Attribute Groups \>
AutoCare Attributes \> AutoCare ACES Attributes \> ACES Sub Model.

![](../../../Resources/Images/AppMgr/ACES.png)

-   Reference Validation Path Example:

Below is an example of how to configure the Option Properties for the
ACES reference, ACES Application To Engine Base.

![](../../../Resources/Images/AppMgr/Criterion%20Option%20Properties%20Engine.png)

The Automotive Validation Path for the **ACES Application To Engine
Base** reference type can be found in the workbench by navigating to
System Setup \> Reference Types \> Classification Reference Types \>
ACES Application To Engine Base.

![](../../../Resources/Images/AppMgr/Validation%20Path%20WB%20Engine.png)

6.  Once the required parameters are populated, click the **Add** button
    to return to the Options Search Box Properties, and optionally add
    additional options for the Options Search Box, or click the **Add**
    button and return to the Options Group Search Box Properties.
7.  Optionally repeat the steps above to add an additional Options
    Search Box, or click the **Add** button to return to the Vehicle
    Type Search Panel Properties.
8.  Once the required parameters are populated, click the **Add** button
    to return to the Vehicle Type Search Panel Properties, and
    optionally add another search box type, or move on to the next
    required parameter.
