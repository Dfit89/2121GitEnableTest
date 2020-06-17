---
description: 'Automotive Solution: Describes how Automotive Validation
  Path affect Search Box Criteria. '
title: '\[%=Heading.AnyLevel%\]'
---

Validation Path Functionality and Search Box Criteria
=====================================================

The validation path concept drives the intelligence that allows
Application Manager search boxes to display only valid options filtered
by previous selections and/or specific vehicle configurations.

For example, the 2013 Audi A3 was manufactured with six engine options,
and some of those engines require diesel fuel instead of gas. When the
Make/Model search box is populated with the Audi A3 criterion, and the
Year search box is populated with the 2013 criterion, then the Fuel Type
options search box will display the two available fuel types; Diesel and
Gas (as shown below).

Options search boxes can be configured with many different attributes
and/or references. For the following examples, the Options search boxes
are displayed using the Fuel Type and Engines attributes.

![](../../../Resources/Images/AppMgr/Validation%20Paths/A3%202013%20Fuel%20Type%20Dropdown.png)

When the Fuel Type options search box is left blank, then the Engine
options search box will display the six engines available for the 2013
Audi A3 (as shown below).

![](../../../Resources/Images/AppMgr/Validation%20Paths/A3%202013%20Engine%20Dropdown.png)

Whereas, when the Diesel criterion is selected for the Fuel Type options
search box, then the Engine options search box will display the engine
that uses diesel fuel and is available for the 2013 Audi A3 (as shown
below).

![](../../../Resources/Images/AppMgr/Validation%20Paths/EngineDropdownFuel.png)

Notice in the examples provided above, the AND/OR toggle button is set
to AND. When the toggle button is set to OR, then the Options search
boxes (displaying the \'Fuel Type\' and \'Engine\' options in the
screenshot below) do not limit the display of valid criteria based upon
each other. However, the Options search boxes always consider the
Make/Model and Year search box criteria before displaying the valid
criteria options within the dropdown. In the example below, the same
criteria is selected from the previous example, however the OR toggle
button is active, and all the valid engines for the 2013 Audi A3
display.

![](../../../Resources/Images/AppMgr/Validation%20Paths/AfterFuelOR.png)

For more information on the Options search boxes, see the **Using the
Options Search Boxes** topic ([here]{.mcFormatColor
style="color: Blue;"}) within the Intelligent Search Interface section
of this guide.
