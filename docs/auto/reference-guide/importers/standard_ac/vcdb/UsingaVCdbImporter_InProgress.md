---
title: '\[%=Heading.AnyLevel%\]'
---

Using a VCdb Importer
=====================

The intention of the automotive import core solution is to provide an
out-of-the-box solution for importers with various automotive standards.
Each customer can then apply their own validations, business processes,
and data management procedures.

This section details how to import VCdb files in Web UI. For more on
importing VCdb file in STEP workbench, see the **Import Framework**
topic in the **Automotive** section of the **Solution Enablement**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

### Prerequisites

The VCdb Importer screen must be configured in Web UI. Additional
information can be found in the **Using Automotive Importers** topic in
the **Automotive** section of the **Solution Enablement** documentation[
here]{.mcFormatColor style="color: Blue;"}.

### Overview

When a file is uploaded in Web UI, a background process is initiated and
creates an entity in STEP that represents the file. This entity object
is called the \'controller\' and contains some basic data about the file
and the file\'s status in the workflow.

The background process service that runs as part of the import state
allow for business rules to be selected that function in the same way as
standard import rules run, meaning that they act on the objects being
imported.

Importing VCdb file in Web UI
-----------------------------

1.  Click on the link \'VCdb select file\' available in REFERENCE DATA
    IMPORTS widget, or Drag and drop the file to upload the file.
2.  A dialog will display at the top of the screen confirming the file
    has been submitted.
3.  Background processes will start, and Entity objects called \'Entity
    controllers\' will be created.

As the Entity moves through the import workflow, a series of background
processes handle the various processing and import activities.

For more information on workflow states, see the **Import Workflow
Overview** topic in the **Automotive** section of the **Solution
Enablement** documentation[ here]{.mcFormatColor style="color: Blue;"}.

-   The original file name is recorded as the STEP Name of the Entity
    controller.
-   The IDs of the background processes are stored in the Automotive
    Import Flow State BGP attribute.
-   The Import Flow State Status attribute is also noteworthy as it
    stores the status of each process, as opposed to the Import Flow
    Overall Status attribute which displays a global status of the file
    (rather than a per-process status).

All of the information displayed on the Entity controller is also
displayed within the workflow and controller screens in Web UI. These
are discussed in the **Quick Start for Users** topic in the
**Automotive** section of the **Solution Enablement** documentation[
here]{.mcFormatColor style="color: Blue;"}.

Once created, the Entity controller is initiated into the workflow
associated with the importer. From there, the workflow takes over
processing of the file via a series of states using business rules and
background processes to carry out the processing of the file.

It is critical to understand that it is only the Entity controller that
is in the workflow - the objects being acted on (created / updated /
deleted) via information supplied in the import file are not in the
workflow. Therefore, running standard business actions acting on current
object will impact the Entity controller only, not the objects in the
input file.

Each import has an associated workflow, and all proceed through the same
states by default. However, it is intended that customers will expand on
the existing states and actions and add their own validations, means of
reports, and any other additional process as needed.

A new state can be inserted at any point in the workflow, and additional
rules can be added to any of the existing states.

### Sample file structure

1.  A file must be in zip format. Example: AAIA VCdbYYYY ASCII
    YYYYMMD.zip
2.  The zip shall contain the following files as seen in the picture
    below:

Input files are .txt files. The output is based on the input files. In
this case, the classification structure will be created under the
\'AC\_VehicleConfigRoot\' group.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/inputAndOutput.png)

Input:

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/Notepad1.png)

Output: Based on the files \'BodyType.txt\' and
\'BodyStyleConfiguration.txt,\' the classification shown in the
screenshot below will be created.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/5%20door.png)

Input files:

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/Input1.png)

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/Input2.png)

Output: Based on the files \'BaseVehicle.txt,\' \'Model.txt,\'
\'Make.txt,\' and \'VehicleType.txt,\' the following classification
structure will be created under \'AC\_VehicleRoot\' group root.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/Vehicles1.png)

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/Suzuki.png)

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/Aerio.png)

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/Suzuki%20Aerio.png)

Input file:

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/VehicleNotebook1.png)

Output:

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/202%20Suzuki.png)

Input:

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/InputSedan1.png)

Output: Based on the files \'VehicleToBodyStyleConfig.txt,\'
\'BodyStyleConfig.txt,\'and \'BodyType.txt,\' the vehicle will be linked
to the body type via the \'VehicleToBodyStyleConfig\' reference type.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/OutputSedan1.png)

 
