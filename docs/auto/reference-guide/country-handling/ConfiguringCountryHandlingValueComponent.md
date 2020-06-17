---
description: 'Automotive Solution: Describes how to configure the
  Country Handling Value component to display the country inclusion /
  exclusion data within a Node Editor screen used to view and/or edit
  country handling data on parts and/or applications (i.e., Product
  Details screen).'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring Country Handling Value Component
============================================

PRODOC note: MEDU RDCUST- 3012 includes spec doc for labels.

When using the Country Handling solution within a Node Editor, the
\'Country Handling Value\' component can be configured to display the
country inclusion / exclusion data within a Node Editor screen used to
view and/or edit country handling data on parts and/or applications
(i.e., Product Details screen).

When configured, this component can be used to view and edit the country
inclusion data for applications and/or parts. Once an application and/or
part object type is selected, then the Country Handling Value component
displays only for those countries currently referenced to the attribute
or part for inclusion. It only displays inclusion and exclusion data for
the selected object. Therefore it does not display any inclusion nor
exclusion data from the part\'s parent and/or child objects (i.e., Part
Types, Applications).

Prerequisites

Configuration of the Automotive - Country Model component model is
required before the Country Handling Value component can be configured.
For more information, see the **Prerequisites** section of the **Country
Handling Solution** topic[ here]{.mcFormatColor style="color: Blue;"}.

Attempting to add the Country Handling Value component to a Web UI prior
to configuring the Automotive - Country Model component model will
result in the following warning: The screen cannot be saved while one or
more components has configuration errors.

![](../../Resources/Images/Country%20Incl%20Excl/Warn.png)

Configuration Steps

Below are steps to configure the Country Handling Value component within
a Node Editor. Each of the parameters for the Country Handling Value
Properties are described below.

1.  Using Web UI designer, go to Node Editor Properties Child Components
    Rows parameter for the screen that needs to display country handling
    data.
2.  Click the **Add** button for the Child Components Rows parameter,
    and the Add Component dialog will display.
3.  Find and select the **Country Handling Value** component, click the
    **Add** button, and the Country Handling Value Properties dialog
    will display (as shown below).

![](../../Resources/Images/Country%20Incl%20Excl/51.png)

1.  Populate the required parameters listed below.

-   **Exclude Attribute:** This required parameter is used to select a
    multivalued attribute where the country exclusion data is stored.
    Attribute values (country names) within this attribute will not be
    displayed as included within the country handling components. to
    browse and/or search for the necessary attribute value.
-   For the AutoCare solution, this may be [\<\<SIMO / NIFE to
    provide\>\>]{style="color: #ff6347;"}
-   For the NAPA solution, this may be [\<\<SIMO / NIFE to
    provide\>\>]{style="color: #ff6347;"}
-   For the TecDoc solution, this may be \'TD\_ATTR\_LKZ\_Exclude\'

A value cannot exist in both the configured exclude attribute and in the
include attribute. If a value is stored within the exclusion attribute,
and is later selected for inclusion within the Country Handling Value
editor, then the referenced value is removed from the exclusion
attribute. However, if that attribute value is deselected from
inclusion, it is **NOT** added back to the exclusion attribute. When
this occurs, the assumption is that desired attribute values for
inclusion are specified within the inclusion attribute, and therefore
all others are excluded.

-   **Include Attribute:** This required parameter is used to select a
    multivalued attribute where the country inclusion data will be
    stored. to browse and/or search for the necessary attribute value.

```{=html}
<!-- -->
```
-   For the AutoCare solution, this may be [\<\<SIMO / NIFE to
    provide\>\>]{style="color: #ff6347;"}
-   For the NAPA solution, this may be [\<\<SIMO / NIFE to
    provide\>\>]{style="color: #ff6347;"}
-   For the TecDoc solution, this may be \'TD\_ATTR\_LKZ\_Include\'

When an attribute value selection is made within the Country Handling
Value editor, the referenced attribute values are stored within the
configured inclusion attribute. However, when an attribute value is
deselected from inclusion, it is **NOT** added to the exclusion
attribute. When this occurs, the assumption is made that desired
attribute values for inclusion are specified within the inclusion
attribute, and therefore all others are excluded.

1.  Optionally, populate the other parameters listed below.

-   **Included By Default:** By default, the parameter is disabled. This
    filter option provides user an option to include all countries by
    default in the Country Inclusion list. When disabled, all countries
    are listed in the Country Exclusion list and user needs to add the
    desired countries to the Country Inclusion list. When enabled, all
    countries are listed in the Country Inclusion list and user
    deselects the excluded countries from the Country Inclusion list.
    PRODOC note: BOND RDCUST-3221 Discuss this with Sujay
-   **Context Help:** By default, the parameter is blank. But after
    clicking the **Add** button, the default label (Selected Countries)
    will be stored. Optionally, enter desired text to be displayed when
    a user hovers over the component label.
-   **Label:** By default, the parameter is blank. But after clicking
    the **Add** button, the default label (Selected Countries) will be
    stored. Optionally, enter a desired label to be displayed within the
    Node Editor and to the left of the component.

7.  Once the required parameters are populated, the Add button will
    activate. Click the **Add** button to save the newly added component
    to the Headers parameter.
8.  Optionally, on the Node Editor Properties Child Components Rows
    parameter, use the **Up** and/or **Down** buttons to configure the
    order in which the newly added component should display within the
    node editor.
9.  Click the **Save** and **Close** buttons for the designer.
