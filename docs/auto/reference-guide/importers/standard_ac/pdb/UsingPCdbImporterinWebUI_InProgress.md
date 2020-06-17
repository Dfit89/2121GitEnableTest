---
title: '\[%=Heading.AnyLevel%\]'
---

Using PCdb Importer in Web UI
=============================

The Parts Categorization Database (PCdb) was developed primarily to
support the enhanced standard and replaces the Parts Definition (PD)
table. The PCdb is a critical component of coding catalog applications
data as it addresses the need to categorize groups of aftermarket
replacement parts and commodities. The PCdb standardizes automotive
parts nomenclature and validates parts that are used in multiple
positions on the same vehicle, resulting in a more consistent and
accurate application data.

This section provides details when using Web UI to import PCdb files.
For more on importing PCdb file in the workbench, see the STEP
Automotive Reference Guide section of the \<PCdb Import in STEP\>
documentation here.

### Overview

When a file is uploaded in Web UI, a background process is initiated and
creates an entity in STEP that represents the file. This entity object
is called the \'controller\' and contains basic data about the file and
the file\'s status in the workflow.

The background process service that runs as part of the import state
allows for the selection of business rules that function in the same way
as rules run as part of a standard import, meaning that they act on the
objects being imported.

### Prerequisites

The PCdb Importer screen must be configured in Web UI. Additional
information can be found in the **Configuring a PCdb Importer in Web
UI** topic in this documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Importing PCdb files in Web UI
------------------------------

1.  Click on the link \'PCdb select file\' available in the REFERENCE
    DATA IMPORTS widget, or drag and drop the Pcdb file to the \'PCdb
    select file\' importer to upload the file.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/Reference%20Data%20Imports.png)

PCdb Importer requires single-update mode while running. Additional
information can be found in the **Single-Update Mode** topic within the
**System Setup / Super User Guide** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

1.  A dialog will display at the top of the screen confirming the file
    has been submitted.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/SubmittedAAIA.png)

1.  The background process will start, and an entity object called the
    \'controller\' is created.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/AAIAENitityObj.png)

As the entity moves through the import workflow, a series of background
processes handle the various processing and import activities, such as:

-   The original file name is recorded as the STEP Name for the Entity
    controller.
-   The IDs of the background processes are stored in the Automotive
    Import Flow State BGP attribute.
-   The Import Flow State Status attribute is also noteworthy as it
    stores the status of each process, as opposed to the Import Flow
    Overall Status attribute which displays a global status of the file
    (rather than a per-process status).

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/AutoCarePCDB.png)

User action is required for the state \'Ready for Import.\'

For more information on workflow states, see the **Import Workflow
Overview** topic within the **Automotive** section of the **Solution
Enablement** documentation[ here]{.mcFormatColor style="color: Blue;"}.

All of the information displayed on the Entity controller is also
displayed within the workflow and controller screens in Web UI, which is
discussed in the **Quick Start for Users** topic in the **Automotive**
section in the **Solution Enablement** documentation.

Once created, the controller is initiated into the workflow associated
with the importer. From there, the workflow takes over processing the
file via a series of states using business rules and background
processes.

It is critical to understand that it is only the Entity controller that
is in the workflow - the objects being acted on (created / updated /
deleted) via information supplied in the import file are not in the
workflow. Therefore, running standard business actions acting on current
objects will impact the Entity controller only, not the objects in the
input file.

Each import has an associated workflow, and all proceed through the same
states by default. However, it is intended that customers will expand on
the existing states and actions to add their own validations, reporting,
and additional processing as needed.

For more information on validation rules, see the **PCdb Import
Validation Rules** topic within the **Automotive** section of the
**Solution Enablement** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

1.  Navigate to \'Ready for Import\' state in the \'AUTOCARE PCDB
    IMPORT\' workflow widget.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/DeltaCalcuations.png)

1.  Select the controller, and click on the **Start import** button.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/AutoCarePCdbImport.png)

### Sample File Structure

1.  File must be in zip format., and the naming convention of the Zip
    file should always be in the standardized format 'AAIA PCdb ASCII
    YYYYMMDD' where YYYYMMDD represents the year, month and the date.
    Example: AAIA PCdb ASCII 20180330.zip
2.  Zipped files contain the following pipe-delimited text files

-   Codemaster.txt

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/Condemaster.text.png)

The Codemaster.txt file defines the relationship / hierarchy between the
Categories, Subcategories, Part Terminologies, and Positions.

-   Category.txt

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/Categoriestxt.png)

