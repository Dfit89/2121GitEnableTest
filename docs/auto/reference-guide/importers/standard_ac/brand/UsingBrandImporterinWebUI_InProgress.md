---
title: '\[%=Heading.AnyLevel%\]'
---

Using Brand Importer in Web UI
==============================

The intention of the Brand importer of the automotive solution is to
provide an out-of-the-box solution for importing data included within
the Brand file.

This section provides details for using the Web UI to import Brand
files. For importing Brand file in workbench, see the Using Brand
Importer in Workbench topic in this documentation[ here]{.mcFormatColor
style="color: Blue;"}.

### Overview

The Brand Table is a hierarchy that includes parent company names, brand
owners, brands, and sub-brands. A unique four character ID is assigned
to each record in the table.

When a file is uploaded in Web UI, a background process is initiated and
creates an entity in STEP that represents the file. This entity object
is called the \'controller\' and contains basic data about the file and
the file\'s status in the workflow.

The background process service that runs as part of the import state
allows for the selection of business rules that function in the same way
as rules run as part of a standard import, meaning that they act on the
objects being imported.

### Prerequisites

The Brand Importer screen must be configured in Web UI. Additional
information can be found in the **Configuring a Brand Importer in Web
UI** topic in this documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Importing Brand file in Web UI
------------------------------

1.  Click on the link \'Brand select file\' available in the Reference
    Data Imports widget, or drag and drop the Brand file to the \'Brand
    select file\' importer to upload the file.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/BrandSelect.png)

1.  A dialog will display at the top of the screen confirming that the
    file has been submitted.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/SubmittedDialogue.png)

1.  A background process will start, and an entity object called the
    \'controller\' is created.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/workbenchTree.png)

1.  The entity moves through the import workflow, as a series of
    background processes handle the various processing and import
    activities.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/DeltaCalculation.png)

User action is required for the state \'Ready for Import.\'

For more information on workflow states, see the **Import Workflow
Overview** topic within the **Automotive** section of the **Solution
Enablement** documentation[ here]{.mcFormatColor style="color: Blue;"}.

-   The original file name is recorded as the STEP Name of the Entity
    controller.
-   The IDs of the background processes are stored in the Automotive
    Import Flow State BGP attribute.
-   The Import Flow State Status attribute is also noteworthy as it
    stores the status of each process, as opposed to the Import Flow
    Overall Status attribute which displays a global status of the file
    (rather than a per-process status).

Once created, the controller is initiated into the workflow associated
with the importer. From there, the workflow takes over processing the
file via a series of states using business rules and background
processes to carry out the processing of the file.

Each import has an associated workflow, and all proceed through the same
states by default. However, it is intended that customers will expand on
the existing states and actions to add their own validations, reporting,
and additional processing as needed.

For more information on validation rules, see the **Qdb** **Import
Validation Rules** topic within this documentation[ here]{.mcFormatColor
style="color: Blue;"}.

1.  **Navigate** to the \'Ready for Import\' state in the \'Autocare
    Brand Import\' workflow.

2.  **Select** the imported file, and **click** on the \'Start Import\'
    button. The file will be imported successfully.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/AutoCareBrandImports.png)

1.  A dialoge confirming the file submission will display.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/Start_Import.png)

**Sample file structure**

The Brand Table file must have the name 'ParentSupplierBrand' to be
recognized by the AAIA Importer. The Brand Table is a flat
pipe-delimited text file.

Below table outlines the fields in a Brand Table file and how they are
stored in STEP:

