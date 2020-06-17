---
description: 'Automotive Solution: Describes the functions of the
  Validation default workflow state.'
title: '\[%=Heading.AnyLevel%\]'
---

Validation State
================

The validation state does some basic schema validation of the file. If
the automotive standard (i.e., AutoCare, TecDoc, NAPA) supplies an XSD,
the file format is validated against the XSD. If an XSD is not provided
by the standard, the file is loosely validated to ensure the format
conforms to what is expected for the file type.

The validation state includes one business action (**Run background
process action**) by default, which runs the validation service as a
background process. Each standard has its own validation service.

The validation services are coded specifically for the file types
provided for that standard and cannot be repurposed for other formats,
even within the standard. For example, the AutoCare validation service
accepts PCdb files as zipped files containing pipe delimited subfiles
and ACES files in XML format. If you wanted to validate a PCdb file in
Access format or a flat file supplying ACES data, a new validation
service would need to be created using the Extension API.

Validation State Common Parameters
----------------------------------

Despite having different services for each standard, each validation
service contains several common parameters.

The AutoCare validation service (AutoCareValidationService) is shown as
an example below.

![](../../../Resources/Images/QS/ValidationService.png)

1.  **QueueID:** For all three validation services, this required
    parameter value defaults to \'queue\_Validation\' for all background
    process actions that specify the queue in which the background
    process should run.

This parameter is specified for the action itself, not the particular
service within the action, though the outcome is the same as each action
runs only a single service.

Additionally, this parameter value can be used to define the
configuration property within the sharedconfig.properties for when a
process needs to run in parallel.

For example, by default, files go through the following states one at a
time; validation, conversion, delta calculation, and import. If it is
necessary for ACES files to be imported four at a time, then the
following would need to be added to the sharedconfig.properties:

    BackgroundProcess.Queue.queue_Import.Size=4

Typically, reference files do not need to have parallel processes
because they are only updated once a month, and it is important to have
certain reference files imported before others. Therefore, running them
in parallel is not ideal.

However, it is likely that multiple supplier files would need to be
imported at once, because they are updated more frequently. Therefore,
running them in parallel is ideal.

After adding the property, the application server must be restarted for
it to take effect.

1.  **AutoCare file attachment ID / NAPA file attachment ID / Attachment
    ID for TAF file:** For all three validation services, this required
    parameter value:

-   Defaults to \'original.\'
-   Forms the relationship between the file supplied to the endpoint and
    the file that the workflow is going to process.
-   Prefixes the file name for the workflow attachment.

The \'AutoCare file attachment ID\' / \'NAPA file attachment ID\' and/or
\'Attachment ID for TAF file\' parameter entry in the validation service
must match the File Attachment ID value in the corresponding endpoint
configuration. For example, the \'AutoCare file attachment ID:\' value
is \'original,\' and can be viewed in both the Edit Operation dialog
(shown above) and the Inbound Integration Endpoint Wizard (shown below).

![](../../../Resources/Images/QS/IIEP5.png)

1.  **Continue on Error:** Specifies whether or not the file can
    continue to process after encountering some \'allowable\' data
    errors. For additional information and considerations relevant for
    this setting, see the **7. Determine Validation Error Handling for
    Each Import** topic within the **Automotive Quick Start Guide**[
    here]{.mcFormatColor style="color: Blue;"}.

Validation State TecDoc Specific Parameter
------------------------------------------

Along with the common parameters (described above) the TecDoc validation
service (TAFValidationService) offers the following additional
parameter:

1.  **Reference data Asset ID:** Required parameter available only for
    the TecDoc validation service. When importing a Reference Data file,
    the file itself is stored in the selected asset.

When importing a Supplier Data file, the Supplier Data file is validated
against the Reference Data file stored in the selected \'Reference data
Asset ID.\'

The TecDoc validation service (TAFValidationService) is shown as an
example below.

![](../../../Resources/Images/ImportProcess/1.jpg)

