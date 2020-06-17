---
description: 'The intention of the Qdb importer of the automotive
  solution is to provide an out-of-the-box solution for importing data
  included within the Qdb file. '
---

Importing Qdb Files via Web UI
==============================

This section provides details about importing a Qdb file via Web UI.

Prerequisites
-------------

An AutoCare Qdb Imports Node Details screen must be configured in Web
UI. For more information, see the xxx section of the **xxx**
documentation.

Steps for Importing Qdb files via Web UI
----------------------------------------

1.  From a Web UI Homepage, locate the REFERENCE DATA IMPORTS widget and
    either drag and drop the ZIP file on the \'Qdb select file\' area,
    or click the area to begin uploading the file.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/ReferenceDataImports.png)

2.  Once an upload has started, a dialog will display at the top of the
    screen confirming the file has been submitted to the Qdb hotfolder.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/SubmittedAAIA.png)

2.  Once the file is uploaded, a background process will start, and an
    Import Flow Controller Type Entity object will be created within the
    AutoCare Qdb Import Flow Group Types Entity object of the Import
    Flow Group Type. In the example below, the \'AAIA Qdb ASCII.zip\'
    file is displayed within the AutoCare Qdb Import Flow Group Type.

-   **Name:** STEP Entity controller Name used to store the original
    import file name.
-   **Automotive Import Flow State BGP:** Attribute used to store the
    IDs of the background processes.
-   **Import Flow State Status:** Attribute used to store the status of
    each process.
-   **Import Flow Overall Status:** Attribute used to display the global
    status of the file (rather than a per-process status).

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/TreeAAIAQdb.png)

All of the information displayed on the Entity controller is also
displayed within the workflow and controller screens in Web UI, and are
discussed in the **Quick Start for Users** section of the **Automotive
Quick Start Guide**[ here]{.mcFormatColor style="color: Blue;"}.

1.  Once created, the controller is initiated into the workflow
    associated with the importer. From there, the workflow takes over
    processing of the file via a series of states using business rules
    and background processes to carry out the processing of the file.

By default, each import type has an associated workflow, and all
importers proceed through the same states. However, it is intended that
customers will expand on the existing states and actions to add their
own validations, reporting, and additional processing as needed. For
more information on validation rules, see the **Qdb Import Validation
Rules** topic within **Import Validation Rules** section of this guide[
here]{.mcFormatColor style="color: Blue;"}.

It is critical to understand that only the Entity controller is within
the workflow - the objects being acted on (created / updated / deleted)
via information supplied in the import file are not within the workflow.
Therefore, running standard business actions acting on current object
will impact the Entity controller only, not the objects in the input
file.

1.  As the controller Entity moves through the configured import
    workflow, a series of background processes handle the various
    processing and import activities. Though much of the file processing
    is handled automatically, user interaction is required to actually
    start the file import. Users are able to do this when the file
    reaches the \'Ready for Import\' state. The progress of the
    controller Entity can be viewed on the Web UI Homepage within the
    Status Selector Widget labeled \'AUTOCARE QDB IMPORT.\'

For more information on workflow states, see the **Import Workflow
Overview** topic within the **Using Automotive Importers** section of
this guide[ here]{.mcFormatColor style="color: Blue;"}.

In the example below, the Status Selector Widget displays the status for
four Qdb imports, and one is Ready for Import.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/AutocareQDBImport.png)

1.  Once a file reaches the \'Ready for Import\' state, users can click
    on the \'Ready for Import\' state of the \'AUTOCARE QDB IMPORT\'
    Status Selector Widget, and the AutoCare Qdb Imports Node Details
    screen will display.

2.  Clicking the icon next to the listed Controller displays the Import
    Details section, as shown below.

3.  Clicking the **Reject** button will stop the file from being
    imported, once in a Rejected state, the **Discard file** button can
    be clicked to remove the file from the hotfolder.

4.  Clicking the **Start import** button will start the import, and a
    confirmation dialog will display at the top of the screen, as shown
    below.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/StartImportdialog.jpg)
