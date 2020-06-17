---
description: 'Automotive Solution: Describes how to control the display
  of conditions in the Application Manager Results Table and Application
  Coverage Report.'
title: '\[%=Heading.AnyLevel%\]'
---

Application Condition Header Components
=======================================

The Application Manager results table can be configured to display
vehicle option data for applications within columns using the following
two header components:

-   **Application Condition Header - Individual**: Allows table headers
    to be expanded to display condition attributes and/or references in
    individual columns. Condition attributes can be displayed in their
    own column in the results table and/or Application Coverage Report
    when one of the following are configured:
-   Condition attribute is linked to the part type of the application,
    and has metadata DisplayCondition=true.
-   Condition attribute is linked to the part type of the application,
    and has an attribute ID = ReferencePartTypeLinks valid on a part
    type that contains \'true\' after the reference ID.
-   **Application Condition Header - Group**: This is used to group
    multiple conditions into a single column and requires that one or
    more attribute groups be selected for which all attributes and
    references in that group will be evaluated. Any attributes or
    references that have values but do *not* have the attribute linked
    to the part type with a DisplayCondition=true are displayed in a
    single column using this header. Clicking in the cell to edit
    options will open the Value editor where all populated options are
    displayed, along with all unpopulated options that are linked to the
    part type but do not have a true display condition. A search feature
    is also available to add unlinked options to the Value editor for
    population.

As described above, whether a vehicle option is displayed in its own
column or in a consolidated column, and whether or not it displays by
default in the Value editor or must be searched for, is determined by if
and how the condition is linked to the part type.

If the condition is modeled using an attribute, the condition link is
handled via a simple attribute link to the part type classification.

In the example below:

-   **ACES Brake ABS** and **ACES Brake System** are both linked to the
    part type and have a \'true\' Display Condition, allowing them to
    display within the Value editor, in their own columns and in the
    order indicated by the Display Sequence within the Application
    Manager results table.
-   **ACES Mfr Label** and **ACES Quantity** both have values but are
    not linked to the part type, so they are displayed in the
    consolidated column and in the Value editor.
-   **ACES Position** is also linked, but without a true Display
    Condition so it is displayed in the Value editor by default. Any
    other conditions can be accessed by typing in the search field.

![](../../../../Resources/Images/QS/AttributePartTypeLinks.png)

In the screenshot below, the **ACES Brake System** and **ACES Brake
ABS** attributes are displayed as individual columns within the results
table of an Application Manager. Whereas, the **ACES Mfr Label**,
**ACES Position**, and **ACES Quantity** display within the Value
editor.

![](../../../../Resources/Images/QS/AttributePartTypeLinksInEditor.png)

The behavior of the Value editor is the same, whether the condition is
modeled using an attribute or a reference. However, on references, the
condition link is modeled using the Reference Part Type Links metadata
attribute (ID=ReferencePartTypeLinks). The Reference Part Type Links
attribute is created by Easy Setup and made valid on part type objects
in the Classification Hierarchy for any standards for which setup has
been run (e.g., Part Terminology for AutoCare, MPCC for NAPA, and
Generic Article for TecDoc). It can then be populated on part types
using the same concepts as with an attribute, where both a display
condition and display sequence are indicated. For example, in an
AutoCare model where Engine Base and Transmission Base are references,
if you wanted to make these options available on a particular part type,
you would populate the Reference Part Type Links attribute on that part
type using the following syntax:

\[**ReferenceType ID**(string)\]**:**\[should it be displayed in
separate column(boolean -
**true/false**)\]**:**\[IntegerForSortSequence(**integer**)\]

For example:

![](../../../../Resources/Images/QS/ReferencePartTypeLinks_workbench.png)

Since the transmission reference is set to false and the engine
reference is set to true, the engine option is displayed within its own
column in the Application Manager results table, and the transmission
option is only displayed within the Value editor (as shown below).

![](../../../../Resources/Images/QS/ReferencePartTypeLinks_editor.png)

PRODOC note: MEDU RDCUST-2420 Fixed Application Condition Header - Group
component to display newly added conditions with filtered values based
on the validation path. Previously in Application Editor, when a new
condition is added in the condition editor, the list of values to select
from would be empty. The Application Condition Header - Group component
has been fixed so that when a new condition is added in the condition
editor, values will be displayed to select from. The values are filtered
based on the Automotive Validation Path that is configured on the
condition attribute.

PRODOC note: Application Condition Header - Individual component in
Application Editor be displayed in alphabetical order if Display
Sequence is not populated Previously, if multiple conditions are added
for individual column display in the Application Editor, they would be
displayed in random order if the Display Sequence attribute is not
populated. The Application Condition Header - Individual component has
been updated so if the Display Sequence is not populated for any of the
individual conditions, then the individual conditions will be displayed
in alphabetical order. If some individual conditions have Display
Sequence populated and some do not, then the conditions with the Display
Sequence populated will be handled first in the order of the Display
Sequence number. Then the conditions without Display Sequence populated
are handled next and displayed in alphabetical order.
