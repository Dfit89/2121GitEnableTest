---
description: 'Automotive Solution: Describes the procedure to track
  objects that is newly added in the importing file in the subsequent
  imports.'
title: 'Use Cases - Tracking Newly Created Objects'
---

Use Cases - Tracking Newly Created Objects
==========================================

The user is responsible for configuring the PMDM for Automotive system
to keep track of all newly created objects on subsequent imports.

Consider an example that a new ACES file is imported into the system and
all applications are stored in the system under their respective
hierarchy. The next time the same file with an addition of few more
applications is imported into the system, the newly created applications
are tracked as defined below.

Track new objects created during import

1.  Create an attribute (or verify that one exists) with the validity
    set to the object type(s) that need to be tracked. In this example,
    an attribute \'New Object\' is created with the validity set to
    object type ACES Application.

![](../../Resources/Images/BRs/1.png)

1.  Configure the business rule to include the newly created attribute
    within the \'New object attribute\' parameter in the \'Set import
    status attributes\' operation. For more information on configuring
    the attribute in the business action, see the topic **Business
    Action: Set Import Status Attributes**[ here]{.mcFormatColor
    style="color: Blue;"}. In the example below, the \'New Object\'
    attribute is defined in the \'Set import status attributes\'
    operation within the business action \'Set Change Flags.\'

![](../../Resources/Images/BRs/21.png)

1.  Configure the **Import** state of the workflow with the updated
    business action discussed in the previous step. For detailed
    procedures on updating the workflow settings, see the topic
    **Business Action: Set Import Status Attributes**[
    here]{.mcFormatColor style="color: Blue;"}. In the example below,
    the Import state in the AutoCare ACES Import workflow is configured
    with Set Change Flags business action.

![](../../Resources/Images/BRs/Set%20import%20status%20attributes%20Add%20To%20WF.png)

When a file is imported, the system evaluates the contents of the import
file as compared to the contents of the database, or against the
previously loaded file of that type. For data that is observed to be a
new object, the importer writes to the defined attribute with a value of
\'true.\' Hereafter, users shall determine their own strategy for
managing the newly added objects.

In the example below, the ACES import created a new application for part
VC21499. Because the application is new, the configured attribute New
Object displays the value of \'true.\'

![](../../Resources/Images/MPNotes/New%20Object%20True.png)
