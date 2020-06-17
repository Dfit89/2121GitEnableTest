---
title: '\[%=Heading.AnyLevel%\]'
---

Using PAdb Importer in Web UI
=============================

The PAdb is an automotive aftermarket industry standard reference
database to be used in conjunction with PIES. The PAdb defines the way
trading partners exchange information concerning the product-specific
performance and physical attributes of parts.

This section provides details for using Web UI to import PAdb files. For
more on importing PAdb files in workbench, see STEP Automotive Reference
Guide section of the \<PAdb Import in STEP\> documentation.

### Overview

The PAdb is made up of eight (8) tables (8 pipe-delimited text files)
that when used together with an already existing PCdb Parts table,
define a standardized source of Automotive Aftermarket Part Attributes
including their validation and Part Type linkages.

The below mentioned figure describes the basic flow of the project from
the PAdb provided by the Auto Care Association through the several
primary processes of creating the necessary LOVs, matching the required
Units of Measure, creating the PAdb attributes, and linking the PAdb
attributes to the Part Terminologies (sometimes referred to and
configured as Part Type in STEP) as dictated by the PAdb.

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/PAdbDiagramChart.png)

When a file is uploaded in Web UI a background process is initiated and
creates an entity in STEP that represents the file. This entity object
is called the \'controller\' and contains basic data about the file and
the file\'s status in the workflow.

The background process service that runs as part of the Import state
allows for the selection of business rules that function in the same way
as rules run as part of a standard import, meaning that they act on the
objects being imported.

### Prerequisites

The PAdb Importer screen must be configured in Web UI. Additional
information can be found in **the Configuring a PAdb Importer In Web
UI** topic in this documentation here.

 
-

 
-

Importing PAdb file in Web UI
-----------------------------

1.  Click on the link \'PAdb select file\' available in the REFERENCE
    DATA IMPORTS widget, or drag and drop the PAdb file to the \'PAdb
    select file\' importer to upload the file.

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/ReferenceDATAimports.png)

1.  A dialog will display at the top of the screen confirming the file
    has been submitted.

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/SubmitedAAUA.png)

1.  A background process will start, and an Entity object called a
    \'controller\' is created.

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/ImportFlowRoot.png)

As the entity moves through the import workflow, a series of background
processes handle the various processing and import activities.

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/Delta%20Calculation.png)

User action is required for the \'Ready for Import\' state.

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

All of the information displayed on the Entity controller is also
displayed within the workflow and controller screens in Web UI, which
are discussed in the **Quick Start for Users** topic of the
**Automotive** section in the **Solution Enablement** documentation[
here]{.mcFormatColor style="color: Blue;"}.

Once created, the controller is initiated into the workflow associated
with the importer. From there, the workflow takes over processing of the
file via a series of states using business rules and background
processes to carry out the processing of the file.

It is critical to understand that it is only the Entity controller that
is in the workflow - the objects being acted on (created / updated /
deleted) via information supplied in the import file are not in the
workflow. Therefore, running standard business actions acting on current
object will impact the controller entity only, not the objects in the
input file.

Each import has an associated workflow, and all proceed through the same
states by default. However, it is intended that customers will expand on
the existing states and actions to add their own validations, reporting,
and additional processing as needed.

For more information on validation rules, see the **PAdb Import
Validation Rules** topic within this documentation[ here]{.mcFormatColor
style="color: Blue;"}.

1.  Navigate to \'Ready for Import\' state in \'AUTOCARE QDB IMPORT\'
    workflow.

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/AutoCarePADBInport.png)

1.  Select the imported file, and click on the \'Start Import\' button
    to import the file successfully.

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/AutoCarePAdbimports1.png)

### Sample file structure:

1.  File must be in zip format. The naming convention of the Zip file
    should always be in the standardized format 'AAIA PAdb ASCII
    YYYYMMDD' where YYYYMMDD represents the year, month, and the date.
    Example: AAIA PAdb ASCII 20180427
