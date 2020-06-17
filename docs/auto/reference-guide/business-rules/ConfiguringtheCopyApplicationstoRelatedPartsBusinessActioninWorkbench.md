---
description: 'Automotive Solution: Describes how to configure the Copy
  Applications to Related Parts business action in Workbench.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Copy Applications to Related Parts Business Action in Workbench
===============================================================================

The \'Copy applications to related parts\' business operation is found
within the STEP Workbench Business Rule Editor under the Automotive menu
and does not offer additional parameters, but does require the use of
the reference type \'Part Relation.\' Setup is required within both STEP
Workbench and Web UI for the action to be available to users. This
section addresses configuring the reference type and business action
within the workbench.

Configuring the Reference Type
------------------------------

Before the business action can be used within Web UI, the reference type
\'Part Relation\' must be populated with one or more parts that relate
to the selected part. If the business rule is run against an application
using a part that has a blank Part Relation parameter, then no changes
will occur. In the example below, parts VC21499 and VC36009 have part VC
36112 populated within the Part Relation reference type.

![](../../Resources/Images/BRs/Copy%20Application%20to%20Related/WBVC21499.png)

Configuring the Business Action
-------------------------------

Before the business action can be used within Web UI, the business
action must be created. Below are the steps required to create the
business action.

![](../../Resources/Images/BRs/Copy%20Application%20to%20Related/WBCreate.png)

1.  Create the business action with a name that accurately describes to
    the user what this action will do. The name of the business action
    displays within the Web UI and should be easy for the user to
    identify. For this example, the business action name is \'Copy
    Applications To Related Parts.\'

The business action Name will display to the Application Manager user
once the Bulk Updates action button is selected. If more than one bulk
update is configured, then the name displays both within the Bulk
Applications Update dialog, and within the copy applications to related
parts dialog where the user enters the part for the application (as
shown in the example within the **Using the Configured Copy Applications
To Related Parts Business Action in Web UI** section of the **Business
Action: Copy Applications To Related Parts** topic[ here]{.mcFormatColor
style="color: Blue;"} within this guide).

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
    **Automotive** \> **Copy applications to related parts** operation,
    and the Save button will become active (as shown above).

```{=html}
<!-- -->
```
1.  Click the **Save** button and continue to the next topic,
    **Configuring the Copy Applications To Related Parts Business Action
    in Web UI** ([here]{.mcFormatColor style="color: Blue;"}).
