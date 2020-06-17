---
description: 'Automotive Solution: Describes the functions of the
  Conversion State default workflow state.'
title: '\[%=Heading.AnyLevel%\]'
---

Conversion State
================

The conversion state converts the original file into a series of STEPXML
files. This provides two benefits:

1.  By converting to STEPXML, the import can be carried out using
    standard STEP import functionality.
2.  By converting to multiple standalone files rather than a single
    large file, there is a performance gain in that some files can be
    imported in parallel.

By default, the conversion state includes one business action (**Run
background process action**), which runs the conversion service as a
background process. Each standard has its own conversion service and
some parameters are specific to the standards. Each standard\'s
Conversion state parameters are described below, along with the possible
conversion state results.

AutoCare Conversion State Parameters
------------------------------------

Within the STEP AutoCare solution, two conversion services are offered;
\[AutoCareToStepXMLConvertService\] and \[ACESToStepXMLConvertService\].
\[AutoCareToStepXMLConvertService\] is used in the workflow Conversion
state for the Brand, PAdb, PCdb, VCdb, Qdb and PIES imports. The
\[ACESToStepXMLConvertService\] is used only in the workflow Conversion
state for the ACES import.

**\[AutoCareToStepXMLConvertService\]**

Each of the parameters are explained in detail below.

![](../../../Resources/Images/TecDoc/Autocare%20Conversion%20state%20background%20process.png)

-   **QueueID:** Required parameter for all background process actions
    that specifies the queue in which the background process should run,
    which defaults to \'queue\_Conversion\'. This parameter is specified
    for the action itself, not the particular service within the action,
    though the outcome is the same as each action runs only a single
    service.
-   **Background Process Service:** Required parameter for all
    background process actions that specifies the background process,
    which defaults to \[AutoCareToStepXMLConvertService\].
-   **AutoCare file attachment ID:** Required parameter used in all
    conversion services and functions the same as described in the
    Validation process (forming the relationship between the file
    originally supplied to the endpoint and the file that the workflow
    processes will act on). For more information, see the **Validation
    State** topic[ here]{.mcFormatColor style="color: Blue;"}.
-   **STEP XML attachment ID:**Required parameter used in all conversion
    services and specifies the name of the file that is the product of
    the conversion process, which defaults to \'convert.\' If multiple
    files are created by the conversion service, this will be a zipped
    file, e.g., convert.zip.

**\[ACESToStepXMLConvertService\]**

Each of the parameters are explained in detail below. PRODOC note: BOND
RDCUST-3335 : Insert this discussion in the document

![](../../../Resources/Images/TecDoc/Aces%20Coversion%20state.png)

-   **QueueID:** Required parameter for all background process actions
    that specifies the queue in which the background process should run,
    which defaults to \'queue\_Conversion\'. Note that this parameter is
    specified for the action itself, not the particular service within
    the action, though the outcome is the same as each action runs only
    a single service.
-   **Background Process Service:** Required parameter for all
    background process actions that specifies the background process,
    which defaults to \'\[ACESToStepXMLConvertService\]\'.

```{=html}
<!-- -->
```
-   **ACES Default FULL Import handling:** By default, BRAND is
    selected. Defines how files with a SubmissionType=FULL are handled.
    For more information, see the **9. Specify Complete Replacement
    Handling (ACES Import Workflow Only)** topic within the **Automotive
    Quick Start Guide**[ here]{.mcFormatColor style="color: Blue;"}.
-   **ACES Default SUPPLIER Import handling:** By default, NO is
    selected. Defines whether or not Supplier is taken into
    consideration when evaluating replacement scenarios. For more
    information, see the **9. Specify Complete Replacement Handling
    (ACES Import Workflow Only)** topic within the **Automotive Quick
    Start Guide**[ here]{.mcFormatColor style="color: Blue;"}.
-   **ACES Default UPDATE Import handling:** By default, STANDARD is
    selected. Defines how files with a SubmissionType=UPDATE are
    handled. For more information, see the **9. Specify Complete
    Replacement Handling (ACES Import Workflow Only)** topic within the
    **Automotive Quick Start Guide**[ here]{.mcFormatColor
    style="color: Blue;"}.

```{=html}
<!-- -->
```
-   **AutoCare file attachment ID:** Required parameter used in all
    conversion services and functions the same as described in the
    Validation process (forming the relationship between the file
    originally supplied to the endpoint and the file that the workflow
    processes will act on). For more information, see the **Validation
    State** topic[ here]{.mcFormatColor style="color: Blue;"}.
