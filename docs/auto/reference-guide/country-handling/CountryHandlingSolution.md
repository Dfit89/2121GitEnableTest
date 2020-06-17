---
description: 'Automotive Solution: Describes using and configuring the
  Country Handling solution that is intended to help users view, edit,
  and create accurate country handling inclusion and exclusion
  references for specific parts and applications.'
title: '\[%=Heading.AnyLevel%\]'
---

Country Handling Solution
=========================

PRODOC note: MEDU PDO- 1548, PRODOC- 1469, RDCUST- 2594, 2916,

Within the automotive industry, it is vital to properly maintain parts
data pertaining to country inclusion and/or exclusion to ensure
market-specific coverage and legal compliance. The Country Handling
solution helps users view, edit, and create accurate country handling
inclusion and exclusion references for specific parts and applications.
This Web UI solution also prevents users from creating conflicting
inclusion and/or exclusion relationships.

The Country Handling solution can be used within an Application Manager
Results Table via an \'Application Country Handling Table Header\'
component and within a Node Editor screen via a \'Country Handling
Value\' component.

This section addresses

-   Prerequisites
-   Using Country Handling ([here]{.mcFormatColor style="color: Blue;"})
-   Using Country Handling Value Editor to Add or Edit Country Handling
    Data ([here]{.mcFormatColor style="color: Blue;"})
-   Configuring Automotive - Country Model Component Model
    ([here]{.mcFormatColor style="color: Blue;"})
-   Configuring Application Country Handling Table Header
    ([here]{.mcFormatColor style="color: Blue;"})
-   Configuring Country Handling Value Component ([here]{.mcFormatColor
    style="color: Blue;"})
-   Configuring Reference Country Handling Table Header PRODOC note:
    BOND RDCUST- 3223

Prerequisites

1.  Apply the automotive recipe to the STEP instance to display the
    \'Automotive - Country Model\' component model within Workbench \>
    System Setup \> Component Models.
2.  Configure the \'Automotive - Country Model\' component model.

For more information, see the **Configuring Automotive - Country Model
Component Model** topic[ here]{.mcFormatColor style="color: Blue;"}.

1.  If needed, configure the \'Application Country Handling Table
    Header\' component.

For more information, see the **Configuring Application Country Handling
Table Header** topic[ here]{.mcFormatColor style="color: Blue;"}.

1.  If needed, configure the \'Country Handling Value\' component.

For more information, see the **Configuring Country Handling Value
Component** topic[ here]{.mcFormatColor style="color: Blue;"}.

Additionally, when implementing this solution, it is recommended
practice to create a \'Product Details\' screen within a Web UI and
configure it to display the Country Handling Value component when a
product of a specified object type is selected within the Tree
navigator. For more details on configuring screen mappings for this
configuration, see the **Mappings** topic within the **Main Properties
Overview** of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.
