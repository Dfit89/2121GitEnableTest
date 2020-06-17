---
description: 'Automotive Solution: Describes the import validation rules
  specific to TecDoc Reference data.'
title: '\[%=Heading.AnyLevel%\]'
---

Reference Data Import Validation Rules
======================================

When importing a TecDoc Reference Data file many STEP validation rules
are performed. The table below describes each of these validation rules,
where the validation check occurs, what happens when a validation fails,
and an example of a failed validation message (when applicable).
However, it does not detail the file type\'s data rules per TecAlliance.

For information on the supported versions, see the **Supported Versions
and Formats** topic[ here]{.mcFormatColor style="color: Blue;"}.

**Accepted File Extension:** ZIP and/or 7z (A compressed archive file
format by the 7-Zip achiever that supports several different data
compression, encryption and pre-processing algorithms.)

PRODOC note: RDCUST-2357 has some good examples of validation errors

+----------------+----------------+----------------+----------------+
| Validation     | Occurs         | When           | Failed         |
| Rule           |                | Validation     | Validation     |
|                |                | Fails          | Message        |
|                |                |                | Example        |
+================+================+================+================+
| Attribute      | Import state   | If \'Continue  | Error: The     |
| validity       |                | on Error\' is  | attribute      |
|                |                | enabled, then  | \'TD\          |
|                |                | the record is  | _ATTR\_BJvon\' |
|                |                | skipped and a  | is not valid   |
|                |                | warning        | for            |
|                |                | displays in    | \'             |
|                |                | the BGP        | classification |
|                |                | report.        | \'TD\          |
|                |                | Otherwise, the | _AXLE\_CODE.\' |
|                |                | import fails.  |                |
+----------------+----------------+----------------+----------------+
| Character      | Import state   | If \'Continue  | Error in this  |
| length limits  |                | on Error\' is  | import         |
|                |                | enabled, then  | 04\_LOVD       |
|                |                | the record is  | efinitions.xml |
|                |                | skipped and a  | setting        |
|                |                | warning        | completed with |
|                |                | displays in    | errors -       |
|                |                | the BGP        | Error: The     |
|                |                | report.        | value \'Value' |
|                |                | Otherwise, the | isn\'t valid   |
|                |                | import fails.  | for LOV \'LOV  |
|                |                |                | ID\': Length:  |
|                |                |                | 60 does not    |
|                |                |                | fit: 'Value.'  |
|                |                |                |                |
|                |                |                | The automotive |
|                |                |                | importer       |
|                |                |                | adheres to the |
|                |                |                | character      |
|                |                |                | length limits  |
|                |                |                | set by         |
|                |                |                | TecAlliance    |
|                |                |                | for each of    |
|                |                |                | the Delta      |
|                |                |                | Keys. These    |
|                |                |                | limits are     |
|                |                |                | listed within  |
|                |                |                | the            |
|                |                |                | TecAlliance    |
|                |                |                | TecDoc Data    |
|                |                |                | Format guide.  |
|                |                |                | When errors    |
|                |                |                | occur, the     |
|                |                |                | error message  |
|                |                |                | includes the   |
|                |                |                | necessary      |
|                |                |                | character      |
|                |                |                | length (as     |
|                |                |                | shown in the   |
|                |                |                | example        |
|                |                |                | above).        |
+----------------+----------------+----------------+----------------+
| Link type      | Import state   | If \'Continue  | Error in this  |
| validity       |                | on Error\' is  | import         |
|                |                | enabled, then  | 06\_Se         |
|                |                | the record is  | arch\_Tree.xml |
|                |                | skipped and a  | setting        |
|                |                | warning        | completed with |
|                |                | displays in    | errors -       |
|                |                | the BGP        | Error: The     |
|                |                | report.        | link type      |
|                |                | Otherwise, the | \'TD\_         |
|                |                | import fails.  | StandardGAToSe |
|                |                |                | archTree(PC)\' |
|                |                |                | is not valid   |
|                |                |                | for            |
|                |                |                | \'             |
|                |                |                | classification |
|                |                |                | \'TD\_GEN      |
|                |                |                | ART\_06911.\'' |
|                |                |                |                |
|                |                |                | For more       |
|                |                |                | information,   |
|                |                |                | see the **Link |
|                |                |                | Type           |
|                |                |                | (Reference     |
|                |                |                | Type) Not      |
|                |                |                | Valid for      |
|                |                |                | Generic        |
|                |                |                | Article**      |
|                |                |                | topic[         |
|                |                |                | here]{         |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
+----------------+----------------+----------------+----------------+
| Missing Object | Import state   | If \'Continue  | Error in this  |
| Type when      |                | on Error\' is  | import         |
| allocating     |                | enabled, then  | 25\_CV         |
| Engine Number  |                | the record is  | TypesAndEngine |
| (MotNr)        |                | skipped and a  | Allocation.xml |
|                |                | warning        | setting        |
|                |                | displays in    | completed with |
|                |                | the BGP        | errors -       |
|                |                | report.        | Error: Missing |
|                |                | Otherwise, the | object type    |
|                |                | import fails.  | for new        |
|                |                |                | object:        |
|                |                |                | TD\_C          |
|                |                |                | V\_TYPE\_23420 |
|                |                |                | of type:       |
|                |                |                | com.stibo      |
|                |                |                | .core.domain.C |
|                |                |                | lassification. |
|                |                |                |                |
|                |                |                | For more       |
|                |                |                | information,   |
|                |                |                | see the        |
|                |                |                | **Missing      |
|                |                |                | Object Type    |
|                |                |                | When           |
|                |                |                | Allocating     |
|                |                |                | Engine         |
|                |                |                | Number**       |
|                |                |                | topic[         |
|                |                |                | here]{         |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
+----------------+----------------+----------------+----------------+
| Object Type    | Import state   | If \'Continue  | ObjectType     |
| existence      |                | on Error\' is  | \'             |
|                |                | enabled, then  | TD\_NoAssembly |
|                |                | the record is  | GroupSynonym\' |
|                |                | skipped and a  | not found.     |
|                |                | warning        |                |
|                |                | displays in    |                |
|                |                | the BGP        |                |
|                |                | report.        |                |
|                |                | Otherwise, the |                |
|                |                | import fails.  |                |
+----------------+----------------+----------------+----------------+
| file version   | Validation     | Import fails   | cvc-           |
| validation     | state          | Validation     | pattern-valid: |
|                |                | state.         | Value          |
|                |                |                | \'somethi      |
|                |                |                | ngWrongBrand\' |
|                |                |                | is not         |
|                |                |                | facet-valid    |
|                |                |                | with respect   |
|                |                |                | to pattern     |
|                |                |                | \'\[B-Z-\[EIOU |
|                |                |                | \]\]\[B-Z-\[EI |
|                |                |                | O\]\]\[B-Z-\[O |
|                |                |                | U\]\]\[A-Z\]\' |
|                |                |                | for type       |
|                |                |                | \'brandType.\' |
+----------------+----------------+----------------+----------------+
| Base vehicle   | Import state   | Record         | An application |
| existence      | via Business   | skipped.       | (id=13) for    |
|                | Action         |                | part: VC36004  |
|                |                |                | has no         |
|                |                |                | assembly       |
|                |                |                | target.        |
+----------------+----------------+----------------+----------------+
| Engine and     | Import state   | Application is | Target         |
| transmission   |                | imported, but  | \'             |
| base existence |                | Condition is   | AC\_EngineBase |
|                |                | NOT imported.  | \_2127123321\' |
|                |                |                | of reference   |
|                |                |                | not found.     |
+----------------+----------------+----------------+----------------+
| File name      | Conversion     | BGP ends in an | Conversion     |
| matches        | state          | error          | stopped due to |
| configuration  |                | triggering the | en error:      |
|                |                | import to      | Current import |
|                |                | enter the      | handling       |
|                |                | Error state.   | configuration  |
|                |                |                | for brand DKGX |
|                |                |                | requires       |
|                |                |                | Supplier       |
|                |                |                | information    |
|                |                |                | that failed to |
|                |                |                | be obtained    |
|                |                |                | from the       |
|                |                |                | filename.      |
+----------------+----------------+----------------+----------------+
| Import mode    | Conversion     | Record is      | Application 16 |
| Full and       | state          | skipped and a  | will be        |
| action = D     |                | warning will   | skipped as the |
|                |                | display in the | import mode    |
|                |                | BGP report.    | FULL only      |
|                |                |                | processes the  |
|                |                |                | applications   |
|                |                |                | with A (Add)   |
|                |                |                | action.        |
+----------------+----------------+----------------+----------------+
| Part existence | Import state   | Record         | A              |
|                | via Business   | skipped.       | C\_PIESItem\_D |
|                | Action         |                | KGX\_BADNumber |
|                |                |                | does not exist |
|                |                |                | for            |
|                |                |                | application    |
|                |                |                | (id=15).       |
+----------------+----------------+----------------+----------------+
| Part           | Import state   | Record         | An application |
| terminology    | via Business   | skipped.       | (id=14) for    |
| existence      | Action         |                | part: VC36004  |
|                |                |                | has no         |
|                |                |                | parttype.      |
+----------------+----------------+----------------+----------------+
| Qualifier      | Import state   | Record is      | Target         |
| existence      |                | imported but a | \'AC\_Qua      |
|                |                | standard STEP  | lifier\_129461 |
|                |                | reference      | 111111111111\' |
|                |                | target not     | of reference   |
|                |                | found error    | not found.     |
|                |                | will display.  |                |
+----------------+----------------+----------------+----------------+
| Text in number | Conversion     | BGP ends in an |                |
| conditions     | state          | error          |                |
|                |                | triggering the |                |
|                |                | import to      |                |
|                |                | enter the      |                |
|                |                | Error state,   |                |
|                |                | and an         |                |
|                |                | exception will |                |
|                |                | display within |                |
|                |                | the conversion |                |
|                |                | report.        |                |
+----------------+----------------+----------------+----------------+
