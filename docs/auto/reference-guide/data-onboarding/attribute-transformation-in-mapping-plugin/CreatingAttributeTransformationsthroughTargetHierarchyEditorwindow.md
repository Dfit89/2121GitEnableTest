---
description: 'Automotive Solution: Describes how to create the attribute
  transformations that is to be configured in Target Hierarchy Editor
  window within Web UI.'
title: '\[%=Heading.AnyLevel%\]'
---

Creating Attribute Transformations Through Target Hierarchy Editor window
=========================================================================

Users can create an attribute transformation and define one or more
transformations to it through a Mapping Guide window and the Target
Hierarchy Editor window. The created attribute transformation will
reside in System Setup under the Attribute Transformations node and will
be available to be used in all other places where the attribute
transformations can be applied on.

This topic explains how to create an attribute transformation through a
Mapping Guide window in the Web UI. For information on how to create and
configure an attribute transformation through the Target Hierarchy
Editor window, see the **Creating Attribute Transformations Through
Mapping Guide Window** topic within this guide ([here]{.mcFormatColor
style="color: Blue;"}). For information on how to create and configure
an attribute transformation in workbench, see the **Attribute
Transformations** section of the **System Setup / Super User Guide**
documentation of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

When clicking the Edit icon
(![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png)) that
is displayed to the right of the **Target Hierarchy** parameter
(available on the Setup tab of the Onboarding Mappings Details Screen),
the Target Hierarchy Editor window displays. Clicking on the \'Select
and modify transformation\' icon
(![](../../../Resources/Images/Release%20Notes/9.3mp2/Select%20and%20modify.png))
will open the Transformations dialog. For any Transformation dialog, if
no attribute transformation is applied, then a create button
(![](../../../Resources/Images/Data%20Onboarding/Create%20transformation%20icon.png))
is displayed within the Transformation field. Clicking the create
button(![](../../../Resources/Images/Data%20Onboarding/Create%20transformation%20icon.png))
will open the Transformation Overview dialog with the parameters
explained as follows:

![](../../../Resources/Images/Data%20Onboarding/238.png)

-   **ID:** Type an ID for the attribute transformation.
-   **Name:** Type a suitable name that describes the attribute
    transformation functionality.
-   **The Parent of the new object:** The user can select the parent
    node under which the newly created attribute transformation will
    reside.

In the example below, an attribute transformation named \'Change Case\'
(ID=ChangeCase) is created to reside in the Attribute Transformations
folder.

![](../../../Resources/Images/Data%20Onboarding/224.png)

Once all parameters are populated, clicking on the **Save** button will
save and close the Transformation Overview dialog, and the newly created
attribute transformation will be populated within the Transformation
field of the Transformation window. Should changes need to be made, an
edit (![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png))
and a delete
(![](../../../Resources/Images/Data%20Onboarding/Delete%20icon.png))
button will be displayed next to the attribute transformation placed in
the Transformation field.

![](../../../Resources/Images/Data%20Onboarding/239.png)

The newly created attribute transformation will not have any
transformations defined in them. To define one or more transformations,
click the edit button
(![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png)) to
open the Transformation Overview dialog and add a transformation by
clicking the New Transformation button (as shown below).

![](../../../Resources/Images/Data%20Onboarding/240.png)

Clicking on **New Transformation** displays the list of rules to be
used. Select the relevant transformation.

![](../../../Resources/Images/Data%20Onboarding/227.png)

If the selected transformation requires any further configuration, then
the **Edit Transformation** dialog will display. Enter the necessary
values and click **Save** to save and close the Edit Transformation
dialog. The selected transformation will get listed in the
Transformation Overview dialog (as shown below). For a description of
the available transformations, see the **Transformations** topic in the
**Resource Materials** online help[ here]{.mcFormatColor
style="color: Blue;"}.

It is possible to create multiple sequential transformations as a rule,
but the user must to be careful about the order in which the
transformations are applied.

In the example below, \'Change case\' and \'Append\' transformations are
used.

![](../../../Resources/Images/Data%20Onboarding/228.png)

Click **Save** to save and close the Transformation Overview dialog. The
Validation Type column within the Mapping Guide window will display the
total number of transformations available in the selected attribute
transformation.

![](../../../Resources/Images/Data%20Onboarding/2020-04-22_00-42-28.png)
