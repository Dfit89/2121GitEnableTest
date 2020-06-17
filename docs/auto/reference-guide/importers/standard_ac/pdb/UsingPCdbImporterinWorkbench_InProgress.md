---
title: '\[%=Heading.AnyLevel%\]'
---

Using PCdb Importer in Workbench
================================

The intention of the PCdb importer for the automotive solution is to
provide an out-of-the-box solution for importing data included within
the PCdb file.

This section provides details on using workbench to import PCdb files.
For a detailed explanation on input file types and output appearances,
see the **Using PCdb Importer in Web UI** topic within this
documentation[ here]{.mcFormatColor style="color: Blue;"}.

### Overview

When an import file is placed in a hotfolder, manually a background
process is initiated and creates an entity in STEP that represents the
file. This entity object is called the \'controller\' and contains basic
data about the file and the file\'s status in the workflow.

The background process service that runs as part of the Import state
allows for the selection of business rules that function in the same way
as rules that run as part of a standard import, meaning that they act on
the objects being imported.

Importing a PCdb file in Workbench
----------------------------------

1.  Place the PCdb file in the application server in the relevant
    hotfolder which is configured in the **AutoCare PCdb Inbound
    Endpoint**.

For example, for a windows system the hotfolder might look like:
/upload/hotfolders/AutoCarePCdbInputFolder

1.  Upon placing the file, a background process will be started and an
    entity object called the \'controller\' will be created based on the
    invoke time scheduled.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/Tree-AAIA.png)

For more information about Schedule Endpoints, see the **Configuring a
PCdb Importer in Workbench** topic in this documentation[
here]{.mcFormatColor style="color: Blue;"}.

1.  The entity moves through various states of the workflow, as a series
    of background processes handle the various processing and import
    activities.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/STEPWorkflow1.png)

For more information on workflow states, see the **Import Workflow
Overview** topic within the **Automotive** section of the **Solution
Enablement** documentation[ here]{.mcFormatColor style="color: Blue;"}.

Once created, the controller is initiated into the workflow associated
with the importer. From there, the workflow takes over processing of the
file via a series of states using business rules and background
processes to carry out the processing of the file.

Each import has an associated workflow and all proceed through the same
states by default. However, it is intended that customers will expand on
the existing states and actions to add their own validations, reporting,
and additional processing as needed.

For more information on validation rules, see the **PCdb Import
Validation Rules** topic in this documentation[ here]{.mcFormatColor
style="color: Blue;"}.

4\. Navigate to the \'Ready for Import\' state in the \'Autocare PCdb
Import\' workflow.

5\. Select the controller, with the \'Start Import\' option selected in
the dropdown. Click on the \'Submit\' button, and the file will be
imported successfully.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/STEPWorkflow.png)

For more information on file structure rules, see the **Automotive Quick
Start Guide** section of the **Using a PCdb Importer** documentation.
