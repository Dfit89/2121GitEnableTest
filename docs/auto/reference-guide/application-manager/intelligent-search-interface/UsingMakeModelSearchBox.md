---
description: 'Automotive Solution: describes how to use the Make/Model
  Search Box within the intelligent search interface of the Application
  Manager.'
title: '\[%=Heading.AnyLevel%\]'
---

Using Make/Model Search Box
===========================

The Make/Model search box allows users to add one or more make and/or
model criteria to their search. This section addresses functionality
that is specific to the Make/Model search box. For more information on
the general functionality found within the search boxes, see the **Using
Search Boxes** topic ([here]{.mcFormatColor style="color: Blue;"})
within this guide.

PRODOC note: MEDU RDCUST-2786 Within the Make/Model Search Box, the
typeahead field can be used to search for make and/or model criteria.
The dropdown list will display the criteria options alphabetically by
Make, and then by Model. Models are always displayed below their
respective Make. For example, if \'a4\' is typed into the field, then
the dropdown list displays the Audi, Austin, Checker, and Mercedes-Benz
makes alphabetically, and the Models that match the information typed
into the field (a4) will be listed alphabetically below their respective
makes (as shown below).

![](../../../Resources/Images/AppMgr/Make%20Model%20A4%20Dropdown.png)

If the text typed in matches a make only, then all Models below that
make will be displayed. For example, if \'maz\' is typed into the field,
then the dropdown list will display the Mazda make with all its
available Models listed below.

![](../../../Resources/Images/AppMgr/Make%20Model%20maz%20dropdown.png)

If the text typed in matches a model only, then the make for the
matching model is displayed with only the model that matches the search
string. For example, if \'fox\' is typed into the field, then the
dropdown list will display the Audi and Volkswagen makes with the
\'Fox\' Models listed below.

![](../../../Resources/Images/AppMgr/Make%20Model%20fox%20dropdown.png)

If the text typed in matches the make AND Model, then the matching makes
and/or Models will display within the dropdown for selection. For
example, if \'opel\' is typed into the field, then the dropdown list
will display the Buick make with the Opel model beneath, and then the
Opel make will display with all of its available Models below.

![](../../../Resources/Images/AppMgr/Make%20Model%20Opel%20Dropdown.png)

To search for a make within a specific Model, two or more characters can
be typed into the field to narrow down the Make, then using the keyboard
space bar allows for the following text to conduct a \'contains\' search
for Models. For example, to display all the Audi models containing
Quattro, then the following can be entered into the Make/Model field:
\'aud \[space bar\] qua.\'

![](../../../Resources/Images/AppMgr/Quattro.png)

PRODOC note: MEDU RDUCST-2624 Additionally, users can browse for the
Make/Model criteria by clicking the browse icon located to the right of
the Make/Model typeahead field. In the screenshot below, the Make/Model
Browse dialog displays after the node picker browse icon is selected.

![](../../../Resources/Images/AppMgr/Make%20Model%20Browse.png)

Recommended practice is to provide at least one value for the Make/Model
search box, otherwise longer than expected wait times can occur. When
the use of broad search criteria is required, recommended practice is to
use the Application Coverage Report by clicking the Report button within
the Application Manager. For more information about running a search
without the Make/Model search box populated, see the **Minimum Search
Criteria** section of the **Using Search Boxes** topic[
here]{.mcFormatColor style="color: Blue;"}.