2.  Zip shall contain following 8 following pipe-delimited text files.

-   MetaData.txt
-   MetaUOMCodes.txt
-   PartAttributeAssignment.txt
-   PartAttributes.txt
-   PartAttributeStyle.txt
-   PartTypeStyle.txt
-   Style.txt
-   Version.txt

Please note that the Information regarding the PAdb Attribute
validations will be sourced from three tables (.txt files) namely:
PartAttributes.txt, PartAttributeAssigment.txt and MetaData.txt

### MetaData.txt

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/MetaDatatxt.png)

This file contains the attribute value validation rules and is joined to
PartAttributeAssignment.txt (described below). The relationship between
MetaData.txt to PartAttributeAssignment.txt is a One-to-Many with each
record in MetaData.txt potentially being referenced by many distinct
records in PartAttributeAssignment.txt

In the .txt file the last four fields, DataType, MinLength, MaxLength
and Decimals are used to determine the broadest validation necessary for
creating PAdb attributes in STEP

The MetaData.txt contains the following columns / headers

1.  MetaID: provides the Primary Key and unique identifier for the
    combination of fields 2 through 8 throughout the table.
2.  MetaName: provides the text Name of the Entry.
3.  MetaDescr: provides the text Description of the Entry.
4.  MetaFormat: provides the Abbreviated Format Description.
5.  DataType: provides the Basic Data Type (Text, Integer, Alphanumeric,
    Decimal, etc).
6.  MinLength: provides the Minimum Length Limit (Length of characters).
7.  MaxLength: provides the Maximum Length Limit (Length of characters).
8.  Decimal: determines the number of allowed decimal places.

### PartAttributeAssignment.txt

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/PartAttributeAssignment.png)

PartAttributeAssignment.txt contains the details and/or links to details
for the individual validations for the PAdb Attributes. This information
includes a reference to the Part Terminology, a reference to the
MetaData.txt table \[MetaID\], for attribute value validation rules, a
list of Valid Values if applicable, and a list of applicable unit of
measures, also when applicable. PartAttributeAssignment.txt synchronizes
with the MetaData.txt table in the following manner:

PAdb \> PartAttributeAssignment \> MetaID = PAdb \> MetaData \> MetaID

To recapitulate, this is used to join the PartAttributes table
(PartAttributes.txt) to the MetaData table (Metadata.txt) in order to
fully define PAdb attribute validation.

The PartAttributeAssignment.txt contains the following columns / headers

1.  PAPTID: Provides the Primary Key and unique identifier for the
    combination of fields 2 through 6 throughout the table.
2.  PartTerminologyID: Provides the Foreign Key to PCdb and used within
    STEP to reference the AC\_PartTerminology (Object type of part
    terminology in PCdb. For more information refer Using PCdb Importer
    in Web UI topic (here) within XXXX in STEP OLH).
3.  PAID: provides the Foreign Key to Part Attribute table.
4.  MetaID: provides the Foreign Key to MetaData table.
5.  ValidValues: Provides the List of Allowed Values. The presence of
    data in this field dictates whether a List of Values is applicable
    for this attribute.
6.  UoMList: Provides the List of allowed Units of Measure. The presence
    of data in this field dictates whether units of measure must be
    assigned to this attribute.

**PartAttributes.txt**

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/Friction%20Material%20Bonding%20Type.png)

PartAttributes.txt contains the ID, Name, and Description of each PAdb
Attribute. The relationship between PartAttributes.txt to
PartAttributeAssignment.txt is a One-to-Many with each record in
PartAttributes.txt potentially having many different validations defined
in PartAttributeAssignment.txt (above). The ID from PartAttribute.txt,
\[PAID\], will be used to join the table to the
PartAttributeAssignment.txt table on:

PAdb \> PartAttributes.txtPAID = PAdb \> PartAttributeAssignment.txt \>
PAID

