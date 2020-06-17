---
description: 'Automotive Solution: Describes how to configure the
  Advanced Part Number References Component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Advanced Part Number References Component
=========================================================

PRODOC note: BOND PRODOC- 1664The Advanced Part Number References
component is a Node Editor component used to display referenced part
numbers (Competitor / OE Number) and their attribute and/or metadata
values in a filtered and sorted way when a part number is selected
within the Tree navigator. This is an extended feature of the Part
Number References component with an additional feature of Node List
properties.

This section describes how to configure the Advanced Part Number
References component. For information about how to use this component,
and prerequisites, see the **Competitor and OE Numbers Solution** topic[
here]{.mcFormatColor style="color: Blue;"}.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

Anyone configuring the Advanced Part Number References component within
a Node Editor is expected to be familiar with the basic configuration
and functionalities of a Node Editor component and a Node List
component. For more information, see the **Node Editor Component**
([here]{.mcFormatColor style="color: Blue;"}) and **Node List
Component** ([here]{.mcFormatColor style="color: Blue;"}) topics within
the **Using a Web UI** section of **STEP Online Help**.

Configuration Steps

Configuration Steps {#configuration-steps conditions="Primary.Web"}
-------------------

Below are the steps to configure the Advanced Part Number References
component within a Node Editor. Each of the parameters for the Advanced
Part Number References Properties are described below.

1.  In the Web UI Designer, go to Node Editor Properties \> Child
    Components \> Rows parameter for the screen that needs to display
    competitor and/or OE number information.

![](../../Resources/Images/Competitor%20OE%20Number/97.png)

1.  Click the **Add** button, and the Add Component dialog will display.

![](../../Resources/Images/Competitor%20OE%20Number/96.png)

1.  Select the **Advanced Part Number References** component, and click
    **Add** button. The Advanced Part Number References Properties
    dialog will display. Parameter options are explained below:

![](../../Resources/Images/Competitor%20OE%20Number/98.png)

**Business Action to Invoke:** By default, this field is blank.
Optionally, select a Business Action to be invoked after a new part is
created using the Create New Part dialog. This can be helpful when a
Business Action is configured to normalize / harmonize a part number.
For more information about using this feature, see the **Creating and
Referencing New Competitor and/or OE Part Numbers** topic within this
section[ here]{.mcFormatColor style="color: Blue;"}.

**Height:**This optional parameter specifies the visual height of the
Advanced Part Number References component in pixels. By default, this
parameter is pre-populated with a value \'400.\' User can enter a
numeric value to alter height of the component.

**New Number Prefix:** By default, this mandatory parameter is populated
with the following prefix: \'NewReferenceNumber\_.\' This prefix will be
used for the ID of any part number that is created using this Create New
Part dialog (as shown below). Optionally, if a different prefix is
desired, edit the prefix to something more suitable.

The prefix must be unique, otherwise errors will occur. For example, if
the existing default prefix is already in use for the implementation,
then edit the prefix so it is unique.

![](../../Resources/Images/BRs/11.jpg)

**Original Number Attribute:** PRODOC note: MEDU RDCUST-2975 By default,
this field is blank. Because part numbers created using the Create New
Part dialog are normalized / harmonized to use alphanumeric characters
only, this parameter allows for the original part numbers created using
special characters, spaces, and/or non ASCII characters to be stored and
made searchable. Optionally, select an attribute to be used to store the
original part number exactly as it is entered when creating a new part
using the Create New Part dialog. The attribute selected for this
parameter must be valid for the competitor / OE number object type. The
normalized / harmonized version will be stored as the STEP Name of the
new part number.

An error message will display, and users will not be able to create a
new part if the attribute configured within the \'Original Number
Attribute\' parameter in not valid for the competitor and/or OE part
number object type.

**Reference Types:** By default, this required parameter is blank.
However, it is mandatory to add at least one Product Reference Type so
that when a part is selected STEP can follow the reference types listed
within this parameter and display the target and/or related attribute
values on the targets. Some examples include:

-    Within the AutoCare solution, when a part is selected STEP would
    need to follow the **PIES Interchange** reference and display the
    targets and/or a related attribute values on the targets.

```{=html}
<!-- -->
```
-   Within the NAPA solution, when a part is selected STEP would need to
    follow the **Product to Interchange Product** reference and display
    the targets and/or a related attribute values on the targets.

```{=html}
<!-- -->
```
-   Within the TecDoc solution, when a part is selected STEP would need
    to follow the **Supplier Article to Competitor Number** and/or the
    **Supplier Article to OE Number** references and display their
    targets and/or a related attribute values on the targets.

**Suggestion Manufacturer Name:** By default, the parameter is populated
with a value \'PARENT\_NAME\'. This parameter defines the search
criteria in the typeahead field whether if the competitor / OE number
search is based on the manufacturer name or the configured attribute
value (configured in the Suggestion Manufacturer Attribute parameter
explained below). Following options are available within this parameter:

-    **PARENT\_NAME:** Selecting this option defines the search criteria
    in the typeahead field to search the competitor / OE number based on
    the manufacturer name.
-   **ATTRIBUTE\_VALUE:** Selecting this option defines the search
    criteria in the typeahead field to search the competitor / OE number
    through the configured attribute value. The valid attribute is
    configured in the next parameter Suggestion Manufacturer Attribute.

**Suggestion Manufacturer Attribute:** By default, this parameter is
blank. The value of an attribute configured in this parameter is used to
search the competitor / OE number in the typeahead field. To search
through an attribute value, user must have the \'ATTRIBUTE\_VALUE\'
option selected in the Suggestion Manufacturer Name parameter above. To
select an attribute, click the ellipsis to the right of the field. A
Select Node(s) dialog will appear and an attribute can be selected by
browsing and navigating down to the desired attribute or by using the
search feature. The attribute selected for this parameter must be valid
for the competitor / OE number object type.

**Reference Types to create:** By default, this parameter is blank. This
parameter defines the reference type target that the part gets created
while creating a part through the typeahead field. Adding a reference
type in this parameter becomes necessary when there is more than two
reference types present in the Reference Types parameter. If no
reference type is listed in this parameter than the creation of new part
through the typeahead field will randomly be the target of any one of
the reference type listed in the Reference Types parameter.

4.  Click the **Save** button and the Advanced Part Number References
    Properties dialog will close, and the newly added component will
    display within the Rows parameter of the Node Editor Properties as
    shown in the screenshot below. Double click the added component to
    make further edits if needed.

![](../../Resources/Images/Competitor%20OE%20Number/95.png)

The Node List component defined within this parameter displays the
competitor and/or OE number information in a table / grid format. The
view can be further customized by configuring the data to display via
different display modes and adding different action buttons that users
can click while working with the competitor and/or OE number
information. The display modes can then be customized with a range of
headers, allowing for different information about the listed objects to
be displayed. The behavior of many of the various actions can be further
configured, also. For more information, see the **Node List Component**
topic within the **Web User Interfaces** section of **STEP Online
Help**[ here]{.mcFormatColor style="color: Blue;"}.

5.  Click the **Save** button and then click the **Close** button to
    close the designer.
