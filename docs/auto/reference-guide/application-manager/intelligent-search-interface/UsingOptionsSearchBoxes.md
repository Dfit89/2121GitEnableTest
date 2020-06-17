---
description: 'Automotive Solution: Describes how to use the Options
  search boxes within the Options Group search box type.'
title: '\[%=Heading.AnyLevel%\]'
---

Using Options Search Boxes
==========================

Attributes or references within STEP can be displayed as options within
an Application Manager. The attribute and/or reference values can then
be selected as search criteria.

The Options search boxes allow users to choose pre-configured attribute
and/or reference type options, and the valid criteria, to their search.
This section addresses functionality that is specific to the Options
search boxes. For more information on the general functionality found
within the search boxes, see the **Using Search Boxes** topic
([here]{.mcFormatColor style="color: Blue;"}) within this guide.

The Options search boxes can be configured to allow users to select up
to two attribute and/or reference type options. The attribute and/or
reference type option dropdown is located in the top left corner of the
Options search box. Clicking the down arrow to the right of the Options
search box label, or clicking the label itself will display the
available options within the dropdown. Using the Options search box
dropdown, users can choose criteria related to different search options
(i.e., Sub Model, Region, Engine, Fuel Type). In the example below, two
Options search boxes have been configured. The Options search box on the
left displays the option \'Sub Model\' by default, and the one on the
right displays the option \'Region\' by default. Clicking the option
label displays a dropdown of available options for each Options search
box (as shown below).

![](../../../Resources/Images/AppMgr/DropDown.png)

A Search Panel can have up to two Options search boxes. When two Options
search box types are configured, an AND / OR toggle button displays
between the two boxes. This toggle button allows users to determine if
the search criteria within the two Options search box types should be
inclusive or exclusive of each other. The AND / OR toggle button only
applies to the criteria within the two Options search box types. It does
not affect the inclusion of the criteria within the other search box
types (i.e., Make/Model, Year, Part Type).

When the toggle button displays \'AND,\' then the search results only
display a match for the criteria provided within Options search box 1
**and** Options search box 2. However, when the toggle button displays
\'OR,\' then the search results will display a match for the criteria
provided within Options search box 1 **or** Options search box 2.

PRODOC note: MEDU RDUCST-2725 The Options search box typeahead field
results are dependent upon selections made in the Make/Model and Year
search boxes. In the example below, the Toyota 4Runner is added to the
Make/Model search box, and the 2015 year is added to the Year search
box, allowing the Sub Model search box dropdown to only display options
related to the 2015 4Runner. When the Sub Model option criteria is
selected, then the dropdown displays only those sub models available for
the 2015 4Runner.

![](../../../Resources/Images/AppMgr/Options%20Dropdown%20Make%20Year%204Runner.png)

Adding additional makes or models to the Make/Model search box will
expand the Options search box dropdown results. In the example below,
the Toyota and Jeep makes have been added, and result in all Toyota,
Jeep, and 4Runner sub models displaying within the Sub Model Options
search box dropdown. (Though the long list of available sub models
cannot be seen in the screenshot, the display of a mixture of available
sub models is apparent with the inclusion of the Jeep Rubicon, Toyota
Hybrid SE, and Toyota 4Runner TRD Pro.)

![](../../../Resources/Images/AppMgr/Options%20Dropdown%20Mixed%20Makes%202015.png)

By changing the Option selection from Sub Model to Engine, the results
dropdown only displays the one engine available for the 2015 4Runner.

![](../../../Resources/Images/AppMgr/Region%20Sub%20Model%20Options.png)

Additionally, when two Options search boxes are enabled, allowing for
the \'AND / OR\' toggle button to be set to \'AND,\' the dropdown for
the options cards will also be dependent upon selections made between
the two Options search boxes. In the example below, the Region criterion
has been set to Canada, so the Sub Model search box displays only those
sub model options available for the 2015 4Runner in Canada. Notice from
the previous example, the TRD Pro was available for selection, until the
Canada region criterion was added, because the 2015 TRD Pro sub model is
not available in Canada.

![](../../../Resources/Images/AppMgr/Search%20Functions/20154runner.png)

The Options search boxes will not automatically display the suggested
dropdown options until at least one value is added to the Make/Model
search box.

Optionally, the Report button can be used to export these results to an
Excel file. For more information, see the **Using Application Coverage
Report** section ([here]{.mcFormatColor style="color: Blue;"}) of this
guide.
