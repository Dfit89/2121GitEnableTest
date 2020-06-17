---
description: 'Automotive Solution: Describes the \''Validate Application
  Conditions and start in workflow\'' Business Action.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Action: Validate Application Conditions and Start in Workflow
======================================================================

PRODOC note: BOND RDCUST-3365 and PRODOC-1759

The \'Validate Application conditions and start in workflow\' operation
is found within the STEP Workbench Business Rule Editor under the
Automotive menu and requires population of a single parameter
(Workflow). Setup is required in the STEP Workbench for the action to be
available to users.

This business action can ONLY be used within the Import state of a
workflow.

PRODOC note: Delete this because it is not true. This Business Action
can also be used as a Bulk Update. The following is NGK\'s use case per
VEKE: I can actually use this Business Action from outside the workflow.
We've currently set up a workflow for NGK and asked them to run a bulk
update of all their applications periodically to validate their
applications and start them in an invalid applications workflow. So,
they'll at least know which applications are invalid. This is also true
for Validate Application on Import Business Condition, it can also be
used in a bulk update outside of the ACES import workflow.

![](../../Resources/Images/BRs/Validate%20Application%20Conditions%20and%20Start%20in%20Workflow/1.png)

Configuring this business action in the Import state of the relevant
workflow checks for applications with invalid vehicle configurations,
and when a record is found that does not meet the condition, it will
initiate the invalid application records into a workflow configured
within the Workflow parameter of the business action.

The \'Validate Application conditions and start in workflow\' business
action does the same check as \'Validate Application on Import\'
business condition, but instead of rejecting the application, the
\'Validate Application conditions and start in workflow\' business
action imports the invalid application records and starts them in the
configured workflow.

When a record is found that does not meet the condition,an error is
written to the execution report of the import process and the record is
imported .

Below is an example of an error that is written to the execution report
when an assembly (Base Vehicle id) mentioned in the ACES file does not
exist in the STEP database.

PRODOC note: No error message was detected while importing the invalid
ACES File. I assume that it is better that there is a mention of such
changes written in the execution report. Currently, when I write this
document, BEJA, NIFE and SIMO are in a meeting for 2 weeks. I am
assuming to release this document as is for now.

When an application record is found that does not meet the condition, an
error is written to the execution report of the import process and the
invalid application record is imported and then initiated in to the
workflow configured in the business action.

In order to divert invalid application records into a different workflow
when applications with invalid configurations are imported, a business
action with the \'Validate Application conditions and start in
workflow\' operation can be used within the Import state of a workflow.
As a prerequisite, one unique workflow that can handle the invalid
applications is necessary for the invalid application record import. In
all cases, when an importer determines that applications with invalid
configurations should be handled separately, it routes those application
records to the workflow indicated in the business action configuration.
This allows each customer to determine their own strategy for managing
applications with invalid configurations., such as processing the
invalid applications via a workflow.

Configuring Business Action for Applications with Invalid Configuration
-----------------------------------------------------------------------

To properly configure this business action to handle applications with
invalid configurations, the following is needed:

-   Create / Identify a Valid Workflow that Handles Applications with
    Invalid Configurations
-   Configure a Business Action to Use the \'Validate Application
    conditions and start in workflow\' Operation
-   Update Workflow Settings

Create / Identify a Valid Workflow

1.  Create the necessary workflow (or verify that it exists) to be used
    to handle the applications with invalid configurations.
2.  Make the workflow valid for the object type being managed by the
    import.

For example:

-   The workflow used to handle ACES applications with invalid
    configurations must be valid on the AC\_ACESApplication object type.
-   The workflow used to handle TecDoc linkages with invalid
    configurations must be valid on the DS\_Linkage object type.

```{=html}
<!-- -->
```
-   The workflow used to handle NAPA applications with invalid
    configurations must be valid on the NAPA\_Application object type.

Configure a Business Action to Use the \'Validate Application conditions
and start in workflow\' Operation

1.  Create a business action and give it a name that users can easily
    identify. In the example below, the \'Validate Application
    Conditions and Start in Workflow\' name is used.
2.  to the right of the Valid Object Types parameter to find and select
    the necessary object type(s). In the Validate Application Conditions
    and Start in Workflow example below, \'All object types valid\' is
    selected.
3.  On the Operations tab, click the \'Merge into\' button, and the Edit
    Operation dialog will display.
4.  Click on the Edit Operation dropdown, click **Automotive**, and then
    click **Validate Application conditions and start in workflow**.

![](../../Resources/Images/BRs/Validate%20Application%20Conditions%20and%20Start%20in%20Workflow/2.png)

1.  The Workflow parameter will be displayed. Configure the parameter to
    use the necessary workflow.

-   **Workflow:** to find and select the workflow. The configured
    workflow should be able to handle the applications with invalid
    configurations (if any) upon import of the relevant application
    file. The workflow defined in this parameter should be made valid
    for the object type being managed by the import. For the example
    above, the Invalid Application Workflow (created / identified in the
    previous section) valid for AC\_ACESApplication object type is
    selected.

Upon configuration of the \'Validate Application conditions and start in
workflow\' business action, the Automotive solution only provides an
option to import the applications with invalid configuration and start
them in another workflow. Users need to determine their own strategy for
how to handle these invalid applications in another workflow.

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

1.  Go to workbench \> System Setup \> Workflows \> select the workflow
    to be used when validating applications.
2.  Right-click and select **Edit STEP Workflow**.

```{=html}
<!-- -->
```
1.  On the STEP Workflow Designer window, double click on the **Import**
    state to open the State Editor.
2.  Select the **On Entry** tab, and within the Operations tab, click
    the Edit button to display the Edit Operations Dialog (as shown
    below).

![](../../Resources/Images/BRs/Validate%20Application%20Conditions%20and%20Start%20in%20Workflow/3.png)

1.  In the Edit Operation dialog, to the right of the \'Import action\'
    parameter to find and select the business action previously created.
2.  Click the **Save** button and exit the workflow.
