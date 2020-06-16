---
description: 'PLM Solution: For the Multi-Reference Editor, several
  business rules can be configured. Each of the business rules will be
  described in detail in this section.'
title: '\[%=Heading.Level1%\]'
---

Multi-Reference Editor Business Rules
=====================================

For the Multi-Reference Editor (MRE), several business rules can be
configured. Each of the business rules will be described in detail in
this section.

Get Reference Type -- Business Function
---------------------------------------

This business function is used by the **PLM Create Reference Action**
component to get the reference type ID that will be used to create the
new reference.

It has two input parameters:

-   Source object of the type Node which is the owner of the reference
    that will be created
-   Target object of the type Node which is the target object of the
    reference that will be created

The return type of the business function is in the format of a string,
containing the STEP reference type ID.

Below is an example of a business function that is used in the private
label food solution to get the reference type ID when adding a
requirement or a parameter to a variant.

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE10.png)

Copy From Template- Business Action
-----------------------------------

This business action is used by the **PLM Create Reference Action**
component for getting default values to display in the Multi-Reference
Editor (MRE).

The low-level processing flow to display default values in the MRE
dialog is:

1.  Start a transaction.
2.  Create a reference between the source and target object using the
    reference type ID returned by the \'get reference type -- business
    function\'.
3.  Execute the defined \'copy from template -- business action\'. This
    will populate values on the created reference in step 2.
4.  The MRE dialog reads the defined attribute values from the reference
    that was created in step 2 and has default values populated in
    step 3.
5.  MRE dialog is shown.
6.  The transaction is rolled back.

Any values that are copied to the created reference that are not
displayed in the MRE dialog will be deleted when the reference is
deleted (rolled back). The values in the MRE dialog will be saved to a
new reference when the user clicks the save button in the MRE dialog.

This business action has a bind that is an instance of the reference
object that was created in step 2 above.

Below is an example for a business action that is used in the private
label food solution to copy default values based on attributes in an
attribute group when adding a requirement or parameter.

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE11.png)

Validation -- Business Function
-------------------------------

This business function is used by the **PLM Create Reference Action**
and the **PLM Edit Reference Action** components to validate the entered
data in the Multi- Reference Editor (MRE) dialog.

It has two input parameters:

-   Source object of the type Node which is the owner of the reference
    that was created
-   Target object of the type Node which is the target object of the
    reference that was created

The return type of the business function is in the format of a
list\<String\>, which is a list of strings containing pairs of values
where the first value is the attribute name and the second value is the
validation error message. The validation error message can contain html
tags including links (a href)

PRODOC note: Jan says that even though this is not used the in PLM food
solution, we need to tell the reader how to create a validation if they
need to, independently of if one is used or not.

Below is an example of a validation -- business function. This example
is not used in the private label food solution.

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE12.png)

The validation errors are shown to the user in a dialog as shown below:

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE13.png)

Copy From Template (Context) -- Business Action
-----------------------------------------------

This business action is used by the **PLM Create Reference Action**
component for copying additional values to the created reference,
including values in other contexts than the current context. An example
of copying values in other contexts could be that when working in the US
English context, and adding a new parameter to a variant, we need to
populate the default help text in Spanish and potential other contexts
as well.

This business action has a bind which an instance of the reference
object.

Below is an example for a business action that is used in the private
label food solution to copy default values based on attributes in an
attribute group when adding a requirement or parameter. This is the same
business action used in the \'copy from template -- business action\'.
The business action is copying attribute values for all of the
system-defined contexts.

![](../../../Resources/Images/Solution%20Enablement/PLM/MRE14.png)