-   **Create PIES items:** PRODOC note: BOND RDCUST-3525 Optional
    parameter used to import applications when associated part number
    (PIES Item) does not exist in the system. Selecting the parameter
    allows an ACES file to be imported even if the Part Number does not
    already exist. The Part Terminology product hierarchy (PIES
    Brand/PIES PCdb Category/PIES PCdb Sub Category/PIES PCdb Part
    Terminology/PIES Item) and Part Number will be created by the ACES
    import, and applications will be created below the Part Number.
    Having the parameter deselected would require that the Part Number
    must already exist. With this parameter deselected and if the Part
    Number doesn\'t exist, then the ACES import will not be able to
    create any applications because of the missing Part Number.
-   **Omit application names:** By default, this optional parameter
    specific to the AutoCare standard is disabled and when the ACES
    Importer creates application objects it sets the STEP Name to be the
    same value as the Part Number. After the applications are created,
    users have the option to change the STEP Name to something other
    than the Part Number (i.e., Acura TSX 2010). However, an issue is
    encountered the next time an ACES file containing those same
    applications is imported, because the STEP Name will be reverted to
    the Part Number. This occurs because the Conversion state checks the
    name in the file against the name in the database, and processes
    them as an update. Therefore, it includes those records in the delta
    file, even though nothing has changed in the record. If the
    application name and part number should always match, then the
    parameter should remain disabled. This way, upon the next import of
    an ACES file, the Part Number\'s STEP Name will be reverted to the
    Part Number\'s name within the ACES file. If the application name
    should not be altered to match what is in the ACES file then PRODOC
    note: MEDU RDCUST- 2704 When enabled, application names will be
    omitted during the conversion process so that the record will not be
    included in the delta file.PRODOC note: This parameter is
    exclusively available in the ACES Conversion State workflow. A new
    screenshot needs to be added and behavior of this parameter needs to
    be documented.The ACES Importer creates application objects and sets
    the STEP Name to be the same value as the Part Number. After the
    applications have been created, users have the option to change the
    STEP Name to be something other than the Part Number (i.e., Acura
    TSX 2010). An issue is encountered when the next time that an ACES
    file is imported, the STEP Name will get reverted to the Part Number
    again because the Conversion is checking the name in the file
    against the name in the database, and sees it as an update and is
    including those records in the delta file even though nothing has
    changed in the record. To resolve this issue, AutoCare ACES Import
    workflow has been updated to include a new parameter called \'Omit
    application names\' in the Conversion state. When this option is
    selected, the name of applications would be omitted in the
    conversion process so that the record will not be included in the
    delta file.
-   **STEP XML attachment ID:** Required parameter used in all
    conversion services and specifies the name of the file that is the
    product of the conversion process, which defaults to \'convert.\' If
    multiple files are created by the conversion service, this will be a
    zipped file, e.g., convert.zip.
-   **Regular Expression for parsing Supplier from file
    name:**Optionally, populate the \'Regular Expression for parsing
    Supplier from file name\' parameter (using the JavaScript regular
    expression format) to specify how the Supplier value should be
    extracted from the ACES file name. By default, the parameter is
    populated with **(.\*?)\_.\***, meaning that the system will extract
    the first string prior to an underscore (typically a Supplier value)
    in the file name as this is how the ACES standard defines the naming
    convention. For example, with a file name of
    ACMESupply\_BrakeHardware\_2016-04-23\_FULL.xml, \'ACMESupply\'
    would be extracted as the Supplier value. If this is not desired, a
    Regular Expression can be inserted in the parameter to extract
    Supplier in an alternate way.**PRODOC note**: Changing the value to
    .\*\_(.+?)\_.\* parses what is between the 1st and 2nd underscore
    (if there are only 2 underscores. If there are 2, it takes what is
    between the 2nd and 3rd). Can be updated however the user needs
    though to get the right information from the file name.

NAPA Conversion State Parameters
--------------------------------

Within the STEP NAPA solution, two conversion services are offered;
\[NAPAToStepXMLConvertService\] and
\[NAPATransToStepXMLConvertService\]. \'NAPAToStepXMLConvertService\' is
used in the workflow Conversion state for Vehicle, Attribute,
Application, and Interchange imports. The
\'NAPATransToStepXMLConvertService\' is used only in the workflow
Conversion state for Translation import.

**\[NAPAToStepXMLConvertService\]**

