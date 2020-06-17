---
description: 'Automotive Solution: Describes the use case of copying
  data from one object to another object.'
title: '\[%=Heading.Level1%\]'
---

Use Cases - Copy Attribute Values from One Object to Another Object
===================================================================

Because the Attribute Mapping plugin within Onboarding Mappings Details
screen has many uses for how the mappings can be configured, describing
the components within the mapper does not fully cover all of the
functional use cases.. With that in mind, a use case is described below
that outlines instances where this Attribute Mapping plugin has been
successfully implemented to copy attribute values from one object to
another object.

The use case for the **Attribute mapping** plugin are described below.

Example One
-----------

The requirement for this use case entails that the user has an attribute
value in the Source object that needs to be copied over to the Target
object. The user can do this either by using the Attribute Mapping
plugin or by using the Object to Object Mapping plugin where the Source
STEP path and the Target attribute is defined to hold the Source and the
Target attribute value respectively. As the main intention of this topic
is to address the various possible use cases of Attribute Mapping
plugin, the Attribute Mapping method will be described below to achieve
this requirement.

For this example, the Source object is PIES Item \'034-VC21499\' and the
Target object is NAPA Product \'ATA64A\' interlinked through the
reference type \'PIESItemtoNAPAProduct\' in the system.

**Prerequisites**

The validity of the Source and the Target attribute shall not have any
mismatch.

In the Web UI, create and configure the Mapper Configuration and define
the Source and Target objects and the Reference type to follow to
determine the relationship between the Source and Target object. For
more information on configuring and setup procedure about the Mapper
Configuration, see topic **Configuring Mapper Configuration Setup
Entity** within this guide[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/86.png)

Configure an Initiate Business Action button within the Product Details
screen of the Source object which shall execute the Mapper
Configuration. For more information on executing the Mapper
Configuration, see topic **Executing Mapper Configuration Setup Entity**
within this guide[ here]{.mcFormatColor style="color: Blue;"}.

1.  Add a new Attribute Mapping plugin (or edit the one that exists) in
    the required Mapper Configuration.
2.  Type in a suitable name next to Name field. In this example, the
    Name field is entered with the text \'Copy PIES Attribute to NAPA
    Product Attribute\'

![](../../../Resources/Images/Data%20Onboarding/125.png)

1.  Click the 'Add attribute mapping' icon, and the Mapping Guide window
    will display (as shown below).

![](../../../Resources/Images/Data%20Onboarding/126.png)

1.  With the Sources tab selected, click in the search field and start
    typing the initial letters of the attribute name or ID. This
    searches for the attribute of the Source object from where the
    attribute value could be retrieved. Select the attribute from the
    result list displayed below the search bar. In this example, the
    attribute \'Description Long\' is used as source attribute.

![](../../../Resources/Images/Data%20Onboarding/127.png)

1.  Click **OK** and the selected attribute will be populated in the
    Source field (as shown below)

![](../../../Resources/Images/Data%20Onboarding/128.png)

5.  With the Targets tab selected, search and select the attribute of
    the Target object where the retrieved value from the Source object
    shall reside.

![](../../../Resources/Images/Data%20Onboarding/129.png)

The Source object attribute and the Target object attribute should have
a validity match.

Once selected, the selected attribute will be populated in the Target
field.

![](../../../Resources/Images/Data%20Onboarding/130.png)

1.  Click **OK** to save and close the Mapping Guide window. The newly
    added object mapping row will be listed as shown below.

![](../../../Resources/Images/Data%20Onboarding/131.png)

1.  In the Web UI, standing on the Source object, execute the Mapper
    Configuration that holds the mapping plugin. For more information on
    executing the Mapper Configuration, see topic **Executing Mapper
    Configuration Setup Entity** within this guide[ here]{.mcFormatColor
    style="color: Blue;"}.

 

![](../../../Resources/Images/Data%20Onboarding/84.png)

After the user runs the mapping, the value (Check Engine Light Sensor)
of the \'Description Long\' attribute from the Source object is copied
over to the Target object attribute \'NAPA Text Block.\'

![](../../../Resources/Images/Data%20Onboarding/85.png)
