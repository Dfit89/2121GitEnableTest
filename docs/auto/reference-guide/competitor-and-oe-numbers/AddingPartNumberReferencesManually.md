---
description: 'Automotive Solution: Describes how to easily add part
  number references to a selected part in Web UI.'
title: '\[%=Heading.AnyLevel%\]'
---

Adding Part Number References Manually
======================================

Users can easily add an existing competitor and/or OE part number
reference to a selected part within Web UI. When the Part Number
References component is configured, and a part is selected, STEP looks
at the configured Reference Types and displays their targets, attribute
values, and/or metadata via configurations within the \'Part Number
References\' Node Editor component. Whether or not references are
displayed, at a minimum a blank typeahead field will display prompting
users to \'Enter a manufacturer name and/or part number.\' This
typeahead field can be used to manually add a reference from an existing
part number to the selected part.

In the example below, part 90069 is selected within the Web UI Tree, and
an \'OE Numbers\' tab is configured to display results for \'Existing OE
Part Number References.\' Within the results, two Make / Manufacturer
part numbers are displayed, along with the blank typeahead field that
prompts users to \'Enter a manufacturer name and/or part number.\'

![](../../Resources/Images/Competitor%20OE%20Number/30.jpg)

Though a new part number can be created using the Create New Part
dialog, a new manufacturer name cannot be created. For more information
on simultaneously creating a new part number and referencing it to a
selected part, see the **Creating and Referencing New Competitor and/or
OE Part Numbers** topic[ here]{.mcFormatColor style="color: Blue;"}
within this section.

When the manufacturer name and part number exist in STEP, users can type
in the manufacturer name \[space bar\] part number to easily find the
desired part number. Once a manufacturer name is typed into the
typeahead field, available part numbers for the manufacturer will
display in the dropdown list. Clicking a listed part number will add the
part number to the top of the references list.

In the example below, \'lancia 46444\' is typed into the typeahead field
and the Lancia part numbers that begin with 46444 display within the
dropdown list.

![](../../Resources/Images/Competitor%20OE%20Number/34.jpg)

Clicking on 46444287 adds the part number to the top of the references
list, as shown below.

![](../../Resources/Images/Competitor%20OE%20Number/35.jpg)

If the Part Number Suggestions component is configured below the
references list, then the suggestions list will update as new part
numbers are added to the references list. For more information, see the
**Adding Part Number References from Suggestions** topic
([here]{.mcFormatColor style="color: Blue;"}) within this section.
