---
description: 'The Object to Object Mapping Plugin is accessible on
  Onboarding Mappings Details screen. The settings available in this
  \''plugin\'' allow more control over the behavior of Mapper
  Configuration.'
title: '\[%=Heading.Level1%\]'
---

Object to Object Mapping Plugin
===============================

Object to Object Mapping plugin will copy the information present on the
Source object or from its related object (Source STEP Path) to the
Target object or to its related object. The information retrieved from
the Source object could be the ID, name, attribute values, or
references. The information from the Source object could be stored
directly on Target object, as the child of the Target object, or as the
referenced object of the Target object. The Object to Object Mapping
plugin is added and configured in the Onboarding Mappings Details Screen
for the selected Mapper Configuration.

To configure the Object to Object Mapping plugin, follow these steps:

1.  With the required Mapper Configuration selected, click on **New
    mapping** which is available on the Mappings tab of the Onboarding
    Mappings Details screen.

![](../../Resources/Images/Data%20Onboarding/23.png)

1.  Select Object to Object Mapping, and a screen displays prompting the
    user to further configure the plugin. Below is a screenshot of the
    Mappings tab on the Onboarding Mappings Details screen. The steps
    required to configure the Object to Object Mapping are denoted with
    a number in the screenshot. Below the screenshot is a numbered list
    that describes each step, corresponding to the number shown in the
    image.

![](../../Resources/Images/Data%20Onboarding/53.png)

1.  Type in a suitable name next to the Name field. This could be any
    unique name that describes the mapping functionality.
2.  Populate the parameters available under the Target Definition
    flipper as explained below:

-   **Mapping type:** This parameter defines where the retrieved
    information from the source object need to be stored in the target
    location. The available options are:

```{=html}
<!-- -->
```
-   **On Target:** Selecting this option will evaluate the Source STEP
    Path and store the results in the Target object either as an
    attribute value or as a referenced object. This will *not* create
    any new objects.

When this option is selected, the Object Type, Reference Type, and
Parent Node parameters available under the Target Definition flipper are
grayed out and are not used with the On Target Mapping type.

-   **Child:** Selecting this option will evaluate the Source STEP Path
    in order to get the data to be used to create child objects below
    the Target object. The child objects that are created can either be
    Classification or Product objects. The data that is retrieved from
    the Source object can be used in the new objects as an ID, Name,
    attribute value, or reference. The object type to be used for the
    new children objects that will be created below the Target object
    must already exist. This object type is what will be selected in the
    Object Type parameter.

When this option is selected, the Reference Type and Parent Node
parameters are grayed out and are **not** used with the Child Mapping
type.

-   **Reference:** Selecting this option will evaluate the STEP Path on
    the Source object to create new objects below another object, and
    then establish a reference between the Target object and the newly
    created object. The data that is retrieved from the Source object
    can be used in the new objects as an ID, Name, attribute value, or
    reference. The new object can be created under any node (called as
    Parent Node) and then a reference is established between the Target
    object and the new object.

```{=html}
<!-- -->
```
-   **Object Type:** This parameter is used when either the Child or
    Reference Mapping option is selected within the \'Mapping type\'
    parameter. The user can select the object type to be used for the
    new objects that will be created below the Target object,or below
    the defined parent node if the Reference Mapping option is selected.

```{=html}
<!-- -->
```
-   **Reference Type:** This parameter is used when Reference Mapping
    option is selected within the \'Mapping type\' parameter. This
    parameter allows the user to select the Reference Type that should
    be used to establish the reference between the Target object and the
    newly created objects.

```{=html}
<!-- -->
```
-   **Parent Node:** This parameter is only used when Reference Mapping
    option is selected within the \'Mapping type\' parameter. The user
    can select the parent node under which the newly created objects
    will reside.
-   **Condition:** This parameter is used when either the Child or
    Reference Mapping option is selected within the \'Mapping type\'
    parameter. The user can select a business condition that gets
    executed when the associated Mapper Configuration setup entity is
    executed. This parameter will most often be used to define a
    business condition that decides whether the objects related to
    Target is to be created or not.

5.  Click the 'Add object mapping' icon, and the Mapping Guide window
    will display.

![](../../Resources/Images/Data%20Onboarding/54.png)

1.  To define which information (ID, Name, attribute values, or
    references) from the Source object needs to be retrieved, click on
    the Edit icon
    (![](../../Resources/Images/Data%20Onboarding/Edit%20icon.png)) in
    the Source field, and the Step Path Editor window will display (as
    shown below). The user also has the option to select specific data
    points from the Source object, or any of its related objects by
    selecting a combination of the elements available in the Keywords
    field and thereby creating a STEP Validation path. For more
    information on defining the Source STEP Path, see the **Mapping
    Validation Path Functionality** topic within this guide[
    here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/Data%20Onboarding/55.png)

