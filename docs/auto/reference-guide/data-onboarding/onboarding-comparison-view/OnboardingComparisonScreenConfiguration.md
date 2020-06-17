---
description: 'Automotive Solution: The Onboarding Comparison Screen
  allows users to preview the onboarding data, and provides an option to
  assess each of the changes affecting the Target object. This lets the
  user to allow / reject the changes affecting the Target object.'
title: '\[%=Heading.AnyLevel%\]'
---

Onboarding Comparison Screen Configuration
==========================================

The Onboarding Comparison Screen allows users to preview the onboarding
data, and provides an option to assess each of the changes affecting the
Target object. This lets the user to allow / reject each individual
changes affecting the Target object.

Configuration Prerequisites
---------------------------

It is expected that anyone configuring the Onboarding Comparison Screen
is familiar with the Web UI Designer as basic concepts for working with
the designer are not covered in this section. In addition, the user must
have appropriate privileges to access the designer. Additional
information can be found in the [Designer Access]{.bold} section of the
[Web User Interfaces / Web UI Getting Started]{.bold} documentation[
here]{.mcFormatColor style="color: Blue;" conditions="Primary.Web"}.

The required Mapper Configuration setup entity has to be readily
available in the system. For creating and configuring Mapper
Configuration setup entity, see **Configuring Mapper Configuration Setup
Entity** topic within this guide[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration Process
---------------------

In the designer, create a new screen by selecting \'New.\' Select the
\'Onboarding Comparison Screen,\' and create a name for the screen in
the \'Screen ID\' field. In the example below, the Screen ID is
\'OnboardingComparisonScreen.\' Click \'Add.\'

The Screen ID you use should be something descriptive since this will be
the name shown on any design component list in the Web UI. Screen IDs
cannot be reused and must be unique.

![](../../../Resources/Images/Data%20Onboarding/177.png)

Once this screen is created, the Add Component - Onboarding Comparison
Screen Properties designer screen displays, which contains the following
parameters for configuration:

![](../../../Resources/Images/Data%20Onboarding/178.png)

**Mapper configuration:** Select a Mapper Configuration setup entity
that will be used as the context for comparison. All Mapping plugin(s )
available within the configured Mapper Configuration setup entity will
be listed amongst their respective stages of the Onboarding Comparison
Screen. For example, all Attribute Mapping plugins will be contained in
the Attributes stage

**Accepted Onboarding Business Action:** Select a Business Action to be
executed after clicking the **Onboard** button in the Onboarding
Comparison Screen.

**Rejected Onboarding Business Action:** Select a Business Action to be
executed after clicking the **Reject Update** button in the Onboarding
Comparison Screen.

**Comparison Stages:** This parameter allows adding multiple phases of
Onboarding that are displayed as individual Stage within the Onboarding
Comparison Screen. Each stage listed in this parameter will contain
their respective Mapping plugins that are available in the defined
Mapper Configuration setup entity. For example, all Attribute Mapping
plugins available within the defined Mapper Configuration setup entity
will be listed in the Attribute Mapping Stage. Each Stage can be added
only once. The order that the Stages are listed determines the order
that they will be displayed within the Onboarding Comparison Screen.
Once added, no additional configuration is required. Clicking the Add
button next to the Comparison Stages parameter displays an Add Component
dialog with the option to add one of the following stages:

-   **Application Mapping Stage:** Adding this stage will display all of
    the Application Mapping plugins contained in the configured Mapper
    Configuration setup entity.

For the Application Mapping Stage to display within the Onboarding
Comparison Screen, the selected Source object must meet all of the
following criteria:

-   The Source application must have references to a vehicle and a part
    type
-   There must be reference between the Source vehicle and the Target
    vehicle
-   There must be reference between the Source part type and the Target
    part type

```{=html}
<!-- -->
```
-   **Attribute Mapping Stage:** Adding this stage will display all of
    the Attribute Mapping plugins contained in the defined Mapper
    Configuration setup entity.
-   **Objects Mapping Stage:** Adding this stage will display all of the
    Object to Object Mapping plugins contained in the defined Mapper
    Configuration setup entity.

Use the Up / Down button to rearrange the order of display for each
stage.

Only the Mapping Plugins and/or Mapper rows that are in the enabled
(active) state within their Mapper Configuration setup entity are
displayed in the Onboarding Comparison Screen. The disabled Mapping
plugins and/or Mapper rows will not be displayed in the Onboarding
Comparison Screen. For information on enabling / disabling the Mapping
plugins see **Using the Onboarding Mappings Details Screen** topic, and
for enabling / disabling the Mapper rows, see **Modifying Mapper Rows on
the Onboarding Mapping Details Screen** within this guide.

**Target Object Current Values Header Label:** If required, specify a
custom label for the column header that displays the current value
populated in the Target object. If nothing is added, the Label default
will display as \'\[Current STEP\] values.\' This column header is
displayed within the Attribute Mapping Stage and Object Mapping Stage of
the Onboarding Comparison Screen as shown below:

This is how the column header will display at the Onboarding Comparison
Screen.

![](../../../Resources/Images/Data%20Onboarding/187.png)

**Source Object Values Header Label:** If required, specify a custom
label for the column header that displays the value populated in the
Source object. If nothing is added, the Label default will display as
\'\[Supplier\] values.\'

This is how the column header will display at the Onboarding Comparison
Screen.

![](../../../Resources/Images/Data%20Onboarding/189.png)

**Target Object New Values Header Label:** If required, specify a custom
label for the column header displaying the value that gets populated in
the Target object after accepting the Onboarding. If nothing is added,
the Label default will display as \'\[Updated STEP\] values.\'

This is how the column header will display at the Onboarding Comparison
Screen.

![](../../../Resources/Images/Data%20Onboarding/188.png)

Configuring Access to an Onboarding Comparison Screen
-----------------------------------------------------

Any number of Onboarding Comparison Screen can be added to a Web UI.
Once added, as with any screen, an admin user must configure how users
access an Onboarding Comparison Screen.

For the Onboarding Comparison Screen to display, there must be a
reference established between the Source Object and the Target object.
If no Target object exists for the selected Source object, then the
following error message is displayed in the screen.

![](../../../Resources/Images/Data%20Onboarding/186.png)

There are multiple ways that the screen can be accessed in the Web UI.
These are the common ways in the Automotive solution that the Onboarding
Comparison Screen can be accessed:

1.  The Onboarding Comparison Screen can be mapped to the Source Object
    using Main Properties. For more information about mapping, see
    [Configuring the Parameters]{.bold} in the [Main Properties]{.bold}
    topic of the **Web User Interface / Web UI Setup and User Guide**
    documentation[ here]{.mcFormatColor style="color: Blue;"}.

Below is an example of an Onboarding Comparison Screen that is
configured (mapped) to display when a Source object is selected.

 

Image

 

 

1.  The Onboarding Comparison Screen can be added to a sub screen tab
    page on a Node Details Screen for Source Objects. For more
    information about sub screen tab pages, see the [Tab Pages]{.bold}
    topic in the **Node Details Component** section of the **Web User
    Interface / Web UI Setup and User Guide** documentation[
    here]{.mcFormatColor style="color: Blue;"}.

The example below shows the Onboarding Comparison Screen displayed as a
sub screen tab page on a Node Details screen and is displayed when a
Source object is selected.

![](../../../Resources/Images/Data%20Onboarding/191.png)

1.  Selecting the Source object in any of the Web UI search screen Node
    List and navigating the selected Source object using Forward Screen
    Action button. For more information about Forward Screen Action
    component, see the [Forward Screen Action Component]{.bold} topic
    within this guide[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/190.png)

The values listed within this column will display the current value
populated in the Target object. This column is displayed only in the
Attribute Mapping Stage of the Onboarding Comparison Screen.
