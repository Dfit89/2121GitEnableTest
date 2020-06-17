---
description: 'The Reference Delegation Screen is a Web UI screen type
  that, when configured with a reference type and a screen ID, will
  follow the reference from the source object to its target and display
  the information of the target object.'
title: '\[%=Heading.AnyLevel%\]'
---

Reference Delegation Screen
===========================

PRODOC note: RDCUST-2139

The Reference Delegation Screen is a Web UI screen type that, when
configured with a reference type and a screen ID, will follow the
reference from the source object to its target and display the
information of the target object. It allows you to take any active
selection, follow a reference on that selection, and display any screen
configured for the target of the reference (noting that the selected
screen may show data from the target itself, data from the children of
the target (Automotive specific using the Application Editor Screen),
data from objects referenced by the target, etc).

One common use case of the Reference Delegation Screen within the
Automotive solution is to view the application records of any other
standard model from the OWN model. There are no explicit limits on how
the screen can be used, but it was created specifically to satisfy two
use cases:

1.  View applications belonging to a standard\'s part (example,
    AutoCare) while the OWN part is selected.
2.  View product data on a standard\'s part while the OWN part is
    selected.

For example, the screen can be configured to display applications from a
PIES Item when an OWN part is selected. To do this, the reference
parameter must specify a reference that has the OWN part as a source and
the PIES Item as a target, and a screen must be selected that displays
applications for a part. The \'AutoCare Application Editor Screen
(Parts)\' exists via easy setup creation and displays applications when
a part is selected, so this screen would be a good candidate. Once
configured properly, the Reference Delegation Screen can then be added
to any existing screen mapped to display data from the OWN part. An
example of this configuration would be a Node Details screen using Tab
Control in which the Sub Screen Tab Page configuration specifies the
Reference Delegation Screen.

The above is just an example, and as stated, there are a variety of use
cases for which this screen can be applied. The only limitation to its
use is that **the selected reference must be of a reference type that
allows single references only**. If a selected reference is of a
reference type that allows multiple references, the user will see an
error.

Prerequisites
-------------

It is expected that anyone configuring the Reference Delegation Screen
is familiar with the Web UI Designer, as basic concepts for working with
the designer are not covered in this section. In addition, the user must
have appropriate privileges to access the designer. Additional
information can be found in the [Designer Access]{.bold} section of the
[Web User Interfaces]{.bold} / [Web UI Getting Started]{.bold}
documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.

The target screen that is used to display the target object information
must already be created.

A reference must already be established between the source and the
target object using the reference type that will be configured in the
Reference Delegation Screen.

Configuring Reference Delegation Screen
---------------------------------------

To create and configure a Reference Delegation Screen, users must first
determine the reference type that links the source and the target
object, and the screen that displays the target object details. Once
this has been determined, users may begin the configuration process.

1.  Create a new 'Reference Delegation Screen.' Steps for creating a new
    screen are outlined in the **Creating a New Screen** section
    described within the **Design Mode Basics** topic in the **Web User
    Interfaces / Web UI Getting Started** documentation of **STEP Online
    Help**[ here]{.mcFormatColor style="color: Blue;"}.

Select \'Reference Delegation Screen\' as shown below:

![](../../Resources/Images/Application%20Editor/60.png)

1.  After creating the new 'Reference Delegation Screen\', users must
    determine which reference type must be used to follow from the
    source to the target object. to bring up a Node Selector dialog.

![](../../Resources/Images/Application%20Editor/61.png)

1.  Using either the \'Search\' or the \'Browse\' option, select the
    reference type that will be used to follow from the source object to
    its target. In the example below, reference type ID
    \'OWNPartToPIESPart\' is selected. When the reference type has been
    selected, click **OK**.

![](../../Resources/Images/Application%20Editor/62.png)

1.  In the dropdown next to the Screen ID field, select the required
    screen from the available list. This determines the screen that will
    be used to display the target object information. In the example
    below, we have selected the screen entitled, 'AutoCare Application
    Editor Screen (Parts).'

![](../../Resources/Images/Application%20Editor/63.png)

1.  Check the Reverse Reference parameter only if required. Selecting
    this field will work the other way of the reference type defined in
    the Reference Type parameter above by using the \'Referenced By\'
    tab to find the target. Selecting this parameter will follow the
    reference on the selected object, and display any screen configured
    for the children objects of the target referenced by the source
    object. Click **Add** to finish creating the screen.
2.  Once configured, set the Reference Delegation Screen as a Sub Screen
    Tab Page. Steps for setting up as a Sub Screen Tab Page are outlined
    in the **Tab Pages** topic within in the **Web User Interfaces / Web
    UI Getting Started** documentation of **STEP Online Help**[
    here]{.mcFormatColor style="color: Blue;"}.
3.  Save and close the designer.

Use Case
--------

Shown below is an example where the OWN part \'124RX\' is referenced to
a PIES Item \'551DX\' (AutoCare standard) through the
\'OWNPartToPIESPart\' reference type. The target object PIES Item has
few application records as its child objects.

![](../../Resources/Images/Application%20Editor/67.png)

![](../../Resources/Images/Application%20Editor/64.png)

### Example One

When the Reference Delegation Screen is configured as a Sub Screen Tab
Page within the source Node Details screen to display the Application
Editor Screen of the target object, the application records belonging to
the PIES Item are displayed when the OWN part is selected, as shown
below.

![](../../Resources/Images/Application%20Editor/65.png)

### Example Two

When the Reference Delegation Screen is configured as a Sub Screen Tab
Page within the source Node Details screen to display the product data
of the target object, the information available within the Part Details
screen belonging to the PIES Item is displayed when the OWN part is
selected, as shown below.

![](../../Resources/Images/Application%20Editor/66.png)
