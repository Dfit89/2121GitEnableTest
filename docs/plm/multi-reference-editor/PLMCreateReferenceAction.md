---
description: 'PLM Solution: The PLM Create Reference is a configurable
  action for the PLM private label food solution. It allows users to
  configure a toolbar action, that adds references to an object when
  used with the Multi-Reference Editor.'
title: '\[%=Heading.Level1%\]'
---

PLM Create Reference Action
===========================

The PLM Create Reference is a configurable action for the PLM private
label food solution. It allows users to configure a toolbar action that
adds references to an object when used with the Multi-Reference Editor.
The PLM Create Reference Action can be configured to specify business
rules for consistent creation, object nodes to restrict applicable
references, and validation methods to ensure that the created reference
is allowed. Once the PLM Create Reference Action component is added, it
opens a configurable dialog box.

For more on how to configure the Create Reference Action in the
Multi-Reference Editor, see the **Multi-Reference Editor in PLM** topic
in the **PLM for Admins** section of the **Product Lifecycle
Management** documentation[ here]{.mcFormatColor style="color: Blue;"}.

Multi-Reference Editor Use Case
-------------------------------

The quality manager user is responsible for reviewing the requirement
and parameter references for each Recipe Specification, Label
Specification, and Packaging Specification. They may need to add a
requirement and/or a parameter references to the product in addition to
what was added automatically by the system.

The quality manager user must access the Specify Details state of the
Private Label Product Specification list in the Web UI, and select the
Specification (Recipe Specification, Label Specification or Packaging
Specification) to be maintained.

They can select the Specify Requirements tab to add requirements, or
they can select the Specify Parameters tab to add parameters. The
quality manager user then selects the **Add Requirement** or **Add
Parameter** action in the toolbar.

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE4.png)

Once the Add Requirement or Add Parameter action is executed, it opens a
dialog box.

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE5.png)

The quality manager user can do one or more of the following actions:

-   They can search for a requirement or parameter (typeahead search
    capability embedded in the Add Reference component). The search is
    performed below the specified node. The quality manager user then
    selects the requirement or parameter to be added. If the requirement
    or parameter is already referenced, it will not be enabled for
    selection.

When the requirement or parameter is selected, the following actions
take place:

1.  Business function **PLM Food Get Requirement or Parameter
    Reference** Type is executed and returns the reference type ID to
    use.

```{=html}
<!-- -->
```
1.  The requirement or parameter reference is created.

```{=html}
<!-- -->
```
1.  Business action **PLM Food Copy Requirement or Parameter Template**
    is executed to copy default values from the requirement or parameter
    to populate attribute value(s) displayed in the dialog box.

The quality manager user can now change values for the configured
attributes to be displayed in the dialog box.

The created reference is deleted after the data is displayed in the
dialog including copied values. The reference is then recreated and
committed when the user clicks the Add button.

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE6.png)

-   If **Add Another** box is selected, the **Add a New Requirement** or
    **Add a New Parameter** dialog box will be refreshed after the
    reference is added, so that an additional requirement or parameter
    can be created and added to the Recipe Specification.
-   When the **Add** button is clicked the reference will be created,
    values in the dialog box are saved to the reference and committed,
    and any validation of the data needed will be executed. A business
    action for copying default values in other contexts will be
    executed. If the validation fails, an error is shown in the dialog
    box and the dialog box stays open.
-   Select **Cancel** to cancel the **Add Requirement** or **Add
    Parameter** action.