+---------------+----------------+----------------+----------------+
| File Name     | File Type      | Example        | Field          |
|               |                |                | Definition     |
+===============+================+================+================+
| BrandID       | Text, 4        | BBXR           | The ID code    |
|               | characters,    |                | assigned to    |
|               | Alpha, no      |                | the Brand.     |
|               | Vowels         |                | Stored in STEP |
|               |                |                | as the ID of   |
|               |                |                | the Brand      |
|               |                |                | object type in |
|               |                |                | the format     |
|               |                |                | 'AC\           |
|               |                |                | _Brand\_XXXX'. |
|               |                |                |                |
|               |                |                | Eg:            |
|               |                |                | AC             |
|               |                |                | \_Brand\_BBXR. |
+---------------+----------------+----------------+----------------+
| BrandName     | Text, Maximum  | Champion Spark | The Name of    |
|               | 80 character,  | Plugs or       | the Brand.     |
|               | alpha-numeric  | Champion       | Stored in STEP |
|               |                | Iridium Spark  | as the Name of |
|               |                | Plugs          | the Brand      |
|               |                |                | object type.   |
+---------------+----------------+----------------+----------------+
| BrandOwnerID  | Text, 4        | BBFG           | The ID code    |
|               | characters,    |                | assigned to    |
|               | Alpha, no      |                | the Brand      |
|               | Vowels         |                | Owner. This    |
|               |                |                | code may be    |
|               |                |                | used in more   |
|               |                |                | than one       |
|               |                |                | record for     |
|               |                |                | Brand Owners   |
|               |                |                | with multiple  |
|               |                |                | Brands and/or  |
|               |                |                | Sub-Brands.    |
|               |                |                | Stored in STEP |
|               |                |                | as the ID of   |
|               |                |                | the Brand      |
|               |                |                | Owner object   |
|               |                |                | type in the    |
|               |                |                | format         |
|               |                |                | 'AC\_Bran      |
|               |                |                | dOwner\_XXXX'. |
|               |                |                | Eg:            |
|               |                |                | AC\_Bra        |
|               |                |                | ndOwner\_BBFG' |
+---------------+----------------+----------------+----------------+
| BrandOwner    | Text, Maximum  | Champion Spark | The Company or |
|               | 80 character,  | Plugs          | Division with  |
|               | alpha-numeric  |                | ownership and  |
|               |                |                | responsibility |
|               |                |                | for brand      |
|               |                |                | management of  |
|               |                |                | the Brand /    |
|               |                |                | Sub-Brand.     |
|               |                |                | This may be    |
|               |                |                | the same as    |
|               |                |                | the Brand      |
|               |                |                | Name.          |
|               |                |                | "Unknown" is   |
|               |                |                | allowed when   |
|               |                |                | the Brand      |
|               |                |                | Owner cannot   |
|               |                |                | be validated.  |
|               |                |                | Stored in STEP |
|               |                |                | as the Name of |
|               |                |                | the Brand      |
|               |                |                | Owner object   |
|               |                |                | type.          |
+---------------+----------------+----------------+----------------+
| ParentID      | Text, 4        | BHSC           | The ID code    |
|               | characters,    |                | assigned to    |
|               | Alpha, no      |                | the Parent     |
|               | Vowels         |                | Company.       |
|               |                |                | Stored in STEP |
|               |                |                | as the ID of   |
|               |                |                | the Brand      |
|               |                |                | Parent object  |
|               |                |                | type in the    |
|               |                |                | format         |
|               |                |                | 'AC\_BRAND     |
|               |                |                | PARENT\_XXXX'. |
|               |                |                | Eg:            |
|               |                |                | AC\_BRAND      |
|               |                |                | PARENT\_BHSC'. |
+---------------+----------------+----------------+----------------+
| ParentCompany | Text, 80       | Federal-Mogul  | The Corporate  |
|               | character,     |                | Entity that    |
|               | alpha-numeric  |                | owns the       |
|               |                |                | Company or     |
|               |                |                | Division       |
|               |                |                | related to the |
|               |                |                | Brand or       |
|               |                |                | Sub-Brand.     |
|               |                |                | This value may |
|               |                |                | be the same as |
|               |                |                | the            |
|               |                |                | BrandOwner.    |
|               |                |                | "Unknown" is   |
|               |                |                | allowed when   |
|               |                |                | the Parent     |
|               |                |                | Company cannot |
|               |                |                | be validated.  |
|               |                |                | Stored in STEP |
|               |                |                | as the Name of |
|               |                |                | the Brand      |
|               |                |                | Parent object  |
|               |                |                | type.          |
+---------------+----------------+----------------+----------------+
| SubBrandID    | Text, 4        | FBRJ           | The ID code    |
|               | characters,    |                | assigned to    |
|               | Alpha, no      |                | the SubBrand.  |
|               | Vowels         |                | Stored in STEP |
|               |                |                | as the ID of   |
|               |                |                | the Sub Brand  |
|               |                |                | object type in |
|               |                |                | the format     |
|               |                |                | 'AC\_SU        |
|               |                |                | BBRAND\_XXXX'. |
|               |                |                | Eg:            |
|               |                |                | 'AC\_SU        |
|               |                |                | BBRAND\_FBRJ'. |
+---------------+----------------+----------------+----------------+
| SubBrand      | Text, 80       | OE Service     | The Name of    |
|               | character,     |                | the SubBrand.  |
|               | alpha-numeric  |                | Stored in STEP |
|               |                |                | as the Name of |
|               |                |                | the Sub Brand  |
|               |                |                | object type.   |
+---------------+----------------+----------------+----------------+
| Revision Date | Date in text   | July 12, 2007  | The date, this |
|               | form           |                | record was     |
|               |                |                | last updated.  |
|               |                |                | Used to        |
|               |                |                | prevent        |
|               |                |                | updating       |
|               |                |                | brands with    |
|               |                |                | earlier        |
|               |                |                | releases.      |
|               |                |                | Stored as an   |
|               |                |                | attribute      |
|               |                |                | (ID=AC\_Bran   |
|               |                |                | dRevisionDate) |
|               |                |                | on the Brand   |
|               |                |                | or Subbrand    |
|               |                |                | object in      |
|               |                |                | STEP. If the   |
|               |                |                | record         |
|               |                |                | contains a     |
|               |                |                | Subbrand,      |
|               |                |                | revision date  |
|               |                |                | is stored      |
|               |                |                | there. If the  |
|               |                |                | record         |
|               |                |                | contains a     |
|               |                |                | Brand only,    |
|               |                |                | revision date  |
|               |                |                | is stored on   |
|               |                |                | the Brand      |
|               |                |                | object. Note:  |
|               |                |                | The date is    |
|               |                |                | translated     |
|               |                |                | into \'ISO     |
|               |                |                | Date\' format  |
|               |                |                | for population |
|               |                |                | of the         |
|               |                |                | revision date  |
|               |                |                | attribute in   |
|               |                |                | STEP.          |
+---------------+----------------+----------------+----------------+

For example, in the input file shown below, consider that the data in
the first row is being imported along with the other data.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/BBBBB.png)

Output: The following Brand parent, Brand owner, Brand and the sub brand
is created.

1.  A classification folder with object type 'Brand Parent', ID
    'AC\_BrandParent\_BBBB' and name '3M' is created.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/3DAutoparts.png)

1.  A classification folder with object type 'Brand Owner', ID
    'AC\_BrandOwner\_BBBB' and Name '3M' is created.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/3M.png)

1.  A classification folder with object type 'Brand', ID
    'AC\_Brand\_BBBB' and Name '3M' is created. Also, a revision date of
    value '2007-07-12' is added.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/34.png)

1.  A classification folder with object type 'SubBrand', ID
    'AC\_SubBrand\_BBBB' and Name 'ScotchBlue' is created.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/Description.png)
