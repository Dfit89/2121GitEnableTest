---
description: 'Automotive Solution: Describes the procedure to track
  objects that has underwent any changes in the subsequent imports.'
title: 'Use Cases - Tracking Changed Objects'
---

Use Cases - Tracking Changed Objects
====================================

The user is responsible for configuring the STEP to keep track of all
changed objects on subsequent imports.

Consider an example that a file containing the Brand details is imported
into the system and all Brands including their additional information
are stored in the system under their respective hierarchy. The next time
the same file with any changes in the existing Brands are imported into
the system, the Brands with changes are tracked as defined below.

Track changed objects created during import

1.  Create an attribute (or verify that one exists) with the validity
    set to the object type(s) that need to be tracked. In this example,
    an attribute \'Changed Object\' is created with the validity set to
    object type Brand.

![](../../Resources/Images/BRs/26.png)

1.  Configure the business rule to include the newly created attribute
    within the \'Updated values attribute\' parameter in the \'Set
    import status attributes\' operation. For more information on
    configuring the attribute in the business action, see the topic
    **Business Action: Set Import Status Attributes**[
    here]{.mcFormatColor style="color: Blue;"}. In the example below,
    \'Changed Object\' attribute is defined in the \'Set import status
    attributes\' operation within the business action \'Set Change
    Flags.\'

![](../../Resources/Images/BRs/27mod.png)

1.  Configure the **Import** state of the workflow with the updated
    business action discussed in the previous step. For detailed
    procedures on updating the workflow settings, see the topic
    **Business Action: Set Import Status Attributes**[
    here]{.mcFormatColor style="color: Blue;"}. In the example below,
    the Import state in the AutoCare Brand Import workflow is configured
    with Set Change Flags business action.

![](../../Resources/Images/BRs/Set%20import%20status%20attributes%20Add%20To%20WF.png)

When a file is uploaded, the system evaluates the contents of the import
file as compared to the contents of the database, or against the
previously loaded file of that type. For data that is observed to have
information changed during the import, the importer writes to the
defined attribute with a value of \'true.\' Hereafter, users shall
determine their own strategy for managing the changed objects.

In the example below, the brand 3M had previously existed and had
information changed during the import. Because the brand 3M is changed,
the configured attribute Changed Object displays the value of \'true.\'

![](../../Resources/Images/BRs/25.png)
