---
description: 'Automotive Solution: Describes the Set Condition Links on
  Part Types Business Action.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Action: Set Condition Links on Part Types
==================================================

This rule is a business action found under the Automotive menu that
serves to link application conditions / options to part types to assist
in configuring display options in the Web UI Application Record Editor
(Application Manager Screen). Additional information on the display
settings can be found in the Application Manager section of this guide
(specifically, the section titled Controlling Display of Conditions in
the Editor) so the details of this functionality are not described.

The rule requires selection of one or more application records and if it
should be applied en masse, it may be useful to use search functionality
and apply the rule as a bulk update using the Run Business Rule
operation in the Bulk Update wizard. When run, the rule will evaluate
all selected applications and identify which conditions are populated on
the applications, per part type. It will then link the attributes or
references representing the conditions to the part types, using standard
attribute links or the Reference Part Type Links metadata attribute as
appropriate.

The business action has two parameters:

-   **Attribute groups:** Select one or more attribute groups that hold
    the condition attributes. All attributes and references in the
    selected group will be evaluated and any that are populated on the
    selected application records will be linked to the part type of the
    application on which it was populated. Attributes and references
    that are not part of the selected group(s) will remain unaltered.
-   **Display condition:** Check this box if the display condition
    should be set to true for the link, meaning that the attribute or
    reference will display in its own column within the editor using the
    \'Application Condition Header - Individual\' column. If unchecked,
    conditions will be linked without the \'true\' display condition,
    meaning that they will show up within the \'Application Condition
    Header - Group\' consolidated column in the editor.

If attribute or reference links already exist on any part type for the
populated conditions, the existing links are not altered by running the
rule - only new links are added.
