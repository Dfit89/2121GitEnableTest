---
description: 'Automotive Solution: PMDM for Automotive 7.0.27 May 2020
  Patch Notes'
title: 'PMDM for Automotive 9.3 - 7.0.27 May 2020 Patch Notes'
---

PMDM for Automotive 9.3 - 7.0.27 Patch Notes {#pmdm-for-automotive-9.3---7.0.27-patch-notes .MPN}
============================================

Release Date: May 15, 2020 {#release-date-may-15-2020 style="text-align: center;"}
--------------------------

PRODOC Note: MORC says that NGK-767 and RDCUST-4092 are the NGK specific
issues and there was nothing to mention about it in the patch notes.

Announcement {#announcement .MPNDocumentation}
------------

Internal Note:Change in the PMDM for Automotive release naming
convention

With this maintenance patch, the PMDM for Automotive release sequence
numbering in online help has been changed. This helps to accurately
refer to the automotive release instead of previously being out of sync
with the core STEP releases. Instead of this release being named as
\'PMDM for Automotive 9.3 MP3,\' it will be named as \'PMDM for
Automotive 9.3 - 7.0.27.\'

New Features {#new-features .MPNNewFeatures}
------------

Internal Note: RDCUST- 4055Added support for import and export of PIES
7.2 file

Updated AutoCare Easy Setup, PIES Importer, and PIES Exporter to handle
import and export of PIES 7.2 version. The AutoCare PIES Exporter now
provides an option to select between PIES 6.5, 6.7, 7.0, 7.1, and 7.2
versions in the \'Version\' parameter within the \'Select Format\'
dialog as shown below. For more information, see the AutoCare PIES
Exporter topic of the Automotive Reference Guide[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../Resources/Images/Release%20Notes/9.3MP3/1.png)

Run step 1 of the Automotive - AutoCare Model Easy Setup to create the
**PCdb Version Date** attribute (ID= AC\_PCdbVersionDate) as mandatory.

Existing implementations will need to manually change the Mandatory
parameter for this attribute from \'No\' to \'Yes.\'

PIES Exporter has been updated to:

-   Make Version **7.2** available in the Select Format step
-   Not allow users to enter a value in the **Brand Owner AAIAID**
    parameter within the Select Format step if PIES Version 7.2 is
    selected since this element has been removed from the Header Segment
-   If PIES Version 7.2 is selected and the PCdb Version Date attribute
    does not have a value, then the export will fail with the error
    message \'*Convert failed with exception: PCDBVersionDate is
    required for PIES starting from version 7.2\'* that is written to
    the BGP.

PIES Importer has been updated to:

-   Check and warn against a mismatch in the PCdb Version Date during
    the Conversion state when comparing the date that is provided in the
    import file to the date that is stored in STEP.
-   If the imported file contains the \<BrandOwnerAAIAID\> element in
    version 7.2, then the import process will fail during the Validation
    state.
-   If the import file is missing the \<PCdbVersionDate\> element in
    version 7.2, then the import process will fail during the Validation
    state.

Internal Note: RDCUST- 4059Added support for import and export of ACES
4.1 file

Updated AutoCare Easy Setup, ACES Importer, and ACES Exporter to handle
import and export of ACES 4.1 version. The AutoCare ACES Exporter now
provides an option to select between ACES 3.0, 3.2, 4.0, and 4.1
versions in the \'Version\' parameter within the \'Select Format\'
dialog as shown below. For more information, see the AutoCare ACES
Exporter topic of the Automotive Reference Guide[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../Resources/Images/Release%20Notes/9.3MP3/3.png)

The following updates have been implemented:

-   Step 1 of the Automotive - AutoCare Model Easy Setup has been
    updated to create the AC\_ACESQuantity attribute with \'Integer\'
    Validation Base Type and a Minimum Value of \'0\' to ensure that a
    positive integer is entered.

Existing implementations will need to manually change the Validation
Base Type of the attribute from \'Number\' to \'Integer\' and add a
Minimum Value = 0.

-   The ACES Exporter has been updated to make Version 4.1 available in
    the Select Format step.
-   Both ACES Importer and Exporter has been updated to validate against
    the ACES 4.1 XSD.

PRODOC note: RDCUST- XXXXAdded option to include / exclude Digital
assets based on their Asset Type from the ACES Export

Previously, the \'AutoCare ACES Exporter\' format was hard-coded to
include all Digital assets irrespective of their Asset Type in the
exported file. The ACES Exporter has now been updated to include a new
parameter called \'Digital Assets\' to allow users to select the Digital
asset types to be included or excluded in the exported file. The
\'Digital Assets\' parameter is available within the \'Advanced\' tab of
the Export Manager. Clicking the ellipses button
(![](../../../../Resources/Images/Buttons/ellipsis.png){.img_intext})
that is available next to the parameter will display the Filter Digital
Asset Types dialog (as shown below). By default, all Asset Types will be
included in the exported file.

This parameter is available in all the versions of the PIES export.

Following are the features of this parameter:

-   The new parameter allows multi Asset Type selection. If more than
    one Asset Type needs to be excluded from the export, users can
    define more than one Asset Type in the parameter.
-   This new functionality also handles the values defined in the Asset
    Item Order (AC\_PIES\_ASSTAssetItemOrder) attribute that belongs to
    the reference types as the metadata attribute. The exported assets
    will be in the order defined within the Asset Item Order attribute.

![](../../Resources/Images/Release%20Notes/9.3MP3/2.png)

PRODOC note: RDCUST-4082Added option to filter PIES Market Copy based on
the Market Copy Types from the PIES Export

Previously, the \'AutoCare PIES Exporter\' format only had an option to
either include or exclude all the PIES Market Copies related to the PIES
Item in the PIES exported file. This prevented users from filtering
which Market Copy Type to be included / excluded in the exported file.
The existing \'Market Copy\' parameter within the PIES Exporter has been
updated with two additional fields, \'General Copy\' and \'Features and
Benefits,\' which allows users to select the Market Copy Type to be
excluded in the exported file. By default, selecting the Market Copy
parameter will select all Market Copy Types to be included in the
exported file. Users can exclude the PIES Market Copies belonging to a
particular Market Copy Type by deselecting the \'General Copy\' or
\'Features and Benefits\' checkbox as required. Deselecting both
\'General Copy\' and \'Features and Benefits\' checkbox with the
\'Market Copy\' parameter still selected *will not* include any PIES
Market Copies in the exported file.

This parameter is available in all the versions of the PIES export.

![](../../Resources/Images/Release%20Notes/9.3MP3/4.png)

PRODOC note: NGK-701Added option to filter and sequence application
notes based on the Note Types from the ACES Export

Previously, the \'AutoCare ACES Exporter\' format was hard-coded to
include all application notes that are referenced by the application
records in the ACES exported file. It was not possible to filter out
certain notes from the export. To handle this requirement, a new
metadata attribute called Note Type is made available in the system that
allows users to define the Note Type for an application note and then be
able to filter the application notes based on those Note Types. This
solution allows users to filter out the application notes belonging to
the particular Note Type to be excluded in the exported file.

To handle filtering of application notes based on their Note Type:

1.  Run step 1 of the Automotive - AutoCare Model Easy Setup to:

-   Create a new Description attribute called AC\_ACESNoteType and make
    it valid for ACES Application To Application Note reference
-   Create a new LOV called AC\_NoteType and make it referenced for
    AC\_ACESNoteType attribute

Users will need to manually add the values to this LOV. Users will then
need to populate these values on the application in the
AC\_ACESApplicationToApplicationNote Product Reference to define which
Type the Note should be. These values will then be used in the ACES
exporter **Note types filter** parameter to indicate which Note
reference should get included in the exported file.

2.  The ACES Exporter has been updated with a new parameter called
    \'Note types filter\' that is available within the Advanced tab of
    the ACES Export Manager. Selecting this parameter will ensure that
    all the application notes belonging to the ACES application will be
    included in the exported ACES file. Clicking the ellipses button
    (![](../../../../Resources/Images/Buttons/ellipsis.png){.img_intext})
    that is available next to the parameter will display the \'Filter
    note types\' dialog (as shown below). By default, all Note Types
    will be included in the exported file, however, adding any one note
    type from the Excluded to the Included column will overwrite the
    default settings and continues only to include those Note Types that
    are listed in the Include column.

This parameter is available in all the versions of the ACES export.

Following are the features of this parameter:

-   The new parameter allows multi Note Type selection. If more than one
    Note Type needs to be included / excluded in the export, users can
    define more than one Note Type in the parameter.
-   This new functionality also handles the values defined in the
    Display Sequence (DisplaySequence) metadata attribute that is valid
    for ACES Application To Application Note reference. The exported
    application notes will be placed in the order defined within the
    Display Sequence attribute. However, if users need to rearrange the
    sequence of application notes to have different sequences for
    different receivers, then the users can utilize the up
    (![](../../Resources/Images/Release%20Notes/9.3MP3/6.png)) and down
    (![](../../Resources/Images/Release%20Notes/9.3MP3/7.png)) arrow
    buttons that are available within the \'Filter note types\' dialog
    to rearrange the sequence.

![](../../Resources/Images/Release%20Notes/9.3MP3/5.png)

3.  For existing implementations, update the \'Value editor\' window of
    the **Application Comment** table header component configured in the
    AutoCare Application Manager Screen to include following two
    additional Headers (as shown in the screenshot below):

-   Reference Metadata Value Header configured to display the
    \'DisplaySequence\' attribute
-   Reference Metadata Value Header configured to display the
    \'AC\_ACESNoteType\' attribute

![](../../Resources/Images/Release%20Notes/9.3MP3/8.png)

PRODOC note: RDCUST-4064, 4065. 4066Added a feature to retrieve the
error file that is generated in the ACES Conversion

The \[ACESToStepXMLConvertService\] conversion service has been updated
to generate an error report if the ACES imported file encounters
validation errors. As the conversion service runs a background process
(BGP), a corresponding BGP folder is created on the application server
in the /workarea/background-processarea/ACEStoStepXMLConvertService
directory. The BGP folder contains an output file of the conversion
process. Now, if an ACES file completes conversion with errors, the
conversion service also writes an additional error.xlsx file in the BGP
folder. In the screenshot below, **error.xlsx** is the error report file
that is placed in the BGP\_41839 folder.

![](../../Resources/Images/Release%20Notes/9.3MP3/11.png)

The Conversion state within the AutoCare ACES import workflow now
includes a new \'Error file attachment ID\' parameter that allows a user
to define a value to identify the error file. The value that is entered
in this parameter specifies the filename of the error report in the
conversion process. Meaning, that the error report Excel file will
contain the name that is specified in the \'Error file attachment ID\'
parameter.

![](../../Resources/Images/Release%20Notes/9.3MP3/10.png)

The error file can also be accessed in the AutoCare ACES Import
Controller screen of the Web UI that is used to display the details of
the ACES file import. Users need to add the new **Importflow
Attachment** table header component to the AutoCare ACES Import
Controller screen to access this file in the Web UI.

![](../../Resources/Images/Release%20Notes/9.3MP3/9.png)

Within the Attachment ID parameter of the Importflow Attachment
Properties designer screen, the user has to enter the same value that is
entered in the \'Error file attachment ID\' parameter in the Conversion
state to identify this file.

![](../../Resources/Images/Release%20Notes/9.3MP3/12.png)

PRODOC note: XXXXXUpdated ACES Importer to store the Brand information
(postponed to next release)

Previously, the Brand information present in the ACES file was not
stored in ACES Importer and the importer. Now, the
\[ACESToStepXMLConvertService\] conversion service of the ACES Importer
is updated so that the Brand information will get marked in the defined
attribute. A new parameter \'Importing Brands attribute\' is avaialable
within the \[ACESToStepXMLConvertService\] conversion service that
allows users to configure an attribute that stores information on Brands
of the ACES file

Note: This requires that the xxxxx attribute has been created, made
valid on the XXXX and XXX objects, and indicated for use in the correct
workflow state.

PRODOC note: RDCUST-4066Updated ACES conversion process to be able to
check on application records with invalid vehicle configurations and
invalid part type conditions

The Conversion state within the AutoCare ACES import workflow now
includes a new parameter called \'Validate application\' that will write
errors to a file for application records with invalid configurations.
The validation process of the \'Validate application\' parameter works
similar to the \'Validate Application on Import\' business condition
with the only difference that it runs a check for the applications with
invalid configurations during the Conversion state on the xml ACES
object rather than in the Import state on a product node application.
The benefit of this is that users will be able to detect invalid
applications prior to having to import the file.

Since the validation is done in the ACES converter, the Conversion
process will be slower if the \'Validate application\' parameter is
selected.

Some examples of applications that will error are: Missing Part Type;
missing Vehicle; vehicle configurations such as Sub Model, Engine Base,
Drive Type, etc. that are not valid for the vehicle.

With the \'Validate application\' parameter checked, when an application
record is found that does not meet the condition, an error is written to
the execution report of the conversion process and the record will
continue to the pass conversion process. The error contains the
application ID from the ACES file, as well as IDs of the objects that it
failed on. If the \'Validate application\' parameter is not checked,
importing ACES applications that have invalid configurations will pass
the conversion process but without writing an error in the execution
report.

![](../../Resources/Images/Release%20Notes/9.3MP3/13.png)

PRODOC note: RDCUST-4066Updated ACES conversion process to be able to
treat application records with application notes as errors

The Conversion state within the AutoCare ACES import workflow now
includes a new parameter called \'Treat notes as errors\' that will
write errors to a file for application records with Notes in the ACES
import file.

With the \'Treat notes as errors\' parameter checked, when an
application record with application notes is found, an error stating
\'*Application has note(s), that is not allowed on application
id=\<ID\>, partNumber=\<Part Number\>*\' is written to the execution
report of the conversion process, and the record will continue to the
pass conversion process. The error contains the application ID from the
ACES file, as well as IDs of the part number belonging to the
application. If the \'Treat notes as errors\' parameter is not checked,
importing ACES applications with application notes will pass the
conversion process but without writing an error in the execution report.

![](../../Resources/Images/Release%20Notes/9.3MP3/14.png)

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: RDCUST-4087Corrected the Attribute Mapping plugin to
rightly handle context-dependent multivalued attribute

Previously, onboarding data from a context-dependent multivalued Source
attribute to the Target attribute was not being performed and exhibited
a Nullpoint Exception error. This issue has been resolved so that now
there is a possibility to onboard data from a context-dependent
multivalued Source attribute to a Target attribute.

PRODOC note: NGK-391Corrected the Application Condition Header - Group
table header component to rightly filter out the irrelevant condition
attributes

Previously, condition attributes that had Vehicle Types defined but were
not marked \'true\' in the \'Display Condition\' metadata were not
getting filtered out correctly and was still being displayed in the
\'Value editor\' dialog within the \'Application Condition Header -
Group\' table header component (that is configured in the Application
Manager Screen). This bug has been resolved and irrelevant condition
attributes are now filtered out correctly in the \'Value editor\' dialog
of \'Application Condition Header - Group\' table header component based
on the Vehicle Types.

### AutoCare {#autocare conditions="Primary.Under Construction"}

PRODOC note: RDCUST-4063Corrected a Validation Error related to the
Approved For parameter in ACES Exporter

Previously, selecting the options available in the Approved For
parameter for the ACES 3.0 version in the ACES Exporter exhibited a
validation error that displayed \'*Validation Error: at line 10, column
38: cvc-complex-type.2.3: Element \'ApprovedFor\' cannot have character
\[children\], because the type\'s content type is element-only. at line
10, column 38: cvc-complex-type.2.4.b: The content of element
\'ApprovedFor\' is not complete. One of \'{Country}\' is expected.*\'
The problem exhibited was that the output file which is ACES 3.0 was
validated with the 3.2 schema. Now, this issue has been corrected so
that the user can select the options available in the Approved For
parameter for the ACES 3.0 version.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.27.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible with the following STEP 9.3 MP3 and STEP
9.3 MP4 baseline recipes:

[to:step/platform/step-9.3-mp3.spr]{.commandfont}

[to:step/platform/step-9.3-mp4.spr]{.commandfont}

Once an Automotive add-on is installed to a base STEP system, the base
system cannot be upgraded without upgrading the Automotive add-on at the
same time. Additionally, when upgrading any base STEP system that has
any Automotive add-on installed, both install recipes must be prepared
at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
 
