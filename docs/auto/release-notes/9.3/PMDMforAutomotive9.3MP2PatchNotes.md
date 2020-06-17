---
description: 'Automotive Solution: PMDM for Automotive 9.3 MP2 April
  2020 Patch Notes'
title: PMDM for Automotive 9.3 MP2 April 2020 Patch Notes
---

PMDM for Automotive 9.3 MP2 Patch Notes {#pmdm-for-automotive-9.3-mp2-patch-notes .MPN}
=======================================

Release Date: April 24, 2020 {#release-date-april-24-2020 style="text-align: center;"}
----------------------------

Announcement {#announcement .MPNDocumentation}
------------

Internal Note: RDCUST- 3756Removed NAPA Attribute Import and Export from
all Easy Setup configurations

The NAPA Easy Setup is updated to no longer create the NAPA Attribute
IIEP, workflow, and Web UI screens. The following services are no longer
supported by the Easy Setup action:

-   Creation of IIEP ID = NAPAAttributeInboundEndpoint
-   Creation of workflow ID = NAPAAttributeImport
-   Creation of NAPA Attribute Exporter in Export Manager Format
-   Creation of NAPAAttributeImport Status Selector Homepage Widget in
    the Web UI ID = NAPAWebUI
-   Creation of NAPAAttributeControllerScreen in the Web UI ID =
    NAPAWebUI
-   Creation of NAPAAttributeWorkflowScreen in the Web UI ID = NAPAWebUI
-   Creation of NAPAAttributeInboundEndpoint from the Inbound
    Integration Endpoint Parameter in the File Loading Widget in Web UI
    ID = NAPAWebUI

New Features {#new-features .MPNNewFeatures}
------------

Internal Note: RDCUST- 4006Updated Mapping plugins to allow editing the
existing transformations

It is now possible to edit existing transformations that are available
within the attribute transformation. Clicking the three-dotted icon
(![](../../Resources/Images/Data%20Onboarding/three%20dotted%20icon.png))
that is available in the right of an existing transformation will now
display the Edit Transformation
(![](../../Resources/Images/Data%20Onboarding/Edit%20icon.png)) button.
Clicking on the Edit Transformation button allows users to edit the
existing Transformations.

![](../../Resources/Images/Release%20Notes/9.3mp2/2.png)

Internal Note: RDCUST- 4006Updated Mapping plugins to allow editing
transformation lookup tables

It is now possible to edit / create the transformation lookup tables
that are available within the attribute transformation. There are
multiple ways that one can access and edit the transformation lookup
table in the Mapper row. One easy access is by clicking the three-dotted
icon
(![](../../Resources/Images/Data%20Onboarding/three%20dotted%20icon.png))
that is available to the right of an existing lookup table derived
transformation. Clicking the three-dotted icon
(![](../../Resources/Images/Data%20Onboarding/three%20dotted%20icon.png))
will now display the Edit Lookup Table
(![](../../Resources/Images/Data%20Onboarding/Edit%20icon.png)) button
that allows users to edit the existing transformation lookup table.

![](../../Resources/Images/Release%20Notes/9.3mp2/13.png)

PRODOC note: RDCUST- 4029Target Hierarchy Editor window now allows
creating / editing an attribute transformation

The Target Hierarchy Editor window gets displayed when the user clicks
the edit icon
(![](../../Resources/Images/Data%20Onboarding/Edit%20icon.png)) next to
the Target Hierarchy field in the Setup tab of the Onboarding Mappings
Details screen. The Target Hierarchy Editor window now provides users an
option to create / edit attribute transformations. Previously, users had
an option to only use an existing attribute transformation in the
system. Now, a \'Select and modify transformation\' icon
(![](../../Resources/Images/Release%20Notes/9.3mp2/Select%20and%20modify.png))
is available within the Target Hierarchy Editor window that allows users
to create / edit attribute transformations. Clicking on the \'Select and
modify transformation\' icon
(![](../../Resources/Images/Release%20Notes/9.3mp2/Select%20and%20modify.png))
will open the Transformation dialog that allows users to add a new
attribute transformation
(![](../../Resources/Images/Data%20Onboarding/Create%20transformation%20icon.png))
or edit an existing transformation from the list.

For more information, see Creating Attribute Transformations Through
Target Hierarchy Editor window topic in the Automotive Reference Guide[
here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/Release%20Notes/9.3mp2/10.png)

Internal Note: RDCUST-3796Updated the Stack Panel in Web UI to be able
to list Mapper Configuration setup entities under a setup group

Previously, the creation of the Mapper Configuration setup entities in
Web UI was defaulted to be created directly under the setup group root.
This provided no option for the user to select any setup group to reside
the Mapper Configuration setup entity in. Now, a new **Parent** field is
available within the \'Create New Mapping Configuration\' dialog that
allows users to select an existing setup group to reside the Mapper
Configuration setup entity in.

![](../../Resources/Images/Release%20Notes/9.3mp2/3.png)

Also, the following changes are implemented to assist in creating the
Mapping:

![](../../Resources/Images/Release%20Notes/9.3mp2/4.png)

-   The \'Create new global mapping\' link has been renamed to \'Create
    new Mapping\'
-   The stack panel now shows all setup groups that are available below
    the root node

For more information, see Configuring Mapper Configuration Setup Entity
topic in the Automotive Reference Guide[ here]{.mcFormatColor
style="color: Blue;"}.

Internal Note: RDCUST-New Advanced tab in the Mapping Guide window to
handle attribute transformations on multivalued attributes

The Mapping Guide window now has the Advanced tab that allows users to
perform some advanced transformation functionalities when required. The
functionalities in this tab are mainly designed to handle multivalued
source attributes.

While the attribute transformation configured in the Mapping tab is
applied to the values of the source attribute, the attribute
transformation configured in the Advanced tab will be applied to the
intermittent string that gets created during the transition of data from
the source attribute to the target attribute.

For example, consider that data is being onboarded into a single-valued
target attribute (named \'Body Color\') from a multivalued source
attribute (Color) with an attribute transformation that changes the
value from the upper case to the lower case. The source attribute Color
has three values, RED, BLUE, and BLACK. If the attribute transformation
was set in the Transformation field of the Mapping tab, the target
attribute Body Color would be populated with a value \'black\' (because
the target attribute can accommodate only one value). However, before it
populates this value in the target attribute, it is to be known that in
the background, the system creates an intermittent string called
\'red\<multisep/\>blue\<multisep/\>black\' and extracts only the value
\'black\' out of this string to populate on the target attribute. Now,
with the introduction of the Advanced tab, it is possible to configure
and apply another attribute transformation on this string, and users can
transform and retrieve the desired data from this string to be populated
in the target attribute value. For example, if the On Save
Transformation field is populated with an attribute transformation that
replaces the \'\<multisep/\>\' substring into the hyphen \'-\', then the
final value in the target attribute will be populated as
\'red-blue-black\'.

Along with the functionality described above, the Advanced tab can also
be used for the following:

-   Ensure that no duplicate values are populated in the target
    attribute by selecting the Distinct checkbox
-   Determine if the value of a LOV or the ID of the LOV value is to be
    populated in the target attributes using the \'UseValueOnValueID\'
    checkbox

The features in this tab would be of no significance when the
transformations are to be applied on single valued source attributes. It
means that the attribute transformation configured in the Advanced tab
would behave normally as the attribute transformations being configured
and applied for the single valued attributes in the Mapping tab
(screenshot below). However, the significance of the attribute
transformations configured in this tab kick in when there is a
multivalued source attribute. This ststement violates with the

![](../../Resources/Images/Release%20Notes/9.3mp2/12.png)

Internal Note: RDCUST-3493Updated Target Hierarchy Editor window with an
option to rearrange the order of existing criteria

Clicking on the \'Add\' icon
(![](../../Resources/Images/Data%20Onboarding/165.png)) that is
available within the Target Hierarchy Editor window allowed users to set
criteria that could be used to define the name and ID of the newly
created objects. Previously, if there were multiple criteria created
within the Target Hierarchy Editor window, users did not have an option
to rearrange the order of the listed criteria. Now, a new three-dotted
icon
(![](../../Resources/Images/Data%20Onboarding/three%20dotted%20icon.png))
is made available to the right of each criteria to display the
rearranging dialog. The user can select the Top, Up, Down, or Bottom
button to rearrange the transformation accordingly.

![](../../Resources/Images/Release%20Notes/9.3mp2/5.png)

PRODOC note: NGK-459Updated the Mapper Configuration setup entity to be
able to duplicate an existing Mapping plugin

The Mapper Configuration setup entity is now able to duplicate an
existing Mapping plugin in the Web UI. The \'Duplicate mapping\' button
will be displayed in the toolbar while clicking on the checkbox
available on the left side of the listed Mapping plugins. Clicking on
the \'Duplicate mapping\' button will create a copy of the selected
Mapping plugin that resides in the same Mapper Configuration setup
entity. The newly copied Mapping plugin will be listed in the last order
of listings.

![](../../Resources/Images/Release%20Notes/9.3mp2/8.png)

PRODOC note: NGK-459Updated some Mapping plugins to be able to duplicate
existing Mapper rows

The Application Mapping plugin, Attribute Mapping plugin, Object to
Object Mapping plugin, and the Concatenator Mapping plugin now has the
option to duplicate existing Mapper rows. The \'Duplicate\' button will
be displayed in the toolbar after clicking on the checkbox that is
available on the left side of the listed Mapper rows. Clicking on the
\'Duplicate\' button will create a copy of the selected Mapper row(s)
that resides in the same Mapping plugin. The newly copied Mapper row
will be listed in the last order of listings.

![](../../Resources/Images/Release%20Notes/9.3mp2/9.png)

Internal Note: NGK-491Updated the Suggested Part Number table header
component with an option to determine if the ID or name or the attribute
value of the suggested part number to be displayed within the table cell

The Suggested Part Number table header component which can be configured
in the Application Manager Screen and the Application Editor Screen is
updated with an option that determines if the table cell has to display
the ID, Name, or with an attribute value of the suggested part number.
Previously, the table cell was defaulted to display only the ID of the
suggested part number. Now, two new parameters (Display ID and
Attribute) have been added in the Suggested Part Number Properties
designer window. These parameters determine if the ID or name or the
attribute value of the suggested part number to be displayed within the
table cell. the Display ID parameter defaults to the \'NODE\_ID\' value.
This allows the Id of the suggested part number to display within the
cell. Optionally, the \'NAME\_VALUE\' or \'ATTRIBUTE\_VALUE\' value can
be selected using the dropdown. While the \'NAME\_VALUE\' displays the
name of the suggested part number, the \'ATTRIBUTE\_VALUE\' allows the
values of the attribute selected within the \'Attribute\' parameter to
display within the cell. The Attribute parameter allows the user to
populate with an attribute that is valid for the suggested part number.
The Attribute parameter should only be populated when the
\'ATTRIBUTE\_VALUE\' value is selected in the Display ID parameter.
Otherwise, the defined attribute value will not be displayed in the
cell.

![](../../Resources/Images/Release%20Notes/9.3mp2/6.png)

Internal Note: RDCUST-3990Updated Easy Setup to mark certain PIES
attributes as Mandatory and updated certain PIES attribute formatting to
meet validation requirements

Previously, AutoCare Easy Setup did not create certain PIES attributes
as mandatory or with the correct format in order to meet the validation
requirements. Now, Easy Setup and certain parameters in the PIES
Exporter \'Select Format\' step have been updated in order to fix the
PIES attributes to meet the validation requirements that are provided in
the PIES spec. It is to be noted that the changes that have been done to
Easy Setup will only take effect when newly creating PIES attributes and
will not update existing attributes in the system. All existing
implementations will need to manually change for PIES attributes.

The following parameters in PIES Exporter Select Format step have been
updated:

-   Currency Code parameter is restricted to use the valid 3-digit
    Currency Code values from LOV ID = AC\_PIESCurrencyCode
-   Language Code parameter is restricted to use the valid 3-digit
    Currency Code values from LOV ID = AC\_PIESLanguageCode
-   Technical Contact parameter is changed to be an optional parameter.
    Previously it was required to enter a value in this parameter.
-   Contact Email parameter is changed to be an optional parameter.
    Previously it was required to enter a value in this parameter. Also,
    this parameter is now restricted to allow typing in the maximum of
    254 characters.

For **new implementations**, run step 1 of the **Automotive - AutoCare
Model** Easy Setup to create the PIES attributes.

For **existing implementation**, manually update the following
attributes in STEP workbench:

-   Update attribute ID = AC\_PIES\_PRCS\_PriceSheetNumber:
-   Change the Validation Base Type from Text to Regular Expression
-   Add the following to the Regular Expression field:
    \[0-9A-Za-z\\{\\}\\,\\%\\!\\\$\\?\'\"\\
    \\/\\.\\-\\\`\\\_\\\#\\&\\+\\=\\\<\\\>\\@\]{1,15}
-   Change the Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_PRCS\_PriceSheetName to have Maximum
    Length = 30
-   Update attribute ID = AC\_PIES\_PRCE\_SuperSPrcShtNbr:
-   Change the Validation Base Type from Text to Regular Expression
-   Add the following to the Regular Expression field:
    \[0-9A-Za-z\\{\\}\\,\\%\\!\\\$\\?\'\"\\
    \\/\\.\\-\\\`\\\_\\\#\\&\\+\\=\\\<\\\>\\@\]{1,15}
-   Update attribute ID = AC\_PIES\_MKTC\_Code to change the Mandatory
    parameter to Yes
-   Update attribute ID = AC\_PIES\_MKTC\_CodeReference to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_MKTC\_Type to change the Mandatory
    parameter to Yes
-   Update attribute ID = AC\_PIES\_MKTC\_RecordSequence to add a Mask
    of 99999
-   Update attribute ID = AC\_PIES\_ITEMItemLevelGTIN to remove the
    Maximum Value of 99999999999999, and to add a Mask of 99999999999999
-   Update attribute ID = AC\_PIES\_PRCE\_SuperSPrcShtNbr:
-   Change the Validation Base Type from Text to Regular Expression
-   Add the following to the Regular Expression field:
    \[0-9A-Za-z\\{\\}\\,\\%\\!\\\$\\?\'\"\\
    \\/\\.\\-\\\`\\\_\\\#\\&\\+\\=\\\<\\\>\\@\]{1,15}
-   Change the Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_ITEMBrandAAIAID to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_ITEMVMRSBrandID to add a Mask of
    AAAAA
-   Update attribute ID = AC\_PIES\_ITEMItemQuantitySize to change
    Validation Base Type from Number to Regular Expression, and to add
    the following to the Regular Expression field: \[0-9\\.\]{1,8}
-   Update attribute ID = AC\_PIES\_ITEMQuantityPerApplication to change
    Validation Base Type from Text to Numeric Text, and to add Mask of
    99999999
-   Update attribute ID = AC\_PIES\_ITEMMinimumOrderQuantity to add a
    Mask of 99999999
-   Update attribute ID = AC\_PIES\_ITEMAAIAProductCategoryCode to
    change Validation Base Type from Text to Number, and to add Mask of
    999999
-   Update attribute ID = AC\_PIES\_ITEMUNSPSC:
-   Remove the existing Minimum Value of 10000000
-   Remove the existing Maximum Value of 9999999999
-   Change the Validation Base Type from Number to Regular Expression
-   Add the following to the Regular Expression field:
    \[0-9\]{8}\|\[0-9\]{10}
-   Update attribute ID = AC\_PIES\_DESC\_TYPE to change the Mandatory
    parameter to Yes
-   Update attribute ID = AC\_PIES\_Description:
-   Change the Validation Base Type from Text to Regular Expression
-   Add the following to the Regular Expression field:
    \[0-9A-Za-z\\;\\{\\}\\,\\%\\!\\\$\\?\\\'\\\"\\
    \\/\\.\\-\\\`\\\_\\\#\\&\\+\\=\\\<\\\>\\@\\(\\)\\xA9\\u00AE\\u2122\]{1,2000}
-   Change the Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_PRCE\_PriceType to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_PRCE\_PriceTypeDescription to change
    Validation Base Type from Text to Numeric Text, and to add Maximum
    Length of 80
-   Update attribute ID = AC\_PIES\_PRCE\_Price to add Mask of 999990,
    and to change the Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_PRCE\_PriceUOM to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_PRCE\_PriceMultiplier to add a Mask
    of 999990.0000
-   Update attribute ID = AC\_PIES\_PACKPackageLevelGTIN to change
    Validation Base Type from Text to Number, and to add Mask of
    00000000000000
-   Update attribute ID = AC\_PIES\_PACKPackageBarCodeCharacters:
-   Change the Validation Base Type from Numeric Text to Regular
    Expression
-   Add the following to the Regular Expression field:
    \[0-9A-Za-z\\/\\.\\-\\\#\\&\\+\\=\\\<\\\>\\@\\\`\\\_\]{1,48}
-   Update attribute ID = AC\_PIES\_PACKPackageUOM to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_PACKQuantityOfEaches to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_PACKInnerQuantity to change
    Validation Base Type from Number to Regular Expression, and to add
    the following to the Regular Expression field: \[0-9\\.\]{1,8}
-   Update attribute ID = AC\_PIES\_PACKHeight to remove Maximum Value
    of 9999999999, and to add Mask of 9990.0000
-   Update attribute ID = AC\_PIES\_PACKWidth to remove Maximum Value of
    9999999999, and to add Mask of 9990.0000
-   Update attribute ID = AC\_PIES\_PACKLength to remove Maximum Value
    of 9999999999, and to add Mask of 9990.0000
-   Update attribute ID = AC\_PIES\_PACKShippingHeight to remove Maximum
    Value of 9999999999, and to add Mask of 9990.0000
-   Update attribute ID = AC\_PIES\_PACKShippingWidth to remove Maximum
    Value of 9999999999, and to add Mask of 9990.0000
-   Update attribute ID = AC\_PIES\_PACKShippingLength to remove Maximum
    Value of 9999999999, and to add Mask of 9990.0000
-   Update attribute ID = AC\_PIES\_PACKWeight to remove Maximum Value
    of 9999999999, and to add Mask of 9990.0000
-   Update attribute ID = AC\_PIES\_PACKWeightVariance to change
    Validation Base Type from Number to Regular Expression, and to add
    the following to the Regular Expression field: \[0-9\\.\]{1,8}
-   Update attribute ID = AC\_PIES\_PACKDimensionalWeight to change
    Validation Base Type from Number to Regular Expression, and to add
    the following to the Regular Expression field: \[0-9\\.\]{1,9}
-   Update attribute ID = AC\_PIES\_HAZMShippingScope to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_HAZMBulk to change the Mandatory
    parameter to Yes
-   Update attribute ID = AC\_PIES\_HAZMRegulatingCountry to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_HAZMTransportMethod to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_HAZMRegulated to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_HAZMUNNAIDCode to change Validation
    Base Type from Text to Numeric Text, and to add Mask of LL0000
-   Update attribute ID = AC\_PIES\_KITSComponentIDQualifier to change
    the Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_KITSQuantityInKit to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_KITSQuantityUOM to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_ASSTAssetID to have Maximum Length =
    34
-   Update attribute ID = AC\_PIES\_ASSTAssetType to change the
    Mandatory parameter to Yes
-   Update attribute ID = AC\_PIES\_ASSTFileSize to add a Mask of
    9999999999
-   Update attribute ID = AC\_PIES\_ASSTAssetHeight to add a Mask of
    999999
-   Update attribute ID = AC\_PIES\_ASSTAssetWidth to add a Mask of
    999999
-   Update attribute ID = AC\_PIES\_ASSTFilePath to have Maximum Length
    = 80
-   Update attribute ID = AC\_PIES\_ASSTDuration to add a Mask of 999
-   Update attribute ID = AC\_PIES\_ASSTTotalFrames to add a Mask of 999
-   Update attribute ID = AC\_PIES\_ASSTPlane to add a Mask of 999
-   Update attribute ID = AC\_PIES\_ASSTPlunge to add a Mask of 999999
-   Update attribute ID = AC\_PIES\_ASSTTotalPlanes to add a Mask of 999
-   Update attribute ID = AC\_PIES\_INTEBrandAAIAID to add Mask of AAAA
-   Update attribute ID = AC\_PIES\_INTESubBrandAAIAID to add Mask of
    AAAA
-   Update attribute ID = AC\_PIES\_ITEMVMRSBrandID to add Mask of AAAAA

Internal Note: RDCUST-3953, 3954Added support for recent AutoCare PAdb
format change

Starting with the February 2020 PAdb file, AutoCare updated the format
by removing the \"ValidValues\" and \"UoMList\" fields from the
PartAttributeAssignment table. And introduced four new tables:
ValidValues, ValidValueAssignment, MetaUOMCodeAssignment, and
MeasurementGroup. The PAdb Importer has been updated to handle these new
tables.

This will not change the existing PAdb data model or how PAdb attributes
are created and stored in STEP.

Internal Note: RDCUST-3989New parameter \'Select Business Condition\' in
all mapping plugins of Mapper Configuration setup entity

A new parameter called \'Select Business Condition\' is available in all
mapping plugins of the Mapper Configuration setup entity. This parameter
provides an option to configure a business condition on each mapping
plugin that defines to run the mapper plugin only on the object if the
condition is true.

![](../../Resources/Images/Release%20Notes/9.3mp2/11.png)

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

Internal Note: RDCUST-3493Corrected Advanced Part Number Suggestions
Node List component to display \'Node List\' as an option

Corrected Advanced Part Number Suggestions component to display \'Node
List\' as an option to select when the user clicks on the dropdown next
to the Node List parameter. Previously, clicking on the \'go to
component\' link without any selection from the drop down was navigating
to the Node List Properties designer screen. Now the dropdown list
consists of \'Node List\' as an option so that users can select the
\'Node List\' option and click on the \'go to component\' link to
navigate to the Node List Properties designer screen. Also, the Node
List parameter is now marked with a red asterisk indicating that the
parameter is mandatory.

![](../../Resources/Images/Release%20Notes/9.3mp2/1.png)

PRODOC note: NGK-335Corrected the Onboarding Mappings Details screen to
retain the state of the screen when the user clicks the Save button

Previously, when the user makes an edit in any Mapper row and saves the
changes by clicking the Save button, the Onboarding Mappings Details
screen was not holding the exact previous state of the screen and was
navigating to display the state of the screen where the Mapping plugins
were listed. Now, the Onboarding Mappings Details screen is updated to
remember the state of the screen so that users can save the changes made
to the Mapper row with the same state of the Onboarding Mappings Details
screen retained.

Internal Note: RDCUST-3909Corrected a bug in the display of \'Add Object
Type\' icon
(![](../../Resources/Images/Data%20Onboarding/Add%20description%20Icon.png))
in the Target Hierarchy Editor dialog

Previously, if the Target Hierarchy parameter that is available in a
Mapper Configuration setup entity had an existing hierarchy configured
and if the user clicked on the **Clear All** link in the Target
Hierarchy Editor dialog, it was forcing the user to click on the **Ok**
button first before being able to go back into the Target Hierarchy
Editor dialog to configure the root node and children objects. Now, this
issue is fixed so that if the Target Hierarchy parameter has an existing
hierarchy defined and the user clicks on the Clear All link in the
Target Hierarchy Editor dialog, as soon as the user enters and selects
the Root Node, the \'Add Object Type\' icon
(![](../../Resources/Images/Data%20Onboarding/Add%20description%20Icon.png))
is enabled so that the user can select a child node.

PRODOC Note: RDCUST-2787Updated ACES Application Qualifiers component in
Application Manager to have a fixed height and vertical scroll bar

In the Application Manager Screen, the vertical scroll bar of the \'ACES
Application Qualifiers\' value editor window has been updated to not
engulf the Delete icon if the data to be displayed is greater than the
window size.

PRODOC Note: RDCUST-3999Fixed some bugs exhibited in the Onboarding
Comparison Screen

The following updates are made in the Onboarding Comparison Screen:

-   Updated to not display the Mapper row checkboxes in Attribute stage
    of the Onboarding Comparison Screen if the current values in source
    attribute and the target attribute is empty
-   Previously, if the LOV validated attribute had an ID for each LOV
    values, then the Attribute stage of the Onboarding Comparison Screen
    displayed empty parentheses as the attribute value when the
    attribute actually had no value in it. Now, this issue is fixed so
    that the word \[Empty\] is displayed whenever there is no value
    populated in the attributes.
-   If there is any transformation applied on the source attribute in
    Attribute Mapping plugin, the \'\[Updated STEP\] values\' column in
    the Attribute stage of the Onboarding Comparison Screen will display
    a help text icon
    (![](../../Resources/Images/Release%20Notes/9.3mp2/help%20text%20icon.png)).
    Clicking on the icon displays the transformation name that is being
    applied on the source attribute. Previously, when the current values
    of the source attribute and the target attribute were empty, the
    help text icon
    (![](../../Resources/Images/Release%20Notes/9.3mp2/help%20text%20icon.png))
    was still being displayed on an empty value. This issue is corrected
    so that there will not be a help text icon displayed when there is
    no value populated in the source and the target attributes.
-   For the Application Mapping plugins displayed in the Application
    stage, if any mapper row is defined to retrieve the value from an
    attribute, and if that attribute has no value, then such mapper rows
    will not be displayed in the Application stage of the Onboarding
    Comparison Screen.

PRODOC Note: NGK-780Corrected an error that was displayed when the
system runs multiple onboarding processes simultaneously

Previously, when trying to run multiple onboarding processes
simultaneously, the onboarding process would fail with an internal
error. This has been fixed so that multiple onboarding processes
performed simultaneously will complete the onboarding without throwing
any error.

**Hotfix recipe compatible with STEP 9.3 MP2 + Automotive-7.0.25:**
[to:hotfix/394/issue-394063-HOTFIX-3901.spr]{.commandfont}

PRODOC Note: RDCUST-3352Corrected the \'Create New\' button to be always
displayed in the dropdown-list dialog when typing a manufacturer name in
the typeahead field of a Part Number Reference component

Previously, when typing a manufacturer name in the typeahead field of a
Part Number Reference component, in a case when the long list of part
numbers in the dropdown-list dialog was exceeding the screen size, the
\'Create New\' button was not visible and the user could not access it.
Now, this issue is corrected so that the \'Create New\' button is always
visible when there is a long suggestion list and the search field is at
the bottom of the screen.

PRODOC Note: RDCUST-3696Enabled to copy and paste Part Number in
Application Manager results table without having to double-click in the
cell

Previously, in the Application Manager search results table, a user was
not able to just select the cell for an existing Part Number to copy and
then select the cell for a missing application to paste in the Part
Number. In order to copy the existing Part Number, a user had to either
double-click in the Part Number cell in order to highlight and select
it, or had to select the cell and hit the \[Enter\] button in order to
select the Part Number. To paste what was copied, the user had to either
double-click in the desired cell, or hit \[Enter\], or multi-select the
Part Number cells and then hit \[Enter\] in order to paste the Part
Number. Now, this issue is fixed so that users will hereafter be able to
click once on the existing Part Number cell and press Ctrl + c to copy,
and then click once on the missing Part Number cell(s) and press Ctrl +
v to paste the Part Number.

PRODOC Note: NGK-690Enabled to simultaneously paste the copied value in
multiple cells of Application Manager results table

Previously, in the Application Manager search results table, a user was
not able to paste the copied value in multiple cells simultaneously.
Now, this issue is fixed so that users will hereafter be able to copy
from a cell, and then select multiple cells and press Ctrl + v to paste
the copied value.

This feature will be available with the STEP 10.0 baseline recipe. For
this to be working with STEP 9.3 MP3, apply the following hotfix recipe:

**Hotfix recipe compatible with STEP 9.3 MP3 + Automotive-7.0.26:**
[to:hotfix/397/issue-397815-HOTFIX-3978.spr]{.commandfont}

PRODOC Note: RDCUST-3582Corrected an Internal Server error that was
displayed on a specific case while creating a new Mapper Configuration
setup entity

Corrected an Internal Server Error that was displayed if more than 40
characters is entered in the \'From\' or \'To\' fields of the \'Create
New Mapping configuration\' dialog. This dialog is displayed during the
creation of a new Mapper Configuration setup entity in the Web UI. Now,
users can type any number of characters within the \'From\' and the
\'To\' fields.

![](../../Resources/Images/Release%20Notes/9.3mp2/7.png)

PRODOC note: RDCUST- 3910Updated the description texts for some
parameters that are available within the Mapping plugins

The description texts and icons for some parameters that are available
within the Mapping plugins have been updated in the Web UI to avoid
confusion for users. The changes are as follows:

-   The Add comment icon is changed from
    ![](../../Resources/Images/Release%20Notes/9.3mp2/Old%20add%20icon.png)
    to
    ![](../../Resources/Images/Release%20Notes/9.3mp2/New%20add%20icon.png)
-   The name of the dialog \'Edit Information\' is changed to \'Add
    Comment\' and the new dialog displays as shown below

![](../../Resources/Images/Release%20Notes/9.3mp2/15.png)

-   Once any description is added, the new Add comment icon changes to
    the Edit comment icon
    ![](../../Resources/Images/Release%20Notes/9.3mp2/commentadded.png).
    Previously, this icon was of a different appearance
    (![](../../Resources/Images/Release%20Notes/9.3mp2/14.png)).
-   Previously, when a comment existed for a Mapper row, clicking on the
    Edit icon
    (![](../../Resources/Images/Release%20Notes/9.3mp2/14.png)) to edit
    the information was opening a dialog named \'Edit Information\'.
    This dialog is renamed to display as \'Edit Comment\' with a
    \'Delete\' button to delete an existing comment.

![](../../Resources/Images/Release%20Notes/9.3mp2/Edit%20comment.png)

PRODOC note: RDCUST-3998Corrected the Validation Path Editor to be able
to retrieve the parent or child information after the
**reference\[type:\'\[id\]\'\]** element

A variety of information can be retrieved from the source/ target object
by using the combination of multiple elements that are available within
the Step Path Editor window for the Mapping Validation Path
functionality in \'Application Mapping\' and \'Object to Object
Mapping\' plugins. Previously, using the
**child\[objecttype:\'\[id\]\'\]** and **parent** elements after the
**reference\[type:\'\[id\]\'\]** element was failing to retrieve any
data despite its presence. This issue has been corrected so that it is
possible to retrieve the parent and child information after using the
**reference\[type:\'\[id\]\'\]** element.

PRODOC note: RDCUST-3998Corrected an error in the Application Mapping
plugin

Previously, when using an Application Mapping plugin, some special cases
ended up creating one application record referenced to multiple part
types instead of creating separate individual application records
referenced to each part type. This behavior of the Application Mapping
plugin is now corrected.

PRODOC note: RDCUST-3997Corrected an inappropriate flag displayed in the
Onboarding Comparison Screen

Previously, when the LOV validated attributes were compared between the
Source and the Target object, the attributes with the same values but
with a different order of listings were flagged as different in the
Onboarding Comparison Screen. Now, this issue is corrected, so that the
LOV validated attributes with the same values in the Source and the
Target object are considered as equal values and are not flagged as
unique.

PRODOC note: NGK-471 Corrected an Internal Server error that displayed
while sorting / filtering \'Application Approval Status\' table header
results in the Application Manager screen

Corrected an Internal Server error (*Error communicating with the STEP
server. Unexpected error. Please contact your system administrator*)
that was displayed when the user clicks on the \'Application Approval
Status\' table header for sorting / filtering the missing and existing
applications search results in the Application Manager screen. Now, the
user can sort / filter all the search results (existing, missing, and
existing and missing applications) via \'Application Approval Status\'
table header.

PRODOC note: RDCUST-4089Corrected the Enable and Disable button in the
Mapping plugins to clear the selection after the user clicks the Enable
/ Disable button

Previously, when the user enables or disables any Mapping plugins /
Mapper rows by selecting the checkbox and clicking the Enable / Disable
button, the selected Mapping plugins / Mapper rows checkboxes held the
state of being selected and the user had to deselect them by clicking
the checkboxes again. Now, the Enable and Disable button in the Mapping
plugins are updated to clear the state of selection so that it clears
the selection after the user clicks the Enable / Disable button.

PRODOC Note: SKF-970Corrected an Internal Server error that was
displayed while duplicating an application record in the Application
Manager Screen

Corrected an Internal Server error (*Error communicating with the STEP
server. Unexpected error. Please contact your system administrator*)
that was displayed when the user clicks on the \'Duplicate\' button for
duplicating the application records from the search results of the
Application Manager screen. Now, the user can duplicate the application
records via \'Duplicate\' button.

**Hotfix recipe compatible with STEP 9.1 MP6 + Automotive-7.0.18:**
[to:hotfix/395/issue-395095-HOTFIX-3918.spr]{.commandfont}

### AutoCare

Internal Note: RDCUST-3948Updated PIES Importer to handle EXPI codes
dynamically

In the previous release, the PIES Importer was updated to include all 55
EXPI codes, and the EXPI codes were correctly getting populated when the
PIES Item was created through PIES Importer. But the previous solution
had the PIES Importer handling the EXPI Codes with Enum class checking a
static list of EXPI codes. This solution required to keep changing the
Automotive code to update the list whenever the new EXPI values were
added by AutoCare. Now, as a permanent fix, the PIES EXPI codes are
handled dynamically by the PIES Importer so that whenever AutoCare
introduces new EXPI codes that the Automotive code does not need to be
updated.

Internal Note: RDCUST-4048Updated PIES importer and exporter to handle
UOMs for PAdb attributes with multivalues

Previously, if a multivalued PAdb attribute had any UOMs, PIES importer
was not populating the UOMs for the attribute. And PIES exporter did not
export the UOMs for the multivalues if it was populated. Now, the PIES
importer and exporter is updated to handle UOMs for PAdb attributes with
multivalues.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive-7.0.23:**
[to:hotfix/395/issue-395646-HOTFIX-3931.spr]{.commandfont}

PRODOC note: RDCUST-4044Fixed NPE generated in the outbound integration
endpoint related to the selection of PIES Exporter format

Previously, when the Output Templates that are available in the
Configuration tab of an outbound integration endpoint was to be
configured with PIES Exporter format, a null pointer error would be
generated. This has been corrected so an exception error is no longer
thrown and users are able to configure the PIES Exporter format in the
OIEP.

**Hotfix recipe compatible with STEP 9.3 MP2 + Automotive-7.0.25:**
[to:hotfix/396/issue-396870-HOTFIX-3961.spr]{.commandfont}

**Hotfix recipe compatible with STEP 9.3 MP2 + Automotive-7.0.25:**
[to:hotfix/396/issue-396493-HOTFIX-3953.spr]{.commandfont}

PRODOC note: RDCUST-3993Updated Easy Setup and ACES Importer to handle
ACES asset description field

\<AssetDescription\> tag is available within the AutoCare ACES file that
can be metadata for any asset on an application. Previously, importing
an ACES asset with the \<AssetDescription\> tag was creating the
application but the value that is stored in that field was not populated
anywhere for the ACES asset. Now, the ACES Importer has been updated to
handle the information available within the AssetDescription tag.

To handle the \<AssetDescription\> tag for the ACES import and export,
run step 1 of the **Automotive - AutoCare Model** Easy Setup to create
the Asset Description attribute (ID = AC\_ACESAssetDescription) and make
it valid for all ACES assets.

The ACES Importer has been updated to populate the
AC\_ACESAssetDescription attribute values.

The ACES Exporter has been updated to include data from the
AC\_ACESAssetDescription attribute in the exported file.

Previously, importing an ACES asset with the \<AssetDescription\> field
was generating the following error:

Error in this import 00\_Assets.xml setting completed with errors -
Error: The value for attribute \'AC\_PIES\_ASSTAssetDescriptionCode\' on
asset \'AC\_4c0e9c06db3f159c5ff85fc255b6c066\' isn\'t valid
(IllegalLOVValue: Line Art Diagram for LOV:
com.stibo.core.domain.impl.ListOfValuesImpl: AC\_PIES\_DESC\_TYPE\_LOV)

The application will still get created but the value that is stored in
that field isn\'t populated anywhere for the ACES asset.

Internal Note: RDCUST-2988 ACES reference type names no longer use the
ACES prefix

To improve users\' ability to find and view ACES reference types, the
default reference type names are no longer prefixed with \'ACES.\' When
Easy Setup actions are used for new environments, the reference types\'
names will no longer be prefixed with \'ACES.\'

**Existing Implementations**: Optionally, manually update the name of
the ACES reference types to no longer contain the \'ACES\' prefix.

Internal Note: RDCUST-4079 Fixed a synchronization problem between the
search boxes and Hierarchy Restriction dropdown in Application Manager
screen

Previously, there was some synchronization problem between the search
boxes and the Hierarchy Restriction dropdown in the Application Manager
screen that failed to filter the search results based on the criteria
defined in the Hierarchy Restriction dropdown. This synchronization
problem occurred only when there was any criteria defined in the Make /
Model search box and/or Part Type search box but there was no criteria
defined in the Year search box. This issue is now resolved so that the
criteria set in the Hierarchy Restriction dropdown will always be
considered irrespective of the presence / absence of the criteria set in
the Year search box.

**Hotfix recipe compatible with STEP 9.2 MP3 + Automotive-7.0.23:**
[to:hotfix/397/issue-397548-HOTFIX-3971.spr]{.commandfont}

PRODOC note: RDCUST- 3943Updated the context method of delta calculation
to compare the Pricing and Description information from the PIES file
against the data containers in the system

Previously, the \'Context\' method delta calculation used in the PIES
Importer did not compare the Pricing and Description data from the PIES
file against the existing respective data containers in the system. This
caused the same PIES Item to be imported again thereby causing PIES
imports to be slower than needed. Now, the \'Context\' method of delta
calculation is updated to compare the Pricing and Description
information from the PIES file against the respective data containers
existing in the system. If the existing PIES Item data in the system
matches the data in the PIES file being imported, then such PIES Item
will be excluded from being imported into the system.

PRODOC note:RDCUST4097Corrected the Conversion state in the AutoCare
PIES Importer

Corrected an error in Conversion state that would occur while importing
the AutoCare PIES file. Previously, the attribute information of
\'Expiration Date\' and \'Effective Date\' were being retrieved from
\<PriceSheet\> and \<Price\> segments of the importing PIES file, and
were populated in the data container of the PIES Item. Now, this issue
is corrected so that these attribute information will only be retrieved
from the \<Price\> segment.

### TecDoc

PRODOC note: NGK-784Corrected TAF import error

Corrected an error in Conversion state that would occur while importing
the TecDoc Supplier Data file. Previously, the absence of TAF table 702
and TAF table 701 in the loaded supplier file would cause a stacktrace
error to occur during conversion. These tables have now been removed
from validation, therefore the validation state no longer displays the
\'*Conversion failed: Missing file \'702.102\'. Please include this file
in the import even though it is empty*\' and \'*Conversion failed:
Missing file \'701.102\'. Please include this file in the import even
though it is empty*\' message.

PRODOC note: BOND NGK-650Corrected TAF import error

Corrected an error in Conversion state that would occur while importing
TecDoc Supplier Data file. Previously, creating
\'58\_ArticleSearchTreeAllocation-table400-Number-3.xml\' file in
Conversion state was not creating references to \'Generic Article\'
object in classification hierarchy.

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

Attribute Transformation in Mapper Configuration Setup Entity topic

The **Attribute Transformation in Mapper Configuration Setup Entity**
topic explains how to access and create / edit attribute transformations
in Mapper Configuration setup entity. The topic has been added to the
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

Search by Card Screen topic

The **Search by Card Screen** topic explains how to configure and use
the Search by Card screen. The topic has been added to the **Automotive
Reference Guide**[ here]{.mcFormatColor style="color: Blue;"}.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.26.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible with the following STEP 9.3 MP2 baseline
recipe:

[to:step/platform/step-9.3-mp3.spr]{.commandfont}

Once an Automotive add-on is installed to a base STEP system, the base
system cannot be upgraded without upgrading the Automotive add-on at the
same time. Additionally, when upgrading any base STEP system that has
any Automotive add-on installed, both install recipes must be prepared
at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
 
