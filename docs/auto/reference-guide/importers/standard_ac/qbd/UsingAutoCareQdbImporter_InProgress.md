---
description: 'Automotive Solution: '
title: '\[%=Heading.AnyLevel%\]'
---

Using AutoCare Qdb Importer
===========================

The intention of the Automotive AutoCare Qdb Importer is to provide an
out-of-the-box solution for importing data included within the AutoCare
Qdb (Qualifier Database) file type.

This section addresses the following:

-   Sample Qdb File Structure and Output
-   Importing Qdb Files via Web UI[ here]{.mcFormatColor
    style="color: Blue;"}
-   Qdb Import Validation Rules[ here]{.mcFormatColor
    style="color: Blue;"}
-   Configuring Qdb Importer for Web UI[ here]{.mcFormatColor
    style="color: Blue;"}
-   Configuring Qdb Importer for Workbench[ here]{.mcFormatColor
    style="color: Blue;"}

Sample Qdb File Structure and Output
------------------------------------

This section describes a sample Qdb file structure and output.

### Sample Qdb file structure

-   Whether uploading the file via accessing the application server or a
    file loading widget, the file must be in Zip format. The Example
    file name for this section is: AAIA Qdb ASCII.zip

```{=html}
<!-- -->
```
-   Each Zip file can contain the following files:

```{=html}
<!-- -->
```
-   **Language.txt:** Provides data for translation purposes, but is
    ignored during the AAIA Import process. An example of the contents
    of this file is shown below.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/LanguageID.png)

-   **QdbCHanges.txt:** Outlines all changes to the Qualifier Database,
    but is ignored during the AAIA Import process. An example of the
    contents of this file is shown below.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/QdbChanges.png)

-   **Qualifier.txt:** Provides information within each of the following
    columns:
-   **QualifierID:** Provides the ID of the qualifier.
-   **QualifierText:** Provides the actual text of the qualifier, which
    appears as the name in STEP and as an attribute (Qdb\_QualifierText)
    on the Qualifier object type.
-   **ExampleText:** Provides an example of the qualifier in use, which
    is particularly helpful when the qualifier contains parameters. This
    is stored as an attribute on the Qualifier object type
    (Qdb\_ExampleText).
-   **QualifierTypeID:** Indicates the ID of the qualifier type under
    which the qualifier resides and must match the ID of an existing
    Qualifier Type object type.
-   **NewQualifierID:** Used to supersede the current qualifier to
    another, and is stored in STEP as an attribute
    (Qdb\_NewQualifierID). An entry of '0' indicates no supersession
    applies and no further action is taken. A nonzero entry indicates
    that the current qualifier is being superseded by the indicated
    qualifier ID. In this case, a Classification reference (Reference
    Type=Qualifier Supersession, ID=Qdb\_Supersession) is created
    between the two qualifiers. The new qualifier is the source of the
    reference, and the old qualifier is the target. This reference is
    created upon import of the file only if both qualifiers will exist
    in STEP post-import. Any qualifiers present in STEP, but not
    included in the input file, are removed from STEP.
-   **WhenModifiedDate:** Used to maintain the modification date of the
    qualifier.

An example of the contents of this file is shown below.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/QualifiertxtNotepad.png)

-   **QualifierTranslation.txt:** Provides data for translation purposes
    but is ignored during the AAIA Import process. An example of the
    contents of this file is shown below.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/QualifierTranslationIDQ.png)

-   **QualifierType.txt:** Provides information within each of the
    following columns:
-   QualifierTypeID: Provides the ID of the Qualifier Type as referenced
    in the other files. The STEP ID for the qualifier type prefixes the
    QualifierTypeID with \'AC\_QualifierType\_\'
-   QualifierType: Provides the name of the Qualifier Type in STEP.

An example of the contents of this file is shown below.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/QualifierTypeID.png)

In the example below the Fitment Qualifier Type has been created within
the Qualifiers (Qdb) Object type of the AutoCare Root.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/Fitment.png)

-   **Version.txt:** Contains only two lines indicating the version date
    of the Qdb. This should match the date in the file name. Version
    date is stored as a description attribute (Qdb\_VersionDate) on the
    Qualifier Group node of the hierarchy. An example of the contents of
    this file is shown below.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/VersionDate.png)

In the example below the Qdb Version Date attribute is displayed within
the Qualifiers (Qdb) Object type of the AutoCare Root.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/Qualifiers%20and%20Cautlon.png)

### Sample Qdb Output:

Upon successful import of a file, based on the qualifier type ID, the
necessary record / data will be created / updated under the \'Qualfiers
(Qdb)\' node in the hierarchy under the respective folders.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/Qualifiers(Qdb).png)

For example, in the import file, if the qualifier is specified with the
Qualifier Type ID of five. Then the qualifier will be created / updated
under the 'Product' folder.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/QualifierType.txt.png)