The PAID column provides the Primary Key and unique identifier for the
combination of fields 2 and 3 throughout the table. Contains the data
that will be used to populate the PAdb attribute ID, Name, and
Description fields in STEP.

The PartAttributes.txt contains the following columns / headers.

1.  PAID: provides the Primary Key and unique identifier for the
    combination of fields 2 and 3 throughout the table.
2.  PAName: Provides the Text Name of Entry.
3.  PADescr: Provides the Text Description of Entry

**MetaUOMCodes.txt**

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/Millimeter.png)

The MetaUOMCodes table ties together common industry abbreviations for
units of measure.

The MetaUOMCodes.txt file contains the following 3 columns \'UOMCode,\'
\'UOMDescription,\' \'UOMLabel.\'

1.  UOMCode: Provides the Primary Key and unique identifier for the
    combination of fields 2 and 3 throughout the table.
2.  UOMDescription: Provides the Full Name of Entry.
3.  UOMLabel: provides the Abbreviation of Entry

**PartAttributeStyle.txt**

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/PartAttributeStyle.png)

The PartAttributeStyle.txt file contains the following 2 columns

1.  PaptID: Used in combination with StyleID as a Primary Key / Foreign
    Key to Part Attribute Assignment table.
2.  StyleID: Used in combination with PaptID as a Primary Key / Foreign
    Key to Style table.

**Style.txt**

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/Styletxt-Notepad.png)

The Style.txt file contains the following 2 columns

1.  StyleID: Provides the Primary Key and unique identifier for all
    records in this table.
2.  StyleName: Provides the Text Name of Entry.

**PartTypeStyle.txt**

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/StyleID.png)

The PartTypeStyle.txt file contains following 2 columns

1.  StyleID: Provides the Foreign Key to Style.txt.
2.  PartTerminologyID: Provides the Foreign Key to PCdb

**Version.txt**

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/PAdbVersion%20Provides.png)

The Version.txt file contains following 3

1.  PadbVersion: Provides the Text Version.
2.  PadbPublication: Provides the Date of PAdb Publication.
3.  PCdbPublication column provides the Date of Associated PCdb
    Publication.

If STEP finds that any of the PAdb files contains a different quantity
of columns than is defined above, the process will be stopped and a
message will be recorded in the background process.

**ER (Entity Relation) Diagram**:

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/EREntity%20Relation%20DIagram.png)

**Output**

Upon successful import, the following items will be created or modified
according to the values in the import file.

1.  Product attributes (PAdb Attributes)
2.  PAdb List of Values (LOV's)
3.  PAdb Unit of measurement Attributes
4.  PAdb Version Attribute
5.  PAdb Version Date Attribute

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/AttributeGroups.png)

This also links PAdb Attributes to Part Terminologies as discussed in
the later section below.

### Creating PAdb Attributes

The PAdb Attributes will all be placed in a subgroup of attributes
specific to the PAdb called \[Padb Attributes\] as shown below:

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/AutoCarePAdbAttributes.png)

ID of the Attribute shall always be in the format \'AC\_PAdb\_\' +
\<PAID from Consolidated Attribute List\>

For example: AC\_PAdb\_1, where '1' is the PAID.

The name of the attribute is fetched from the PAName from the
Consolidated Attribute List.

For Eg the attribute \'Brake Shoe Width\' in the input file appears as
shown in the below figure:

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/BrakeShoeWidth.png)

After importing the attribute into STEP the attribute will be created as
shown below:

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/BrakeShoeWidthAC.png)

Creating a PAdb attribute for \'Brake Shoe Width\' is done as detailed
in the below table:

### Creating PAdb LOVs

PAdb LOVs will be created in their own subfolder within the primary LOV
group. The PAdb LOV subfolder will be named \[PAdb LOV Group\] and will
have an ID of \[AC\_PAdb\_LOVGroup\].

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/ACPadb.png)

