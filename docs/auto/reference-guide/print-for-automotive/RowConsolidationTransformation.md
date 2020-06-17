Row Consolidation Transformation
================================

PRODOC note: RDPRT-3866. This was previously a custom transformation (do
we need to mention this, since it\'s new to everyone else?) I believe
that it is also an expansion of what was known as the Year Consolidation
transformation?

The automotive Row Consolidation transformation has been upgraded to
allow for adjacent rows to be consolidated (merged together) based on
the data in *more than one* column being different. Previously, the Row
Consolidation transformation would only allow for two adjacent rows to
be consolidated if the data in *one* specified column was different. The
updated Row Consolidation transformation allows for multiple selections
of column types and also handles the special situation with the
consolidation of date ranges.

Different date values, such as those for year, are a typical reason that
rows need to be consolidated. When additional information is added, such
as months, then a date range consolidation is also required. This date
range consolidation has been achieved in the enhanced Row Consolidation
transformation.

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RowConsolidation.png)

The following example shows a table as it appears before the
transformation is applied. The first 5 rows (light blue background) can
be consolidated to one row, and the next two rows (light yellow) can
also be consolidated to one row. The columns that are allowed to have
different values are: Model, Type, Eng Code, and the four columns that
denote the start / end year and month.

![](../../../../Resources/Images/Table%20ComponentImages/AutoRowConsol_Before.png)

After applying the transformation---which will consolidate multiple rows
by comparing two adjacent rows---the result should resemble the
following. The differing values in the Model, Type, and Eng Code columns
remain; identical values in the Make, \#Cyl, Eng Size, Fuel, and KW
columns have been merged; and the differing values in the start / end
year and month columns have been merged into date ranges.

![](../../../../Resources/Images/Table%20ComponentImages/AutoRowConsol_After.png)

For additional information on the automotive Row Consolidation
transformation, including configuration instructions and additional
examples, see the **XX** section in the Automotive documentation.

By default, the transformation wants you to merge rows based on
start/end month and year for car models.

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RowConsol2.png)

You click on \'Add Start/End Month & Year\' and then are presented with
four dropdowns representing Start Month, End Month, Start Year, and End
Month. These aren\'t necessarily column types in the system\...

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RowConsol3.png)

From TWST Word doc attached to PRODOC-1237 (NAPA Print Solution) \[I
found this ticket when doing a Jira search for \"Row Consolidation\"
since I knew that this was existing \... \] --

### Consolidating rows based on consecutive numbers in a column {#consolidating-rows-based-on-consecutive-numbers-in-a-column conditions="Primary.PRODOC Note"}

Consider the following table:

![](../../../../Resources/Images/Table%20ComponentImages/AutoAppTableExample.png)

Assume that the table above will already be sorted (using the standard
Sorting transformation) so that similar records are adjacent to each
other. Note that the Year column is sorted in descending order. The
first three rows highlighted in the screenshot are indicative of the
other row groupings in the table:

![](../../../../Resources/Images/Table%20ComponentImages/AutoAppTableExample_Sorted.png)

A "compaction" of Application Records may be done by consolidating on a
specific column type, e.g., the Year column. The list of column types in
the Column Type dropdown displays the valid column types for the table.
The Transformation setup looks like this:

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RowConsol2.png)

For consolidating records based on a Year (or any number), then the
option "Consecutive Numbers" should be chosen. The "Drop Characters at
position" option allows for an entry of 2015-2010 to be curtailed to
2015-10. The "separator" is usually a hyphen but could be any text
string. Based on how the rows were sorted before the transformation, it
will automatically determine whether the year range should be low-high
or high-low (e.g., 2015-10 or 2010-15).

The result of consolidating rows based on the \'Year\' column in this
example would be:

![](../../../../Resources/Images/Table%20ComponentImages/AutoAppTable_RowsConsolidated.png)

Subsequent transformations will organize the table into its final
display.

If any two adjacent rows have identical data (including the Year value),
then the system should consolidate the duplicated row, so the
transformation will avoid the condition of two consecutive identical
rows.

### Error Handling {#error-handling conditions="Primary.PRODOC Note"}

If the selected Column Type occurs more than once in the Table
definition, a warning will be posted and entered in the log. Thus, if
there is more than one column with the Column Type of Spec Type 1:

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RowConsolError.png)

If an additional column is inserted in the Table Definition after the
Row Consolidation transformation has been set up, and the column type is
the one that is already established in the transformation, the system
will again take only first column type encountered in the table and log
the warning.

### Consolidating rows based on different values in a column {#consolidating-rows-based-on-different-values-in-a-column conditions="Primary.PRODOC Note"}

For consolidating rows that do not have consecutive numbers, the "Other"
option should be selected. For example:

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RowConsol4.png)

Here we wish to consolidate these rows based on the Column Type =
Comment. Assume that prior transformations (e.g., sorting) have been
applied before the Row Consolidation transformation is applied. In this
case we would have the options set similar to this:

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RowConsol5.png)

Note that the "Drop characters at position" option is only enabled when
the "Consecutive Numbers" option is selected. And the result would be
like this. Note that consecutive rows with identical values will be
merged and the transformation will avoid the condition of two
consecutive identical rows.

![](../../../../Resources/Images/Table%20ComponentImages/AutoPrint_RowConsol6.png)
