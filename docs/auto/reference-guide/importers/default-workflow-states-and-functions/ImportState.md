---
description: 'Automotive Solution: Describes the functions of the Import
  State default workflow state.'
title: '\[%=Heading.AnyLevel%\]'
---

Import State
============

The Import state carries out the actual import of the files generated
from the delta calculation service. As the generated files are in
STEPXML format, the standard STEP Importer is the engine used behind the
scenes to carry out the import.

Import State Common Parameters
------------------------------

The Import state includes one business action (**Run background process
action)** by default, which runs the import service as a background
process. All standards share a common import service (though default
actions and conditions applied to the imports differ) and the parameters
are described below.

![](../../../Resources/Images/QS/ImportBGPService.png)

-   **QueueID:** Required parameter for all background process actions
    that specifies the queue in which the background process should run,
    which defaults to \'queue\_Import.\' Note that this parameter is
    specified for the action itself, not the particular service within
    the action, though the outcome is the same as each action runs only
    a single service.
-   **File Attachment ID:** Required parameter that must be populated
    with the name of the file to be imported. This defaults to \'delta\'
    as that would be the correct file name if no additional states
    and/or processing were added to the default workflow. If an
    additional workflow state or service had been added that generated
    some other output file that the import should act on, the parameter
    should be updated accordingly.

This value must match the value provided for the \'Output file
Attachment ID\' parameter within the Delta Calculation state (if no
other states are added to the default workflow). If it does not match,
then the process will fail at the Import state.

-   **Import action:** Optional parameter allowing administrators to
    select one or more business actions to be run as part of the import.
    By default, there are no actions included but customers may add any
    that they wish.
-   **Import condition:** Optional parameter allowing administrators to
    select one of more business conditions to be run as part of the
    import. Importers that manage applications / linkages have one
    default condition applied (Validate application on import). This
    condition prevents applications from being imported if they do not
    contain a vehicle / assembly and part type in STEP. Additional
    information on the condition can be found in the **Automotive
    Business Rule Plugins** section[ here]{.mcFormatColor
    style="color: Blue;"}.

Any business rules selected within the import service function the same
as business rules applied in a standard STEP import, meaning that they
act on the objects being imported (rather than the controller entity).
If conditions are used, they must render true or the data will be
excluded from the import.

Automotive importers do not automatically approve objects that are
created by importer. So if Objects need to be approved, then a Business
Action using the following JavaScript function must be created:
*[\'node.approve();\'.]{.commandfont}* Additionally, that Business
Action must be added to the \'Import action\' parameter.

Import State Function Details
-----------------------------

As the import service runs a background process (BGP), a corresponding
BGP folder is created on the application server at
/workarea/background-processarea/ImportingFlowImportService. The BGP
folder contains a sub-folder whose name matches the STEP ID of the
controller entity that is moving through the workflow and contains the
delta calculation file that is being imported. The import service also
writes a copy of each file for which import was attempted (the number of
content of files will differ based on the import) and a status file
which indicates success or completion of each individual import file.

For example, an AutoCare ACES import result is shown below:

![](../../../Resources/Images/QS/ImportFileAttachments.png)

![](../../../Resources/Images/QS/ImportStatus.png)

Import State Results
--------------------

The import can succeed, fail, or \'complete with errors\' and the
controller will automatically follow appropriate bgp. transitions as
applicable. All transitions lead to the same Import Completed state and
none contain business rules by default, though each customer can add
additional handling as they see fit.

Information on errors and/or failures will be visible in Web UI via the
background process information provided for the import.
