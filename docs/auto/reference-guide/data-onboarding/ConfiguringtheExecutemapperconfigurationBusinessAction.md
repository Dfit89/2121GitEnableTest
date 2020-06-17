---
description: 'Automotive Solution: Describes how to configure the
  Execute mapper configuration Business Action in Workbench.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Execute Mapper Configuration Business Action
============================================================

The \'Execute mapper configuration\' business operation is found within
the STEP Workbench Business Rule Editor under the Mapping menu and
requires population of a mapper configuration. This section addresses
the steps necessary for configuring the \'Execute mapper configuration\'
business action within the workbench.

![](../../Resources/Images/Data%20Onboarding/5.png)

1.  Create the business action with a name that accurately describes to
    the user what this action will do. For this example, the business
    action name is \'PIES Item to NAPA Product.\'

```{=html}
<!-- -->
```
1.  Edit the new business rule, next to the Valid Object Types
    parameter, and select the \'All Object Types\' for this business
    action.
2.  On the Operations tab of the Business Rule Editor, click the **Add
    new Business Action** link, and click the edit button to open the
    Edit Operation dialog.
3.  Use the dropdown menu within the Edit Operation dialog to select
    **Mapping** \> **Execute mapper configuration** operation, and the
    parameter \'Mapper configuration\' will display (as shown above).
4.  Within the parameter, and select the desired Mapper Configuration
    from the list of available Mapper Configurations.

A different Business Action will need to be created for each different
mapper configuration so that the Business Action can be used wherever
the mapping needs to be executed.

1.  Click the **Save** button.
