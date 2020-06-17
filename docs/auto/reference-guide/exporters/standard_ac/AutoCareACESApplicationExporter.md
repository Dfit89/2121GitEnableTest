---
description: 'Automotive Solution: Describes the AutoCare ACES
  Application Exporter.'
title: '\[%=Heading.AnyLevel%\]'
---

AutoCare ACES Application Exporter
==================================

The AutoCare ACES Application Exporter is used to export application
data in ACES format. ACES versions 3.0, 3.2 and 4.0 are supported. The
exporter requires that applications be stored in the standard AutoCare
data model.

PRODOC note: BOND RDCUST-3928, 3897 From Automotive 9.3MP1 there are two
kinds of Application records. Vehicle application record and the
Equipment application record. The Base vehicle application record are
linked into the Base vehicle that has Make - Model-Base Vehicle -
Vehicle as the hierarchy. And the Equipment application record is linked
to the Equipment Base that has Vehicle Type - Vehicle Model - Equipment
Base - Equipment as the hierarchy. So, the Make - Model-Base Vehicle -
Vehicle in hierarchy is symmetrical to Vehicle Type - Vehicle Model -
Equipment Base - Equipment (hierarchy. Change this whole topic
accordingly\.....

Prerequisites

The ACES exporter runs using standard Export Manager functionality. Only
information specific to the ACES exporter is covered within this guide.
Additional information on general Export Manager functionality is
covered in the **Export Manager** topic within the **Data Exchange**
section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

Using ACES Application Exporter

Using ACES Application Exporter {#using-aces-application-exporter conditions="Primary.Web"}
-------------------------------

### Step 1. Start ACES Application Exporter

The AutoCare ACES Application Exporter can be started via standard
Export Manager methods, e.g., File \> Export \> Data, or by selecting an
object in Tree, right-clicking, and selecting \'Export Data Below\' from
the menu. In the case of the right-click option, an object in the
AutoCare PIES Product hierarchy or a yellow classification where the
applications are linked to must be selected.

Click the **Add Objects** link to add one or more blue folders in the
AutoCare PIES Products hierarchy, or one or more classification folders.

All ACES Application objects beneath the selection(s) (either as child
objects or via links) will result in the export file.

### Step 3. Select Format

Select **AutoCare ACES Application Exporter** format to expose options
specific to the ACES exporter. The version will default to 4.0, but any
one of the available ACES export versions can be selected from the
dropdown list.

![](../../../Resources/Images/Exporters/922.png)

Use of the 'Approved For' parameter requires manual setup, which is
covered in the **10. Add Country Codes to Approved for LOV (ACES Export
Only)** topic within the **Automotive Quick Start Guide**[
here]{.mcFormatColor style="color: Blue;"}.

Required Parameters

This section describes the required parameters that display in bold and
require manual data population. The Next button will not enable until
the required parameters are populated with at least one character. By
default, the required parameter values are blank unless an existing
configuration is selected.

-   **Company**: Allows a company to be specified for the exported data
    within the free text field. The value (along with the \'Document
    Title\' value) is used to create the ZIP file name and will display
    within the ACES export between the \<Company\> tags. For example, if
    the value 'ACME' is provided, then the exported ACES file will
    display as shown below.

``` {space="preserve"}
<Company>ACME</Company>
```

-   **Sender Name**: Allows a sender name to be specified for the
    exported data within the free text field. The value will display
    within the ACES export between the \<SenderName\> tags. For example,
    if the value 'Grace' is provided, then the exported ACES file will
    display as shown below.

``` {space="preserve"}
<SenderName>Grace</SenderName>
```

-   **Sender Phone**: Allows a sender phone to be specified for the
    exported data. The value will display within the ACES export between
    the \<SenderPhone\> tags. For example, if the value '770-123-1234'
    is provided, then the exported ACES file will display as shown
    below.

``` {space="preserve"}
<SenderPhone>7701231234</SenderPhone>
```

-   **Document Title**: Allows a document title to be specified within
    the free text field. The value (along with the \'Company\' value) is
    used to create the ZIP file name and will display within the ACES
    export between the \<DocumentTitle\> tags. For example, if the
    parameter is populated with the value 'EXPORT\_V2,' then the
    exported ACES file will display as shown below.

``` {space="preserve"}
<DocumentTitle>EXPORT_V2</DocumentTitle>
```

When an ACES export is run, the ZIP file name is created using the
following template: \'Company Value (defined in step 3 of the exporter
wizard)\_Document Title Value (defined in step 3 of exporter
wizard)\_current date\_FULL.xml.\'

In the screenshot below, the AutoCare ACES Application Exporter is
displayed with the \'Company\' and \'Document Title\' parameters
outlined in red. The values configured for these required parameters
help to determine the ZIP file name displayed within a BGP Details
screen. Using the example below, the ZIP file name would display as
\'ACME\_BrandAAIAID in Part\_2018-10-31\_FULL.zip\'

![](../../../Resources/Images/MPNotes/ACESExporter.png)

Optional Parameters

Optional parameters are describe below. By default, the parameter values
are blank unless an existing configuration is selected.

-   **Version**: By default, the \'4.0\' version is selected, but any
    one of the available ACES export versions can be selected from the
    dropdown list. Within the ACES export, the version displays before
    the Header column (as shown below).

``` {space="preserve"}
<?xml version="1.0" encoding="UTF-8" standalone="true"?>
```

``` {space="preserve"}
<ACES version="4.0">
```

-   **Sender Phone Ext**: Allows a sender phone extension to be
    specified within the free text field. The value will display within
    the ACES export between the \<SenderPhoneExt\> tags. For example, if
    the value '6789' is provided, then the exported ACES file will
    display as shown below.

``` {space="preserve"}
<SenderPhoneExt>6789</SenderPhoneExt>
```

-   **Mfr Code**: Allows a manufacturer code to be specified within the
    free text field. The value will display within the ACES export
    between the \<MfrCode\> tags. For example, if the value 'TNT' is
    provided, then the exported ACES file will display as shown below.

``` {space="preserve"}
<MfrCode>TNT</MfrCode>
```

-   **Brand AAIAID**: Allows a Brand or Sub Brand AAIAID (Automotive
    Aftermarket Industry Association ID) object to be selected. , and
    the 'Select Brand AAIAID' dialog will display, as shown in the image
    below.

![](../../../Resources/Images/Exporters/Standard_ACES/E4.png)

Select the desired Brand, and save and close the dialog. The STEP Name
of the selected Brand will display followed by the Brand AAIAID in
parentheses. However, only the four character Brand AAIAID will display
between the \<BrandAAIAID\> tag in the export.

For Example, if the Brand object '034MOTORSPORT (ID=GWWQ)' is selected,
then the exported ACES file will display as shown below.

``` {space="preserve"}
<BrandAAIAID>GWWQ</BrandAAIAID>
```

The \<BrandAAIAID\> tag embedded within the \<Part\> tag is not
populated from this value. The embedded \<BrandAAIAID\> tag is populated
directly from the application record itself (i.e., if the application
record had the parameter populated on import, it is populated with the
same value on export).

-   **Doc Form Number**: Allows a document or catalog number to be
    specified within the free text field. The value will display within
    the ACES export between the \<DocFormNumber\> tags. For example, if
    the value 'XX98765' is provided, then the exported ACES file will
    display as shown below.

``` {space="preserve"}
<DocFormNumber>XX98765</DocFormNumber>
```

-   **Effective Date**: Allows an effective date to be specified using
    the YYYY-MM-DD date format. Clicking within the field displays the
    Date Picker dialog (as shown below), which ensures the correct
    format is used when editing the value.

![](../../../Resources/Images/Exporters/Standard_ACES/E5.png)

The Date Picker dialog defaults to the current date, regardless of what
is displayed in the Effective Date field prior to selection. Any past or
future date can be selected, and changes made are displayed in the
Effective Date field and populated in the export as YYYY-MM-DD. Within
the ACES export, the date value will display between the
\<EffectiveDate\> tags. For example, if the value '2018-06-18' is
provided, then the exported ACES file will display as shown below.

``` {space="preserve"}
<EffectiveDate>2018-06-18</EffectiveDate>
```

When a saved configuration is used and the value is blank, then the
effective date will be generated from the export\'s scheduled run date.

-   **Approved For**: Allows for one or more country codes to be
    specified. The display of available two character country code
    values is controlled by an LOV that is created as part of the Easy
    Setup actions. For more information, see the **10. Add Country Codes
    to Approved for LOV (ACES Export Only)** topic within the
    **Automotive Quick Start Guide**[ here]{.mcFormatColor
    style="color: Blue;"}. Optionally, select one or more checkboxes and
    the selected value(s) will display within the ACES export between
    the \<ApprovedFor\> tags. However, the ApprovedFor tag in the Header
    segment varies based on format. Assuming values of \'US\' and \'DK\'
    are included, an exported ACES file will display for as shown below.

```{=html}
<!-- -->
```
-   Version 3.0:

``` {.PreIndent}
<ApprovedFor>DK,US</ApprovedFor>
```

-   Version 3.2:

``` {.PreIndent}
<ApprovedFor>
```

``` {.PreIndent}
<Country>DK</Country>
```

``` {.PreIndent}
<Country>US</Country>
```

``` {.PreIndent space="preserve"}
</ApprovedFor>
```

-   Version 4.0:

``` {.PreIndent}
<ApprovedFor>
```

``` {.PreIndent}
<Country>DK</Country>
```

``` {.PreIndent}
<Country>US</Country>
```

``` {.PreIndent space="preserve"}
</ApprovedFor>
```

-   **Mapper Company**: Allows for a company responsible for mapping the
    data to ACES to be specified within the free text field. The value
    will display within the ACES export between the \<MapperCompany\>
    tags. For example, if the value 'NYKA' is provided, then the
    exported ACES file will display as shown below.

``` {space="preserve"}
<MapperCompany>NYKA</MapperCompany>
```

-   **Mapper Contact**: Allows for a person to contact at the mapping
    company to be specified within the free text field. The value will
    display within the ACES export between the \<MapperContact\> tags.
    For example, if the value 'MAC' is provided, then the exported ACES
    file will display as shown below.

``` {space="preserve"}
<MapperContact>MAC</MapperContact>
```

-   **Mapper Phone**: Allows for the mapper contact\'s phone information
    to be specified within the free text field. The value will display
    within the ACES export between the \<MapperPhone\> tags. For
    example, if the value '7801323312' is provided, then the exported
    ACES file will display as shown below.

``` {space="preserve"}
<MapperPhone>7801323312</MapperPhone>
```

-   **Mapper Phone Ext**: Allows for the mapper contact\'s phone
    extension to be specified within the free text field. The value will
    display within the ACES export between the \<MapperPhoneExt\> tags.
    For example, if the value '2222' is provided, then the exported ACES
    file will display as shown below.

``` {space="preserve"}
<MapperPhoneExt>2222</MapperPhoneExt>
```

-   **Mapper Email**: Allows for the mapper contact\'s email information
    to be specified within the free text field. The value will display
    within the ACES export between the \<MapperEmail\> tags. For
    example, if the value 'abcd\@acme.com' is provided, then the
    exported ACES file will display as shown below.

``` {space="preserve"}
<MapperEmail>abcd@acme.com</MapperEmail>
```

-   **Deliver a file if there are validation errors?**: By default,
    \'no\' is selected, and the export file will not be delivered when
    validation errors occur. When 'yes' is selected, the export file
    will be delivered even though validation errors occur.

### Step 5. Advanced

When an ACES application format is selected in the previous dialog, the
Advanced step within the Export Manager includes several parameters
unique to the ACES exporter (outlined in red below). Only the parameters
specific to the ACES format are described within this topic. For more
information on the general parameters within the Advanced Export Manager
dialog, see the **Export Manager - Advanced** topic within **STEP Online
Help**[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Exporters/Standard_ACES/E12.png)

-   **Part Number Source:** [The following options are available for
    this parameter: ID, Name, Attribute
    Value.]{style="font-weight: normal;"}
-   **Attribute Value:** By default, the \'Attribute Value\' radio
    button is selected and the \'Part Number
    (AC\_PIES\_ITEMPartNumber)\' value from the parental PIES part is
    inserted between the \<Part\> tags of the export. For example, when
    the application '034-VC21499Disc Brake Pad Set2011 Acura TSX' (a
    child application of \'034-VC21499\') is selected for export, then
    the parental part\'s Part Number attribute value displays within the
    export. The application and its parent are displayed in the
    workbench screenshot below.

![](../../../Resources/Images/Exporters/Standard_ACES/E9.png)

When the \'Include BrandAAIAID in Part\' parameter is disabled, then the
ACES export will display as shown below.

``` {.PreIndent}
<Part>034-VC21499</Part>
```

Whereas, if the \'Include BrandAAIAID in Part\' parameter is enabled,
then the ACES export will display as shown below.

``` {.PreIndent}
<Part BrandAAIAID="GWWQ">034-VC21499</Part>
```

-   **ID:** When enabled, the STEP ID of the parental PIES part is
    inserted between the \<Part\> tags of the export. For example, when
    the application '034-VC21499Disc Brake Pad Set2011 Acura TSX' (a
    child application of \'034-VC21499\') is selected for export, then
    the parental part\'s STEP ID (\'AC\_PIESItem\_GWWQ\_034-VC21499\')
    displays within the export. The application and its parent are
    displayed in the workbench screenshot below.

![](../../../Resources/Images/Exporters/Standard_ACES/E7.png)

When the \'Include BrandAAIAID in Part\' parameter is disabled, then the
ACES export will display as shown below.

``` {.PreIndent space="preserve"}
<Part>AC_PIESItem_GWWQ_034-VC21499</Part>
```

Whereas, if the \'Include BrandAAIAID in Part\' parameter is enabled,
then the ACES export will display as shown below.

``` {.PreIndent space="preserve"}
<Part BrandAAIAID="GWWQ">AC_PIESItem_GWWQ_034-VC21499</Part>
```

-   **Name:** When enabled, the STEP Name of the parental PIES part is
    inserted between the \<Part\> tags of the export. For example, when
    the application '034-VC21499Disc Brake Pad Set2011 Acura TSX' (a
    child application of '034-VC21499') is selected for export, then the
    parental part\'s STEP Name (\'034-VC21499\') displays within the
    export. The application and its parent are displayed in the
    workbench screenshot below.

![](../../../Resources/Images/Exporters/Standard_ACES/E8.png)

When the \'Include BrandAAIAID in Part\' parameter is disabled, then the
ACES export will display as shown below.

``` {.PreIndent space="preserve"}
<Part>034-VC21499</Part>
```

Whereas, if the \'Include BrandAAIAID in Part\' parameter is enabled,
then the ACES export will display as shown below.

``` {.PreIndent space="preserve"}
<Part BrandAAIAID="GWWQ">034-VC21499</Part>
```

-   **Use Attribute for Mfr Label:** Allows for any attribute value from
    the parental PIES Item or the ACES application object to be
    populated between the \<MfrLabel\> tag of the application record. If
    the option is not selected and the application has a value for the
    \'ACES Mfr Label\' attribute, then that attribute value will get
    exported as the value in the \<MfrLabel\> tag. For example, when the
    application '034-VC21499Disc Brake Pad Set2011 Acura TSX' (a child
    application of '034-VC21499') is selected for export, and the
    parameter is populated with the \'ACES Mfr Body Code\' attribute,
    then the ACES export file will display the \'ACES Mfr Body Code\'
    attribute value (0SF08E) between the \<MfrLabel\> tags. The
    application\'s parent attribute \'ACES Mfr Body Code\' is displayed
    in the workbench screenshot below with the \'0SF08E\' value.

![](../../../Resources/Images/Exporters/Standard_ACES/E10.png)

The automotive solution does not support the MfrLabel value coming from
both the Part and the application. The MfrLabel value can only be
retrieved from the Part or the application.

-   If selected, and an attribute is specified from the Part to retrieve
    the value for the MfrLabel, then the MfrLabel value from the Part
    will be included for all applications belonging to that Part.
-   If selected, and an attribute is specified from the Application to
    retrieve the value for the MfrLabel, then only the applications that
    have a MfrLabel attribute value will have the \<MfrLabel\> tag
    included for those specific applications in the exported file.
-   If not selected, and an application has a value in the
    AC\_ACESMfrLabel attribute, then that value will be exported only
    for the application that has the AC\_ACESMfrLabel attribute value.

```{=html}
<!-- -->
```
-   **Include BrandAAIAID in Part:** By default this parameter is
    deselected so that the BrandAAIAID is excluded from the part number
    tag. When selected, the Brand AAIAID is inserted between the
    \<Part\> tag of the export. Examples are included within the above
    Part Number Source parameter details.
-   **Export in Make/Year format:** By default this parameter is
    deselected so that the exported file will include the application
    record with the linked Base Vehicle / Equipment Base object
    information (as shown in the image on the left below). If the
    parameter is selected, the exported file will include the
    application record with the information about related Make, Model
    and Year (or Manufacturer, Equipment Model and Vehicle Type for
    Equipment application records) in the exported file (as shown in the
    image on the right below).

![](../../../Resources/Images/Release%20Notes/9.3MP1/11.png)

General Export Manager functionalities like Tag conversion, Locale
Conversion, Resolve Inline References, Calculated Attributes, Workspace,
and Context are covered in the **Export Manager - Advanced** topic
within the **Data Exchange** section of **STEP Online Help**[
here]{.mcFormatColor style="color: Blue;"}.

### Example

Below is an example of how the exporter could be configured and the
expected ACES xml file results for one application.

![](../../../Resources/Images/Exporters/Standard_ACES/99.png)

![](../../../Resources/Images/Exporters/Standard_ACES/991.png)

``` {space="preserve"}
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
```

    <ACES version="3.2">

    <Header>

``` {.PreIndent space="preserve"}
<Company>ACME</Company>
```

``` {.PreIndent space="preserve"}
<SenderName>Grace</SenderName>
```

``` {.PreIndent}
<SenderPhone>770-123-1234</SenderPhone>
```

``` {.PreIndent}
<SenderPhoneExt>6789</SenderPhoneExt>
```

``` {.PreIndent space="preserve"}
<TransferDate>2018-11-02</TransferDate>
```

``` {.PreIndent space="preserve"}
<MfrCode>TNT</MfrCode>
```

``` {.PreIndent}
<BrandAAIAID>GWWQ</BrandAAIAID>
```

``` {.PreIndent}
<DocumentTitle>EXPORT_V2</DocumentTitle>
```

``` {.PreIndent}
<DocFormNumber>XX98765</DocFormNumber>
```

``` {.PreIndent space="preserve"}
<EffectiveDate>2018-11-02</EffectiveDate>
```

``` {.PreIndent}
<ApprovedFor>
```

``` {.PreIndent}
<Country>DK</Country>
```

``` {.PreIndent}
<Country>US</Country>
```

``` {.PreIndent}
</ApprovedFor>
```

``` {.PreIndent}
<SubmissionType>FULL</SubmissionType>
```

``` {.PreIndent}
<MapperCompany>NYKA</MapperCompany>
```

``` {.PreIndent space="preserve"}
<MapperContact>MAC</MapperContact>
```

``` {.PreIndent}
<MapperPhone>7801323312</MapperPhone>
```

``` {.PreIndent}
<MapperPhoneExt>2222</MapperPhoneExt>
```

``` {.PreIndent space="preserve"}
<MapperEmail>abcd@acme.com</MapperEmail>
```

``` {.PreIndent space="preserve"}
<VcdbVersionDate>2018-03-30</VcdbVersionDate>
```

``` {.PreIndent space="preserve"}
<QdbVersionDate>2018-03-30</QdbVersionDate>
```

``` {.PreIndent space="preserve"}
<PcdbVersionDate>2018-03-30</PcdbVersionDate>
```

    </Header>

``` {space="preserve"}
<App action="A" id="1">
```

``` {.PreIndent space="preserve"}
<BaseVehicle id="31991"/>
```

``` {.PreIndent space="preserve"}
<EngineBase id="2127"/>
```

``` {.PreIndent}
<Qual id="1920">
```

``` {.PreIndent}
<text>Cast Iron Steel Gears are not Interchangeable. Use of Incorrect Part Number will Cause Severe Damage to Camshaft Gear and/or Distributor Gear</text>
```

``` {.PreIndent}
</Qual>
```

``` {.PreIndent}
<Qual id="6">
```

``` {.PreIndent}
<param value="1"/>
```

``` {.PreIndent}
<param value="2"/>
```

``` {.PreIndent}
<text>#1  #2 Intake Inlets are Oval</text>
```

``` {.PreIndent}
</Qual>
```

``` {.PreIndent}
<Qty>1</Qty>
```

``` {.PreIndent}
<PartType id="11279"/>
```

``` {.PreIndent}
<Part BrandAAIAID="GWWQ">AC Delco Part Number 034-VC21499</Part>
```

    </App>

    <Footer>

``` {.PreIndent}
<RecordCount>1</RecordCount>
```

    </Footer>

    </ACES>

Considerations for Version ACES 3.0, ACES 3.2 and ACES 4.0

Considerations for Version ACES 3.0, ACES 3.2 and ACES 4.0 {#considerations-for-version-aces-3.0-aces-3.2-and-aces-4.0 conditions="Primary.Web"}
----------------------------------------------------------

-   \<ACES version=\"X.X\"\> must be populated accordingly in the Header
    segment

```{=html}
<!-- -->
```
-   The DigitalAsset segment is excluded for ACES 3.0 export.
-   If an application has an asset linked to it, only the AssetName will
    get exported with the application.
-   For a 3.2 and 4.0 export, AssetName will also be populated within
    the application record, but an additional DigitalAsset segment with
    details about the asset is also included.
-   The value for AssetName comes from attribute
    ID=AC\_PIES\_ASSTAssetID on the asset.
-   The value for AssetType comes from the metadata attribute
    ID=AC\_PIES\_ASSTAssetType on the asset reference.
-   The asset included in an export must be linked to the application
    record using any of these Image and Document Reference Types:
    -   AC\_ACESApplicationToInstallation
    -   AC\_ACESApplicationToOwnersManual
    -   AC\_ACESApplicationToPrimaryProductImage
    -   AC\_ACESApplicationToProductImage
    -   AC\_ACESToAsset

ACES standard only supports one asset linked to each application, but
STEP supports multiple assets linked per application. If more than one
asset is linked to the application in STEP, only one asset is exported
randomly. An entry is written to the execution report of the export for
any skipped assets.

Sending Data Downstream

Sending Data Downstream {#sending-data-downstream conditions="Primary.Web"}
-----------------------

In order to send data to downstream systems, the AutoCare ACES
Application Exporter has a Version parameter to select either 3.0 or 3.2
or 4.0 format.

The version will default to 4.0. If 3.0 is selected, then the exported
file will contain the following:

-   UTF-8 encoding
-   \<ACES version=\"3.0\"\>

```{=html}
<!-- -->
```
-   The ApprovedFor tag in the Header is in the 3.0 format:
    \<ApprovedFor\>DK,US\</ApprovedFor\>

This tag must be removed from the a 3.0 file before importing through
the STEP ACES Importer, otherwise it will fail validation against 3.2
and 4.0 XSD.
