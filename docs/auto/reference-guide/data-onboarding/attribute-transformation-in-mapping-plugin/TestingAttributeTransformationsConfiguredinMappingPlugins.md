---
description: 'Automotive Solution: Describes how to test the attribute
  transformations configured in Attribute Mapping plugin within Web UI.'
title: '\[%=Heading.AnyLevel%\]'
---

Testing Attribute Transformations Configured in Mapping Plugins
===============================================================

Users can test the attribute transformation configured in the Mapping
plugin in the Web UI by entering a sample test value as explained below.
This helps to test the transformation by evaluating if the attribute
value is transformed correctly without actually changing the data or
moving the data from one attribute to the other.

When an existing attribute transformation is added for any Mapping
plugin, an edit icon
(![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png)) is
displayed within the Transformation field in the Mapping Guide window.
Clicking the edit icon
(![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png)) opens
the Transformation Overview dialog and lets users test the functionality
of the transformation via the Test button (as shown below).

![](../../../Resources/Images/Data%20Onboarding/47.png)

Click the Test button in the Transformation Overview dialog to open the
Test Transformation dialog with the parameters explained as follows:

![](../../../Resources/Images/Data%20Onboarding/49.png)

-   **Test Value:** This editable blank field lets users enter text to
    be used as the sample value for testing.
-   **Timing:** This read-only field displays the time elapsed in
    transforming the \'Test value\' field once the **Test** action
    button is clicked in the Test Transformation dialog.
-   **Status:** This read-only field displays the success or failure
    status of the transformation when the **Test** action button is
    clicked in the Test Transformation dialog.
-   **Result:** This read-only field displays the final transformed
    value of the \'Test value\' field.

In the example below, a value \'Blue\' is entered in the \'Test value\'
field and the **Test** action button is clicked to display the result
\'NaN.\'

![](../../../Resources/Images/Data%20Onboarding/50.png)
