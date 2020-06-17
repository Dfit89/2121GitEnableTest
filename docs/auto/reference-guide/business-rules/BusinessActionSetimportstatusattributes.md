---
description: 'Automotive Solution: Describes the Set import status
  attributes Business Action.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Action: Set Import Status Attributes
=============================================

While not strictly required, it may be helpful to implement change
flags; a way for users to view what data has been created or changed due
to an import.

In order to enable the system to indicate when data is new and/or
changed, metadata attributes and the \'Set import status attributes\'
business action can be used within the Import state of a workflow. At a
minimum, at least one attribute is required for delete statuses, new
statuses, and changed statuses for all imports. If additional
distinction is desired, unique attributes can be created to store
delete, new, and changed statuses for varying objects or imports. In
either case, when an importer determines that data should be flagged as
delete, new, or changed, it writes \'true\' in the attributes indicated
in the business action configuration. This allows each customer to
determine their own strategy for managing delete, new, and/or changed
data, such as processing the new and/or changed data via a workflow.

In the example below, an ACES import created a new application for part
VC21499. Because the application is new, the configured attribute New
Object displays the value of \'true.\'

![](../../Resources/Images/MPNotes/New%20Object%20True.png)

If the application had previously existed and had information changed
during the import, then only the Changed Object attribute value would
display \'true.\'

![](../../Resources/Images/MPNotes/Changed%20Object.png)

This business action can ONLY be used within the Import state of a
workflow. Additionally, an error will occur when delete flags are used
for TecDoc reference data on an 8.2 system. It is recommended that
change flags for TecDoc reference data only be implemented on 8.3 (or
newer) releases.

Configuring Change Flags for New and/or Updated Objects
-------------------------------------------------------

To properly configure this business action to track new and/or updated
objects, the following is needed:

-   Create / Identify Valid Attributes
-   Configure a Business Action to Use the Set Import Status Attributes
    Operation
-   Update Workflow Settings

Create / Identify Valid Attributes

1.  Create the necessary attributes (or verify that they exist) to be
    used to store the new and/or changed data (i.e., Delete Status, New
    Object, Changed Object).
2.  Make sure the attributes are valid for the object(s) being managed
    by the import.

For example, an attribute used in the AutoCare ACES Application Importer
must be valid on ACES Application objects. Alternatively, an attribute
used in the AutoCare PCdb Importer must be valid on all nodes in the
PCdb classification hierarchy.

Configure a Business Action to Use the Set Import Status Attributes
Operation

1.  Create a business action and give it a name that users can easily
    identify. In the example below, Set Change Flags is used.
2.  to the right of the Valid Object Types parameter to find and select
    the necessary object type(s). In the Set Change Flags example below,
    \'All object types valid\' is selected.
3.  On the Operations tab, click the \'Merge into\' button, and the Edit
    Operation dialog will display.
4.  Click on the Edit Operation dropdown, click **Import flow**, and
    then click **Set import status attributes**.

![](../../Resources/Images/MPNotes/6.png)

1.  Three parameters will display. Configure the parameters to use the
    necessary attributes. Some detailed use cases of these parameters
    are explained towards the end of this topic.

-   **Deleted object attribute:** to find and select the attribute which
    is configured in the Delta Calculation state within the \'Delete
    status attribute\' parameter. This parameter clears the delete flag
    status (if any) upon successful import of the same object again. The
    attribute that is used in this parameter should be the same
    attribute that is configured in the Delta Calculation state. For the
    example above, the Delete Status attribute (created / identified in
    the previous section) is selected.

```{=html}
<!-- -->
```
-   **New object attribute:** to find and select an attribute to be used
    to identify when an object is added. For the example above, the New
    Object attribute (created / identified in the previous section) is
    selected.
-   **Updated values attribute:** to find and select an attribute to be
    used to identify when an object is changed. For the example above,
    the Changed Object (created / identified in the previous section) is
    selected.

PMDM for Automotive solution, upon configuration, only provides an
option to automatically erase the existing flags in the attribute marked
for deletion. Wherein the flags (attribute value) marked for notifying
newly added objects and changed objects cannot be erased automatically.
User needs to determine their own strategy for erasing the flags
(attribute value). For information on erasing the existing delete status
flags, see topic **Use Cases - Clearing Delete Status Flag**[
here]{.mcFormatColor style="color: Blue;"}.

7.  Click the **Save** buttons to save and close the business rule.

For more information on creating and/or editing business rules, see the
**Creating a Business Rule or Library** topic ([here]{.mcFormatColor
style="color: Blue;"}), and the **Editing a Business Rule** topic
([here]{.mcFormatColor style="color: Blue;"}) within the **Business
Rules** guide.

Update Workflow Settings

Once the business rule is configured, the necessary workflows need to be
updated to use the business rule. Below are the steps to update a
workflow to use the business rule created in the previous section.

Because the business rule created in the previous section is configured
to work with ACES Application valid object types, the ACES Import
Workflow is used for the example below. If the business rule is
configured to also work with TecDoc and/or NAPA Applications, then those
import workflows would need to also be edited.

1.  Go to workbench \> System Setup \> Workflows \> select a workflow.
2.  Right-click, and select **Edit STEP Workflow**.

```{=html}
<!-- -->
```
1.  On the STEP Workflow Designer window, double click on the **Import**
    state to open the State Editor.
2.  Select the **On Entry** tab, and within the Operations tab, click
    the Edit icon to display the Edit Operations Dialog (as shown
    below).

![](../../Resources/Images/BRs/Set%20import%20status%20attributes%20Add%20To%20WF.png)

1.  In the Edit Operation dialog, to the right of the Import action
    parameter to find and select the business action previously created.
2.  Click the **Save** button, and exit the workflow.

PRODOC note: Per KRMA Using change flags in general is an optional
feature of the system and you wouldn't expect by default that the
importer would apply this information. So it only needs to be in the
reference guide.... In the Business Rules section of the Reference
Guide, document the rule in it's own header. And include there that it
is for use in the import state. Many of the out of the box rules are
related to the various import flow states so we will end up documenting
everything twice if we try to cover it both as part of import and as
part of business rules. So I just want to keep it in business rules and
each rule should describe it's intended place of use if applicable (some
of them can be used anywhere and it's not relevant, but others are
supposed to be used specifically in an Import or Conversion or whatever
and when that is the case, we can state that). If you want, you can add
some statement to the Import Framework Modifications section that says
that there are many out of the box business rules that can be added for
advanced functionality in the importers and to see the Business Rules
section for more info - that will then tie it all together a little
more.
