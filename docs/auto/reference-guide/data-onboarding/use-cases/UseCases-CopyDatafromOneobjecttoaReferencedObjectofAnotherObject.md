---
description: 'Automotive Solution: Describes the use case of copying
  data from one object to a referenced object of another object.'
title: '\[%=Heading.Level1%\]'
---

Use Cases - Copy Data from One Object to a Referenced Object of Another Object
==============================================================================

Because the Object to Object mapping plugin within the Onboarding
Mappings Details screen has many uses for how the mappings can be
configured, describing the components within the mapper does not fully
cover all of the functional use cases. With that in mind, two full use
cases are described below that outline instances where this Object to
Object Mapping plugin has been successfully implemented to copy data
from one object to a referenced object of another object.

Example One
-----------

The requirement for this use case entails that the user has maintained
part numbers (PIES Items) and Interchange objects (PIES Interchange
objects) in the AutoCare Product hierarchy, but also wants to create the
PIES Interchange objects as Interchange objects in the NAPA product
hierarchy and establish the reference from the NAPA part number ( NAPA
Product) to the newly created interchange objects.

In this example, the AutoCare PIES Item \'JK21499\' is used as the
Source object and NAPA Product \'RPC12345\' as the Target object. All
referenced Interchange objects of Source object \'JK21499\' will be used
to create new objects in the selected Target Parent Node \'Great Lakes\'
(existing (or can be created) within NAPA Interchange Product Hierarchy)
and establish references from the Target object \'RPC12345\' to the new
objects. The Source object and the Target object is interlinked through
the reference type \'PIES Item to NAPA Product\' in the system.

Following are the detailed steps describing how to achieve the same via
the mapping solution.

**Prerequisites**

Create a new Product Reference Type to link the Source object PIES Item
to the Target object NAPA Product and establish the reference between
the PIES Item to the NAPA Product. In this example, the Product
Reference Type \'PIES Item to NAPA Product\' is defined to create a link
between PIES Item and NAPA Product. Below is the image displaying
hierarchy of Source object (JK21499), Target object (RPC12345), and the
reference linking them.

![](../../../Resources/Images/Data%20Onboarding/115.png)

Also, create a new Product Reference Type (or use the one that exists)
to link the Target object NAPA Product and newly created objects. In
this example, the existing Product Reference Type \'Product To
Interchange Product\' shall be used to create link between NAPA Product
and newly created Interchange object (as shown below). For information
about creating reference types and establishing references, see the
**Reference Types** topic within the **System Setup / Super User Guide**
documentation in **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/116.png)

In the Web UI, create and configure the Mapper Configuration and define
the Source and Target objects and the Reference type to follow to
determine the relationship between the Source and Target object. For
more information on configuring and setup procedure for the Mapper
Configuration, see topic **Configuring Mapper Configuration Setup
Entity** within this guide[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/86.png)

Configure an Initiate Business Action button within the Product Details
screen of the Source object which shall execute the Mapper
Configuration. For more information on executing the Mapper
Configuration, see topic **Executing Mapper Configuration Setup Entity**
within this guide[ here]{.mcFormatColor style="color: Blue;"}.

1.  Add a new Object to Object Mapping plugin (or edit the one that
    exists) in the required Mapper Configuration.
2.  Type in a suitable name next to Name field. In this example, the
    Name field is entered with the text \'PIES Item to NAPA Product
    Reference Mapping Type.\'

![](../../../Resources/Images/Data%20Onboarding/117.png)

1.  Expand the Target Definition flipper, and select \'Reference\'
    option in the dropdown next to \'Mapping type\' field.

2.  Choose the Object Type that should be used for the new objects that
    are getting created. In this example, object type with ID
    \'NAPA\_InterchangeProduct\' is selected.

3.  Choose the Reference Type that should be used to reference from the
    Target object to the newly created object. In this example, an
    existing reference type with ID
    \'NAPA\_ProductToInterchangeProduct\' is selected.

4.  Choose the Parent Node where the new objects will be created below.
    In this example, an existing node from NAPA hierarchy \'Great
    Lakes\' with ID \'NAPA\_InterchangeManufacturer\_5692\' is selected.
    PRODOC note: Currently, the Parent Node is static meaning that only
    one Parent Node can be selected to create new objects below. There
    is ongoing development for future releases to make the Parent Node
    be dynamic by looking at the Manufacturer Name, for example, so that
    the new objects can be created below multiple Parent Nodes.

```{=html}
<!-- -->
```
5.  Click the 'Add object mapping' icon, and the Mapping Guide window
    will display.

![](../../../Resources/Images/Data%20Onboarding/118.png)

1.  Click on the Edit icon
    (![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png))
    in the Source field, and the Step Path Editor window will display
    (as shown below). For more information on defining the Source STEP
    path, see topic **Mapping Validation Path Functionality** within
    this guide[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/55.png)

1.  For this use case, since there are multiple functions required to be
    executed, the following series of logic is used to accomplish the
    requirement through the Step Path Editor.

-   To define what to use for the ID of the new objects that will get
    created.

In this example, the new objects that are going to get created need to
have an ID pattern of NAPA\_Interchange\_\[PIESInterchangeName\]. To
achieve the prefix of \'NAPA\_Interchange\_\' in the ID, we are using
the \'text\' element in the STEP path \> enter the static text of
\'NAPA\_Interchange\_\' \> select \'Use in ID\' checkbox (shown below).

![](../../../Resources/Images/Data%20Onboarding/119.png)

-   To define what to use for the Name of the new objects that are
    getting created, as well to get the PIES Interchange object name
    value in the ID of the new objects that will get created.

In this example, the PIES Interchange object name will be used in the ID
and the Name of the new objects. So, using the
**reference\[type:\'\[id\]\'\]** and **name** elements in the STEP path
will follow defined referenced objects of the Source object and retrieve
the PIES Interchange object name. The \'Use in ID\' and \'Use in Name\'
checkboxes are selected (as shown below).

![](../../../Resources/Images/Data%20Onboarding/120.png)

10. Click **OK** to save and close the Mapping Guide window. The newly
    added object mapping row will be listed.

![](../../../Resources/Images/Data%20Onboarding/121.png)

1.  In the Web UI, standing on the Source object, execute the Mapper
    Configuration that holds the mapping plugin. For more information on
    executing the Mapper Configuration, see topic **Executing Mapper
    Configuration Setup Entity** within this guide[ here]{.mcFormatColor
    style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/122.png)

After the user runs the mapping, the following changes are implemented
in the system.

-   New objects (Interchange products) are created as child objects
    below the Parent Node (Great Lakes) as defined in the Mapper
    Configuration Setup.
-   The new objects are created with an ID pattern as
    NAPA\_Interchange\_\[PIESInterchangeName\].
-   The Name of the new objects are the same as the PIES Interchange.
-   The Object Type that is used for the new object is the one that is
    defined in the Object Type parameter available within the Mapping
    Target Definition flipper.

![](../../../Resources/Images/Data%20Onboarding/123.png)

-   The NAPA Product that was referenced by the PIES Item will be
    referenced to the newly created NAPA Interchange part using the
    reference type that is defined in the Reference Type parameter.

![](../../../Resources/Images/Data%20Onboarding/124.png)