To view the import file within Workbench, go to Tree \> Configurations
\> TecDocConfigurations.

In the example below, the TecDoc Reference Data File is displayed below
the TecDocConfigurations classification folder.

![](../../../Resources/Images/ImportProcess/2.jpg)

Validation Service Function Details
-----------------------------------

As the validation service runs a background process (BGP), a
corresponding BGP folder is created on the application server at
/workarea/background-processarea/\[Standard\]ValidationService. The BGP
folder contains a sub-folder whose name matches the STEP ID of the
controller entity that is moving through the workflow. The original file
that was loaded can be found inside the controller sub-folder, as shown
below.

![](../../../Resources/Images/QS/ValidationFiles.png)

Further, the file is prefixed with the value from the file attachment ID
parameter in the BGP service (\'original\' in our example) and deposited
on the application server at
/workarea/stepworkflow-area/\[Standard\]\[Format\]Import/entity-\[ControllerID\]/attachments/ImportFlowAttachment,
as shown below.

![](../../../Resources/Images/QS/ValidationFileAttachments.png)

If modifications need to be made to the original file as part of
validation and/or following validation, it is the workflow attachment
file (e.g., original-Acme\_MMY.xml in the above example) that must be
manipulated as this is the file that is actually carried through the
workflow.

Validation State Results
------------------------

PRODOC note: MEDU - I think the State Results need to be what is
displayed in the import controller: \"Validation Failed\" \"Validation
Completed.\".. etc.. but I need to research this more.

The following are possible validation state results:

**Failed:** If the import file fails validation (e.g., does not meet the
schema requirements or the system encounters an error and is unable to
complete the validation process), the controller object in the workflow
is sent to the Error state via the bgp.failed transition. This
transition includes one default business rule which is used to populate
the overall status of the controller entity (the overall status is
displayed to end users in the Web UI Import Controller Screen). The
controller will remain in the Error state until acted on by a user.

Though an import can have a status of \'Validation failed,\' the
controller object in the workflow can still be sent to the next step of
the workflow if the \'Continue on Error\' parameter is enabled for the
workflow. When this occurs, the validation issues are written to the
execution report, but all valid data is converted and made available for
the import process. For more information, see the **7. Determine
Validation Error Handling for Each Import** topic within the
**Automotive Quick Start Guide** ([here]{.mcFormatColor
style="color: Blue;"}) and/or the **Validation Error Handling** topic
within this guide[ here]{.mcFormatColor style="color: Blue;"}.

**Succeeded:** If validation completes successfully without any errors,
the controller automatically moves to the Conversion state via the
bgp.succeeded transition. This transition does not include any default
business rules as the controller is moved automatically so there is no
need to display an overall status to the end user at this time.

**Completed with errors:** It is possible for a file to pass validation
with errors. In this case the controller is moved to the next state via
the bgp.completedwitherrors transition that, like the bgp.succeeded
transition, does not contain any default business rules. This occurs
when the basic schema validation is met, but some additional data-level
validations are in place for which the file does not pass, and the
\'Continue on Error\' parameter is checked, as described in the **7.
Determine Validation Error Handling for Each Import** topic of the
**Automotive Quick Start Guide**[ here]{.mcFormatColor
style="color: Blue;"}. If the \'Continue on Error\' parameter is
unchecked, the data-level validations would result in a validation
failure and the file would be moved to the Error state via the
bgp.failed transition.

In the example below a TecDoc Reference Import Controller Screen is
shown, and because the \'Continue on Error\' parameter is enabled when
the import processes, the import file associated with Controller-102344
is able to be Completed with errors.

![](../../../Resources/Images/ImportProcess/3.jpg)

This is displayed within the Import Controller Screen, in the following
manner:

1.  The Overall Status column for controller is displayed as \'Completed
    with errors: 255.\'
2.  The Status column within the Import Details table displays the
    Status as \'Validation completed.\'
3.  The Background Process Link displays \'completedwitherrors.\'
