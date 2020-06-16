---
description: 'PLM Solution: The Edit Reference action is an action used
  for editing an existing reference. It allows users to edit references
  with metadata attributes.'
title: '\[%=Heading.Level1%\]'
---

PLM Edit Reference Action
=========================

The **Edit Reference** action is used for editing an existing reference.
It allows users to edit references with metadata attributes.

The purpose of the PLM Edit Reference action is to edit attributes on a
reference in a dialog and also be able to run validation on the entered
data.

A user can select more than one reference from the list view and select
the PLM Edit Reference (Labeled as Answer Requirement or Answer
Parameter) action in the toolbar.

In the private label food solution, the references for requirements and
parameters have two phases, called scenarios in this guide, in the
product specification process:

-   The customer quality manager user reviews and customizes the
    requirements and parameters for each specification.
-   The supplier user must complete the information needed for
    requirements and parameters in each specification. This is where the
    PLM Edit Reference Action can be used for a Supplier to respond to
    multiple Requirements or Parameters.

Additionally, the **PLM Edit Reference** action has **Flex Valued
Header** capabilities to show and edit flexible values from different
metadata attributes on a reference in one column for the Multi Edit
Display Mode. It also shows attribute values from different attributes
in one column in the Table Display Mode.

For more on how to configure the Edit Reference Action, see the
**Multi-Reference Editor in PLM** topic in the **PLM for Admins**
section of the **Product Lifecycle Management** documentation[
here]{.mcFormatColor style="color: Blue;"}.

Flex Valued Header
------------------

The **Flex Valued Header** is a highly configurable component that
enables the ability to enter more than one validation base type for a
metadata attribute. The validation base types supported are:

-   Date
-   Embedded Number
-   Function for flex attributes
-   Integer
-   Number and Unit
-   Text

The image below describes the metadata attributes on a Requirement
reference using the Reference Metadata Flex Value Header.

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE%2007.png)

For more information on configuring the Flex Valued Header, see the
**Reference Metadata Flex Value Header Component** topic in the **PLM
for Admins** section of the **Product Lifecycle Management**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

The PLMDefiningAttribute must be a single value LOV. This is the
attribute that defines the ID specific of the Validation Base Type to be
allowed. Additionally, defining the Attribute LOV is a LOV with ID. The
ID will be the attribute ID / business function ID used as the flex
attribute.

**Defining Attribute LOVE**

  ID                            Name                          Description
  ----------------------------- ----------------------------- -----------------------------------------------------------------------------------
  PLMDate                       Date                          One of the required specific attributes. The attribute is a date.
  PLMEmbeddedNumber             Embedded Number               One of the required specific attributes. The attribute is an Embedded Number
  PLMFunctionForFlexAttribute   Function for Flex Attribute   A business function that will return the attribute ID to be used.
  PLMInteger                    Integer                       One of the required specific attributes. The attribute is an Integer.
  PLMNumberAndUnit              Number and Unit               One of the required specific attributes. The attribute is a Number and has units.
  PLMText                       Text                          One of the required specific attributes. The attribute is a text.
  PLMISODate                    ISO Date                      One of the required specific attributes. The attribute is an ISO date.
  PLMProductLOV                 Product Dating                One of the required specific attributes. The attribute has an LOV.

The **defining attribute** is used to identify the attribute defined to
control the allowed attribute validations

Supplier Responding to Requirements and Parameters Use Case
-----------------------------------------------------------

The supplier user is responsible for answering the requirements and
parameters specified by the customer for each Recipe Response, Label
Response, and Packaging Response.

1.  The supplier user accesses the Initial Response state of the Private
    Label Food Supplier Response list in the Web UI, selects the
    response (Recipe Response, Label Response, or Packaging Response)
    that needs to be answered, and navigates to the Recipe Requirements
    and/or Parameters tab.
2.  The supplier user then selects requirements or parameter to answer
    from the list view. If more than one requirement or parameter has
    been selected, the requirements / parameter will be displayed in the
    Answer Requirement / Answer Parameter dialog box in the sequential
    order that they were selected.
3.  To edit each of the selected requirements / parameters, the supplier
    user must select the Answer Requirement / Answer Parameters action
    from the toolbar and the Answer Requirement / Answer Parameters
    dialog box will be displayed.

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE9.png)

1.  A supplier can do one or more of the following actions in the Answer
    Requirement / Parameters dialog box:

-   Views requirement / parameters information, such as attribute values
    on the reference.
-   Views help texts for the requirement / parameters and for the
    attributes shown in the dialog.
-   Views and answers the requirement / parameter specific attribute
    defined by the customer quality manager user.
-   View alerts from validations performed by a business function.

The solution associated with this documentation does not include
function validations. A customer may add their own validation business
functions as needed.

-   Save the answer on the reference.

5.  The Answer Requirement / Answer Parameter dialog box will have
    buttons to move back and forward to view the previous or next
    requirement of all selected requirements / parameters.
6.  Clicking the **Save** button will save any supplier user changes.
7.  Clicking the **Cancel** button will cancel any user changes. An
    **Unsaved Changes** warning message will display. The user can click
    **OK** to confirm that changes will not be saved, or they can click
    **Cancel** to go back to the dialog box and **Save** the changes.
8.  Additionally, the Answer Requirements action has the Flex Valued
    Header capability to show and edit values from different attributes
    in one column for the Multi Edit Display Mode or to show attributes
    values from different attributes in one column for the Table Display
    Mode.
