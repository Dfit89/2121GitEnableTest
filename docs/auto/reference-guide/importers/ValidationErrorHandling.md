---
description: 'Automotive Solution: Describes the functions of the
  Validation Error Handling default workflow state.'
title: '\[%=Heading.AnyLevel%\]'
---

Validation Error Handling
=========================

PRODOC note: MEDU - I plan for this to be viewed a child to the Default
Workflow and States Topic

Each import has some basic format validations applied, and each
implementation must determine how these should be handled.

The handling of validation errors can be configured by enabling /
disabling the \'Continue on Error\' parameter on the Validation state of
each import workflow. By default, the \'Continue on Error\' parameter is
disabled.

For example, when reference data includes multiple files and a data
point included in one is not present in a corresponding related file
(e.g., a PCdb Codemaster file includes a position that is omitted from
the Position file in the same PCdb), an error will be written to the
execution report of the validation process. However, as reference data
is typically managed by an outside source (e.g., AutoCare, TecDoc, or
NAPA), it may be desired to import the data regardless of these types of
errors. If so, the \'Continue on Error\' parameter should be checked on
the validation service. In this case the validations issues will still
be written to the execution report, but all valid data will be converted
and made available for the import process. If unchecked, validation
errors will cause the import process to stop and will need to be
corrected before the file can complete validation and continue on in the
import process.

The sections below detail how this setting changes user actions when
importing data.

For the examples in the sections below, consider when an importer has a
strict file name validation rule (e.g., NAPA Vehicle and NAPA
Translation Importers), should a bad file name stop the data from being
imported? If so, then the parameter should remain disabled. If not, then
the parameter should be enabled.

Continue on Error Disabled

Continue on Error Disabled {#continue-on-error-disabled conditions="Primary.Web"}
--------------------------

In the example below, the NAPA Vehicle Import Controller Screen displays
the import file name, if you look closely you can see that spaces were
used instead of underscores. Because the \'Continue on Error\' parameter
was disabled at the time this import file was processed, the Import
Details table displays the status as \'Validation failed,\' the
Background Process Link displays as \'failed,\' and the Overall Status
of the import displays as \'Error: Validation failed.\'

![](../../Resources/Images/Importers/Standard_NAPA/Vehicle%20Imports/1.png)

The validation errors caused the import process to stop, and the errors
must be corrected before the file can complete validation and continue
on in the import process. Clicking the \'failed\' Background Process
Link will display the Background Process Details, where the detailed
error message displays (as shown below).

![](../../Resources/Images/Importers/Standard_NAPA/Vehicle%20Imports/3.png)

Once the error is addressed the user will need to begin the file import
process, as before.

Continue on Error Enabled

Continue on Error Enabled {#continue-on-error-enabled conditions="Primary.Web"}
-------------------------

With the \'Continue on Error\' parameter enabled, the import will
continue through the workflow, but the Validation process status will
display as \'Validation failed\' within the Import Details section of a
Web UI Import Controller Screen, and the Background Process Link will
display as \'succeeded. \'

In the example below, the NAPA Vehicle Import Controller Screen displays
the import file name. Notice that spaces are used instead of underscores
in the beginning of the file name. Because the \'Continue on Error\'
parameter was enabled at the time this import file was processed the
Import Details table displays the status as \'Validation failed,\' but
the Background Process Link displays \'succeeded\' and the import file
was able to enter the next state of the workflow, despite the file name
not meeting the validation criteria.

![](../../Resources/Images/Importers/Standard_NAPA/Vehicle%20Imports/2.png)

Clicking the \'succeeded\' Background Process Link will display the
Background Process Details, where the detailed error message is
displayed (as shown below).

![](../../Resources/Images/Importers/Standard_NAPA/Vehicle%20Imports/4.png)
