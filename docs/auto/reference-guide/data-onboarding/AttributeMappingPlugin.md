---
description: 'The Attribute Mapping Plugin is accessible on Onboarding
  Mappings Details screen. The settings available in this \''plugin\''
  allow more control over the behavior of Mapper Configuration.'
title: '\[%=Heading.Level1%\]'
---

Attribute Mapping Plugin
========================

The Attribute Mapping plugin will copy attribute values from the source
object to the target object. It is configured on the Onboarding Mappings
Details Screen for the selected Mapper Configuration. The settings
available in this plugin allow the user to define what the Mapper
Configuration should do with the attribute values.

All settings are not necessary for all attributes. The specific
combinations chosen are dependent on the unique requirements for the
attribute being configured. The settings contained within this plugin
can include transformations. The plugin can be configured to either
Onboard / Outboard the data or in some cases can be configured to work
along with transformations, too.PRODOC note:We should add that this can
be used with lookup tables and provide a use case with the lookup
tables. NGK uses a lot of lookup tables.

To configure the Attribute Mapping plugin, follow these steps.

1.  With the required Mapper Configuration selected, click on **New
    mapping** available within the Mappings tab of the Onboarding
    Mappings Details screen.

![](../../Resources/Images/Data%20Onboarding/23.png)

1.  Select Attribute Mapping, and a screen is displayed prompting the
    user to further configure the plugin (as shown below).

![](../../Resources/Images/Data%20Onboarding/37.png)

1.  Type in a suitable name next to Name field. This could be any unique
    name that clearly describes the mapping functionality.In the example
    below, a name \'Copy attribute value from PIES to NAPA Product\' is
    entered.

```{=html}
<!-- -->
```
1.  Click the 'Add attribute mapping' icon, and the Mapping Guide window
    will display (as shown below).

![](../../Resources/Images/Data%20Onboarding/38.png)

1.  With the Sources tab selected, click in the Search field and start
    typing the initial letters of the attribute name or ID. This brings
    up a dropdown of typeahead search results listing the attributes of
    the Source object available in the system from where the attribute
    value could be retrieved. Select the attribute from the result list
    displayed below the search bar.

![](../../Resources/Images/Data%20Onboarding/39.png)

Once selected, the attribute will be populated in the Source field (as
shown below)

![](../../Resources/Images/Data%20Onboarding/40.png)

1.  With the Targets tab selected, click in the Search field and start
    typing the initial letters of the attribute name or ID. This
    searches for the attribute from the Target object where the
    retrieved value should be copied to. Select the attribute from the
    result list displayed below the search bar.

![](../../Resources/Images/Data%20Onboarding/41.png)

Once selected, the attribute will be populated in the Target field (as
shown below).

![](../../Resources/Images/Data%20Onboarding/42.png)

Only attributes that are valid for the object type that is defined in
the mapping Setup tab will be displayed as options to select from in the
Sources and Targets tabs.

After the source and target attributes are defined, the system evaluates
the validity match between the source and the target attributes. A
hyperlink text explaining the reason for the validity match / mismatch
gets displayed. Clicking on the hyperlink will open the \'Detailed
Information\' dialog and displays the validity match / mismatch
information of the attribute mapping. Below is an example of a
validation mismatch between the source and the target attribute
displayed in the \'Detailed Information\' dialog:

![](../../Resources/Images/Data%20Onboarding/43.png)

The user can suppress the validation mismatch warning message by
clicking on the \'Suppress\' checkbox in the Mapping Guide window.
Selecting the \'Suppress\' checkbox will *only* remove the data type
mismatch warnings displayed on the Mapping Guide window and *does not
resolve* the mismatch irregularities.

![](../../Resources/Images/Data%20Onboarding/48.png)

1.  With the \'Transformations\' tab selected, click in the search field
    and start typing the initial letters of the transformation name or
    ID. This brings up a dropdown of typeahead search results listing
    the attribute transformations available in the system. Select the
    relevant transformation from the list displayed below the search
    bar.

The transformations must be created and defined in workbench System
Setup prior to being available to be selected in the Mapping Guide.

![](../../Resources/Images/Data%20Onboarding/44.png)

The selected transformation will be populated in the Transformation
field (as shown below).

![](../../Resources/Images/Data%20Onboarding/45.png)

The populated transformation can be deleted by clicking the delete icon
(![](../../Resources/Images/Data%20Onboarding/Delete%20icon.png)) in the
Transformation field. Clicking the edit icon
(![](../../Resources/Images/Data%20Onboarding/Edit%20icon.png)) will
open the Transformation Overview dialog and lets the user test the
functionality of the transformation via the **Test** button (as shown
below). For more information on this **Test** button, see the **Testing
Transformations Configured in Attribute Mapping Plugin** topic within
this guide[ here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/Data%20Onboarding/47.png)

The attribute transformations can also be created in the Mapping guide
window by clicking on the Create New Transformation icon
(![](../../Resources/Images/Data%20Onboarding/Create%20transformation%20icon.png))
available within the Transformation field. Users can define the ID,
Name, and the hierarchy in which the attribute transformation should be
stored in.

The Create New Transformation icon
(![](../../Resources/Images/Data%20Onboarding/Create%20transformation%20icon.png))
would only create the attribute transformation, and the user needs to
configure and define the functionality of the transformation separately
in the workbench.

![](../../Resources/Images/Data%20Onboarding/51.png)

For information on configuring the attribute transformations, see the
**Attribute Transformations** topic within the **System Setup** section
of **STEP Online Help** ([here]{.mcFormatColor style="color: Blue;"}).
And for details on each of the available transformation options, see the
**Transformations** topic in the **Resource Materials** online help[
here]{.mcFormatColor style="color: Blue;"}.

1.  Click **OK** to close the Mapping Guide window and then click
    **Save** to save the changes. The newly added attribute mapping row
    will be listed as shown below. To edit the attribute mapping
    selections, click on the row and it will open up the Mapping Guide
    window in order to make edits.

Once the user adds a mapping and selects the Source and Target attribute
and clicks **OK** to close out of the Mapping Guide window, the **Save**
button is enabled until the user clicks on **Save** button. If the user
fails to click **Save**, than the mapping will be lost once user selects
a new mapping configuration.

![](../../Resources/Images/Data%20Onboarding/52.png)

1.  Repeat the above steps 4 to 8 to add more attribute mapping rows for
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
