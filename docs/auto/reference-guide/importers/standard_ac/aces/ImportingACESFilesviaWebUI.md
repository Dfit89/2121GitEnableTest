---
description: 'Automotive Solution: Describes how to import AutoCare ACES
  files via Web UI.'
title: '\[%=Heading.AnyLevel%\]'
---

Importing ACES Files via Web UI
===============================

The intention of the AutoCare ACES Importer Web UI setup included within
this topic is to provide an out-of-the-box solution for importing data
included within a supported AutoCare ACES file format. Because only
supported versions will successfully upload, before attempting to upload
an ACES file, confirm the file version being uploaded is listed within
the **Supported Versions and Formats** topic[ here]{.mcFormatColor
style="color: Blue;"}.

An ACES file includes information on application data, i.e., information
about fitment of a particular part to various vehicles, engines, etc.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

All reference data files (Brand Table, Qdb, PCdb, VCdb, and PAdb) must
be imported before PIES or ACES files are imported.

It is critical to understand that for systems running on Automotive 9.1
version and older, the PIES file must be imported first before importing
the ACES file. Failing to comply, the application records associated
with the missing PIES Items in the system will be skipped from being
imported. For systems running Automotive 9.1 MP1 and newer, users will
have an option to import ACES files without first importing PIES files,
provided that the \'Create PIES items\' parameter is checked in the
Conversion state of the ACES Import workflow. For more information, see
the **Conversion State** topic within the **Default Workflow States and
Functions** section[ here]{.mcFormatColor style="color: Blue;"}.

To easily start and monitor an ACES Import, recommended practice is to
use a Web UI Import Controller screen specific to the AutoCare ACES
Importer. When the Easy Setup actions for the AutoCare standard are
completed, the AutoCare Import Controller screen is automatically
created and configured for use. Additional information can be found in
the **Configuring AutoCare ACES Importer** topic[ here]{.mcFormatColor
style="color: Blue;"}.

It is expected that anyone using and/or configuring the AutoCare ACES
Importer be familiar with the **Importing Automotive Data** section
([here]{.mcFormatColor style="color: Blue;"}), as basic concepts for
working with an automotive importer are not covered in this section.

If the Easy Setup actions for the AutoCare Component model have been
completed, then the functionality explained within this topic should be
available. Otherwise, configuration is necessary. For more information,
see the **AutoCare ACES Importer** topic[ here]{.mcFormatColor
style="color: Blue;"}.

PRODOC note: MEDU GPC- 379 Very good information about the
ImportFlowExtensionContext that allows admins to maniuplate the files
generated by the import framework.

Using the AutoCare ACES Importer in Web UI
------------------------------------------

1.  Access the AutoCare Web UI Homepage.
2.  Upload a valid ACES file to the application server hotfolder
    (root/upload/hotfolders/AutoCareACESApplicationInputFolder), or use
    the \'ACES\' drop zone of the \'SUPPLIER DATA IMPORTS\' File Loading
    Widget.

For more information, see the **File Loading Widget** topic within the
**Web User Interfaces** section of **STEP Online Help**[
here]{.mcFormatColor style="color: Blue;"}.

1.  Once the upload has started, users can view the progress of the
    upload using the Background Process Notification Component.

In the example below, the BGP Notification Panel is expanded and the
file, \'HELLA, Inc.\_ACES\_BHS\_2016-02-04\_FULL.xml\' is 66% processed.

![](../../../../Resources/Images/Importers/Standard_AC/1.png)

For more information on using the BGP Notification Component and side
panel, see the **Background Process Notification Component** topic
within the **Main Properties Overview** section of **STEP Online Help**[
here]{.mcFormatColor style="color: Blue;"}.

Once the file has been uploaded and picked up by the IIEP, the
Controller is initiated into the workflow associated with the importer
(AutoCare ACES Import). From there, the AutoCare ACES Import workflow
takes over processing of the file via a series of states using business
rules and background processes to carry out the processing of the file.
Each import has an associated workflow and all proceed through the same
states by default. However, it is intended that customers will expand on
the existing states and actions to add their own validations, approve
objects, reporting, and additional processing as needed.

1.  If a Node Details screen has been configured, then when the IIEP
    creates the Controller Entity object, users can view the Controller
    and its important information by navigating within the Tree side
    panel to the Import Flow Root \> AutoCare ACES. Otherwise, if a user
    clicks on an Entity in the Tree side panel, an error will display
    indicating the configuration is invalid.