The Category.txt file contains 2 columns. The first is the ID of the
Category. The name of the Category in STEP comes directly from the
CategoryName column.

-   Subcategory.txt

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/Subcategorytext.png)

The Subcategory.txt file contains 2 columns. The first is the ID of the
Subcategory. Subcategory ID includes a reference to the Category
(determined by the Codemaster.txt file), and the name of the Subcategory
in STEP comes directly from the SubCategoryName column. Subcategories
always exist under a Category in the hierarchy.

-   Parts.txt

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/Partstext.png)

The Parts.txt file contains 3 columns. The first is the ID of the Part
Terminology. The name of the Part Terminology in STEP comes directly
from the PartTerminologyName column. The Part Description ID is used to
update the Part Description, and the Part Terminology always exist under
Subcategories in the hierarchy.

-   Position.txt

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/Position.png)

The Position.txt file contains 2 columns. The first is the ID of the
Position. Position ID includes a reference to the Part Type (determined
by the Codemaster.txt file). The name of the Position in STEP comes
directly from the PositionName column.

-   PCdbChanges.txt

The PCdbChanges.txt file contains a summary of all changes from the last
revision. However, the contents of this file is not used during the
import process.

-   Version.txt

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/Versiontext.png)

The Version.txt file contains only two lines indicating the version date
of the PCdb. This should match the date in the file name. Version date
is stored as a Description attribute (Name=Version Date,
ID=PCdb\_VersionDate) on the Parts Categorization node of the hierarchy.

-   PartsRelationship.txt

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/PartsRelationships.png)

The PartsRelationship.txt file contains 2 columns. The first is the ID
of the source PartTerminology, and the second one is the ID of the
target PartTerminology. Linking of the mentioned IDs will be done
according to the PartsRelationship.txt file through the reference type
'Parts Relationship.'

### ER (Entity Relation) Diagram

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/EREntityRelation.png)

### Output

Upon successful import of a file, based on the **CatogoryID**,
**SubcatogoryID**, and **PartTerminologyID**, the necessary record /
data will be created / updated / deleted under the \'Parts
Categorization (PCdb)\' node in the hierarchy under the respective
folders.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/TreeAccessoriesandFluids.png)

### Category

A category exists if the CategoryID and CategoryName combination are
equal to existing data in STEP. A category is a deletion if the
CategoryID appears in STEP but is not in the input file. A category is
new if the CategoryID does not yet exist in STEP. A category is an
update if the CategoryID exists in STEP and in the input file, but the
CategoryName in the input file is different than what it is in STEP.

### Subcategory

A subcategory exists if the SubCategoryID and SubCategoryName
combination are equal to existing data in STEP. A subcategory is a
deletion if the SubCategoryID appears in STEP but is not in the input
file. A subcategory is new if the SubCategoryID does not yet exist in
STEP. A subcategory is an update if the SubCategoryID exists in STEP and
in the input file, but the SubCategoryName in the input file is
different than what is in STEP.

### Part Terminology

A part exists if the PartTerminologyID and PartTerminologyName
combination are equal to existing data in STEP. A part is a deletion if
the PartTerminologyID appears in STEP but is not in the input file. A
part is new if the PartTerminologyID does not yet exist in STEP. A part
is an update if the PartTerminologyID exists in STEP and in the input
file, but the PartTerminologyName in the input file is different than
what is in STEP.

### CodeMaster

The first column of the file CodeMasterID is ignored during import. The
PositionID is stored below the PartTerminologyID, which is below the
SubCategoryID, which is below the CategoryID in the Parts Categorization
hierarchy. The Codemaster.txt file is critical to STEP because it
indicates which Subcategory a Part Terminology should be linked to, and
which Category a Subcategory should be linked to.

For example, consider the following line from a Codemaster.txt file:

32\|1048\|2\|106\|62

This translates as displayed in Table and Figure below:

  File Header         File Value   STEP Object Type   STEP ID                     STEP Name
  ------------------- ------------ ------------------ --------------------------- -----------------------------------
  PartTerminologyID   1048         Part Type          AC\_PartTerminology\_1048   Ground Effects Kit
  CategoryID          2            Part Category      AC\_Category\_2             Body
  SubCategoryID       106          Subcategory        AC\_SubCategory\_2\_106     Aero Ground Effects and Body Kits
  PositionID          62           Position           AC\_POSITION\_1048\_62      Ground Effects Kit, Bottom

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/PicforDeletionafterReadMessage.png)

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/TreeFOldersCreated.png)

### Position {#position conditions="Primary.Under Construction"}

TBD
