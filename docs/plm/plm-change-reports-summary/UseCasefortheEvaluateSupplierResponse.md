---
description: 'PLM Solution: When the Chocolate Cookie project reaches
  the Pending Evaluation state of the Private Label Food New Projects,
  all project specifications are in the Evaluate Supplier Responses
  state of the Private Label Food Product Specification'
title: '\[%=Heading.Level1%\]'
---

Use Case for the Evaluate Supplier Response
===========================================

When the Chocolate Cookie project reaches the Pending Evaluation state
of the Private Label Food New Projects, all project specifications are
in the Evaluate Supplier Responses state of the Private Label Food
Product Specification. The quality manager user can start the process to
evaluate supplier responses.

The quality manager user selects the Chocolate Cookie Project Dark
Chocolate Chip \'Recipe Specification\' from the Evaluate Supplier
Responses task list and starts reviewing Supplier A\'s \'Recipe
Response.\'

Since the Change Report component is active when the quality manager
user opens the \'Recipe Responses\' received from Supplier A, changes
between the snapshot and the current data are detected and an active
Change Report notification displays.

![](../../../Resources/Images/Solution%20Enablement/PLM/usecase4.png)

The notification will include an indication that changes were detected
in one or more languages.

The quality manager user clicks on the Change Report notification, and a
dialog displays showing a comparison of the changes that have taken
place in the user login context. The dialog displays three tabs in this
case since the Supplier performed changes to Recipe Ingredients,
Requirements, and Parameters.

The name of the tabs is taken from the value of the attribute \'Snapshot
Display Name\' in the current context. If Snapshot Display Name is
empty, the STEP ID will be shown.

![](../../../Resources/Images/Solution%20Enablement/PLM/usecase5.png)

The order of the tabs is determined by the attribute Snapshot Tab Order
on the link between the Snapshot Configuration and Snapshot Recorder. If
the Snapshot Tab Order attribute is empty, the display order will be
alphabetic.

Each tab will display only the data that was defined by the Snapshot
Recorder and only if there are changes between the current data and the
last snapshot with the Event ID indicated on the Snapshot Configuration.

Each tab will group changes by the type of change. For example, a tab
displaying changes for Requirements during an internal review can show
new requirements that were added, values that were added to an existing
requirement, deleted requirements, values that were deleted from an
existing requirement, and any attribute value changes. The Additions,
Deletions, and Value Changes sections can be collapsed by the user.

In this example of the Change Report Recipe Requirement tab, only value
changes were made to the Recipe Requirements.

![](../../../Resources/Images/Change%20Reports/UseCase6.png)

In this example of the Change Report Recipe Parameters tab, only value
changes were made to the Recipe Parameters.

![](../../../Resources/Images/Change%20Reports/UseCase7.png)

In this example of the Change Report Recipe Ingredients tab, only
additions were made to the Recipe Ingredients.

![](../../../Resources/Images/Change%20Reports/UseCase9.png)

If there are no changes in the Change Report in any language, the Change
Report notification will appear disabled and it is not clickable.

![](../../../Resources/Images/Change%20Reports/UseCase10.png)
