---
description: 'Automotive Solution: Describes how to configure the Part
  Application Editor Component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Part Application Editor Component
=================================================

PRODOC note: PRODOC- 1817 The Part Application Editor component is a
Node Editor component used to display existing application records and
their attribute values when a part number is selected within the Tree
navigator.

This section describes how to configure the Part Application Editor
component. For information about how to use this component, and
prerequisites, see the **Application Suggestion Solution** topic[
here]{.mcFormatColor style="color: Blue;"}.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

Anyone configuring the Part Application Editor component within a Node
Editor is expected to be familiar with the basic configuration and
functionalities of Node Editor Component as basic concepts for working
with Node Editor component are not covered in this section. For more
information, see the **Node Editor Component** topic within the **Using
a Web UI** section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration Steps

Configuration Steps {#configuration-steps conditions="Primary.Web"}
-------------------

Below are the steps to configure the Part Application Editor component
within a Node Editor. Each of the parameters for the Part Application
Editor Properties are described below.

1.  In the Web UI Designer, go to Node Editor Properties \> Child
    Components \> Rows parameter for the screen that needs to display
    application record information.

![](../../Resources/Images/Competitor%20OE%20Number/97.png)

1.  Click the **Add** button for the Child Components Rows parameter,
    and the Add Component dialog will display.

![](../../Resources/Images/Application%20Suggestions/11.png)

1.  Find and select the Part Application Editor component, click the
    **Add** button, and the newly added component will display within
    the Rows parameter. In the screenshot below, an extra Headline
    component is also added to display a headline on a screen.

![](../../Resources/Images/Application%20Suggestions/10.png)

1.  Double click the newly added component available in the Rows
    parameter, and the Part Application Editor Properties dialog will
    display (as shown below). Parameter options are explained below:

![](../../Resources/Images/Application%20Suggestions/12.png)

The Node List component defined within this parameter displays the
application records in a table / grid format. The view can be further
customized by configuring the data to display via different display
modes and adding different action buttons that users can click while
working with the application records information. The display modes can
then be customized with a range of headers, allowing for different
information about the listed objects to be displayed. The behavior of
many of the various actions can also be further configured. For more
information, see the **Node List Component** topic within the **Web User
Interfaces** section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

**Height:**This optional parameter specifies the visual height of the
Part Application Editor component in pixels. By default, this parameter
is pre-populated with a value \'400.\' Users can enter a numeric value
to alter height of the component.

4.  Click the **Save** button, and then, click the **Close** button to
    close the designer.
