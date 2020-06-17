---
description: 'Automotive Solution: The Onboarding Comparison Screen
  interface is designed to allow users to preview the onboarding data,
  assess each of the changes, and to give the user an option to accept
  or reject each individual changes that will affect the Target object.'
title: '\[%=Heading.AnyLevel%\]'
---

Using Onboarding Comparison Screen Interface
============================================

The Onboarding Comparison Screen interface is designed to allow users to
preview the onboarding data, assess each of the changes, and to give the
user an option to accept or reject each individual changes that will
affect the Target object. This allows users to distinguish and allow
only the required changes to be Onboarded. This is accomplished by
allowing users to select only the required Mapper rows / Mapping plugins
across multiple Mapper rows / Mapping plugins per the configuration of
the Mapper Configuration setup entity.

Each Onboarding Comparison Screen can be configured to display up to
three Mapping stages. Because the final stage called as Confirm stage is
set by default, there can be a maximum of four stages displayed in each
Onboarding Comparison Screen. Within each Mapping stages, a checkbox is
used to select valid Mapping plugins / Mapper rows.

Following are the Mapping stages that can be made available to be
configured in the Onboarding Comparison Screen.

-   Application stage
-   Attributes stage
-   Objects stage
-   Confirm stage

Of all the stages mentioned above, the Confirm stage gets displayed only
when any of the other three stages are available. And the Application
stage, Attributes stage, and Objects stage are displayed when ALL of the
following conditions are met:

-   One or more of the associated Mapping plugin is in the enabled
    state. And atleast one of the Mapper rows listed within these
    Mapping plugins are in the active state too.
-   The comparison Stage parameter that are available within the
    Onboarding Comparison Screen Properties designer screen is either
    empty or has the required stage listed in it.

For example, if the Mapper Configuration setup entity constitutes of
only the Attribute Mapping plugin, then the Onboarding Comparison Screen
configured to display the Mapper Configuration setup entity will only
display the Attribute stage and the Confirm stage. In the example below,
because \'PIES Item \--\> NAPA Product\' Mapper Configuration setup
entity has only the Attribute Mapping Plugin, the Attributes stage and
the Confirm stage are displayed when Source object is selected (as shown
below).

![](../../../Resources/Images/Data%20Onboarding/200.png)

![](../../../Resources/Images/Data%20Onboarding/201.png)

Additionally, if the Object to Object Mapping plugin is added to the
\'PIES Item \--\> NAPA Product\' Mapper Configuration setup entity, then
the available stages display as Attribute stage, Object stage and the
Confirm stage (as shown below).

![](../../../Resources/Images/Data%20Onboarding/202.png)

![](../../../Resources/Images/Data%20Onboarding/203.png)

Additionally, consider being able to add the Application Mapping plugin
for \'PIES Item \--\> NAPA Product\' Mapper Configuration setup entity.
In the screenshot below, the available stages display as Attribute
stage, Object stage, Application stage and the Confirm stage.

![](../../../Resources/Images/Data%20Onboarding/204.png)

![](../../../Resources/Images/Data%20Onboarding/205.png)

The related stage gets displayed in the Onboarding Comparison Screen
only when the respective Mapping plugins are available in the configured
Mapper Configuration setup entity. Similarly, only those Mapping plugins
/ Mapper rows that are in the active state are displayed within the
Onboarding Comparison Screen. If there exists multiple Mapping plugins
of the same type all in the disabled state, then the associated stage
will not be displayed in the Onboarding Comparison Screen.

For example, when the Source object is selected to display the
Onboarding Comparison Screen, and the Attribute stage is selected to
display, only those Mapper rows / Attribute Mapping plugins will be
displayed that are enabled in the Mapper Configuration setup entity.

Taking this example a step further, after selecting Source Object
\'VC21499\' for the Attribute stage of the Onboarding Comparison Screen,
and Mapper rows are enabled for the first row, users can easily view the
enabled Mapper rows within Attribute stage (as shown below).

![](../../../Resources/Images/Data%20Onboarding/206.png)

![](../../../Resources/Images/Data%20Onboarding/207.png)

The Onboarding Comparison Screen have many configuration options. The
Web UI administrator has control over the Stages that are allowed to be
displayed within the Onboarding Comparison Screen. If your screen
display differently than the examples within this section, contact your
Web UI administrator. For more information on configuring an Onboarding
Comparison Screen, see the **Onboarding Comparison Screen
Configuration** topic ([here]{.mcFormatColor style="color: Blue;"})
within this guide.For information about each of the Mapping stages
available, see the **xxxx** topic within this guide.

This section addresses the following:

-   **Using Attributes Stage** [ here]{.mcFormatColor
    style="color: Blue;"}
-   **Using Applications Stage** [ here]{.mcFormatColor
    style="color: Blue;"}
-   **Using Objects Stage**