If an error message displays when selecting an Entity within a Web UI,
then the Node Details screen has not been configured. For information
about configuring the Node Details Screen, see the **Node Details
Screen** topic within the **Web User Interfaces** section of **STEP
Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

In the example below, the Tree side panel is expanded, and the \'HELLA,
Inc.\_ACES\_BHS\_2016-02-04\_FULL.xml\' Controller with ID \'Controller-
105212\' is displayed below the \'AutoCare ACES\' Entity. When the
Controller is selected, many details can be viewed within the Node
Details screen.

In the screenshot below, the \'Enable Tag Conversion\' parameter within
the Attribute Value Group Component is enabled.

![](../../../../Resources/Images/Importers/Standard_AC/2.png)

-   **Name:** STEP Name of the Controller Entity. This is generated from
    the original name of the uploaded file.
-   **Automotive Import Flow State BGP:** Attribute used to store the
    IDs of the background processes.
-   **Import Flow State Status:** Attribute used to store and display
    the status of each process (rather than the overall status).
-   **Import Flow Overall Status:** Attribute used to store and display
    the global status of the file (rather than the process specific
    status).

5.  As the file is uploaded, and the Controller Entity moves through the
    AutoCare ACES Import workflow, users can monitor the progress using
    the \'AUTOCARE ACES IMPORT\' Status Selector Widget on the Web UI
    homepage and/or the left side panel.

In the example below, the Tree panel is expanded, and the **Triple user
button** is selected so that all items assigned to any user are
displayed. Notice that one file is in the \'Ready for Import\' state,
and twenty seven files in the \'Import Completed\' state, for a total of
twenty eight files.

For more information, see the **Moving Tasks Trough a Workflow in Web
UI** topic within **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../../../Resources/Images/Importers/Standard_AC/3.png)

1.  Clicking on the **Ready for Import** state within the Status
    Selector homepage and/or the left side panel widget will navigate
    the user to the AutoCare ACES Import Controller Screen with only
    those Controllers in the \'Ready for Import\' state displayed.
2.  Clicking the Controller icon displays the Import Details below the
    Controller list.

In the example below, Controller \'HELLA,
Inc.\_ACES\_BHS\_2016-02-04\_FULL.xml\' (ID \'Controller-105630\') with
an overall status of \'Done creating delta file\' is selected and the
Import Details are displayed below the Controller list.

![](../../../../Resources/Images/Importers/Standard_AC/4.png)

1.  Optionally, before starting the import, clicking on the
    \'completedwitherrors\' Background Process Link will display the
    Background Process Details screen where users can view or download
    the details of the validation process.
2.  Click the **Reject** button to move the Controller to the Rejected
    state. For more information, see the **Rejected State** topic within
    the **Import Framework** section[ here]{.mcFormatColor
    style="color: Blue;"}.
3.  Click the **Start import** button, the Start import dialog (shown
    below) displays at the top of the screen, and the Controller is
    moved to the Import state of the workflow. For more information, see
    the **Import State** topic within the **Import Framework** section[
    here]{.mcFormatColor style="color: Blue;"}.

![](../../../../Resources/Images/Importers/Standard_TD/Reference/10.png)

While importing an ACES file the import progress can be monitored using
the \'AUTOCARE ACES IMPORT\' Status Selector Widget on the Web UI
homepage and/or the left side panel or the Import Controller Screen,
Import process Status column.

In the example below, the AutoCare ACES Import Controller Screen
displays the Overall Status and the Import process status as \'Importing
files\...\' Additionally, the Background Process Link column displays a
link to the Background Process Details screen as \'running.\'

![](../../../../Resources/Images/Importers/Standard_AC/5.png)

1.  Optionally, click the \'running\' Background Process Link (shown
    above) to view the details of the import process within the
    Background Process Details screen.

Once the import has completed, the Controller is automatically moved to
the Import Completed state. For more information, see the **Import
Completed State** topic within the **Import Framework** section[
here]{.mcFormatColor style="color: Blue;"}.

For more information about ACES import validation rules and example
error messages, see the **ACES Import Validation Rules** topic[
here]{.mcFormatColor style="color: Blue;"}.

For more information on automotive workflow states, see the **Default
Workflow States and Functions** topic[ here]{.mcFormatColor
style="color: Blue;"}.