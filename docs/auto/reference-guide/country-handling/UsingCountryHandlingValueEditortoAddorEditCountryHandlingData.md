---
description: 'Automotive Solution: Describes how to use the Country
  Handling Value editor.'
title: '\[%=Heading.AnyLevel%\]'
---

Using Country Handling Value Editor to Add or Edit Country Handling Data
========================================================================

PRODOC note: MEDU PRODOC-1469 Peer reviewed by JOPI.

Whether the \'Application Country Handling Table Header\' or \'Country
Handling Value\' component is used, the Value editor functions the same.

To add or edit country inclusion / exclusion data to an application
using the \'Application Country Handling Table Header\' component,
double click the desired cell within the \'Countries\' column for the
application row, and a Value editor dialog will display as shown below.
For more information, see the **Configuring Application Country Handling
Table Header** topic[ here]{.mcFormatColor style="color: Blue;"}.

To add or edit country inclusion / exclusion data to an application or
part using the \'Country Handling Value\' component, click the edit
button (![](../../Resources/Images/Country%20Incl%20Excl/iconEdit.png))
to the right of the Filter countries field, and a Value editor dialog
will display as shown below. For more information, see the **Configuring
Country Handling Value Component** topic[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../Resources/Images/Country%20Incl%20Excl/31.png)

The display of the countries and their groupings vary based upon the
configuration of the Automotive - Country Model component model. For
more information, see the **Configuring Automotive - Country Model
Component Model** topic[ here]{.mcFormatColor style="color: Blue;"}.

Using the \'Filter Countries\' typeahead field, users can type in the
first letters of any word within the country name to quickly find the
country for selection. Otherwise, scroll through the list of country
groups and click on the black arrow heads to expand the groups to view
the individual countries within each one. Notice to the right of each
country group name, the parentheses show the count of selected countries
/ number of countries within the group.

PRODOC note: MEDU RDCUST- 2838
https://app.zeplin.io/project/584e71ddd996399118a1dfb7/screen/5ab36fd8dae4f91f9f835834
When selecting a country group name, the child hierarchy will also
automatically be selected. This selection is represented with a blue and
white checkmark
(![](../../Resources/Images/Country%20Incl%20Excl/iconCheck.png)). If
only one country is listed within a country group, and the country is
selected, then the country group will also be selected. Otherwise, the
country group name displays with a blue and white dash icon
(![](../../Resources/Images/Country%20Incl%20Excl/iconDash.png)) for the
group. Additionally, if the selected country belongs to more than one
country group, then it will display as checked below each of its country
groups. Clicking the blue and white dash icon deselects the country or
all countries within the group.

In the example below, \'tra\' is entered into the \'Filter Countries\'
typeahead field, and the country group \'Left-hand traffic (55/55)\' is
selected and displays with a blue and white checkmark
(![](../../Resources/Images/Country%20Incl%20Excl/iconCheck.png)).

![](../../Resources/Images/Country%20Incl%20Excl/32.png)

Clicking the OK button closes the dialog and displays the 55 countries
selected from the \'Left-hand traffic\' country group.

However, as shown in the following example, it is also possible to clear
the previously entered text and either enter new search text or view the
individual countries selected.

In the example below, the \'tra\' text was removed from the \'Filter
Countries\' field using the backspace key, and the selected countries
from the \'Left-hand traffic\' country group display selected within
their additional country groups.

The blue and white dash icon
(![](../../Resources/Images/Country%20Incl%20Excl/iconDash.png)) is used
when only some of the countries in a country group are selected.
Whereas, the blue and white checkmark icon
(![](../../Resources/Images/Country%20Incl%20Excl/iconCheck.png)) is
used when all the countries within a group are selected. Clicking the
checkmark or empty checkbox toggles between selecting all countries and
selecting none.

![](../../Resources/Images/Country%20Incl%20Excl/33.png)

The OK button is only enabled when there are changes to be saved.

Once the desired countries for inclusion are selected, click the OK
button to close the dialog and return to the previous screen.

Clearing the checkbox for any of the countries or groups on the list
will remove them from inclusion.
