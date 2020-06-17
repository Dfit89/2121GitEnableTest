---
description: 'Automotive Solution: Describes how to configure the Change
  Part Type business action in Web UI.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Change Part Type Business Action in Web UI
==========================================================

7.  Within the Key parameter, enter the exact key created within the
    \'Part type parameter key\' parameter during step 5 of the
    **Configuring the Change Part Type Business Action in Workbench**
    topic ([here]{.mcFormatColor style="color: Blue;"}). This is the
    only required parameter.

```{=html}
<!-- -->
```
11. Click the **Add** button beneath the Root Nodes URLs parameter \>
    select the Root Nodes that the user should be able to choose from
    when changing the part type (For this example AC\_PCdbRoot is
    used) \> click the **OK** button to close the dialog, and return to
    the \'Edit component\' for \'Static Root Nodes Properties\' dialog.
    Optionally repeat this step to add additional nodes for a user to
    browse from when looking for a part type.

![](../../Resources/Images/BRs/Change%20Part%20Type/StaticRootNodesProperties.png)

15. Use the dropdown located beneath the Valid Node Types parameter to
    select **CLASSIFICATION\_TYPE** \> click the **Add** button beneath
    the Valid Node Types parameter so that CLASSIFICATION\_TYPE is
    displayed within the Valid Node Types parameter (as shown below).

```{=html}
<!-- -->
```
16. Click the **Add** button beneath the Valid Object Types parameter \>
    select the desired valid object types (For this example
    AC\_PartTerminology is used)\> click the **OK** button to return to
    the \'Add component - configure required properties\' for the \'Node
    Picker Parameter Properties\' dialog.

![](../../Resources/Images/BRs/Change%20Part%20Type/1.png)

1.  Click the **Add** button, and \'Add component - configure required
    properties\' for the \'Bulk Applications Update Properties\' dialog
    will display (as shown below).

![](../../Resources/Images/BRs/Change%20Part%20Type/UpdatePropertiesPopulated.png)

1.  Click the **Add** button, and the \'Bulk Applications Updates
    Properties\' dialog will display with the newly added Bulk Update
    listed.

![](../../Resources/Images/BRs/Change%20Part%20Type/2.png)

1.  Click the **Save** button and then click the **Close** button to
    close the designer.

To use the newly configured business action, see the **Using the
Configured Change Part Type Business Action in Web UI** section of the
**Business Action: Change Part Type** topic[ here]{.mcFormatColor
style="color: Blue;"}.
