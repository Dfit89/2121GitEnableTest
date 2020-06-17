---
description: 'Automotive Solution: Forward Screen Action component is
  used for routing an object into the defined screen. If it is placed in
  the Buttons component, it will route the currently selected product.
  If it is placed in the Actions parameter on a Node List, it will route
  the object that is selected in the list.'
title: '\[%=Heading.Level1%\]'
---

Forward Screen Action Component
===============================

Forward Screen Action component is used for routing an object into the
defined screen. If it is placed in the Buttons component, it will route
the currently selected product. If it is placed in the Actions parameter
on a Node List, it will route the object that is selected in the list.
This component is commonly used within Web UI search screens and the
Node Detail screen.

One common use case of the Forward Screen Action component within the
Automotive solution is to route the selected object to the Onboarding
Comparison Screen. There are no explicit limits on how the component can
be used, but it was created specifically to route the selected object
towards the Onboarding Comparison Screen so that the user can compare
the selected Source object with the Target object in the context of the
configured Mapper Configuration setup entity.

The **Forward Screen Action** button can be added to any Node List as a
toolbar action (a button accessible above the table) and to any Node
Details screen as a standard action button (a button accessible below
the table). PRODOC note: Web UI screens that requires an object
selection

To add the **Forward Screen Action** button to a Node Details screen as
a standard action button, navigate to the relevant \'Node Details
Properties\' screen in the designer. Under \'Child Components\', click
the \'go to component\' link next to the \'Buttons\' parameter. Click
\'Add\' and then find, select, and add the \'Forward Screen Action\'
component.

![](../../../Resources/Images/Data%20Onboarding/184.png)

Displayed in the screenshot below is the Forward Screen action as it
displays when configured within the Node Details screen.

![](../../../Resources/Images/Data%20Onboarding/185.png)

To add the **Forward Screen Action** button to a Node List screen as a
toolbar action button, navigate to the relevant Node List component in
the designer. In the \'Child Components\' section, click the \'Add\'
button below the \'Actions\' field. In the \'Add Component\' screen that
displays, find, select, and add the \'Forward Screen Action\' component.

![](../../../Resources/Images/Data%20Onboarding/183.png)

Displayed in the screenshot below is the Forward Screen action as it
displays when configured within the Node List of the Search by Card
Screen.

![](../../../Resources/Images/Data%20Onboarding/182.png)

Whether configuring the Forward Screen Action component as an action
button or a toolbar action button, the options displayed in the designer
are the same.

Displayed in the screenshot below is the Forward Screen Action
properties screen as it displays when being configured for a Node List
screen. The properties screen for this component when being configured
for a Node Details screen will have slight differences, which will be
outlined in the parameter descriptions located below the screenshot.

![](../../../Resources/Images/Data%20Onboarding/180.png)

-   **Label**: When configuring a standard action button, the text
    entered in this field will display on the button. When configuring a
    toolbar action button, the text entered in this field will display
    beside the button. If nothing is added, the Label default will
    display as \'Forward Screen.\'

This is how the button will display at the Node List toolbar:

![](../../../Resources/Images/Data%20Onboarding/Onboard%20Button%20Label.png)

-   **Forwarding Screen:** Select a specific screen using the dropdown
    so that users are forwarded to that screen when they click on the
    action button. It is important that only the right type of screen is
    configured within this parameter. Configuring the wrong type of
    screen will not allow the action button to perform as intended and
    an error will be displayed. PRODOC note: There are different errors
    displayed for different screens, hence I cannot show the error
    message here.
-   **Context Help** : Enter the text that will display in a small
    informational popup message when the cursor is placed over the
    button.

For example, if the field is populated with the value 'Click to navigate
to Onboarding Comparison Screen,' this is how the help text will display
when the cursor is placed over the action button in the Node List
toolbar:

![](../../../Resources/Images/Data%20Onboarding/181.png)

Using Forward Screen Action button in Search Screens
----------------------------------------------------

The **Forward Screen Action** button
(![](../../../Resources/Images/Data%20Onboarding/Onboard%20Button%20Label.png))
is enabled when an object is selected in the search results table. If no
object or multiple objects are selected, the Forward Screen Action
button remains disabled.

1.  Perform a search for object.
2.  Select the object that needs to be routed to the specific screen.

```{=html}
<!-- -->
```
3.  Click the **Forward Screen Action** button
    (![](../../../Resources/Images/Data%20Onboarding/Onboard%20Button%20Label.png))
    that is available in the toolbar of the screen.
