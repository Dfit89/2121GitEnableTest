---
description: 'Automotive Solution: Describes how to configure the Check
  Path for Missing Application Business Condition.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Check Path for Missing Application Business Condition in Workbench
==================================================================================

Implementing this solution includes configuring a Business Condition
using the \'Check path for missing application\' plugin, and then adding
the Business Condition to the \'Missing Application Conditions\'
attribute.

Configuring the Business Condition

This section provides steps for configuring a Business Condition using
the \'Check path for missing application\' plugin within Workbench.

1.  Confirm the \'Missing Application Conditions\' attribute
    (MissingApplicationConditions) exists, otherwise create it.

2.  Confirm the Missing Application Conditions attribute
    (MissingApplicationConditions) is valid for the necessary object
    types for each standard being used. For example, when Easy Setup
    Actions are completed, the following are made valid when the
    AutoCare, NAPA, and TecDoc standards are used: Part Terminology,
    NAPA MPCC, and Standard Assembly GA.

3.  Create a new Business Condition with a name that represents the
    Condition or Part Type value to be filtered. In the example below,
    the Spark Plug Part Type value will determine if a vehicle with the
    Diesel option will display within the results table, thus the Name
    is **Missing Application Spark Plug**.

```{=html}
<!-- -->
```
1.  Within the Business Rule Editor, click the **Add new Business
    Condition** link, and a Business Condition will display within the
    Operations tab.
2.  Click the **Edit icon**, and an Edit Operation dialog will display.
3.  Click the dropdown within the Edit Operation dialog to select the
    **Automotive** option, and then the **Check path for missing
    application** plugin (as shown below).

![](../../Resources/Images/BRs/CheckPathformissing.jpg)

 

1.  Once the plugin is selected, the Edit Operation dialog will display
    the following parameters:

-   **Path:** Defines the reference that should be followed on the
    application to retrieve the attribute value defined in the path. The
    Path information for an attribute lives on a referenced object that
    is referenced from another referenced object from the child of the
    actual vehicle. For this example, the Path information for Fuel Type
    (GAS/DIESEL) is stored on the Automotive Validation Path attribute
    (as shown below).

For more information on the Automotive Validation Path, see the
Automotive Validation Path Functionality section within the **Automotive
Reference Guide** found within the **Solution Enablement** section of
**STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/BRs/3.jpg)

![](../../Resources/Images/BRs/3.jpg)

The Path information (attribute value) must be copied from the Fuel Type
specification Automotive Validation Path attribute, and pasted into the
Path parameter (as shown below).

![](../../Resources/Images/BRs/4.jpg)

-   **Valid Values:** One or more IDs of an LOV value must be entered.
    IDs entered will be displayed within the Application Manager Results
    Table when applicable. In the example below, the value ID for the
    Fuel Type - List of Values GAS is 5.

![](../../Resources/Images/BRs/5.jpg)

1.  Within the Edit Operation dialog, click the **green plus sign** icon
    (![](../../Resources/Images/GreenAddIcon.png)) to add a value ID to
    the **Valid values** parameter.
2.  In the example below the number 5 is entered so that the GAS Fuel
    Type will display when the Spark Plug part type is searched.

![](../../Resources/Images/BRs/BC%20Check%20Path%20WB%20Config.png)

1.  Optionally, click the **green plus sign** icon
    (![](../../Resources/Images/GreenAddIcon.png)) to add more value
    IDs, if more Fuel Types should display when the Spark Plug part type
    is searched.
2.  Click the **Save** and **Close** buttons to save the Business
    Condition.

Copy the ID of the Business Condition for the next steps.

Adding the Business Condition to the Missing Application Conditions
Attribute

Once the Business Condition has been configured, it must be added to the
Missing Application Conditions attribute. Below are the steps necessary
to add the Business Condition to the Part Type attribute.

1.  Go to the Part Type that needs its results improved. For the example
    below, the \'Spark Plug\' Part Type is used.
2.  Go to the \'Missing Application Conditions attribute, double click
    to add a value, and the Value Editor will display.
3.  Click the **Add Value** link, and a blank row will display.
4.  Paste the ID of the Business Condition into the value row.
5.  Click the **OK** button to save, and the Business Condition ID will
    display as the attribute value.

![](../../Resources/Images/BRs/9.jpg)
