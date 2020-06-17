---
description: 'Automotive Solution: Describes the procedure to track
  objects that is deleted from the importing file in the subsequent
  imports.'
title: 'Use Cases - Tracking Deleted Objects'
---

Use Cases - Tracking Deleted Objects
====================================

The user is responsible for configuring STEP to keep track of all the
deleted objects on subsequent imports and handle the deleted objects
manually in the system.

While importing, if an object is missing in the import file compared to
what is in STEP, the import does not automatically delete the object.
However, It will populate the delete flag attribute with a value of
\'true\' on the object to indicate that the object is missing and/or
deleted in the imported file. This allows the user to determine their
own strategy for managing deletions, such as processing the deletions
via a workflow.

Consider an example that a file containing the Brand details is imported
into the system and all Brands including their additional information
are stored in the system under their respective hierarchy. The next time
the same type of file is imported with some brand name deleted, the
deleted Brand names are tracked as defined below.

Track objects deleted during import

1.  Create an attribute (or verify that one exists) with the validity
    set to the object type(s) that need to be tracked. In this example,
    an attribute \'Delete Status\' is created with the validity set to
    object type Brand.

![](../../Resources/Images/BRs/22.png)

1.  Within the Delta Calculation state of the workflow, configure the
    newly created attribute within the \'Delete status attribute\'
    parameter. For more information on configuring the attribute in the
    workflow, see the topic **5. Update Delete Status Attribute and
    Delta Calculation Method in Import Workflows**[ here]{.mcFormatColor
    style="color: Blue;"}. In the example below, the attribute Delete
    Status is configured within the Delta Calculation state in the
    AutoCare Brand Import workflow. Setting the Delete Status attribute
    in this state is what writes the value to the Delete flag.

![](../../Resources/Images/BRs/23.png)

Each workflow has a Delta calculation method where the importer
evaluates the contents of the imported file to the contents in the
database (\'context\' method), or against the previously loaded file of
that type (\'file\' method) to remove unchanged objects (it will take
failed imports and errors into account). While doing this it will
collect all IDs in the current import file. However, the Delta
Calculation to calculate the delete flag (regardless if \'file\' or
\'context\' method is used) will go through the entire hierarchy in the
database and see what is present in the database but not in the current
file. The objects that are in the database but not in the import file
will be added to the delete file and have the configured delete status
attribute set to \'true.\' For data that is determined to require
deletion, the importer does not actually delete the data, but instead
writes to the defined attribute that the data *should* be deleted. This
allows each customer to determine their own strategy for managing
deletions, such as processing the deletions via a workflow.

In the example below, the Brand import has a brand name \'3M\' deleted.
Because the brand name \'3M\' is deleted in import file, the configured
attribute Delete Status displays the value of \'true.\'

![](../../Resources/Images/BRs/24.png)