Each of the parameters are explained in detail below.

![](../../../Resources/Images/AppMgr/Configuring/C3.png)

-   **QueueID:** Required parameter for all background process actions
    that specifies the queue in which the background process should run,
    which defaults to \'queue\_Conversion\'. Note that this parameter is
    specified for the action itself, not the particular service within
    the action, though the outcome is the same as each action runs only
    a single service.
-   **Background Process Service:** Required parameter for all
    background process actions that specifies the background process,
    which defaults to \'NAPAToStepXMLConvertService\'.
-   **NAPA file attachment ID:** Required parameter used in all
    conversion services and functions the same as described in the
    Validation process (forming the relationship between the file
    originally supplied to the endpoint and the file that the workflow
    processes will act on). For more information, see the **Validation
    State** topic[ here]{.mcFormatColor style="color: Blue;"}.
-   **STEP XML attachment ID:**Required parameter used in all conversion
    services and specifies the name of the file that is the product of
    the conversion process, which defaults to \'convert.\' If multiple
    files are created by the conversion service, this will be a zipped
    file, e.g., convert.zip.

**\[NAPATransToStepXMLConvertService\]**

Each of the parameters are explained in detail below.

![](../../../Resources/Images/AppMgr/Configuring/C4.png)

-   **QueueID:** Required parameter for all background process actions
    that specifies the queue in which the background process should run,
    which defaults to \'queue\_Conversion\'. Note that this parameter is
    specified for the action itself, not the particular service within
    the action, though the outcome is the same as each action runs only
    a single service.
-   **Background Process Service:** Required parameter for all
    background process actions that specifies the background process,
    which defaults to \'NAPATransToStepXMLConvertService\'.
-   **NAPA file attachment ID:** Required parameter used in all
    conversion services and functions the same as described in the
    Validation process (forming the relationship between the file
    originally supplied to the endpoint and the file that the workflow
    processes will act on). For more information, see the **Validation
    State** topic[ here]{.mcFormatColor style="color: Blue;"}.
-   **Product lines:** Required? parameter used in all NAPA conversion
    services and serves to \... PRODOC note: MEDU per KRMA ??? BEJA
    can\'t remember what it does. NAPA is currently unsupported so
    whatever\... conditioning this out for now but we should figure it
    out at some point and then UN-condition it \... NIFE thinks its only
    in the translation import.
-   **Product lines:**Optional parameter specific to the NAPA standard.
    This option allows for the \.... PRODOC note: This parameter shall
    be tested upon import of NAPA file and to be documented. This
    functions similar to the properties mentioned under parameter
    Generic article described below.
-   **STEP XML attachment ID:**Required parameter used in all conversion
    services and specifies the name of the file that is the product of
    the conversion process, which defaults to \'convert.\' If multiple
    files are created by the conversion service, this will be a zipped
    file, e.g., convert.zip.

TecDoc Conversion State Parameters
----------------------------------

Within the STEP TecDoc solution, the \[TAFToStepXMLConvertService\]
conversion services is offered.

\[TAFToStepXMLConvertService\]

Each of the parameters are explained in detail below.

![](../../../Resources/Images/QS/TecDocConversionService.png)

-   **QueueID:** Required parameter for all background process actions
    that specifies the queue in which the background process should run,
    which defaults to \'queue\_Conversion\'. Note that this parameter is
    specified for the action itself, not the particular service within
    the action, though the outcome is the same as each action runs only
    a single service.
