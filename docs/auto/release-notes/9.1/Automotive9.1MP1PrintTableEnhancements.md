---
description: Release notes for the PMDM for Automotive STEP 9.1 MP1
  maintenance patch.
title: '\[%=Heading.AnyLevel%\]'
---

Automotive 9.1 MP1 Print Table Enhancements
===========================================

PRODOC note: This is related to PDO-3365, STEP 9.2, **and** Automotive
9.1 MP1. Per NIFE - Auto 9.1 MP1 is releasing mid-**March** and will be
compatible with core 9.1 MP2. This is the version of the RNs going out
with the Automotive release.

PRODOC note: I think the only existing documentation on print for
automotive is what came out with PDO-2536 / STEP 9.1 (\'Enhancements to
"Application Record Generation" for Print Tables\').

Summary {#summary .RNNoTOC}
-------

One new table transformation, an enhancement of an existing table
transformation, and three new text transformations have been introduced
to the PMDM for Automotive print solution. The table transformations
are:

-   Enhanced \'Row Consolidation\' transformation PRODOC
    note: Automotive only
-   New \'Assign Row/Column Types to Row/Column Numbers\' transformation
    PRODOC note: RDPRT-3867

The new text transformations are:

-   Sort values within cells PRODOC note: RDINT-8076
-   Range consolidation within cellsPRODOC note: RDINT-8077
-   Remove duplicate values within cellsPRODOC note: RDPRT-3865​

Note: Though these are text transformations, they are intended only for
use within tables.

Details {#details .RNNoTOC}
-------

### Enhanced \'Row Consolidation\' transformation {#enhanced-row-consolidation-transformation .RNOrange}

PRODOC note: Automotive only

The automotive Row Consolidation transformation has been enhanced to
allow for adjacent rows to be consolidated (merged together) based on
the data in *more than one* column being different. Previously, the Row
Consolidation transformation would only allow for two adjacent rows to
be consolidated if the data in just *one* specified column was
different. The updated Row Consolidation transformation allows for
adjacent rows to be consolidated even when the data in multiple columns
is different. It also handles the special situation with the
consolidation of date ranges.

The following example shows a table as it appears before the
transformation is applied. The first 5 rows (light blue background) can
be consolidated to one row, and the next two rows (light yellow) can
also be consolidated to one row. The columns that have been allowed to
have different values are: Model, Type, Eng Code, and the four columns
that denote the start / end year and month. Therefore, by elimination,
the data in columns Make, \#Cyl, Eng Size, Fuel, and KW must be
identical for any consolidation to take effect.

![](../../../../Resources/Images/Table%20ComponentImages/AutoRowConsol_Before.png)

After applying the transformation---which will consolidate multiple rows
by repeatedly comparing two adjacent rows---the result will resemble the
following. The differing values in the Model, Type, and Eng Code columns
remain; identical values in the Make, \#Cyl, Eng Size, Fuel, and KW
columns have been merged into one single value; and the differing values
in the start / end year and month columns have been merged into date
ranges.

![](../../../../Resources/Images/Table%20ComponentImages/AutoRowConsol_After.png)

PRODOC note: For additional information on the automotive Row
Consolidation transformation, including configuration instructions and
additional examples, see the **XX** section in the Automotive
documentation.

PRODOC note: An Automotive OLH topic needs to be written for this, but,
we need to check with Silas (SIMO) to find out first of all IF he wants
one, then, WHEN he wants it. Then, WHO needs to actually write it? TWST
has pretty much already done so, but, BOND is the Documenter assigned to
automotive print documentation. If it were only one topic that needed to
be ADDED to the Automotive print documentation that would not be a huge
task for me (KIHE), but, since there is NO existing, published
Automotive print documentation, then the entire section would need to go
live before a single topic can be added \...

### New \'Assign Row/Column Types to Row/Column Numbers\' transformation {#new-assign-rowcolumn-types-to-rowcolumn-numbers-transformation .RNOrange}

PRODOC note: RDPRT-3867

A new \'Assign Row/Column Types to Row/Column Numbers\' table
transformation has been introduced to allow users to assign row and/or
column types to fixed row / column numbers. This is especially useful
after a Pivot Transformation has been applied.

Automotive tables tend to be very structured, using a consistent number
of columns with the same attributes in the same order, and have fixed
column widths. The number of columns can be quite high---15 or more
columns is not unusual. It is also very common that the Pivot
Transformation is required in these tables.

The Pivot Transformation does not allow for the assignment of so many
different column types to the \'common values\' columns. This new
transformation solves this issue by allowing users to assign column
types to these columns after the Pivot Transformation. Further, it can
define the designation of header row types instead of using the Pivot
Transformation.

The following example shows a table in which this transformation will be
used to apply two different column types to four different columns
(columns 7, 8, 9, and 10).

Before the transformation is applied, the columns have no background
shading:

![](../../../../Resources/Images/Table%20ComponentImages/AssignRowColB4.png)

The transformation has been configured to apply the \'Primary PartNo
Column\' column type to columns 7 and 8 and the \'Secondary PartNo
Column\' column type to columns 9 and 10.

![](../../../../Resources/Images/Table%20ComponentImages/AssignRowColTransf.png)

The Primary PartNo Column type has a \'Red Tint\' background and the
Secondary PartNo Column has a \'Silver\' background.

![](../../../../Resources/Images/Table%20ComponentImages/AssignRowColTints.png)

After the transformation is applied, columns, 7, 8, 9, and 10 reflect
the styles of the applied column types.

![](../../../../Resources/Images/Table%20ComponentImages/AssignRowColAfter.png)

### New \'Sort values within cells\' text transformation {#new-sort-values-within-cells-text-transformation .RNOrange}

PRODOC note: RDINT-8076. AJJE note from RDINT-8076: \"Please be aware
that the delimiter \"\\n\" is searching for newlines in the cell value
and not for the string \"\\n\".\"

A new \'Sort values within cells\' text transformation has been
introduced that sorts multiple values when they are contained within a
single table cell. It is available as a selection in the following
locations:

-   \'Row/Column Text Formatting\' table transformation
-   \'Attribute Formatting\' table transformation
-   Within attribute transformations

Entries within a cell may be sorted alphabetically, numerically, or by
fractional values, and in ascending or descending order. Since the
sorting affects multiple values within a single cell, a separator (value
delimiter) must be placed between the values to differentiate them. If a
hard return should separate the entries in a cell, the delimiter of \\n
should be used.

PRODOC note: Users may enter one or more characters to indicate the
delimiter between the entries in a cell. The hard and soft return codes
(\\n and \\r) are accepted characters. Do users literally type in \\n or
\\r or do they just hit the Enter key or hit Shift+Enter? Ask TWST and
AJJE I guess.

The following examples use the pipe character (\|) as the delimiter:

-   The value string \'2002\|2007\|2005\|2012\' becomes
    \'2002\|2005\|2007\|2012\' when sorted using the Ascending and
    Numeric options.
-   \'A\|C\|H\|B\|G \' becomes \'A\|B\|C\|G\|H\' when sorted using the
    Ascending and Alphabetic options.
-   \'DC7\|DC9\|DC13\|DC12\|DC5\|DC6\' becomes
    \'DC5\|DC6\|DC7\|DC9\|DC12\|DC13\' when sorted using the Ascending
    and Numeric options.

The following example shows a table in which this transformation will be
applied to sort values in ascending alphabetic order using the \'/ \'
delimiter. As shown in the field with the ellipsis button, the
transformation has been selected to apply to cells within the \'Engine
Series\' column.

![](../../../../Resources/Images/Table%20ComponentImages/SortValsInCellsDialog.png)

Before the transformation is applied, the values in the Engine Series
column (column 5) display in non-alphabetical order, e.g., AL / AJ / AG
/ AH / AM / AK / AU.

![](../../../../Resources/Images/Table%20ComponentImages/SortValsInCellsB4.png)

After the transformation is applied, the values display in alphabetical
order, e.g., AG / AH / AJ / AK / AL / AM / AU.

![](../../../../Resources/Images/Table%20ComponentImages/SortValsInCellsAfter.png)

### New \'Remove duplicate values within cells\' transformation {#new-remove-duplicate-values-within-cells-transformation .RNOrange}

PRODOC note: RDPRT-3865

A new \'Remove duplicate values within cells\' transformation has been
introduced that removes duplicate values when they are contained within
a single cell of a table. Like the \'Sort values within cells\'
transformation, this transformation is available as a selection in the
following locations:

-   \'Row/Column Text Formatting\' table transformation
-   \'Attribute Formatting\' table transformation
-   Within attribute transformations

This transformation is useful when consecutive rows in a table have been
consolidated into one row. When this is done, the resultant row will
often have cell entries of merged data that require some cleanup and/or
consolidation.

Duplicates are removed by specifying a value delimiter. For example,
using the pipe character (\|) as the delimiter, the string
\'DC9\|DC9\|DC7\|DC12\|DC9\|DC7\' becomes \'DC9\|DC7\|DC12\'. If a hard
return separates the entries in a cell, the delimiter of \\n should be
specified.

PRODOC note: In the following tables example, two adjacent rows exist
that contain identical information except for in one column (Engine
series, again, the fifth column).

![](../../../../Resources/Images/Table%20ComponentImages/RowConsolB4Ex2.png)

The following example shows a table in which a cell contains duplicate
values after a Row Consolidation transformation has been applied. As a
result, in the Engine Series column (column 5), the value \'ED\' appears
twice.

![](../../../../Resources/Images/Table%20ComponentImages/RowConsolAfterEx2.png)

To remove this duplicate value, the \'Remove duplicate values within
cells\' transformation is applied as part of the Row/Column Text
Formatting transformation. It is configured to remove values from the
Engine Series column that are separated by the \' / \' delimiter.

![](../../../../Resources/Images/Table%20ComponentImages/RemoveDupesDialog.png)

After the transformation is applied, the duplicate \'ED\' values are
removed and consolidated into a single value.

![](../../../../Resources/Images/Table%20ComponentImages/RemoveDupesAfter.png)

### New \'Range consolidation within cells\' transformation {#new-range-consolidation-within-cells-transformation .RNOrange}

PRODOC note: RDINT-8077. This one also isn\'t available when doing data
import/export.

A new \'Range consolidation within cells\' transformation has been
introduced that consolidates ranges of data that might exist within a
single cell of a table. Like the \'Sort values within cells\' and
\'Remove duplicate values within cells\' transformations, this
transformation is available as a selection in the following locations:

-   \'Row/Column Text Formatting\' table transformation
-   \'Attribute Formatting\' table transformation
-   Within attribute transformations

As part of the consolidation process, the transformation allows users to
provide delimiter characters to be used between values, as follows:

-   **Value Delimiter:** Users may enter one or more characters to
    indicate the delimiter between the entries in a cell. If a hard
    return separates the entries in a cell, the delimiter of \\n should
    be used.
-   **Range Delimiter:** Users may enter one or more characters that
    denote the delimiter. This delimiter is used when Ranges are created
    as the result of this operation. A range can be created that is
    ascending (low-to-high) or descending (high-to-low). Example:
    2007-2012 or 2012-2007 if a numerical range, and A-F or F-A for an
    alphabetic range.

The following examples assume the value delimiter is the pipe character
(\|) and the range delimiter is a hyphen (-):

-   The string \'2002\|2003\|2004\|2005\|2006\|2007\' becomes
    \'2002-2007\'
-   \'2015\|2014\|2013\|2012\' becomes \'2015-2012\'
-   \'A\|B\|C\|F\|G\|H\' becomes \'A-C\|F-H\'
-   \'2002\|2003\|2004\|2005\|2007\|2008\' becomes
    \'2002-2005\|2007-2008\'

Note: This transformation only operates on numbers or single characters
in the ASCII range \'A to Z\' or \'a to z.\'

The following example shows a table in which a cell contains a range of
values after a Row Consolidation transformation has been applied. The
values are both unsorted and separated by \'\\\\ \' as a delimiter.

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RangeConsolid.png)

To sort these values and convert them into a range, two transformations
are applied. The \'Sort values within cells\' text transformation is
first applied to sort the numbers in ascending numeric order. Next,
\'Range consolidation within cells\' is applied, which has been
configured to remove the \\\\ value delimiters and replace them with \'
to \'.

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RangeConsolid2.png)

After the transformations are applied, the values are consolidated into
a range.

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RangeConsolid3.png)
