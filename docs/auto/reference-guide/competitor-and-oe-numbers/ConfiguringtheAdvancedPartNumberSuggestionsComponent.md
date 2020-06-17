---
description: 'Automotive Solution: Describes how to configure the
  Advanced Part Number Suggestions component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Advanced Part Number Suggestions Component
==========================================================

Suggested OE numbers will display as a list. The suggested OE numbers
are Object Types valid for Reference Types. The Reference Number screen
is extended with this OE Number plugin. The Advanced Part Number
Suggestions component is a Node Editor component, often used along with
the Advanced Part Number References component, to display potential part
numbers listed as suggestions. The Advanced Part Number Suggestions
component displays the suggestion list based on the configured reference
types and Suggestion Plugins when a part is selected in the Tree
navigator. This component is an advanced feature of Part Number
Suggestions Component with additional features as explained in this
document. For information about how to use this component, and
prerequisites, see the **Competitor and OE Numbers Solution** topic[
here]{.mcFormatColor style="color: Blue;"}.

Configuration Steps

Below are steps to configure the Advanced Part Number Suggestions
component within a Node Editor. Each of the parameters for the Advanced
Part Number Suggestions Properties are described below.

1.  In the Web UI the Designer, go to Node Editor Properties \> Child
    Components \> Rows parameter for the screen that needs to display
    part number suggestions.

![](../../Resources/Images/Competitor%20OE%20Number/97.png)

1.  Click the **Add** button, and the Add Component dialog will display.

![](../../Resources/Images/Competitor%20OE%20Number/99.png)

1.  Select the Advanced Part Number Suggestions component, click
    **Add**, and the Advanced Part Number Suggestions Properties dialog
    will display. Parameter options are explained below:

![](../../Resources/Images/Competitor%20OE%20Number/100.png)

**Height:**This optional parameter specifies the visual height of the
Advanced Part Number Suggestions component in pixels. By default, this
parameter is pre-populated with a value \'400.\' Users can enter a
numeric value to alter height of the component.

**Reference Types:** By default, this required parameter is blank.
However, it is mandatory to add at least one Product Reference Type so
that when a part is selected, STEP can follow the reference types listed
within this parameter and directly display the target and/or targets
related information based on the plugins configured in the Suggestion
Plugins parameter. Some examples are:

-   Within the AutoCare solution, when a part is selected STEP would
    need to follow the **PIES Interchange** reference and display the
    target and/or targets related information.

```{=html}
<!-- -->
```
-   Within the NAPA solution, when a part is selected STEP would need to
    follow the **Product to Interchange Product** reference and display
    the target and/or targets related information.

```{=html}
<!-- -->
```
-   Within the TecDoc solution, when a part is selected STEP would need
    to either follow the **Supplier Article to Competitor Number**
    and/or the **Supplier Article to OE Number** reference and display
    the target and/or targets related to the selected reference.

4.  Click the **Save** button, the Advanced Part Number Suggestions
    Properties dialog will close, and the newly added component will
    display within the Rows parameter.

![](../../Resources/Images/Competitor%20OE%20Number/101.png)

5.  Double click the newly added Advanced Part Number Suggestions
    component, and the Advanced Part Number Suggestions Properties will
    display as shown below.

![](../../Resources/Images/Competitor%20OE%20Number/84.png)

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

**Suggestion Plugins:** By default, this required parameter is
pre-populated with the Same Number plugin. Optionally, a user can add
one or more plugins by clicking the **Add** button. It is mandatory to
have at least one plugin so that when a part is selected, information
about the suggested competitor and/or OE number can be displayed.

![](../../Resources/Images/Competitor%20OE%20Number/25.png)

The Suggestion Plugins options are the following:

**Common applications:** This plugin is used to suggest other part
numbers that have the same applications as the current part number.
Additional configuration parameters are not available for this plugin.

**Common number:** This plugin suggests other part number(s) that are
referencing the same part number (or Competitor Number or OE Number) as
the currently selected part number does. In other words, if the current
part refers to a part number (OE Number / Competitor Number) that is
referenced by another part number (OE Number / Competitor Number), then
the other part number is suggested via this plugin. For example, if two
different parts \'JK21499\' and \'JK36004\' are referenced to a part
\'GL26409\', then part \'JK36004\' is suggested in the Part Number
Suggestions component when part \'JK21499\' is selected.

Double click on the plugin name in the Suggestions Plugins parameter to
further configure the plugin.

![](../../Resources/Images/Competitor%20OE%20Number/27.png)

