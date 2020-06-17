---
description: 'Automotive Solution: Describes the use case of copying
  data from one object to the child object of another object.'
title: '\[%=Heading.Level1%\]'
---

Use Cases - Copy Data from One Object to Child Object of Another Object
=======================================================================

Because the Object to Object mapping plugin within Onboarding Mappings
Details screen has many uses for how the mappings can be configured,
describing the components within the mapper does not fully cover all of
the functional use cases. With that in mind, two full use cases are
described below that outline instances where this Object to Object
Mapping plugin has been successfully implemented to copy data from one
object to child object of another object.

Example One
-----------

For the ease of understanding in this topic, data is to be copied from
AutoCare standard to our Own standard. The AutoCare Vehicle hierarchy
creates multiple objects that are split up for Sub Models and Years
below the Model object. In this example, the Model object in the
AutoCare Vehicle hierarchy will be used to illustrate how you are able
to create your Own Vehicle hierarchy that combines the Sub Model and
Year into one object and store the Sub Model and Year as attribute
values on that object. And, consideration has been given to use the
Engine Base value from the AutoCare hierarchy in the ID and Name of the
newly created objects in the Own Vehicle hierarchy.

In this example, the AutoCare Audi 100 model is used as the Source
object and take all Sub Models and Years below 100 model to create as
new objects below the Own object (example Target Vehicle 100 hierarchy).
Below is the image displaying AutoCare hierarchy of Source object
(Model).

![](../../../Resources/Images/Data%20Onboarding/88.png)

Below is the image displaying the Own hierarchy of Target object (Target
Vehicle hierarchy).

![](../../../Resources/Images/Data%20Onboarding/89.png)

Following are the detailed steps describing to achieve the same via the
mapping solution.

**Prerequisites**

Create a new Classification Reference Type and establish the reference
between the AutoCare Audi model 100 and Own Target Vehicle 100 object.
For information about creating reference types and establishing
references, see the **Reference Types** topic within the **System Setup
/ Super User Guide** section of **STEP Online Help**[
here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/90.png)

In the Web UI, create and configure the Mapper Configuration and define
the Source and Target objects and the Reference type to follow to
determine the relationship between the Source and Target object. For
more information on configuring and setup procedure for the Mapper
Configuration, see topic **Configuring Mapper Configuration Setup
Entity** within this guide[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/91.png)

Configure an Initiate Business Action button within the Product Details
screen of the Source object which shall execute the Mapper
Configuration. For more information on executing the Mapper
Configuration, see topic **Executing Mapper Configuration Setup Entity**
within this guide[ here]{.mcFormatColor style="color: Blue;"}.

1.  Add a new Object to Object Mapping plugin (or edit the one that
    exists) in the required Mapper Configuration.
2.  Type in a suitable name next to Name field. In this example, the
    Name field is entered with the text \'Create Target Vehicles from
    AutoCare Model.\'

![](../../../Resources/Images/Data%20Onboarding/92.png)

1.  Expand the Target Definition flipper, select \'Child\' option in the
    dropdown next to \'Mapping type\' field.

2.  Choose the Object Type that should be used for the new objects that
    are getting created. In this example, object type with id
    \'Target\_Vehicle\' is selected.

```{=html}
<!-- -->
```
5.  Click the 'Add object mapping' icon, and the Mapping Guide window
    will display (as shown below).

![](../../../Resources/Images/Data%20Onboarding/93.png)

1.  Click on the Edit icon
    (![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png))
    in the Source field, and the Step Path Editor window will display.
    For more information on defining the Source STEP path, see topic
    **Mapping Validation Path Functionality** within this guide[
    here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/55.png)

1.  For this use case, since there are multiple functions required to be
    executed, the following logic is used to accomplish the requirement
    through the STEP path.

-   To define what to use for the ID of the new objects that will get
    created.

In this example, the new objects that are going to get created are to
have a prefix of \'Target\_\' in the ID. So, using the \'text\' element
in the STEP path \> enter the static text of \'Target\_\' \> select Use
in ID checkbox.

![](../../../Resources/Images/Data%20Onboarding/94.png)

-   To define what to use for the Name of the new objects that are
    getting created, as well as what values to use in the ID to make it
    unique.

