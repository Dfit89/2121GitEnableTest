---
description: 'Automotive Solution: Describes how to implement the
  Application Suggestion solution.'
title: '\[%=Heading.AnyLevel%\]'
---

Application Suggestion Solution
===============================

PRODOC note: RDCUST-2702 is the Epic. **Why:** To make the Application
Suggestions solution more applicable for the end users, we want to be
able to suggest which application a part might bear as a child object.
**What:** Based on existing applications, we are able to extract
potential applications. When doing this we should sort the suggestions
by the most relevant first and cut the list if there are to many
suggestions or the confidence level is too low.

With the automotive solution, it is easy to maintain application data.
The automotive solution not only helps users more easily view, edit, and
create applications for specific parts, but also suggest potential
matches. In other words, when configured, STEP can suggest potential
matches for applications based on existing applications within STEP.
This occurs when a part is selected, STEP looks at the existing
applications and displays their attribute values via configurations
within the \'Part Application Editor\' Node Editor component.

When the new Part Application Editor and/or Application Suggestions
components are configured as shown below, Web UI users can:

1.  View existing applications and related data.
2.  View Target (competitor and/or OE part number) part\'s application
    suggestions and related data.
3.  View information about the suggested application.
4.  Add applications manually.
5.  Add applications from suggestions.
6.  Remove existing applications.
7.  Remove applications from suggestions.

The components used for this solution are extremely flexible and can be
configured to display the existing applications on the same screen.
Also, additional column headers can be added to the components to
display more information than is shown in this example.

![](../../Resources/Images/Release%20Notes/91MP22.png)

In the example above, part VC36115 is selected within a Web UI Tree, and
a Web UI screen (Product Details) is configured to display the existing
and the potential application on a tab page (Application Suggestions).

This section addresses:

-   Prerequisites

-   Adding New Applications Manually ([here]{.mcFormatColor
    style="color: Blue;"})

-   Adding Applications from Suggestions ([here]{.mcFormatColor
    style="color: Blue;"})

-   Removing Existing Applications ([here]{.mcFormatColor
    style="color: Blue;"})

-   Removing Application from Suggestions List ([here]{.mcFormatColor
    style="color: Blue;"})

-   Configuring the Part Application Editor Component
    ([here]{.mcFormatColor style="color: Blue;"})

-   Configuring the Application Suggestions Component
    ([here]{.mcFormatColor style="color: Blue;"})

-   Configuring the Data Model for Application Competitor or OE Part
    Numbers Table Header

-   Configuring the Application Competitor or OE Part Numbers Table
    Header Component

-   Configuring the Metadata Attribute References Component

Prerequisites {#prerequisites .RNNoTOC conditions="Primary.Print"}
-------------

Prerequisites {#prerequisites-1 conditions="Primary.Web"}
-------------

When implementing this solution, it is suggested to create a \'Product
Details\' screen within a Web UI and configure it to display when a
product is selected within the Tree navigator. The Product Details
screen should be created via a Node Details screen with a Tab Control
that is configured to display a \'Application Suggestion\' Tab Page.
Within each of these Tab Pages a Node Editor can be configured with
\'Part Application Editor\' and/or \'Application Suggestions\'
components. The \'Part Application Editor\' component can be configured
to display existing applications. Whereas, the \'Application
Suggestions\' component can be configured to display suggested
applications.

For more details on configuring screen mappings so that a \'Product
Details\' screen will display when a product is selected within the Tree
navigator, see the **Mappings** topic within the **Main Properties
Overview**  section of Web User Interfaces / Web UI Setup and User Guide
in **STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.
