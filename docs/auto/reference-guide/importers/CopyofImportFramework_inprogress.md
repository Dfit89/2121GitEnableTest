---
description: 'Automotive Solution: Describes the Automotive Import
  Framework.'
title: '\[%=Heading.AnyLevel%\]'
---

Import Framework
================

The intention of the import aspect of the Automotive core solution is to
provide out-of-the-box importers for the various automotive standards,
for which each customer can then apply their own validations, business
processes, and data management procedures. To do this successfully, it
is crucial to understand the import framework, which includes the
integration endpoints and workflows created by Easy Setup (as described
in the **Quick Start Setup for Admins** section of the **Automotive
Quick Start Guide**[ here]{.mcFormatColor style="color: Blue;"}).

This section details specifics of the Import Framework, which is
applicable to all Automotive importers across all standards. For more
information on the available automotive importers, see the **Supported
Versions and Formats** topic[ here]{.mcFormatColor
style="color: Blue;"}.

For example:

![](../../Resources/Images/QS/ControllerEntity.png)

As the Entity moves through the import workflow, a series of background
processes handle the various processing and import activities.

-   The original file name is recorded as the STEP Name of the
    controller entity.

```{=html}
<!-- -->
```
-   The IDs of the background processes are stored in the Automotive
    Import Flow State BGP attribute.
-   The Import Flow State Status attribute is also noteworthy as it
    stores the status of each process, as opposed to the Import Flow
    Overall Status attribute which displays a global status of the file
    (rather than a per-process status).

All of the information displayed on the controller Entity is also
displayed within the Web UI Import Controller Screen, which are
discussed in the **Quick Start for Users** section of the **Automotive
Quick Start Guide** [here]{.mcFormatColor
style="color: Blue;font-weight: normal;"}.

Once created, the controller is initiated into the workflow associated
with the importer, and the work of the endpoint stops. From there, the
workflow takes over processing of the file via a series of states using
business rules and background processes to carry out the processing of
the file.

It is critical to understand that it is only the controller Entity that
is in the workflow - the objects being acted on (created / updated /
deleted) via information supplied in the import file are not in the
workflow. Therefore, running standard business actions acting on current
object will impact the controller Entity only, not the objects in the
input file.

In order for the business action to apply to the object(s) that are
getting imported from the input file, the business action needs to be
added to the \'Import action\' parameter in the Background Process
Service Action that runs on the \'Import\' state.

At a high-level, the interaction between the endpoint and the workflow
is as follows:

![](../../Resources/Images/QS/IIEPToWFGraphic.png)

Each import has an associated workflow and all proceed through the same
states by default. However, it is intended that customers will expand on
the existing states and actions to add their own validations, reporting,
and additional processing as needed.

A new state can be inserted at any point in the workflow, and additional
rules can be added to any of the existing states. Additionally, the
ImportFlowExtension interface in the Extension API can be used to create
new background processes to handle what the state should do.