In this example, the AutoCare Sub Model is used in the ID and the Name
of the new objects as well as storing the value as an attribute value in
the new objects. So, using the **child\[objecttype:\'\[id\]\'\]** and
**attribute\[id:\'\[id\]\'\]** elements in the STEP path will follow
child objects of the Source object and retrieve the Sub Model that is
stored as an attribute value on the Vehicle object. The \'Use in ID,\'
\'Use in Name,\' and \'Hash\' checkboxes are selected. (The \'Hash\'
checkbox is used if the combined values for the ID will be \>40
characters since there is a maximum of 40 characters limit for IDs.)
Also, the Target attribute of Sub Model is selected to store the value
in.

![](../../../Resources/Images/Data%20Onboarding/95.png)

-   The use case requires to use the Engine Base ID in the ID of the new
    objects.

Using the **child\[objecttype:\'\[id\]\'\]**,
**reference\[type:\'\[id\]\'\]**, and **id** elements in the STEP path
to follow child objects and references of the Source object, the Engine
Base ID is retrieved to be used in the ID of the new objects. The \'Use
in ID\' and \'Hash\' checkboxes are selected.

![](../../../Resources/Images/Data%20Onboarding/96.png)

-   The use case requires the use of the Engine Base Name in the Name of
    the new objects.

Using the **child\[objecttype:\'\[id\]\'\]**,
**reference\[type:\'\[id\]\'\]**, and **name** elements in the STEP path
to follow child objects and references of the Source object, the Engine
Base Name is retrieved to be used as the Name of the new objects (as
shown below).

![](../../../Resources/Images/Data%20Onboarding/97.png)

-   The use case requires the use of the Year attribute value and store
    it as an attribute value on the new objects.

Using the **child\[objecttype:\'\[id\]\'\]** and
**attribute\[id:\'\[id\]\'\]** elements in the STEP path to follow the
child object of the Source object, the AC\_VCdbYear attribute value is
retrieved for Year. Also, the Target attribute of Year is selected to
store the value in (as shown below).

![](../../../Resources/Images/Data%20Onboarding/98.png)

8.  Click **OK** to save and close the Mapping Guide window. The newly
    added object mapping row will be listed.

![](../../../Resources/Images/Data%20Onboarding/99.png)

1.  In the Web UI, standing on the Source object, execute the Mapper
    Configuration that holds the mapping plugin. For more information on
    executing the Mapper Configuration, see topic **Executing Mapper
    Configuration Setup Entity** within this guide[ here]{.mcFormatColor
    style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/100.png)

After the user runs the mapping, the following changes are implemented
in the system.

-   New objects are created as single child objects below the Target
    object that is defined in the Mapper Configuration Setup.
-   The new objects are created with ID of Target\_\[Hash\].
-   The Name of the new object is the value of the Engine Base Name.
-   The Object Type that is used for the new object is the one that is
    defined in the Object Type parameter in the Mapping Target
    Definition flipper.
-   The Year values are stored in the Own\_Year attribute on the new
    object.
-   The Sub Model value is stored in the Sub Model attribute on the new
    object.

![](../../../Resources/Images/Data%20Onboarding/101.png)

Example Two
-----------

The second requirement for this use case entails that the user has
maintained part numbers (PIES Items) and applications (ACES) in the
AutoCare Product hierarchy, but also want to create the PIES Items as
part numbers in their Own product hierarchy and establish the reference
from their Own part number to the PIES Item.

In this example, the AutoCare part type \'Vehicle Battery\' is used as
the Source object and all PIES Items below \'Vehicle Battery\' are used
to create new objects below the Own object (example \'Own Vehicle
Battery\' hierarchy).

**Prerequisites**

Create a new Product Reference Type to link the PIES Item parent object
to the Target parent object and establish the reference between the PIES
Item parent part type object to the Own parent part type object that
user needs to create the new part numbers below. In this example, the
Product Reference Type \'PIES Part Type to Target Part Type\' is defined
to create the link between PIES Item parent and Own part number parent
object. Below is the image displaying hierarchy of Source object
(Vehicle Battery), Target object (Own Vehicle Battery), and the
reference linking them.

![](../../../Resources/Images/Data%20Onboarding/102.png)

Also, create a new Product Reference Type to link the new Target part
number and existing PIES Item. In this example, the Product Reference
Type \'OWN Part To PIES Part\' is defined to create link between Own
part number and PIES Item object (as shown below). For information about
creating reference types and establishing references, see the
**Reference Types** topic within the **System Setup / Super User Guide**
section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/103.png)

In the Web UI, create and configure the Mapper Configuration and define
the Source and Target objects and the Reference type to follow to
determine the relationship between the Source and Target object. For
more information on configuring and setup procedure for the Mapper
Configuration, see topic **Configuring Mapper Configuration Setup
Entity** within this guide[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/104.png)

Configure an Initiate Business Action button within the Product Details
screen of the Source object which shall execute the Mapper
Configuration. For more information on executing the Mapper
Configuration, see topic **Executing Mapper Configuration Setup Entity**
within this guide[ here]{.mcFormatColor style="color: Blue;"}.

1.  Add a new Object to Object Mapping plugin (or edit the one that
    exists) in the required Mapper Configuration.
2.  Type in a suitable name next to Name field. In this example, the
    Name field is entered with the text \'Create AutoCare PIES Items for
    Own Parts.\'

![](../../../Resources/Images/Data%20Onboarding/105.png)

1.  Expand the Target Definition flipper, select \'Child\' option in the
    dropdown next to \'Mapping type\' field.

2.  Choose the Object Type that should be used for the new objects that
    are getting created. In this example, object type with id
    \'Own\_Partnumber\' is selected.

```{=html}
<!-- -->
```
5.  Click the 'Add object mapping' icon, and the Mapping Guide window
    will display.

![](../../../Resources/Images/Data%20Onboarding/106.png)

1.  Click on the Edit icon
    (![](../../../Resources/Images/Data%20Onboarding/Edit%20icon.png))
    in the Source field, and the Step Path Editor window will display.
    For more information on defining the Source STEP path, see topic
    **Mapping Validation Path Functionality** within this guide[
    here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/55.png)

1.  For this use case, since there are multiple functions required to be
    executed, the following series of logic is used to accomplish the
    requirement through the STEP path.

-   To define what to use for the ID of the new objects that will get
    created.

In this example, the new objects that are going to get created need to
have an ID pattern of Own\_\[BrandAAIAID\]\_\[PIESItemName\]. To achieve
prefix of \'Own\_\' in the ID, we are using the \'text\' element in the
STEP path \> enter the static text of \'Own\_\' \> select Use in ID
checkbox (as shown below).

![](../../../Resources/Images/Data%20Onboarding/107.png)

-   To get the BrandAAIAID value in the ID of the new objects that will
    get created.

In this example, the BrandAAIAID value is used in the ID of the new
objects. So, using the **child\[objecttype:\'\[id\]\'\]** and
**attribute\[id:\'\[id\]\'\]** elements in the STEP path will follow
child objects of the Source object and retrieve the BrandAAIAID value
that is stored as an attribute value on the PIES Item. The \'Use in ID\'
checkbox is selected (as shown below).

![](../../../Resources/Images/Data%20Onboarding/108.png)

-   To get the \'\_\' value in the ID of the new objects that will get
    created.

In this example, the new objects that are going to get created have to
have an ID pattern of Own\_\[BrandAAIAID\]\_\[PIESItemName\]. To achieve
prefix of \'\_\' after the \[BrandAAIAID\] in the ID, we are using the
\'text\' element in the STEP path \> enter the static text of \'\_\' \>
select Use in ID checkbox (as shown below).

![](../../../Resources/Images/Data%20Onboarding/109.png)

-   To define what to use for the Name of the new objects that are
    getting created, as well to get the PIES Item Name value in the ID
    of the new objects that will get created.

In this example, the PIES Item Name is used in the ID and the Name of
the new objects. So, using the **child\[objecttype:\'\[id\]\'\]** and
**name** elements in the STEP path will follow child objects of the
Source object and retrieve the PIES Item Name. The \'Use in ID\' and
\'Use in Name,\' checkboxes are selected (as shown below).

![](../../../Resources/Images/Data%20Onboarding/110.png)

-   The use case requires the establishment of the reference from the
    newly created Own part number to the PIES Item.

Using the **child\[objecttype:\'\[id\]\'\]** and **id** elements in the
STEP path to follow the child object of the Source object, the PIES Item
is retrieved as the Source Object. Also the reference type
\'OwnPartToPIESPart\' is defined in the Target field define the Target
reference type (as shown below).

![](../../../Resources/Images/Data%20Onboarding/111.png)

8.  Click **OK** to save and close the Mapping Guide window. The newly
    added object mapping row will be listed.

![](../../../Resources/Images/Data%20Onboarding/112.png)

1.  In the Web UI, standing on the Source object, execute the Mapper
    Configuration that holds the mapping plugin. For more information on
    executing the Mapper Configuration, see topic **Executing Mapper
    Configuration Setup Entity** within this guide[ here]{.mcFormatColor
    style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/113.png)

After the user runs the mapping, the following changes are implemented
in the system:

-   New objects (Own part numbers) are created as child objects below
    the Target object (Target Part type) that is defined in the Mapper
    Configuration Setup.
-   The new objects are created with ID pattern of
    Own\_\[BrandAAIAID\]\_\[PIESItemName\].
-   The Name of the new objects are same as the PIES Item.
-   The Object Type that is used for the new object is the one that is
    defined in the Object Type parameter available within the Mapping
    Target Definition flipper.
-   The new Own part number is referenced to the PIES Item.

![](../../../Resources/Images/Data%20Onboarding/114.png)
