---
description: 'Automotive Solution: Describes the methods to clear the
  existing delete status flags when the same object is re imported.'
title: 'Use Cases - Clearing Delete Status Flag'
---

Use Cases - Clearing Delete Status Flag
=======================================

When an object marked for deletion is resurrected in a later import, it
is necessary that the previously set delete status flags are erased and
the latest status information of an object is displayed in the system.

The PMDM for Automotive solution provides an option to automatically
erase the existing flags in the attribute marked for deletion. However,
the flags (attribute values) used for identifying newly added objects
and changed objects cannot be erased automatically. In this use case,
the user is responsible for configuring the PMDM for Automotive such
that all the existing delete status flags are erased with the reimport
of the deleted objects.

To clear a delete status flag, choose one of the two configuration
methods as defined below.

Method 1: Using \'Clear delete attribute\' parameter in Delta
Calculation state

1.  In the workflow, double click on the **Delta Calculation** state to
    open the State Editor. Select the **On Entry** tab and click the
    Edit icon on the existing business rule.
2.  Enable the \'Clear delete attribute\' parameter. For more
    information on accessing this parameter, see the topic **Delta
    Calculation State**[ here]{.mcFormatColor style="color: Blue;"}.

![](../../Resources/Images/BRs/28.png)

Method 2: Using \'Set import status attributes\' Operation

1.  Within the Delta Calculation State of the importer workflow,
    identify the attribute configured in the \'Delete status attribute\'
    parameter.
2.  Configure the business rule to include the same attribute within the
    \'Deleted object attribute\' parameter in the \'Set import status
    attributes\' operation. For more information about accessing this
    parameter and business action, see the topic **Business Action: Set
    Import Status Attributes**[ here]{.mcFormatColor
    style="color: Blue;"}. In the example below, \'Delete Status\'
    attribute is configured in the \'Set import status attributes\'
    operation within the business action \'Set Change Flags.\'

![](../../Resources/Images/BRs/30.png)

3.  Configure the **Import** state of the workflow with the updated
    business action discussed in the previous step. For detailed
    procedures on updating the workflow settings, see the topic
    **Business Action: Set Import Status Attributes**[
    here]{.mcFormatColor style="color: Blue;"}. In the example below,
    the Import state in the AutoCare ACES Import workflow is configured
    with Set Change Flags business action.

![](../../Resources/Images/BRs/Set%20import%20status%20attributes%20Add%20To%20WF.png)
