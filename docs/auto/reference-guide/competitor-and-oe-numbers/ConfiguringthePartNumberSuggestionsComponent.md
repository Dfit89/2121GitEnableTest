---
description: 'Automotive Solution: Describes how to configure the Part
  Number Suggestions component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Part Number Suggestions Component
=================================================

PRODOC note: MEDU RDCUST-2830 Suggested OE numbers will display as a
list. The suggested OE numbers are Object Types valid for Reference
Types. The Reference Number screen is extended with this OE Number
plugin. The Part Number Suggestions component is a Node Editor component
usually used along with the Part Number References component to display
potential part numbers listed as suggestions. Part number suggestions
displays the suggestion list based on the configured reference types and
Suggestion Plugins when a part is selected in the Tree navigator. For
information about how to use this component, and prerequisites, see the
**Competitor and OE Numbers Solution** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration Steps

Below are steps to configure the Part Number Suggestions component
within a Node Editor. Each of the parameters for the Part Number
Suggestions Properties are described below.

1.  Using the Designer, go to Node Editor Properties Child Components
    for the screen that needs to display part number suggestions.
2.  Click the **Add** button for the Child Components Rows parameter,
    and the Add Component dialog will display.
3.  Search for and select the Part Number Suggestions component.
4.  Click the **Add** button, the Add Component dialog will close, and
    the Part Number Suggestions Properties dialog will display as shown
    below.

![](../../Resources/Images/Competitor%20OE%20Number/21.jpg)

**Table Headers:** By default, this required parameter is pre-populated
with the Manufacturer References and Name Header components. Optionally
edit these components, and/or add additional Headers components to
display information about the suggested competitor and/or OE number.

**Reference Types:** By default, this required parameter is blank.
However, it is mandatory to add at least one Product Reference Type so
that when a part is selected, STEP can follow the reference types listed
within this parameter and directly display the targets and/or target
related information based on the plugins configured in the Suggestion
Plugins parameter.

-   For example, within the AutoCare solution, when a part is selected
    STEP would need to follow the **PIES Interchange** reference and
    display the targets and/or target related information.

```{=html}
<!-- -->
```
-   For example, within the NAPA solution, when a part is selected STEP
    would need to follow the **Product to Interchange Product**
    reference and display the targets and/or target related information.

```{=html}
<!-- -->
```
-   For example, within the TecDoc solution, when a part is selected
    STEP would need to follow the **Supplier Article to Competitor
    Number** and/or the **Supplier Article to OE Number** references and
    display their targets and/or target related information.

5.  Click the **Save** button, the Part Number Suggestions Properties
    dialog will close, and the newly added component will display within
    the Rows parameter.
6.  Double click the newly added Part Number Suggestions component, and
    the Part Number Suggestions Properties will display as shown below.

![](../../Resources/Images/Competitor%20OE%20Number/23.jpg)

**Suggestion Plugins:** By default, this required parameter is
pre-populated with the Same Number plugin. Optionally, a user can add
one or more plugins by clicking the **Add** button. It is mandatory to
add at least one plugin so that when a part is selected, information
about the suggested competitor and/or OE number can be displayed.

![](../../Resources/Images/Competitor%20OE%20Number/25.png)

**Common applications:** This plugin is used to suggest other part
numbers that have the same applications as the current part number.
Additional configuration parameters are not available for this plugin.

**Common number:** This plugin suggests the other part number(s) that
are referencing the same part number (or Competitor Number or OE Number)
as current part number does. In other words, If the current part refers
to a part number (OE Number / Competitor Number) that is referenced by
an other part number (OE Number / Competitor Number), then the other
part number is suggested via this plugin. For example, if two different
parts \'JK21499\' and \'JK36004\' are referenced to a part \'GL26409\',
then part \'JK36004\' is suggested in the Part Number Suggestions
component when part \'JK21499\' is selected.

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

**Referenced Chain:** This plugin is used for suggesting other part
numbers that are referenced by the part number which is already
referenced by the current part number. Double click on the plugin name
in the Suggestions Plugins parameter to further configure the plugin.

![](../../Resources/Images/Competitor%20OE%20Number/26.png)

-   **Max Chain Size:** By default, this required parameter is blank and
    allows a numeric value. This parameter defines the maximum allowed
    chain size to follow the reference types listed within the next
    parameter Reference Types. For example, If the value \'4\' is
    entered against the Max Chain Size parameter, then the maximum chain
    links of references that the STEP looks to suggest potential Part
    Number / OE Numbers / Competitor Number is four.
-   **Reference Types:** By default, this required parameter is blank.
    However, it is mandatory to add at least one Product Reference Type.
    When a part is selected, the reference types listed within this
    parameter are followed and the target and/or related competitor
    and/or OE number information on the targets are displayed.

For example, consider there are six different parts \'JK21499\',
\'JK36004\', \'JK36009\', \'JK36112\', \'VC21499\' and \'VC36004\'
interlinked in a manner, \'JK21499\' is referenced by \'JK36004\',
\'JK36004\' is referenced by \'JK36009\', \'JK36009\' is referenced by
\'JK36112\', \'JK36112\' is referenced by \'VC21499\' and \'VC21499\' is
referenced by \'VC36004\'. Assuming that the Max Chain Size value as
\'4\' and all the references connecting these parts are listed within
the Reference Types parameter, the Part Number Suggestions component
would suggest the parts \'JK36004\', \'JK36009\', \'JK36112\' and
\'VC21499\' when the part \'JK21499\' is selected.

**Same Number:** This plugin is used to suggest other part numbers based
upon matching part number names used in the Part Number Suggestions
component. Additional configuration parameters are not available for
this plugin. However, customers with the Extension API license can
create their own plugins. For more information, click the STEP API
Documentation button on the Start Page, or contact your Stibo Systems
representative.

7.  Click the **Save** button and then click the **Close** button to
    close the designer.
