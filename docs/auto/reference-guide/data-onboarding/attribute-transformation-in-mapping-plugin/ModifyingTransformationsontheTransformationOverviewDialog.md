---
description: 'Automotive Solution: On the Transformation Overview
  dialog, the user has the flexibility to edit, delete, or rearrange the
  listing order of the transformations. Users can also add
  transformations to an existing attribute transformation.'
title: '\[%=Heading.AnyLevel%\]'
---

Modifying Transformations on the Transformation Overview Dialog
===============================================================

On the Transformation Overview dialog, the user has the flexibility to
add, edit, delete, or rearrange the listing order of the
transformations. When there are multiple transformations listed, the
order of execution of each transformation is based on the order in which
it is listed within the Transformation Overview dialog.

Following are the two ways that the Transformation Overview dialog can
be accessed in the Web UI:

-   Through the Mapping Guide window by clicking the edit button
    (![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png))
    for the attribute transformation.

![](../../../Resources/Images/Data%20Onboarding/236.png)

-   Through the Transformation Hierarchy Editor window by clicking the
    \'Select and modify transformation\' icon
    (![](../../../Resources/Images/Release%20Notes/9.3mp2/Select%20and%20modify.png)),
    and then clicking the edit button
    (![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png))
    for the attribute transformation.

![](../../../Resources/Images/Data%20Onboarding/237.png)

In the following image, the various functionalities that are available
in the Transformation Overview dialog are numbered.

In the image below, the attribute transformation is configured to
include multiple transformations. Each of the transformation is
displayed as rows.

![](../../../Resources/Images/Data%20Onboarding/234.png)

The available modifications defined below include:

1.  Add a new transformation to the attribute transformation
2.  Test the result of the attribute transformation
3.  Delete an existing transformation
4.  Change the listing order of the transformation
5.  Edit an existing transformation

Add a transformation
--------------------

Adding a set of transformations to the attribute transformation will
make a rule, and when applied in the Mapping plugin, it will affect the
Target object name / ID / attribute value as defined within each of the
transformations.

![](../../../Resources/Images/Data%20Onboarding/231.png)

1.  Click on the **New Transformation** button to display the list of
    transformations available.
2.  Select the relevant Transformation. If the selected Transformation
    requires any further configuration, then the **Edit Transformation**
    dialog will display.
3.  Define the transformation and click **Save** to save and close the
    Edit Transformation dialog.

The selected transformation is listed in the Transformation Overview
dialog. For a description of the available transformations, see the
**Transformations** topic in the **Resource Materials** online help[
here]{.mcFormatColor style="color: Blue;"}.

Test an attribute transformation
--------------------------------

Details on how to test an attribute transformation configured in a
Mapping plugin is explained in the **Testing Attribute Transformations
Configured in Mapping Plugins** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Delete a transformation
-----------------------

Deleting a transformation will no longer display nor execute the
transformation in the selected attribute transformation. It must only be
deleted when it is no longer required. Deletion made through the Mapping
Guide window impacts every other place where this transformation is
applied / used.

1.  In the Transformation Overview dialog, select the checkbox that is
    available on the left of the transformation that is intended to be
    deleted. This makes the **Delete** button
    (![](../../../Resources/Images/Data%20Onboarding/Delete%20button.png))
    visible in the toolbar.

![](../../../Resources/Images/Data%20Onboarding/235.png)

2.  Click the **Delete** button. This removes the selected
    transformation(s) from the Transformation Overview dialog in Web UI
    and also removes the functionalities defined in that particular
    transformation.
3.  Click the **Save** button to confirm that the transformation row
    should be deleted.

Change the order of the transformations
---------------------------------------

When there are multiple transformations available within the attribute
transformation, the transformations are applied in the order in which
they are listed within the Transformation Overview dialog. Users can
rearrange the order of the transformation as defined below.

1.  For the selected attribute transformation, access the Transformation
    Overview dialog.
2.  Click the three-dotted icon
    (![](../../../Resources/Images/Data%20Onboarding/three%20dotted%20icon.png))
    that is available in the right of the transformation to display the
    rearranging dialog. The user can select the Top, Up, Down, or Bottom
    button to rearrange the transformation accordingly.

![](../../../Resources/Images/Data%20Onboarding/232.png)

Edit an existing transformation
-------------------------------

Users can edit an existing transformations through the Transformation
Overview dialog. Below is the procedure to edit an existing
transformation.

1.  For the selected attribute transformation, access the Transformation
    Overview dialog, and click the three-dotted icon
    (![](../../../Resources/Images/Data%20Onboarding/three%20dotted%20icon.png))
    that is available in the right of the transformation to display the
    rearranging dialog.
2.  Click the **Edit Transformation** button to open the Edit
    Transformation dialog.
3.  Edit the transformation as needed and click **Save** to save and
    close the Edit Transformation dialog.

![](../../../Resources/Images/Data%20Onboarding/233.png)
