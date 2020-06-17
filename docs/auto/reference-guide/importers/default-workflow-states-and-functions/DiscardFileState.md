---
description: 'Automotive Solution: Describes the functions of the
  Discard File default workflow state.'
title: '\[%=Heading.AnyLevel%\]'
---

Discard File State
==================

When a controller enters the Discard File state, it is automatically
removed from the workflow via a business rule running on entry to the
state. This means that information about the file and processing of it
is no longer visible in Web UI workflow screens, though the controller
entity itself still exists in STEP. Customers should consider if they
would like additional \"clean up\" actions to occur at this point, such
as deleting the entity in STEP and/or deleting the generated files or
background processes from the application server.

Clicking the **Discard file** button will cause the Discard file dialog
(shown below) to display at the top of the screen. A user must click the
\'X\' in the top right of the dialog to close it.

![](../../../Resources/Images/Importers/Standard_TD/Reference/5.png)

Properties can be set in the sharedconfig.properties file on the
application server to manage auto-deletion of the background processes.
This is done using the format:
**AutoDeleteBackgroundProcesses.AgeInHours.\[Service\] = \[hours\]**.
Note that deletion of the background processes will remove the end
user\'s ability to view warnings and errors for the processes in the Web
UI. It is recommended to set up auto-deletion, but care should be taken
to set the timing to an appropriate value for the end user processes.

For example, to set the AutoCare validation processes to delete after 48
hours, specify:

    AutoDeleteBackgroundProcesses.AgeInHours.AutoCareValidationService = 48
