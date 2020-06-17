---
description: 'Automotive Solution: Describes how to configure the
  Application Competitor or OE Part Numbers Table Header component'
title: Configuring the Application Competitor or OE Part Numbers Table
  Header Component
---

Configuring the Application Competitor or OE Part Numbers Table Header Component
================================================================================

PRODOC note: MEDU PRODOC- 1519, RDCUST- 3012, 2956 SEE THE MP NOTE!!!

PRODOC note: Per convo with LURE he will be sending me his setup notes.
New object type is \'OE Application AutoCare\' Interchange Application

The Application Competitor or OE Part Numbers Table Header component is
a Table Header component used to display the competitor or OE
manufacturer part number and name in the Application Manager results
table. Additionally, when a part number value within the column is
clicked, a read-only dialog will display the competitor or OEM
applications. For information about how to use this component and its
prerequisites, see the **Competitor and OE Numbers Solution** topic[
here]{.mcFormatColor style="color: Blue;" conditions="Primary.Web"}.

Within the search result displayed in the Application Manager screen,
the Application Competitor or OE Part Numbers Table Header suggests
potential matches for the searched applications based on existing
competitor and/or OE part number application references and/or matching
applications within STEP.

As a prerequisites, after Easy Setup actions, user needs to configure
the standard data model in workbench along with the Web UI configuration
steps mentioned below. For more information about how to setup the data
model to use this component, see the **Configuring the Data Model for
Application Competitor or OE Part Numbers Table Header** topic[
here]{.mcFormatColor style="color: Blue;"}.

Below are steps to configure the Application Competitor or OE Part
Numbers Table Header Component within an Application Manager Node List.
Each of the parameters for the Application Competitor or OE Part Numbers
Properties are described below.

1.  Using the Designer, go to Vehicle Type Search Panel Properties for
    the Application Manager screen that needs to display competitor
    and/or OE number (Interchange product) information.
2.  Click the **Add** button for the Application Object Types parameter,
    and the Select Node(s) dialog will display.
3.  Find and select the Interchange application (competitor or OE number
    application) object type whose part numbers and manufacturer name
    (optional) for each application will display within the column.

-   For the AutoCare solution, this may be
    \'AC\_PIESInterchangeApplication\'
-   For the NAPA solution, this may be \'NAPA\_InterchangeApplication\'
-   For the TecDoc solution, this may be
    \'TD\_DS\_CompetitorNumberApplication\' and/or
    \'TD\_DS\_OENumberApplication\'

![](../../Resources/Images/Competitor%20OE%20Number/14.jpg)

4.  In the Designer, navigate to Node List Properties Headers parameter
    for the Application Manager screen that needs to display competitor
    and/or OE number information.
5.  Click the **Add** button for the Headers parameter, and the Add
    Component dialog will display.
6.  Find and select the **Application Competitor or OE Part Numbers**
    component.
7.  Click the **Add** button, and the Application Competitor or OE Part
    Numbers Properties dialog will display (as shown below).

![](../../Resources/Images/Competitor%20OE%20Number/11.png)

![](../../Resources/Images/Competitor%20OE%20Number/13.png)

1.  Populate the required parameter listed below.

-   **Part Number Object Type:** This required parameter is used to
    select a competitor or OEM part number object type whose part
    numbers and manufacturer name (optional) for each application will
    display within the column. to browse and/or search for the necessary
    Object Type.
-   For the AutoCare solution, this may be \'AC\_PIESInterchangeItem\'
-   For the NAPA solution, this may be \'NAPA\_InterchangeProduct\'
-   For the TecDoc solution, this may be
    \'TD\_DS\_SupplierCompetitorNumber\' or \'TD\_DS\_OENumber\'

9.  Optionally, populate the other parameters listed below.

-   **Display Manufacturer Name:** By default, this parameter is
    disabled, and only the manufacturer part number of the object type
    configured within the \'Part Number Object Type\' parameter will
    display. Enable this parameter to display part numbers with their
    default manufacturer name.
-   **Alternate Manufacturer Attribute:** This parameter is used to
    select an attribute where the result cell displays the selected
    attribute value along with the part number. For this value to
    display within the results table column, the Display Manufacturer
    Name parameter must be enabled. This parameter is usually used when
    user needs to display an alternate manufacturer name other than the
    name provided in the parent object. to browse and/or search for the
    necessary attribute valid to the object type selected in the \'Part
    Number Object Type\' parameter.
-   **Column Label:** By default, when the parameter is blank, the
    column label will display as \'Competitor / OEM.\' Optionally, edit
    the parameter to a more suitable label.
-   **Dialog Label:** By default, when the parameter is blank, the
    dialog that displays when a user clicks the part number value within
    the column will use the \'Competitor or OEM Applications\' title.
    Optionally, edit the parameter to a more suitable title.
-   **Blacklisted Attributes:** Click the Add button to add one or more
    attributes that do not need to display on the details dialog when a
    user clicks the part number value within the column.
-   **Blacklisted Attribute Groups:** Click the Add button to add one or
    more Attribute Groups that will hide attributes that should not
    display on the details dialog when a user clicks the part number
    value within the column. More information about the **Blacklisted
    Attribute Group** parameter can be found in the **Setting up
    Blacklisted Attribute Groups in Web UI** section of the **Handling
    Duplicated Attributes in Web UI** documentation[
    here]{.mcFormatColor style="color: Blue;"}.
-   **Blacklisted References:** Click the Add button to add one or more
    reference types that will not display on the details dialog when a
    user clicks the part number value within the column.
-   **Dimensions:** Optionally, determine the table header height and/or
    width dimensions. Only valid when the Multi Edit display mode is
    used.
-   **Table Sorting:** Optionally, specifies the default sorting to be
    applied to the header.

10. Click the **Add** button.
