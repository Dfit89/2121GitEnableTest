---
description: 'Automotive Solution: Describes how to configure the Change
  Assembly Business Action in Workbench.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Change Assembly Business Action in Workbench
============================================================

The \'Change assembly\' business operation is found within the STEP
Workbench Business Rule Editor under the Automotive menu and requires
population of a single parameter (Assembly parameter key). However,
setup is required within both STEP Workbench and Web UI for the action
to be available to users. This section addresses the steps necessary
within the workbench.

![](../../Resources/Images/BRs/Change%20Assembly/WB.png)

1.  Create the business action with a name that accurately describes to
    the user what this action will do. The name of the business action
    displays within the Web UI and should be easy for the user to
    identify. For this example, the business action name is \'Change
    Base Vehicle Assembly.\'

The business action Name will display to the Application Manager user
once the Bulk Updates action button is selected. If more than one bulk
update is configured, then the name displays both within the Bulk
Applications Update dialog, and within the change assembly dialog where
the user enters the assembly for the application (as shown in the
example within the **Using the Configured Change Assembly Business
Action in Web UI** section of the **Business Action: Change Assembly**
topic[ here]{.mcFormatColor style="color: Blue;"} within this guide).

1.  Edit the new business rule, next to the Valid Object Types parameter
    and select the valid object types for this business action. For this
    example, the \'ACES Application\' object type is selected, however
    the TecDoc and NAPA applications can also be selected within the
    same or separate business actions. This decision is at the
    discretion of the administrator.
2.  On the Operations tab of the Business Rule Editor, click the **Add
    new Business Action** link, and click the edit button to open the
    Edit Operation dialog.
3.  Use the dropdown menu within the Edit Operation dialog to select
    **Automotive** \> **Change assembly** operation, and the parameter
    \'Assembly parameter key\' will display (as shown above).
4.  Within the parameter enter a unique way (key) to identify this rule.
    Uniqueness is the only restriction for this key. It will not be
    displayed to the user. It is case sensitive.

Common setup is to copy the key so it can be pasted in the Web UI
designer when configuring the business action in Web UI.

1.  Click the **Save** button and continue to the next topic,
    **Configuring the Change Assembly Business Action in Web UI**
    ([here]{.mcFormatColor style="color: Blue;"}).
