---
description: 'Automotive Solution: Describes the use case of copying
  data from one object to another object.'
title: '\[%=Heading.Level1%\]'
---

Use Cases - Copy Data from One Object to Another Object
=======================================================

Because the Object to Object mapping plugin within the Onboarding
Mappings Details screen has many uses for how the mappings can be
configured, describing the components within the mapper does not fully
cover all of the functional use cases. With that in mind, two full use
cases are described below. They outline instances where this Object to
Object Mapping plugin has been successfully implemented to copy data
from one object to another object.

Example One
-----------

Consider an asset that is referenced as the Primary Product Image on the
Source object (for example, PIES Item) and the user needs to also use
the same asset on the Target object (for example, NAPA Product) as the
Primary Product Image.

For this example, the Source object is a PIES Item \'034-VC21499\' and
the Target object is a NAPA Product \'ATA64A\' interlinked through the
reference type \'PIESItemtoNAPAProduct\' in the system.

Following are the detailed steps describing how to configure the mapping
to create the asset that is used as the Primary Product Image reference
on a PIES Item to be used as the Primary Product Image reference on a
NAPA Product, too.

**Prerequisites**

Define the asset object type of the asset referenced in the Source
object as the Valid Target Type for the \'Image and Document Reference
Type\' that is used from the Target object (NAPA Product). In this
example, the existing NAPA Product Image and Document Reference Type
\'Part Number To Image\' is defined to hold asset object type
\'AC\_PIESProductImage\' as a Valid Target Type. For information about
configuring the reference types, see the **Reference Types** topic
within the **System Setup / Super User Guide** section of **STEP Online
Help**[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/70.png)

In the Web UI, create and configure the Mapper Configuration and define
the Source and Target object types as well as the Reference type to
follow to determine the relationship between the Source and Target
object. For more information on configuring and setup procedure about
the Mapper Configuration, see topic **Configuring Mapper Configuration
Setup Entity** within this guide[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/86.png)

Configure an Initiate Business Action button within the Product Details
screen of the Source object which shall execute the Mapper
Configuration. For more information on executing the Mapper
Configuration, see topic **Executing Mapper Configuration Setup Entity**
within this guide[ here]{.mcFormatColor style="color: Blue;"}.

1.  Add a new Object to Object Mapping plugin (or edit the one that
    exists) in the required Mapper Configuration.
2.  Type in a suitable name next to Name field. In this example, the
    Name field is entered with the text \'Copy Primary Product Image
    from PIES to NAPA Product.\'

![](../../../Resources/Images/Data%20Onboarding/67.png)

1.  Expand the Target Definition flipper, select \'On Target\' option in
    the dropdown next to \'Mapping type\' field.

```{=html}
<!-- -->
```
5.  Click the 'Add object mapping' icon, and the Mapping Guide window
    will display.

![](../../../Resources/Images/Data%20Onboarding/68.png)

1.  Click on the Edit icon
    (![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png))
    in the Source field, and the Step Path Editor window will display
    (as shown below). For more information on defining the Source STEP
    path, see topic **Mapping Validation Path Functionality** within
    this guide[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/55.png)

