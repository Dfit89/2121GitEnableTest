---
description: 'Automotive Solution: Describes how to configure the
  Application Suggestions component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Application Suggestions Component
=================================================

The Application Suggestions component is a Node Editor component, often
used along with the Part Application Editor component, to display
potential applications listed as suggestions. The Application
Suggestions component displays the suggestion list based on the
configured reference types and plugins configured within the Application
Suggestion Plugins when a part is selected in the Tree navigator. For
information about how to use this component and its prerequisites, see
the **Application Suggestion Solution** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration
-------------

Below are steps to configure the Application Suggestions component
within a Node Editor. Each of the parameters for the Application
Suggestions Properties are described below.

1.  In the Web UI Designer, go to Node Editor Properties \> Child
    Components \> Rows parameter for the screen that needs to display
    application record suggestions.

![](../../Resources/Images/Competitor%20OE%20Number/97.png)

1.  Click the **Add** button, and the Add Component dialog will display.

![](../../Resources/Images/Application%20Suggestions/9.png)

3.  Select the Application Suggestions component, click **Add**, and the
    newly added component will display within the Rows parameter. In the
    screenshot below, the Application Suggestions component is
    configured along with the Part Application Editor and Headline
    components.

![](../../Resources/Images/Application%20Suggestions/13.png)

1.  Double click the newly added component available in the Rows
    parameter, and the Application Suggestions Properties dialog will
    display (as shown below). Parameter options are explained below:

![](../../Resources/Images/Application%20Suggestions/15.png)

**Height:**This optional parameter specifies the visual height of the
Advanced Part Number Suggestions component in pixels. By default, this
parameter is pre-populated with a value \'400.\' Users can enter a
numeric value to alter height of the component.

**Attribute Group:**This optional parameter, when configured with an
attribute group, sets up an additional unique condition for the
suggested application records. An attribute group which is valid for the
application records can be configured. For example, consider there are
two application records with the same reference target to the Part Type
and the Vehicle. Then the attribute values present within this attribute
group determines the uniqueness of the application records. If both the
application records has the same attribute values, then the system will
suggest as one single potential application record. If any one of the
attribute values differs for the application records, then the system
would suggest as two different potential application records.

The Node List component defined within this parameter displays the
suggested application records information in a table / grid format. The
view can be further customized by configuring the data to display via
different display modes and adding different action buttons that users
can click while working with the application records information. The
display modes can then be customized with a range of headers, allowing
for different information about the listed objects to be displayed. The
behavior of many of the various actions can also be further configured.
For more information, see the **Node List Component** topic within the
**Web User Interfaces** section of **STEP Online Help**[
here]{.mcFormatColor style="color: Blue;"}.

**Application Suggestion Plugins:** By default, this required parameter
is blank. The user can add one or more plugins by clicking the **Add**
button. It is mandatory to have at least one plugin so that when a part
is selected, system would follow the configurations provided in the
plugin and display the potential application records in accordance.

![](../../Resources/Images/Application%20Suggestions/16.png)

The Application Suggestion Plugins options are the following:

**Referenced Competitor / OE Number Part\'s Applications:** This plugin
is used to suggest the Competitor\'s application records where the
Competitor Number is referencing the OE Number of the current part. In
the example chart below, Application 1, Application 2, and Application 3
are suggested as the potential applications to Part A. Additional
configurations are required for this plugin.

![](../../Resources/Images/Application%20Suggestions/19.png)

When a user adds this plugin, an \'Add component\' dialog is displayed
prompting users to configure the associating reference types linked
between the part and the OE Number, and the reference types linked
between the Competitor and OE Number.

![](../../Resources/Images/Application%20Suggestions/17.png)

-   **Competitor Reference Type:** By default, this required parameter
    is blank. However, it is mandatory to add a Product Reference Type
    that establish a reference link between the Competitor to OE Number
    so that when a part is selected, the reference types listed within
    this parameter are followed and display the application records of
    the related competitor number on the targets. In order to have this
    parameter configured, user must establish a reference link between
    the Competitor to OE Number.

```{=html}
<!-- -->
```
-   For AutoCare solution this may be adding reference type which bears
    a relation from id \'AC\_PIESInterchangeItem\' to
    \'AC\_PIESInterchangeItem\'
-   For NAPA solution this may be adding reference type which bears a
    relation from id \'NAPA\_InterchangeProduct\' to
    \'NAPA\_InterchangeProduct\'
-   For TecDoc solution this may be adding reference type which bears a
    relation from id \'TD\_DS\_SupplierCompetitorNumber\' to
    \'TD\_DS\_OENumber\'

```{=html}
<!-- -->
```
-   **OE Number Reference Type:** By default, this required parameter is
    blank. However, it is mandatory to add one Product Reference Type so
    that when a part is selected, the reference types listed within this
    parameter are followed and fetch the Competitor number of the target
    OE number.

```{=html}
<!-- -->
```
-   For AutoCare solution this may be adding reference type with id
    \'AC\_PIESInterchange\'
-   For NAPA solution this may be adding reference type with id
    \'NAPA\_ProductToInterchangeProduct\'
-   For TecDoc solution this may be adding reference type with id
    \'TD\_SupplierArticleToOENumber\'

**Referenced Part\'s Application Suggestion Plugin:** This plugin is
used to suggest an other part\'s application records. Additional
configuration is required for this plugin. When a user adds this plugin,
an \'Add component\' dialog is displayed prompting users to configure
the associating reference type linked between the two parts.

![](../../Resources/Images/Application%20Suggestions/18.png)

**Reference Type:** By default, this required parameter is blank.
However, it is mandatory to add at least one Product Reference Type so
that when a part is selected, the reference types listed within this
parameter are followed and display the application records of the target
part.

-   For AutoCare solution this may be adding reference type with id
    \'AC\_PartRelation\'
-   For NAPA solution this may be adding reference type with id
    \'NAPA\_PartRelation\'
-   For TecDoc solution this may be adding reference type with id
    \'TD\_PartRelation\'

5.  Under the Child Components section of the Node List properties, in
    the dropdown select \'Node List\' \> click on \'go to component.\'
    The Node List Properties dialog with two pre-configured action
    buttons will display as shown below.

![](../../Resources/Images/Application%20Suggestions/14.png)

**Add Applications to Part Action:** This required action button adds
the selected application record to the selected part from the
Application Suggestions list. This is a ready-to-use button, and the
user can double click on the \'Add Applications to Part Action\' to
further configure the Icon style, Title, and Label of the action button
if necessary.

**Remove Application Suggestions Action:** This action button removes
the selected application record from the Part Number Suggestions list.
This is a ready-to-use button, and the user can double click on the
\'Remove Application Suggestions Action\' to further configure the Icon
style, Title and Label of the action button if necessary.

9.  Click the **Save** button, and then click the **Close** button to
    close the designer.
