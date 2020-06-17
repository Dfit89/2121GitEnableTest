---
description: 'Automotive Solution: Describes how to configure a Year
  Search Box type.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring Year Search Box
===========================

With effective from Automotive 9.1 MP2 patch, the Year Search Box
component has been superseded by the Attribute Search Box component and
therefore may be removed in a future release. It is recommended that
users transition to using Attribute Search Box component, which are
described in the **Configuring Attribute Search Box** documentation[
here]{.mcFormatColor style="color: Blue;" conditions="Primary.Web"}.

Steps for adding the Year search box type to a Vehicle Type Search Panel
are below.

1.  From the Vehicle Type Search Panel Properties dialog, click the
    **Add** button below the Search Box Types parameter field, and the
    Add Component dialog will display.

![](../../../Resources/Images/AppMgr/Configuring/Add%20Component.png)

1.  Click **Year Search Box** from the list of components.

```{=html}
<!-- -->
```
1.  Click the **Add** button, and the Year Search Box Properties will
    display, as shown below.

![](../../../Resources/Images/AppMgr/Configuring/Year%20Search%20Card.png)

**Label:** Optionally, provide a label for the Year search box that best
communicates to the user what criteria are available for selection
within the Application Manager. By default, the label is set to 'Year.'

**Year Attribute:** This required field determines the Year Attribute
that allows users to add one or more year criteria to their search. All
attribute validation base types (e.g., Text, Number, List Of Values) are
allowed. to find and select the necessary Year Attribute. The selected
attribute must be valid for the object type that is defined in the
Vehicle Object Types parameter, and the Year Attribute value must be
populated on that object in order for it to display correctly.

1.  Once the required parameters are populated, click the **Save**
    button to return to the Vehicle Type Search Panel Properties, and
    optionally add another search box type, or move on to the next
    required parameter.

Below is an example of a configured Year search box type for the
AutoCare standard.

![](../../../Resources/Images/AppMgr/Year%20Search%20Box%20Properties.png)