1.  First, double click to add the **reference\[type:\'\[id\]\'\]**
    element from the Keywords field. Also, the ID of the asset must be
    configured from the Source to use in the Target reference, so double
    click to add the **id** element from the Keywords field (do not use
    the name of the asset). The selected elements will be populated in
    the Validation Path field (as shown below). The red colored field
    depicts that further configuration is required.

![](../../../Resources/Images/Data%20Onboarding/69.png)

1.  Click on the empty red colored **reference\[type:\'\[id\]\'\]**
    element available within the Validation Path field and select the
    reference type that is referencing the Primary Product Image on the
    Source object. In this example, it is the reference type with id
    \'AC\_PIESItemToProductImage.\'

Once populated, the elements in the Validation path turn green in color
as displayed below.

![](../../../Resources/Images/Data%20Onboarding/71.png)

1.  Click **OK** and the Source STEP Path will be populated in the
    Source field.

![](../../../Resources/Images/Data%20Onboarding/72.png)

5.  With the Targets tab selected, search and select the \'Image and
    Document Reference Types\' of the Target object. In this reference
    type, the Primary Product Image of the Source object will reside.

![](../../../Resources/Images/Data%20Onboarding/73.png)

The asset object type must be defined as the Valid Target Type for the
Image Reference Type for both the Source and the Target object.

Once selected, the selected reference type will be populated in the
Target field.

![](../../../Resources/Images/Data%20Onboarding/74.png)

1.  Click **OK** to close the Mapping Guide window and then click
    **Save** to save the changes. The newly added object mapping row
    will be listed.

![](../../../Resources/Images/Data%20Onboarding/83.png)

1.  In the Web UI, standing on the Source object, execute the Mapper
    Configuration that holds the mapping plugin. For more information on
    executing the Mapper Configuration, see topic **Executing Mapper
    Configuration Setup Entity** within this guide[ here]{.mcFormatColor
    style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/75.png)

After the user runs the mapping, the asset (VC21499\_P04) that was used
in the Source object is created as a reference on the Target object
using the target reference type that is configured in the mapping.

![](../../../Resources/Images/Data%20Onboarding/76.png)

Example Two
-----------

An additional requirement for this use case entails that the user has an
attribute value in the Source object that needs to be copied over to the
Target object. The user can do this either by using the Attribute
Mapping plugin or the Object to Object Mapping plugin. As the main
intention of this topic is to address the various possible use cases of
Object to Object Mapping plugin, the latter method will be used to
achieve this requirement. Also, for the ease of understanding and to
skip repeating some basic steps, the same Object to Object Mapping
plugin detailed above (Copy Primary Product Image from PIES to NAPA
Product) shall be used to achieve this requirement.

**Prerequisites**

The validity of the Source and the Target attribute shall not have any
mismatch.

Configure an Initiate Business Action button within the Product Details
screen of the Source object which shall execute the Mapper
Configuration. For more information on executing the Mapper
Configuration, see topic **Executing Mapper Configuration Setup Entity**
within this guide[ here]{.mcFormatColor style="color: Blue;"}.

Within the Object to Object Mapping plugin, select the \'On Target\'
option in the \'Mapping type\' field under the Target Definition
flipper.

![](../../../Resources/Images/Data%20Onboarding/67.png)

1.  Click the 'Add object mapping' icon, and the Mapping Guide window
    will display.

![](../../../Resources/Images/Data%20Onboarding/68.png)

1.  Click on the Edit icon
    (![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png))
    in the Source field, and the Step Path Editor window will display.
    For more information on defining the Source STEP path, see topic
    **Mapping Validation Path Functionality** within this guide[
    here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/55.png)

1.  Double click on add the **attribute\[id:\'\[id\]\'\]** element from
    the Keywords field. The selected element will be populated in the
    Validation Path field (as shown below). The red colored field
    depicts that further configuration is required.

![](../../../Resources/Images/Data%20Onboarding/77.png)

1.  Click on the empty red colored **attribute\[id:\'\[id\]\'\]**
    element available within the Validation Path field and select the
    Source attribute from which the value will be copied over to the
    Target object. In this example, the attribute with id
    \'AC\_PIES\_DESCDES\' is selected.

Once populated, the elements in the Validation path turn green in color
as displayed below.

![](../../../Resources/Images/Data%20Onboarding/78.png)

1.  Click **OK** and the selected element with the defined data will be
    populated in the Source field.

![](../../../Resources/Images/Data%20Onboarding/79.png)

5.  With the Targets tab selected, search and select the attribute of
    the Target object where the retrieved value from the Source object
    shall reside.

![](../../../Resources/Images/Data%20Onboarding/80.png)

The Source object attribute and the Target object attribute should have
the validity match.

Once selected, the selected attribute will be populated in the Target
field (as shown below).

![](../../../Resources/Images/Data%20Onboarding/81.png)

1.  Click **OK** to close the Mapping Guide window and then click
    **Save** to save the changes. The newly added object mapping row
    will be listed.

![](../../../Resources/Images/Data%20Onboarding/82.png)

1.  In the Web UI, standing on the Source object, execute the Mapper
    Configuration that holds the mapping plugin. For more information on
    executing the Mapper Configuration, see topic **Executing Mapper
    Configuration Setup Entity** within this guide[ here]{.mcFormatColor
    style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/84.png)

After the user runs the mapping, the value (Check Engine Light Sensor)
of the Description Long attribute from Source object is copied over to
the Target object attribute NAPA Text Block.

![](../../../Resources/Images/Data%20Onboarding/85.png)
