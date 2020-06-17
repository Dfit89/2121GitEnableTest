---
title: '\[%=Heading.AnyLevel%\]'
---

Using Brand Importer in Workbench
=================================

The intention of the Brand importer of the automotive solution is to
provide an out-of-the-box solution for importing data included within
the Brand file.

This section provides details on using workbench to import Brand files.
For a detailed explanation on input file types and output appearances,
see the **Using Brand Importer in Web UI** topic within this
documentation[ here]{.mcFormatColor style="color: Blue;"}.

### Overview

When an import file is placed in a hotfolder, manually a background
process is initiated and creates an entity in STEP that represents the
file. This entity object is called the \'controller\' and contains basic
data about the file and the file\'s status in the workflow.

The background process service that runs as part of the import state
allows for the selection of business rules that function in the same way
as rules that run as part of a standard import, meaning that they act on
the objects being imported.

Importing a Brand File In STEP Workbench
----------------------------------------

1.  Place the Brand file on an application server in a relevant
    hotfolder which is configured in the **AutoCare Brand Inbound
    Endpoint**.

For example: for windows system the hotfolder might look like
/upload/hotfolders/AutoCareBrandInputFolder

1.  Upon placing the file, based on the invoke time scheduled, a
    background process will start, and an entity object called the
    \'controller\' is created.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/ParentSuppliersBrand.png)

For more information on schedule endpoints, see the **Configuring a
Brand Importer in Workbench** topic in this documentation[
here]{.mcFormatColor style="color: Blue;"}.

1.  The entity moves through the import workflow, a series of background
    processes handle the various processing and import activities.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/EnglishUS.png)

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

For more information on validation rules, see the **Brand Import
Validation Rules** topic within **Import Validation Rules** the section
of this guide.

1.  Navigate to the \'Ready for Import\' state in the \'Autocare Brand
    Import\' workflow.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/ReadyforImport.png)

1.  Select the controller, with the \'Start Import\' option selected in
    the dropdown. Once selected, click on the \'Submit\' button.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/Controler-ReadyforImport.png)

1.  A 'Submit items' dialog will display enabling the user to enter in a
    submit message if needed. Click the 'Submit Now' button when
    finished to submit the file.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/SubmitNowSubmitItems.png)

In the 'Import completed' state, the user is given an option to discard
the imported controller. Please note that this will only remove the
controller created, and it cannot delete/modify the changes effected on
the objects in the corresponding import.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/STEPWorkflowItemsCOntroller.png)

For more information on file structure rules, see **Automotive Quick
Start Guide** section of the **Using a Brand Importer** documentation.