As semi-colon is used to delineate the valid values in the
PartAttributeAssignment.txt table in the PAdb, thus a semi-colon is not
an allowable character for a valid value by definition.

When creating an LOV, there is a 40 character limit to the length of an
LOV ID. STEP will use the lowest \[PAID\] (from the PartAttribute.txt
table) of all of the attributes referencing an LOV as a part of the
LOV's ID as follows:

ID: \'AC\_PAdb\_\' + \<lowest PAID of all PAdb attributes referencing
the LOV\> + \<STEP generated alphanumeric characters \>

Eg: AC\_PAdb\_16bb5086b1b21b2e86adbfefacfb7fbd

And in the Name of the LOV, the limit to the length of LOV Names is 2000
characters. Step will concatenate all of the allowed values in a given
LOV in alphanumeric order, separated by semi-colons, and use it in the
LOV's name as follows:

Name: \'AC\_PAdb\_\' + \<the list of all valid values in alphanumeric
order, separated by semi-colons\> + \'\_LOV\'

Eg: AC\_PAdb\_Serial;Serial Usb;Usb\_LOV

If an LOV already exists containing the intended PAID (from the
PartAttribute.txt table of the PAdb) in the ID of the LOV, then the PAID
must be suffixed with an incrementing number to ensure uniqueness.

An example of the LOV created in STEP shown below:

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/AC%20LIst.png)Matching
PAdb Units of Measure

PAdb units of measure will be mapped to existing STEP units through the
use of three new description attributes, which will be created and made
valid on Units in STEP and populated with the matching unit of measure
data from the PAdb. Upon importing a PAdb, STEP will check for the
existence of the following three metadata attributes on the existing
units, and if they don't exist, will create them:

1.  PAdb UOM Code
2.  PAdb UOM Description
3.  PAdb UOM Label

These attributes will be created in the PAdb primary Attribute Group in
a \[PAdb UOM\] attribute group as shown below:

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/SystemSetupPAdbUoM.png)

The PAdb Unit of Measure attributes will be set up in the following
fashion:

  PAdb MetaUOMCodes.txt   Code                Description                Label
  ----------------------- ------------------- -------------------------- --------------------
  ID                      AC\_PAdb\_UOMCode   AC\_PAdb\_UOMDescription   AC\_PAdb\_UOMLabel
  Name                    PAdb UOM Code       PAdb UOM Description       PAdb UOM Label

After the Unit of Measure attributes have been created, the attributes
will be added to the Valid Attributes list on Unit under \[System Setup
\> Object Types and Structures \> Basic Object Types \> Units \> Unit\]
which will make them visible on the units of measure in the MetaData
section as seen in Figure below:

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/VaildAttributes.png)

For detailed information on functionalities of units and unit groups,
see the **Units** topic within the **System Setup / Super User Guide**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

### Linking PAdb Attributes to Part Terminologies

PAdb Attributes may be valid on many different Part Terminologies. Part
Terminologies (sometimes also referred to as Part Types) are located in
STEP in the yellow folder structure as shown in the below figure:

For more information on part terminologies, refer to the **Using PCdb
Importer in Web UI** topic within this documentation.

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/PartsCategorization.png)

For instance attribute \'Front Face Color\' is valid on two part
Terminology ID's (Part Terminology ID is described in the
Partattributeassignment.txt Table above)

1.  12554
2.  50606

In STEP, these two part Terminology ID's correspond to the following
Part Types respectfully:

1.  Glove Box (AC\_PartTerminology\_12554)
2.  Glove Box Assembly (AC\_PartTerminology\_50606)

When linking the PAdb attributes to the Part Terminologies, STEP will go
to the References tab for the yellow folder classification for the Part
Type / Part Terminology object the PAdb is being linked to, and will add
the necessary links to PAdb attributes under the Attributes flipper as
shown in the below figure:

![](../../../../Resources/Images/Importers/Standard_AC/PAdb/FrontFaceColor.png)
