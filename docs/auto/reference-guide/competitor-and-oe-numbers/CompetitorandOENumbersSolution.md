---
description: 'Automotive Solution: Describes how to implement the
  competitor and OE numbers solution.'
title: '\[%=Heading.AnyLevel%\]'
---

Competitor and OE Numbers Solution
==================================

PRODOC note: MEDU RDCUST-2702 is the Epic. **Why:** To make the OE
handling solution more applicable for the end users, we want to be able
to suggest which OE numbers a part might be linked to. **What:** Based
on existing OE number references and competitor number references, we
are able to extract potential applications and potential OE numbers.
When doing this we should sort the suggestions by the most relevant
first and cut the list if there are to many suggestions or the
confidence level is to low.

A competitor number refers to the part number used by a competitor.
Whereas an OE number refers to the original parts used by the original
equipment manufacturer to assemble a vehicle at the factory. This number
is only unique within parts from that manufacturer. For example, an OE
number should always be displayed with the OEM (Original Equipment
Manufacturer) name behind the number. This means that ABC123 AUDI will
usually not be the same part as ABC123 BMW. But on the other hand, they
could be the same part if both manufacturers acquired their part from
the same supplier.

With the automotive solution, it is easy to maintain data related to
both the competitor part number and OE number. The automotive solution
not only helps users more easily view, edit, and create competitor
and/or OE part number references for specific parts, but also suggest
potential matches. In other words, when configured, STEP can suggest
potential matches for competitor and/or OE part numbers based on
existing competitor and/or OE part number references and/or matching
part numbers within STEP. This occurs when a part is selected, STEP
looks at the configured Reference Types and displays their targets,
attribute values, and/or metadata via configurations within the \'Part
Number References\' Node Editor component.

When the Part Number References and/or Part Number Suggestions
components are configured as shown below, Web UI users can:

1.  View existing competitor and/or OE part number references and
    related data.
2.  View competitor and/or OE part number reference suggestions and
    related data.
3.  View information about the suggested part number.
4.  Add competitor and/or OE part number references manually.
5.  Add competitor and/or OE part number references from suggestions.
6.  Remove existing competitor and/or OE part number references.
7.  Remove competitor and/or OE part number references from suggestions.

![](../../Resources/Images/Competitor%20OE%20Number/1.jpg)

In the example above, part 90069 is selected within a Web UI Tree, and a
Web UI screen (Product Details) is configured to display the competitor
and OE numbers on separate tabs (OE Numbers, Competitor Numbers). Though
only the content for the \'OE Numbers\' tab is displayed below, the
layout and features on both tabs are the same.

This section addresses:

-   Prerequisites

-   Adding Part Number References Manually ([here]{.mcFormatColor
    style="color: Blue;"})

-   Adding Part Number References from Suggestions
    ([here]{.mcFormatColor style="color: Blue;"})

-   Removing Existing Part Number References ([here]{.mcFormatColor
    style="color: Blue;"})

-   Removing Part Number Reference Suggestions ([here]{.mcFormatColor
    style="color: Blue;"})

-   Creating and Referencing New Competitor and/or OE Part Numbers
    ([here]{.mcFormatColor style="color: Blue;"})

-   Configuring the Part Number References Component
    ([here]{.mcFormatColor style="color: Blue;"})

-   Configuring the Part Number Suggestions Component
    ([here]{.mcFormatColor style="color: Blue;"})

-   Configuring the Advanced Part Number References Component
    ([here]{.mcFormatColor style="color: Blue;"})

-   Configuring the Advanced Part Number Suggestions Component
    ([here]{.mcFormatColor style="color: Blue;"})

-   Configuring the Data Model for Application Competitor or OE Part
    Numbers Table Header ([here]{.mcFormatColor style="color: Blue;"})

-   Configuring the Application Competitor or OE Part Numbers Table
    Header Component ([here]{.mcFormatColor style="color: Blue;"})

-   Configuring the Metadata Attribute References Component
    ([here]{.mcFormatColor style="color: Blue;"})

Prerequisites {#prerequisites .RNNoTOC conditions="Primary.Print"}
-------------

Prerequisites {#prerequisites-1 conditions="Primary.Web"}
-------------

When implementing this solution, it is suggested to create a \'Product
Details\' screen within a Web UI and configure it to display when a
product is selected within the Tree navigator. The Product Details
screen should be created via a Node Details screen with a Tab Control
that is configured to display a \'Competitor Numbers\' and an \'OE
Numbers\' Tab Page. Within each of these Tab Pages a Node Editor can be
configured with \'Part Number References\' and/or \'Part Number
Suggestions\' components. The \'Part Number References\' component can
be configured to display competitor and/or OE number data. Whereas, the
\'Part Number Suggestions\' component can be configured to display
suggested competitor and/or OE part numbers.

For more details on configuring screen mappings so that a \'Product
Details\' screen will display when a product is selected within the Tree
navigator, see the **Mappings** topic within the **Main Properties
Overview**  section of Web User Interfaces / Web UI Setup and User Guide
in **STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: MEDU RDCUST-2693 See this ticket for the design OE Number
screen in Web UI. Users need to be able to view the OE and OEM numbers
of a part on a dedicated screen. Parts can have more than one OE number.
The numbers will display the following three columns within the table:
Make, OE Number, and VIO. The design can be found at:
https://app.zeplin.io/project/584e71ddd996399118a1dfb7/screen/5a83ef8a948d985d0c262698

PRODOC note: MEDU RDCUST-2695 Users can find, create, edit, and remove
OE number references. Per MORC: If the user adds a new OE / competitor
number (using the ID of the new number) a popup displays the make field
populated with the newly added ID and the Number field is empty.

PRODOC note: MEDU RDCUST-2831 Suggested OE numbers display within a
table. Each suggested number displays within its own row. Only the OE
number (not the name) is displayed. When the mouse cursor is placed over
the information icon, a hover text will display OE number suggestions.
Clicking the plus sign next to a suggested OE number will move the
selected OE number from the suggestion list to the table. The OE number
will no longer display within the suggested OE number list since the
reference has been created, and now displays within the reference table.
