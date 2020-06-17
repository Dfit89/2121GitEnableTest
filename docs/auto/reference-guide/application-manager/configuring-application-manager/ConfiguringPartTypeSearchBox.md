---
description: 'Automotive Solution: Describes how to configure a Year
  Search Box type.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring Part Type Search Box
================================

Because the Part Type search box type does not require additional
configuration, it can quickly be added to the Search Box Types parameter
within the Vehicle Type Search Panel Properties dialog by following the
steps listed below:

1.  From the Vehicle Type Search Panel Properties dialog, click the
    **Add** button below the Search Box Types parameter field, and the
    Add Component dialog will display.

![](../../../Resources/Images/AppMgr/Configuring/Add%20Component.png)

1.  Click **Part Type Search Box** from the list of components.

```{=html}
<!-- -->
```
1.  Click the **Add** button, and the Vehicle Type Search Panel
    Properties will display with the Part Type Search Box added to the
    Search Box Types parameter.

Editing the Part Type Search Box Label
--------------------------------------

The Part Type search box label displayed within the Application Manager
can be edited by following the steps listed below:

1.  Go to the Vehicle Type Search Panel Properties for the Application
    Manager.
2.  Within the Search Box Types parameter, select the **Part Type Search
    Box**.
3.  Click the **Edit** button, and the Part Type Search Box Properties
    dialog will display as shown below.
4.  Edit the following parameters as necessary.

-   **Label:** By default, the Label parameter is populated as \'Part
    Type.\' Optionally edit the parameter to a more suitable label.
-   **Root Nodes:** Allows for the restriction of root nodes to be used
    within the Part Type search box when searching / filtering for a
    Part Type. Once the root node(s) is defined, the search input field
    displays only suggestions of objects that belong in the root node
    defined within this parameter. Additionally, when the Node Picker is
    used, its dialog will display the only those classification folders
    that pertain to the root nodes defined within this parameter. Click
    the Add button below the parameter field to browse or search for the
    necessary vehicle root node object(s).
-   **Use Root Nodes In typeahead:** Selecting this parameter allows the
    display of suggestions in the typeahead field of only those objects
    that belong in the root node defined within the Root Nodes
    parameter. However, the user needs to be aware that the selection of
    this parameter would affect the performance of the display of
    suggestions in the typeahead field.

![](../../../Resources/Images/AppMgr/Configuring/Part%20Type%20Label%20Edit.png)
