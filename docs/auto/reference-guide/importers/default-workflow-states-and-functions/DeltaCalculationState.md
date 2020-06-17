---
description: 'Automotive Solution: Describes the functions of the Delta
  Calculation default workflow state.'
title: '\[%=Heading.AnyLevel%\]'
---

Delta Calculation State
=======================

The Delta Calculation state compares the converted file(s) to either the
STEP database, or to the last loaded file of that type, and generates a
set of STEPXML files containing only the changed data. This is done to
increase performance of the actual imports so that unnecessary data is
not processed.

The determination for the comparison method is set per importer using
the **Delta calculation method** parameter described in the **5. Update
Delete Status Attribute and Delta Calculation Method in Import
Workflows** section of the **Quick Start Setup for Admins**[
here]{.mcFormatColor style="color: Blue;"}.

Delta Calculation State Common Parameters
-----------------------------------------

The Delta Calculation state includes one **Run background process
action** business action by default, which runs the delta calculation
service as a background process. All standards share a common delta
calculation service and the parameters are described below.

![](../../../Resources/Images/QS/DeltaCalculationService.png)

-   **QueueID:** Required parameter for all background process actions
    that specifies the queue in which the background process should run,
    which defaults to \'queue\_DeltaCalculate.\'

This parameter is specified for the action itself, not the particular
service within the action, though the outcome is the same as each action
runs only a single service.

-   **Delta calculation method:** Required parameter that determines how
    the delta file is generated (via file or context method).

For additional information and considerations for setting this
parameter, see the **5. Update Delete Status Attribute and Delta
Calculation Method in Import Workflows** section of the **Quick Start
Setup for Admins**[ here]{.mcFormatColor style="color: Blue;"}.

-   **Clear delete attribute:** Optional parameter used to clear the
    existing delete flag. This parameter removes / clears the value
    "true" from an attribute (configured in the \'Delete status
    attribute\' parameter) for an deleted object, when the deleted
    object (Object marked for deletion) is resurrected through the later
    imports.

For example, consider a PIES item A which already has delete attribute
value set as \"true\" in the system. With the \'Clear delete attribute\'
parameter selected, importing of PIES item A via the new PIES file
erases the delete flag existing in the attribute marked for deletion for
the PIES item A.

-   **Delete status attribute:** Optional parameter to select an
    attribute to store the indication for deletion as a result of the
    import. If not set, deletions will not be processed by the importer.
    Defining an attribute in the \'Delete status attribute\' parameter
    will set the flag to "true" if the object exists in STEP, but not in
    the imported file.

AutoCare ACES files using complete replacement concepts require a delete
status attribute to be set.

For additional information and considerations for setting this
parameter, see the **5. Update Delete Status Attribute and Delta
Calculation Method in Import Workflows** section of the **Quick Start
Setup for Admins**[ here]{.mcFormatColor style="color: Blue;"}.

-   **From file Attachment ID:** Required parameter that must be
    populated with the file name that should be used for the delta
    calculation service to act on. This defaults to \'convert\' as that
    would be the correct file name if no additional states and/or
    processing were added to the default workflow. If an additional
    workflow state or service had been added that generated some other
    output file that the delta calculation should act on, the parameter
    should be updated accordingly.
-   **Output file Attachment ID:** Required parameter that must be
    populated with the name of the output file generated via the
    calculation service. The default value is \'delta,\' which is then
    also the default value for the file being picked up in the Import
    service. Optionally, the Delta Calculation file can be made
    available for download in the Web UI Import Controller Screen Report
    column. For more information, see the Adding the Delta Calculation
    Download File Option to the Web UI Import Controller Screen.

### Adding the Delta Calculation Download File Option to the Web UI Import Controller Screen {#adding-the-delta-calculation-download-file-option-to-the-web-ui-import-controller-screen conditions="Primary.Under Construction"}

This section describes how to add the \'Download file\' link to the Web
UI Import Controller Screen Report column (as shown below), so that
users can download the Delta Calculation report from within the Web UI.

![](../../../Resources/Images/Importers/3.png)

This can be accomplished by changing the default \'delta\' value to
something else (i.e., \'DeltaCalculate\'), and then adding this same
value to the Import state. This will generate a link called \'Download
file\' in the Report column.

This is different than the functionality described in the **Adding
Reporting Extensions to Imports** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Delta Calculation State Function Details
----------------------------------------

As the delta calculation service runs a background process (BGP), a
corresponding BGP folder is created on the application server at
/workarea/background-processarea/StepXMLDeltaCalculationService. The BGP
folder contains a sub-folder whose name matches the STEP ID of the
controller entity that is moving through the workflow and contains the
converted file that the delta calculation was performed on. The delta
calculation service also writes an additional file, which is the output
of the delta calculation process, e.g., a zipped file with the name
specified in the \'Output file attachment ID\' parameter. This zipped
file contains sub-files in STEPXML format that are submitted to the
import service for further processing. The sub-files contained in any
delta file differ based on the file type.

For example, an AutoCare ACES delta calculation result is shown below:

![](../../../Resources/Images/QS/DeltaCalculationBGP.png)

![](../../../Resources/Images/QS/DeltaCalculationDeltaFile.png)

In addition, the delta file is prefixed with the value from the \'Output
file attachment ID\' parameter in the BGP service (\'delta\' in our
example) and deposited on the application server at
/workarea/stepworkflow-area/\[Standard\]\[Format\]Import/entity-\[ControllerID\]/attachments/ImportFlowAttachment.
For example:

![](../../../Resources/Images/QS/DeltaCalculationFileAtt.png)

If modifications need to be made to the delta file(s) before further
processing is completed, it is the workflow attachment file (e.g.,
delta-delta.zip in the above example) that must be manipulated as this
is the file that is actually carried through the workflow.

Setup Objects and Delta Calculations

The delta calculation service takes setup objects into account, where
setup objects (LOVs, attributes, reference types, etc.) that have not
changed will be filtered away and not be included in the delta
calculation file. Only changed setup objects will be included in the
delta calculation file. This is done by comparing what is in the import
file to what\'s in the database whether \'context\' or \'file\' delta
calculation method is used.

Importers will not handle deleted setup objects, they will instead be
reported as a warning in the delta calculation background process
Execution Report. For example, if there are LOV values in the database
but are no longer in the import file, then there will be a warning in
the delta calculation background process Execution Report listing the
LOV and values that are missing in the import file. In this case, the
user will need to check the delta calculation report and manually carry
out the deletion of the LOV values.

Delta Calculation State Results
-------------------------------

-   **Failed:** If the import file fails delta calculation for some
    reason, the controller object in the workflow is sent to the Error
    state via the bgp.failed transition. This transition includes one
    default business rule which is used to populate the overall status
    of the controller entity (the overall status is displayed to end
    users in the Web UI). The controller will remain in the Error state
    until acted on by a user.
-   **Succeeded:** If delta calculation completes successfully without
    any errors, the controller automatically moves to the Ready for
    Import state via the bgp.succeeded transition. This transition does
    not include any default business rules as the controller is moved
    automatically so there is no need to display an overall status to
    the end user at this time.
-   **Completed with errors:** It is possible for a file to complete
    delta calculation, but with errors. In this case the controller is
    moved to the next state via the bgp.completedwitherrors transition
    that, like the bgp.succeeded transition, does not contain any
    default business rules. As with successful completion of delta
    calculation, the controller is automatically moved to the Ready for
    Import state.