-   **Attachment ID for TAF file:** Required parameter used in all
    conversion services and functions the same as described in the
    Validation process (forming the relationship between the file
    originally supplied to the endpoint and the file that the workflow
    processes will act on). For more information, see the **Validation
    State** topic[ here]{.mcFormatColor style="color: Blue;"}. PRODOC
    note: MEDU per KRMA Need to create an issue for this to be updated
    to \[Standard file attachment ID\', and then remove this once that
    change is made (and update the TecDoc screenshot)
-   **Generic article filter:** PRODOC note: MEDU RDCUST- 2853 and
    RD-11468 Optional parameter specific to the TecDoc standard. This
    filter option allows for the reduction of unnecessary Generic
    Articles (Classifications) being imported into STEP. Only those
    Generic Articles selected within the filter are imported.

In the example below, the 0003 Product Hierarchy is shown including many
Articles, the editing of the \'TecDoc Reference Import Conversion\'
Business Rule is displaying the \'Generic article filter\' parameter
with the \'Air Mass Sensor\' and \'Glow Plug\' generic articles selected
for import, and the results are the 0003 Product Hierarchy is shown with
only the \'Air Mass Sensor\' and \'Glow Plug\' articles.

![](../../../Resources/Images/TecDoc/1.jpg)

![](../../../Resources/Images/TecDoc/TecDocArticleFiltering.jpg)

![](../../../Resources/Images/TecDoc/3.jpg)

To select a Generic Article, click the green icon
(![](../../../Resources/Images/GreenAddIcon.png)) within the parameter,
and a blank Classification field will display. and a Select
Classification dialog will display. Select the desired classification,
and click the Select button to close the dialog. Repeat these steps to
add more Generic Articles.

-   **Reference data asset ID:** Required parameter used in all TecDoc
    conversion services that functions the same as described for the
    validation service (providing a link between the file being imported
    and the reference data asset it should be stored in or validated
    against). For more information, see the **Validation State** topic[
    here]{.mcFormatColor style="color: Blue;"}.

```{=html}
<!-- -->
```
-   **Attachment ID to store STEP xml to:** Required parameter used in
    all conversion services and specifies the name of the file that is
    the product of the conversion process, which defaults to
    \'convert.\' If multiple files are created by the conversion
    service, this will be a zipped file, e.g., convert.zip.
-   **Omit search structures:** PRODOC note: MEDU PRODOC-1576 Optional
    parameter specific to the TecDoc standard. This filter option allows
    for the reduction of unnecessary TecDoc Reference data being
    imported. When disabled, all Search Trees and Reference Data
    classification folders are imported per the TecDoc Reference Data
    file. When enabled, Search Trees and Reference Data classification
    folders (except Generic Articles and Linking Targets) are omitted.
    To filter Generic Articles and/or Linking Targets, the \'Generic
    article filter\' parameter must be used. For example, if the \'Omit
    search structures\' parameter is enabled, and the \'Generic article
    filter\' is blank, then only the Generic Articles and Linking
    Targets Reference Data will be imported.

Conversion State Function Details
---------------------------------

As the conversion service runs a background process (BGP), a
corresponding BGP folder is created on the application server at
/workarea/background-processarea/\[Standard\]toStepXMLConvertService.
The BGP folder contains a sub-folder whose name matches the STEP ID of
the controller entity that is moving through the workflow and contains
the originally loaded file, the same as is seen in the validation
service. The conversion service also writes an additional file, which is
the output of the conversion process, (e.g., a zipped file with the name
specified in the STEPXML attachment ID parameter). This zipped file
contains sub-files in STEPXML format that are submitted to the delta
calculation service for further processing. The sub-files contained in
any convert file differ based on the file type.

For example, an AutoCare VCdb conversion result is shown below:

![](../../../Resources/Images/QS/ConversionBGP.png)

![](../../../Resources/Images/QS/ConvertSubFiles.png)

In addition, the converted file is prefixed with the value from the file
attachment ID parameter in the BGP service (\'convert\' in our example)
and deposited on the application server at
/workarea/stepworkflow-area/\[Standard\]\[Format\]Import/entity-\[ControllerID\]/attachments/ImportFlowAttachment.
For example:

![](../../../Resources/Images/QS/ConversionFileAttachments.png)

If modifications need to be made to the converted file(s) before further
processing is completed, it is the workflow attachment file (e.g.,
convert-convert.zip in the above example) that must be manipulated as
this is the file that is actually carried through the workflow.

Conversion State Results
------------------------

The following are possible conversion state results:

-   **Failed:** If the import file fails conversion for some reason, the
    controller object in the workflow is sent to the Error state via the
    bgp.failed transition. This transition includes one default business
    rule which is used to populate the overall status of the controller
    entity (the overall status is displayed to end users in the Web UI).
    The controller will remain in the Error state until acted on by a
    user.
-   **Succeeded:** If conversion completes successfully without any
    errors, the controller automatically moves to the Delta Calculation
    state via the bgp.succeeded transition. This transition does not
    include any default business rules as the controller is moved
    automatically so there is no need to display an overall status to
    the end user at this time.
-   **Completed with errors:** It is also possible for a file to
    complete conversion, but with errors. In this case the controller is
    moved to the next state via the bgp.completedwitherrors transition
    that, like the bgp.succeeded transition, does not contain any
    default business rules. As with successful completion of conversion,
    the controller is automatically moved to the Delta Calculation
    state.
