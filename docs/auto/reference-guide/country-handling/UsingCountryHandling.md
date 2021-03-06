---
description: 'Automotive Solution: Describes how to use the Country
  Handling solution that is intended to help users view, edit, and
  create accurate country handling inclusion and exclusion references
  for specific parts and applications.'
title: '\[%=Heading.AnyLevel%\]'
---

Using Country Handling
======================

PRODOC note: MEDU per MABU Spec doc within 2594. 09/11/2018 Sprint Demo
SUJAY, RDCUST- 2916, 2387

The Country Handling solution helps users view, edit, and create
accurate country handling inclusion and exclusion references for
specific parts and applications. This Web UI solution also prevents
users from creating conflicting inclusion and/or exclusion
relationships.

The Country Handling solution can be used within an Application Manager
Results Table via an \'Application Country Handling Table Header\'
component and/or within a Node Editor screen via a \'Country Handling
Value\' component.

Prerequisites

Configuration is required before the Country Handling solution can be
used. For more information, see the **Prerequisites** section of the
**Country Handling Solution** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Using Country Handling within Application Manager
-------------------------------------------------

When using the Country Handling solution within an Application Manager,
the \'Application Country Handling Table Header\' component can be
configured to display the country inclusion data within the \'Country\'
column of the Results Table where users can view country handling data
on applications. This component only displays inclusion and exclusion
data for the selected application. Therefore, it does not display
inclusion nor exclusion data from the application\'s parent (i.e.,
Part). Double clicking a cell within the \'Application Country Handling
Table Header\' column will display a Value editor where users can add
and/or remove country inclusion data.

In the example below, the Application Country Handling Table Header
component is displayed with the default column label \'Countries.\' In
the first row of the Results Table, an application for an ACURA Coupe -
NSX displays with \'All (0/249)\' within the Countries column. This
indicates that the between the configured exclusion and inclusion
attributes, zero values are populated. In other words, for the possible
249 countries, no exclusion nor inclusions have been added to STEP.
Therefore, the inclusion of all countries is assumed because no data
exists in the exclusion and/or inclusion attributes.

![](../../Resources/Images/Country%20Incl%20Excl/11.png)

To add or edit country inclusion / exclusion data to an application
using the \'Application Country Handling Table Header\' component,
double click the desired cell within the \'Countries\' column for the
application row, and a Value editor dialog will display. For more
information, on using the Value editor, see the **Using Country Handling
Value Editor** topic[ here]{.mcFormatColor style="color: Blue;"}.

Once the Value editor is used to edit the country handling data, the
Application Manager Results Table will update to display the country
data referenced for inclusion.

In the screenshot below, the cell that once displayed \'All (0/249)\'
now displays \'All (56/249),\' and then lists the country group names
with their count of selected countries / number of countries within the
group. For example, five of the ten countries included within the ASEAN
country group are displayed as selected because they are also included
in the \'Left-hand traffic\' country group that was selected.

![](../../Resources/Images/Country%20Incl%20Excl/34.png)

To remove any of the selected inclusion countries, double click on the
cell to access the Value editor. Uncheck any country checkboxes, and
click the OK button.

Once a country value is added for inclusion, if it is then added to the
exclusion attribute, it is automatically removed from inclusion
attribute. The same country cannot exist in both the inclusion attribute
and the exclusion attribute.

Using Country Handling within Node Editor
-----------------------------------------

When using the Country Handling solution within a Node Editor, the
\'Country Handling Value\' component can be configured to display the
country inclusion and exclusion data within a Node Editor screen used to
view and/or edit country handling data on parts and/or applications
(i.e., Product Details screen).

When configured, this component can be used to view and edit the country
inclusion data for applications and/or parts. Once an application and/or
part object type is selected, then the Country Handling Value component
displays only those countries currently referenced to the attribute or
part for inclusion. It only displays inclusion and exclusion data for
the selected object. Therefore, it does not display inclusion nor
exclusion data from the part\'s parent and/or child objects (i.e., Part
Types, Applications).

In the example below, when part \'49065\' is selected within a Web UI
Tree, a \'Product Details\' screen displays a \'Country Inclusion /
Exclusion\' tab page where the Country Handling Value component displays
\'All Countries (6/273),\' indicating that six countries of the 273
available are referenced for inclusion. To the right of that heading,
the list of individual country names referenced for inclusion display
(Denmark, France, Germany, Great Britain, Norway, and Sweden).

![](../../Resources/Images/Country%20Incl%20Excl/35.png)

When the component first displays, the \'All Countries (number of
countries referenced for inclusion / total number of countries)\' group
heading displays using bold text and highlighted in blue. Each country
group containing a country referenced for inclusion will display in bold
below the \'All Countries\' heading. Because each country group heading
displays the number of countries referenced for inclusion out of the
total number of countries within the group, it is easy to get an
understanding of the country groups that contain referenced countries
for inclusion.

Clicking any one of the country group names will move the blue highlight
to that header and display the countries referenced for inclusion within
that group to the right of the header. In the example below, the
\'Left-hand traffic\' country group is selected and its one country
referenced for inclusion (Great Britain) displays to the right. From
this display, it is easy to see not only the specific country groups
that the six countries referenced for inclusion belong to, but also, of
the six countries referenced for inclusion, only one is included in the
\'Left-hand traffic\' group that includes 55 countries.

![](../../Resources/Images/Country%20Incl%20Excl/36.png)

When country inclusion and/or exclusion data is not provided, then the
component will display \'No countries selected\' (as shown below). The
edit button
(![](../../Resources/Images/Country%20Incl%20Excl/iconEdit.png)) can be
used to add country handling data.

![](../../Resources/Images/Country%20Incl%20Excl/61.png)

When country inclusion and/or exclusion data is not provided, then only
the \'All Countries\' group heading will display with zero countries
referenced for inclusion of the total countries possible (as shown
below).

![](../../Resources/Images/Country%20Incl%20Excl/37.png)

To search for a specific country within any of the listed country groups
with inclusion data, type text into the \'Filter countries\' text box
and the results will display country names that match the typed text to
the right of the country group headers.

In the example below, \'den\' is typed into the \'Filter countries\'
text box and where the component once displayed \'6/273\' it now
displays \'1/273.\' To the right of the country group headers, the
filter result (Denmark) displays. Each country group that contains an
inclusion filter results match displays in bold. Whereas, any country
groups that do not contain a filter result match (\'Left-hand traffic\')
display in gray text.

![](../../Resources/Images/Country%20Incl%20Excl/38.png)

When the text typed into the \'Filter countries\' text box does not
match any of the country names referenced for inclusion, then the
\'Country not found\' message will display in the results (as shown
below).

![](../../Resources/Images/Country%20Incl%20Excl/39.png)

To add or edit country inclusion / exclusion data to an application or
part using the \'Country Handling Value\' component, click the edit
button (![](../../Resources/Images/Country%20Incl%20Excl/iconEdit.png))
to the right of the Filter countries field, and a Value editor dialog
will display. For more information on using the Value editor, see the
**Using Country Handling Value Editor to Add or Edit Country Handling
Data** topic[ here]{.mcFormatColor style="color: Blue;"}.
