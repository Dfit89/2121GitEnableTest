---
description: 'Automotive Solution: Describes how to configure the Part
  Number References Component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Part Number References Component
================================================

PRODOC note: MEDU PRODOC- 1395 PRODOC note: BOND PRODOC- 1519The Part
Number References component is a Node Editor component used to display
referenced part numbers and their attribute and/or metadata values when
a part number is selected within the Tree navigator.

This section describes how to configure the Part Number References
component. For information about how to use this component, and
prerequisites, see the **Competitor and OE Numbers Solution** topic[
here]{.mcFormatColor style="color: Blue;"}.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

Anyone configuring the Part Number References Component within a Node
Editor is expected to be familiar with the basic configuration and
functionalities of Node Editor Component as basic concepts for working
with Node Editor component are not covered in this section. For more
information, see the **Node Editor Component** topic within the **Using
a Web UI** section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration Steps

Configuration Steps {#configuration-steps conditions="Primary.Web"}
-------------------

Below are the steps to configure the Part Number References component
within a Node Editor. Each of the parameters for the Part Number
References Properties are described below.

1.  Using the Designer, go to Node Editor Properties Child Components
    Rows parameter for the screen that needs to display competitor
    and/or OE number information.
2.  Click the **Add** button for the Child Components Rows parameter,
    and the Add Component dialog will display.
3.  Find and select the **Part Number References** component, click the
    **Add** button, and the Part Number References Properties dialog
    will display (as shown below).

![](../../Resources/Images/BRs/RefNumProp.jpg)

**Business Action to Invoke:** By default, this field is blank.
Optionally, select a Business Action to be invoked after a new part is
created using the Create New Part dialog. This can be helpful when a
Business Action is configured to normalize / harmonize a part number.
For more information about using this feature, see the **Creating and
Referencing New Competitor and/or OE Part Numbers** topic within this
section[ here]{.mcFormatColor style="color: Blue;"}.

**Table Headers:** By default, the following Table Header components are
added to the parameter:

**Manufacturer References:** Table header component used to display the
manufacturer and/or attribute value references of a selected part.
Includes the following parameters:

![](../../Resources/Images/BRs/6.jpg)

-   **Label:** By default, the Label parameter is populated as
    \'Manufacturer.\' Optionally edit the parameter to a more suitable
    label.
-   **Display Value:** By default, parameter uses the \'PARENT\_NAME\'
    value. This allows the parent of the applicated competitor and/or OE
    part number to display within the Web UI. Optionally, the
    \'ATTRIBUTE\_VALUE\' value can be selected. The ATTRIBUTE\_VALUE
    allows the values of the attribute selected within the \'Attribute\'
    parameter to display within the Web UI.

```{=html}
<!-- -->
```
-   **Attribute:** Parameter must be populated with an attribute that is
    valid for the competitor or OE number Object Types.

The Attribute parameter should only be populated when the
\'ATTRIBUTE\_VALUE\' value is selected. Otherwise the component should
be configured as shown in the example above.

**Name Header:** Table header component that displays the name of the
part numbers in the table. Includes the following parameters:

![](../../Resources/Images/BRs/7.jpg)

-   **Dimensions:** By default, the parameter is blank. Optionally,
    select to use the \'Table Header Dimensions.\'
-   **Label:** By default, when the Label parameter is blank, the column
    label will display as \'Name.\' Optionally edit the parameter to a
    more suitable label.
-   **Table Sorting:** Optionally, specifies the default sorting to be
    applied to the header.

Additional components can be added to the Table Headers parameter. It
can be especially helpful to add the \'Headline\' child component to
provide a visual separation and heading between components, and/or
components used within the Headers parameter of an Application Manager
Screen (i.e., Application Set Assembly, Application Part Type Title
Header, Application Set Part, Application Condition Header - Individual,
Application Condition Header - Group, Application Comment, Application
Asset References).

**New Number Prefix:** By default, this mandatory parameter is populated
with the following prefix: \'NewReferenceNumber\_.\' This prefix will be
used for the ID of any part number that is created using this Create New
Part dialog (as shown below). This must be a unique prefix. Do not use
an existing prefix if this default prefix is currently in use for your
implementation, then edit the prefix so it is unique, otherwise errors
will occur. Optionally, if a different prefix is desired, edit the
prefix to something more suitable, but unique.

![](../../Resources/Images/BRs/11.jpg)

**Original Number Attribute:** PRODOC note: MEDU RDCUST-2975 By default,
this field is blank. Because part numbers created using the Create New
Part dialog are normalized / harmonized to use alphanumeric characters
only, this parameter allows for the original part numbers created using
special characters, spaces, and/or non ASCII characters to be stored and
searchable. Optionally, select an attribute that will be used to store
the original part number exactly as it is entered when creating a new
part using the Create New Part dialog. The attribute selected for this
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
values on the targets.

For example, within the AutoCare solution, when a part is selected STEP
would need to follow the **PIES Interchange** reference and display the
targets and/or a related attribute values on the targets.

For example, within the NAPA solution, when a part is selected STEP
would need to follow the **Product to Interchange Product** reference
and display the targets and/or a related attribute values on the
targets.

For example, within the TecDoc solution, when a part is selected STEP
would need to follow the **Supplier Article to Competitor Number**
and/or the **Supplier Article to OE Number** references and display
their targets and/or a related attribute values on the targets.

4.  Click the **Save** button and the Part Number References Properties
    dialog will close, and the newly added component will display within
    the Rows parameter.

5.  Click the **Save** button and then click the **Close** button to
    close the designer.
