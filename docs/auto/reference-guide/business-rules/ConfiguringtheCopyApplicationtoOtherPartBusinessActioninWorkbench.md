---
description: 'Automotive Solution: Describes how to configure the Copy
  Application to Other Part business action in Workbench.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Copy Application to Other Part Business Action in Workbench
===========================================================================

The \'Copy application to other part\' business operation is found
within the STEP Workbench Business Rule Editor under the Automotive menu
and requires population of a single parameter (Copy application to other
part parameter key). However, setup is required within both STEP
Workbench and Web UI for the action to be available to users. This
section addresses the steps necessary within the workbench.

![](../../Resources/Images/BRs/Copy%20Application%20to%20Other/7.png)

1.  Create the business action with a name that accurately describes to
    the user what this action will do. The name of the business action
    displays within the Web UI and should be easy for the user to
    identify. For this example, the business action name is \'Copy
    Application To Other Part.\'

The business action Name will display to the Application Manager user
once the Bulk Updates action button is selected. If more than one bulk
update is configured, then the name displays both within the Bulk
Applications Update dialog, and within the change part dialog where the
user enters the part for the application (as shown in the example within
the **Using the Configured Copy Application To Other Part Business
Action in Web UI** section of the **Business Action: Copy Application To
Other Part** topic[ here]{.mcFormatColor style="color: Blue;"}).

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
    **Automotive** \> **Copy application to other part** operation, and
    the following parameters will display (as shown above):
    -   **Ignore Part Type:** By default, this optional parameter is
        disabled. This parameter gives an option to check for a part
        type or not before copying an application for a part. If
        unchecked, then trying to copy an application to another part
        that does not have the same part type will fail. If checked,
        User can copy an application to a part of same and / or
        different part type.
    -   **Copy application to other part parameter key:** By default,
        this required parameter is blank. Within the parameter enter a
        unique way (key) to identify this rule. Uniqueness is the only
        restriction for this key. It will not be displayed to the user.
        It is case sensitive.

Common setup is to copy the key so it can be pasted in the Web UI
designer when configuring the business action in Web UI.

7.  Click the **Save** button and continue to the next topic,
    **Configuring the Copy Application to Other Part Business Action in
    Web UI**[ here]{.mcFormatColor style="color: Blue;"}.
