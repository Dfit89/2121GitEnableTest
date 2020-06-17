---
description: 'Automotive Solution: Describes how to import AutoCare PAdb
  files via Web UI.'
title: '\[%=Heading.AnyLevel%\]'
---

Importing PAdb Files via Web UI
===============================

The intention of the AutoCare PAdb Importer Web UI setup included within
this topic is to provide an out-of-the-box solution for importing data
included within a supported AutoCare PAdb file format. Because only
supported versions will successfully upload, before attempting to upload
a PAdb file, confirm the file version being uploaded is listed within
the **Supported Versions and Formats** topic[ here]{.mcFormatColor
style="color: Blue;"}.

A PAdb file defines the way trading partners exchange information
concerning the product-specific performance and physical attributes of
parts.

It is always required that the latest PAdb file is imported into the
system. Importing the PAdb file validates the version date against the
version date stored on the \'AC\_PAdb\_VersionDate\' attribute which is
valid on the PCdb root classification object, and displays an error in
the Validation state if the imported file is older than the version date
that exists in STEP.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

Reference data files (Qdb, Brand Table, PCdb, and VCdb) must be imported
before PAdb files are imported.

To easily start and monitor a PAdb Import, recommended practice is to
use a Web UI Import Controller screen specific to the AutoCare PAdb
Importer. When the Easy Setup actions for the AutoCare standard are
completed, the AutoCare Import Controller screen is automatically
created and configured for use. Additional information can be found in
the **Configuring AutoCare PAdb Importer** topic[ here]{.mcFormatColor
style="color: Blue;"}.

It is expected that anyone using and/or configuring the AutoCare PAdb
Importer be familiar with the **Importing Automotive Data** section
([here]{.mcFormatColor style="color: Blue;"}), as basic concepts for
working with an automotive importer are not covered in this section.

If the Easy Setup actions for the AutoCare Component model have been
completed, then the functionality explained within this topic should be
available. Otherwise, configuration is necessary. For more information,
see the **AutoCare PAdb Importer** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Using the AutoCare PAdb Importer in Web UI
------------------------------------------

1.  Access the AutoCare Web UI Homepage.
2.  Upload a valid PAdb file to the application server hotfolder
    (root/upload/hotfolders/AutoCarePAdbInputFolder), or use the
    \'PAdb\' drop zone of the \'REFERENCE DATA IMPORTS\' File Loading
    Widget.

For more information, see the **File Loading Widget** topic within the
**Web User Interfaces** section of **STEP Online Help**[
here]{.mcFormatColor style="color: Blue;"}.

1.  Once the upload has started, users can view the progress of the
    upload using the Background Process Notification Component.

In the example below, the BGP Notification Panel is expanded and the
file, \'AAIA PAdb ASCII 20180320.zip\' is 33% processed.

![](../../../../Resources/Images/Importers/Standard_AC/52.png)

For more information on using the BGP Notification Component and side
panel, see the **Background Process Notification Component** topic
within the **Main Properties Overview** section of **STEP Online Help**[
here]{.mcFormatColor style="color: Blue;"}.

Once the file has been uploaded and picked up by the IIEP, the
Controller is initiated into the workflow associated with the importer
(AutoCare PAdb Import). From there, the AutoCare PAdb Import workflow
takes over processing of the file via a series of states using business
rules and background processes to carry out the processing of the file.
Each import has an associated workflow and all proceed through the same
states by default. However, it is intended that customers will expand on
the existing states and actions to add their own validations, approve
objects, reporting, and additional processing as needed.

1.  If a Node Details screen has been configured, then when the IIEP
    creates the Controller Entity object, users can view the Controller
    and its important information by navigating within the Tree side
    panel to the Import Flow Root \> AutoCare PAdb. Otherwise, if a user
    clicks on an Entity in the Tree side panel, an error will display
    indicating the configuration is invalid.

If an error message displays when selecting an Entity within a Web UI,
then the Node Details screen has not been configured. For information
about configuring the Node Details Screen, see the **Node Details
Screen** topic within the **Web User Interfaces** section of **STEP
Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

In the example below, the Tree side panel is expanded, and the \'AAIA
PAdb ASCII 20190329.zip\' Controller with ID \'Controller- 106327\' is
displayed below the \'AutoCare PAdb\' Entity. When the Controller is
selected, many details can be viewed within the Node Details screen.

In the screenshot below, the \'Enable Tag Conversion\' parameter within
the Attribute Value Group Component is enabled.

![](../../../../Resources/Images/Importers/Standard_AC/53.png)

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
    AutoCare PAdb Import workflow, users can monitor the progress using
    the \'AUTOCARE PADB IMPORT\' Status Selector Widget on the Web UI
    homepage and/or the left side panel.

In the example below, the Tree panel is expanded, and the **Triple user
button** is selected so that all items assigned to any user are
displayed. Notice that six file is in the \'Ready for Import\' state,
and nineteen files in the \'Import Completed\' state, for a total of
twenty five files.

For more information, see the **Moving Tasks Trough a Workflow in Web
UI** topic within **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

![](../../../../Resources/Images/Importers/Standard_AC/54.png)

1.  Clicking on the **Ready for Import** state within the Status
    Selector homepage and/or the left side panel widget will navigate
    the user to the AutoCare PAdb Import Controller Screen with only
    those Controllers in the \'Ready for Import\' state displayed.
2.  Clicking the Controller icon displays the Import Details below the
    Controller list.

In the example below, Controller \'AAIA PAdb ASCII 20190329.zip\' (ID
\'Controller-106327\') with an overall status of \'Done creating delta
file\' is selected and the Import Details are displayed below the
Controller list.

![](../../../../Resources/Images/Importers/Standard_AC/55.png)

1.  Optionally, before starting the import, clicking on the
    \'completedwitherrors\' Background Process Link (only displayed when
    there is any error) will display the Background Process Details
    screen where users can view or download the details of the
    validation process.
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

While importing a PAdb file the import progress can be monitored using
the \'AUTOCARE PAdb IMPORT\' Status Selector Widget on the Web UI
homepage and/or the left side panel or the Import Controller Screen,
Import process Status column.

In the example below, the AutoCare PAdb Import Controller Screen
displays the Overall Status and the Import process status as \'Importing
files\...\' Additionally, the Background Process Link column displays a
link to the Background Process Details screen as \'running.\'

![](../../../../Resources/Images/Importers/Standard_AC/56.png)

1.  Optionally, click the \'running\' Background Process Link (shown
    above) to view the details of the import process within the
    Background Process Details screen.

Once the import has completed, the Controller is automatically moved to
the Import Completed state. For more information, see the **Import
Completed State** topic within the **Import Framework** section[
here]{.mcFormatColor style="color: Blue;"}.

For more information about PAdb import validation rules and example
error messages, see the **PAdb Import Validation Rules** topic[
here]{.mcFormatColor style="color: Blue;"}.

For more information on automotive workflow states, see the **Default
Workflow States and Functions** topic[ here]{.mcFormatColor
style="color: Blue;"}.