-   **Reference Types:** By default, this required parameter is blank.
    However, it is mandatory to add at least one Product Reference Type
    so that when a part is selected, the reference types listed within
    this parameter are followed and display the target and/or related
    competitor and/or OE number information on the targets.

**Referenced By:** This plugin is used for suggesting part numbers that
are referencing the current part number. Additional configuration is
required for this plugin. Double click the plugin name in the
Suggestions Plugins parameter and click on the **Add** button to add the
reference type. When a part is selected, the reference types listed
within this parameter are followed, and the source part number and its
related information is displayed.

![](../../Resources/Images/Competitor%20OE%20Number/24.png)

-   For AutoCare solution this may be adding reference type with id
    \'AC\_PartRelation\'
-   For NAPA solution this may be adding reference type with id
    \'NAPA\_PartRelation\'
-   For TecDoc solution this may be adding reference type with id
    \'TD\_PartRelation\'

**Referenced Chain:** This plugin is used for suggesting a series of
part numbers that reference one another. In other words, part number
\'A\' suggests part number \'B.\' Part number \'B\' suggests Part number
\'C\' and so on. Double click on the plugin name in the Suggestions
Plugins parameter to further configure the plugin.

![](../../Resources/Images/Competitor%20OE%20Number/26.png)

-   **Max Chain Size:** By default, this required parameter is blank and
    allows a numeric value. This parameter defines the maximum allowed
    chain size to follow the reference types listed within the next
    parameter Reference Types. For example, If the value \'4\' is
    entered against the Max Chain Size parameter, then the maximum chain
    links of references that the STEP looks to suggest as potential Part
    Number / OE Numbers / Competitor Number is four.
-   **Reference Types:** By default, this required parameter is blank.
    However, it is mandatory to add at least one Product Reference Type.
    When a part is selected, the reference types listed within this
    parameter are followed, and the target and/or related competitor
    and/or OE number information on the targets are displayed.

For example, consider there are six different parts \'JK21499\',
\'JK36004\', \'JK36009\', \'JK36112\', \'VC21499\' and \'VC36004\'
interlinked in a manner, \'JK21499\' is referenced by \'JK36004\',
\'JK36004\' is referenced by \'JK36009\', \'JK36009\' is referenced by
\'JK36112\', \'JK36112\' is referenced by \'VC21499\' and \'VC21499\' is
referenced by \'VC36004\'. Assuming that the Max Chain Size value as
\'4\' and all the references connecting these parts are listed within
the Reference Types parameter, the Part Number Suggestions component
would suggest only the parts \'JK36004\', \'JK36009\', \'JK36112\' and
\'VC21499\' when the part \'JK21499\' is selected.

**Same Number:** This plugin is used to suggest other part numbers based
upon matching part number names used in the Part Number Suggestions
component. Additional configuration parameters are not available for
this plugin. However, customers with the Extension API license can
create their own plugins. For more information, click the STEP API
Documentation button on the Start Page, or contact your Stibo Systems
representative.

6.  Go to Child Components \> Node List \>in the dropdown select \'Node
    List\' \> click on \'go to component.\' The Node List Properties
    dialog with two pre-configured action buttons will display as shown
    below.

![](../../Resources/Images/Competitor%20OE%20Number/85.png)

**Add suggestion(s) to Reference Numbers Action:** This required action
button adds the selected competitor and/or OE part number reference to a
selected part from the Part Number Suggestions list. Further
configuration is required as explained below.

**Remove from suggestions Action:** This action button removes the
selected Competitor and/or OE part number reference of a selected part
from the Part Number Suggestions list. This is a ready to use button and
user can double click on the \'Remove from suggestions Action\' to
further configure the Icon style, title and label of the action button
if necessary.

7.  Double click on the \'Add suggestion(s) to Reference Numbers
    Action\' to configure, and the Add suggestion(s) to Reference
    Numbers Action Properties will display.

![](../../Resources/Images/Competitor%20OE%20Number/86.png)

8.  In the Reference Types to Create parameter, Click the **Add** button
    and select the Reference Type to determine the reference type which
    the action button follows to create a reference. The action button
    follows through the reference type(s) listed within this parameter
    and creates the references of the selected Competitor and/or OE part
    number to the selected part.

It is required to add a minimum of one reference type in the Reference
Types to Create parameter. Attempting to save the configuration prior to
configuring the Reference Types to Create parameter will result in the
following warning: The screen cannot be saved while one or more
components has configuration errors.

![](../../Resources/Images/Competitor%20OE%20Number/87.png)

9.  Click the **Save** button, and then click the **Close** button to
    close the designer.
