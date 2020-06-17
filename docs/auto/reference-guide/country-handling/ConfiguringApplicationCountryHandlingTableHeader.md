---
description: 'Automotive Solution: Describes how to configure the
  Application Country Handling Table Header component for the Country
  Handling solution. Component make it is possible to display existing
  country handling on applications within the Results Table of an
  Application Manager screen. From there, users can double click a cell
  and a value editor will display allowing users to add and/or remove
  country inclusions and/or exclusions. '
title: '\[%=Heading.AnyLevel%\]'
---

Configuring Application Country Handling Table Header
=====================================================

PRODOC note: MEDU RDCUST- 2916 When configured, the \'Application
Country Handling Table Header\' component can be used to display the
country handling data within an Application Manager Results Table.
Additionally, when a cell within the Table Header is clicked, a Value
editor will display allowing users to edit country handling data.

Prerequisites

Configuration of the Automotive - Country Model component model is
required before the Application Country Handling Table Header component
can be configured. For more information, see the **Prerequisites**
section of the **Country Handling Solution** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Attempting to add the Application Country Handling Table Header
component to a Web UI prior to configuring the Automotive - Country
Model component model will result in the following warning: The screen
cannot be saved while one or more components has configuration errors.

![](../../Resources/Images/Country%20Incl%20Excl/Warn.png)

Configuration Steps

Below are steps to configure the Application Country Handling Table
Header component within a Node Editor. Each of the parameters for the
Application Country Handling Table Header Properties are described
below.

1.  Using the Web UI designer as shown in the image below, go to Node
    List Properties Headers parameter for the Application Manager screen
    that needs to display country handling data.
2.  Click the **Add** button for the Headers parameter, and the Add
    Component dialog will display.
3.  Find and select the **Application Country Handling Table Header**
    component.
4.  Click the **Add** button, and the Application Country Handling Table
    Header Properties dialog will display (as shown below).

![](../../Resources/Images/Country%20Incl%20Excl/41.png)

1.  Populate the required parameters listed below.

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

-   **Dimensions:** By default, the parameter is blank. Optionally, to
    configure column width and height, select \'Table Header
    Dimensions.\'
-   **Included By Default:** By default, the parameter is disabled. This
    filter option provides user an option to include all countries by
    default in the Country Inclusion list. When disabled, all countries
    are listed in the Country Exclusion list and user needs to add the
    desired countries to the Country Inclusion list. When enabled, all
    countries are listed in the Country Inclusion list and user
    deselects the excluded countries from the Country Inclusion list.
    PRODOC note: BOND RDCUST-3221and 3223 Discuss this with Sujay

```{=html}
<!-- -->
```
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

-   **Label:** By default, the parameter is blank. But after clicking
    the **Add** button, the default column header label (Countries) will
    be stored. Optionally enter a desired label to be displayed as the
    column header within the Application Manager Results Table.
-   **Table Sorting:** By default, the parameter is blank. Optionally,
    select from the dropdown values to specify the default sorting order
    of the column data.

7.  Once the required parameters are populated, the Add button will
    activate. Click the **Add** button to save the newly added component
    to the Headers parameter.
8.  Optionally, on the Node List Properties Headers parameter, use the
    **Up** and/or **Down** buttons to configure the order in which the
    newly added column should display within the Results Table.
9.  Click the **Save** and **Close** buttons for the designer.