1.  Double-click on the required element(s) from the \'Keywords\' field.
    The selected element will be populated in the \'Validation Path\'
    field (as shown below). The specific combination of elements are
    chosen depending on the unique requirements for the data being
    retrieved. Selecting the elements will define the Source STEP Path
    which describes the path from which the source data must be
    retrieved. Depending on the element selected, further configurations
    may be required. In the example below, element
    **attribute\[id:\'\[id\]\'\]** is selected and displays in the
    Validation Path field. The red colored field indicates that
    additional configuration is required.

![](../../Resources/Images/Data%20Onboarding/56.png)

Users can add one element or a combination of elements to create a
Source STEP Path. For more information on creating the Source STEP Path,
see the **Mapping Validation Path Functionality** topic within this
guide[ here]{.mcFormatColor style="color: Blue;"}.

In this example, the selected element \'attribute\[id:\'\[id\]\'\]\' is
configured to retrieve the value from attribute with ID
\'AC\_PIES\_DESCDES\'.

![](../../Resources/Images/Data%20Onboarding/58.png)

Once selected, the Source STEP Path with the defined data will be
populated in the Source field.

![](../../Resources/Images/Data%20Onboarding/59.png)

8.  With the \'Targets\' tab selected, click in the Search field and
    start typing the initial letters of the attribute / reference name
    or ID of the target attribute / reference to which the value should
    be copied. Select the attribute / reference from the typeahead
    results displayed below the search bar.

![](../../Resources/Images/Data%20Onboarding/60.png)

Once selected, the attribute / reference will be populated in the Target
field.

![](../../Resources/Images/Data%20Onboarding/61.png)

Only attributes / references that are valid for the object type defined
in the mapping Setup tab will be displayed as options to select on the
Targets tab.

After the Source STEP Path and target attribute / reference are defined,
the system evaluates the validity match between the Source STEP Path and
the target attribute / reference. A hyperlink text explaining the reason
for the validity match / mismatch displays. Clicking on the hyperlink
opens the \'Detailed Information\' dialog which displays the validity
match / mismatch information of the Object to Object mapping. Below is
an example of a valid match between the Source STEP Path and the target
attribute displayed in the \'Detailed Information\' dialog.

![](../../Resources/Images/Data%20Onboarding/62.png)

Users can suppress the validation mismatch warning message by clicking
on the \'Suppress\' checkbox in the Mapping Guide window. Selecting the
\'Suppress\' checkbox *only* removes the data type mismatch warnings
displayed on the Mapping Guide window and does not resolve the mismatch
irregularities.

1.  With the \'Transformations\' tab selected, click in the search field
    and start typing the initial letters of the transformation name or
    ID. This brings up a dropdown of typeahead search results listing
    the attribute transformations available in the system. Select the
    relevant transformation from the list displayed below the search
    bar.

The transformations must be created and defined in workbench System
Setup prior to being available to be selected in the Mapping Guide.

![](../../Resources/Images/Data%20Onboarding/63.png)

The selected transformation will be populated in the \'Transformation\'
field (as shown below).

![](../../Resources/Images/Data%20Onboarding/64.png)

For information on configuring the attribute transformations, see the
**Attribute Transformations** topic within the **System Setup** section
of **STEP Online Help** ([here]{.mcFormatColor style="color: Blue;"}).
And for details on each of the available transformation options, see the
**Transformations** topic in the **Resource Materials** online help[
here]{.mcFormatColor style="color: Blue;"}.

The populated transformation can be deleted by clicking the delete icon
(![](../../Resources/Images/Data%20Onboarding/Delete%20icon.png)) in the
\'Transformation\' field. Similarly the populated Target attribute /
reference can also be deleted by clicking the delete icon
(![](../../Resources/Images/Data%20Onboarding/Delete%20icon.png)) in the
\'Target\' field.

![](../../Resources/Images/Data%20Onboarding/65.png)

1.  Click **OK** to save and close the \'Mapping Guide\' window and then
    click **Save** to save the changes. As shown in the screenshot
    below, the newly added object mapping row will display. To edit the
    object mapping, click on the row to open the Mapping Guide window in
    which edits can be made.

Once the user adds a mapping and selects the Source STEP Path and Target
and clicks **OK** to close out of the Mapping Guide window, the **Save**
button is enabled until the user clicks on **Save** button. If the user
fails to click **Save**, than the mapping will be lost once user selects
a new mapping configuration.

![](../../Resources/Images/Data%20Onboarding/66.png)

1.  Repeat the above steps 5 to 10 to add more object mapping rows for
    the same plugin.

User can add any number of mapping rows in the mapping plugin. When
there are multiple mapper rows available within the mapping plugin, the
order of execution of each mapper row is based on the order in which it
is listed within the mapping plugin.

The health of the mapping row is displayed next to each mapping row.
Users can also add some additional information describing each of the
mapper rows. The user has the flexibility to disable, delete, or
rearrange the listing order of the mapper rows. For more information on
handling the mapper rows, see topic **Modifying Mapper Rows on the
Onboarding Mapping Details Screen** within this guide.
