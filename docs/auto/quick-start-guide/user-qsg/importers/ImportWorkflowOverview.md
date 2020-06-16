---
description: 'Automotive Solution: Import Workflow Overview'
title: '\[%=Heading.AnyLevel%\]'
---

Import Workflow Overview
========================

When a file is loaded through an automotive importer, a STEP entity is
created that represents the file, and then the entity (referred to as
the controller) is initiated into a workflow. This section provides an
overview of the default Automotive Import workflow.

![](../../../Resources/Images/QS/ImportWorkflow.png)

Each workflow can be extended to accomplish additional processing and/or
reporting activities specific to any customer. Therefore, you may notice
additional states (or additional activities occurring within the default
states) on your system.

Validation
----------

The Validation state does some basic schema validation of the file. If
the standard supplies an XSD, the file format is validated against the
XSD. If an XSD is not provided by the standard, the file is loosely
validated to ensure the format conforms to what is expected for the file
type. If the file fails validation, it will move to the Error state and
will remain there until a user takes action on it. Files that
successfully complete validation (with no errors or with only non-fatal
errors) will move automatically to the Conversion state.

Conversion
----------

The Conversion state converts the original file into a series of STEPXML
files that include the full dataset from the import file. If the import
file fails conversion, it will move to the Error state and will remain
there until a user takes action on it. Files that successfully complete
conversion (with no errors or with only non-fatal errors) will move
automatically to the Delta Calculation state.

Delta Calculation
-----------------

The Delta Calculation state evaluates the converted files against either
the database or the previously loaded converted files of that type
(depending on the configuration of the delta calculation method for the
import) and generates a set of delta files for import. Any existing data
that would be unchanged by the import is omitted from the delta files as
a means of increasing performance of the actual import. If the file
fails delta calculation, it will move to the Error state and will remain
there until a user takes action on it. Files that successfully complete
delta calculation (with no errors or with only non-fatal errors) will
move automatically to the Ready for Import state.

For more information, see the **Delta Calculation State** topic within
the **Importing Automotive Data** section of this guide[
here]{.mcFormatColor style="color: Blue;"}.

Error
-----

Files that have failed validation, conversion, or delta calculation will
end up in the Error state. From there, the errors can be reviewed and
the file can be discarded. Note that it is not possible to do further
processing of the file after it has failed, though it can be
subsequently reloaded.

Ready for Import
----------------

When a file has successfully completed validation, conversion, and delta
calculation, it will be available in the Ready for Import state, which
is the first state in which user interaction is required for successful
files. If customer-specific reporting has been added to the
implementation, it is likely that reports can be viewed in this state.
Whether or not reporting has been added, the Ready for Import state is
where the user must decide whether to import or reject the file. If the
user rejects the file, it will be moved to the Rejected state. If the
user chooses to import the file, it is moved to the Import state.

Rejected
--------

The Rejected state displays files that have successfully completed all
pre-import processing, but have been deemed unacceptable for import by a
user, usually due to data issues. A rejected file cannot be imported
unless it is reloaded, so the only option to act on a file in this state
is to discard it.

Import
------

The Import state carries out the actual import of the delta calculation
files. When complete, the file is automatically moved to the Import
Completed state.

Import Completed
----------------

Upon completion of the import, the file will be assigned a \'completed\'
or \'completed with errors\' status. If errors are present, they can be
reviewed in this state. Files may be left in the Import Completed state
or discarded. In either case, no further processing of the file occurs
unless additional customer-specific processing states have been added.

Discard File
------------

Sending a file to the Discard File state removes it from the workflow.
It does not delete any data from STEP or the application server, unless
customer-specific processing has been added to the state to do so.

Additional information on configuration and processing within each
standard\'s importer is available within the **Importing Automotive
Data** section ([here]{.mcFormatColor style="color: Blue;"}) of the
**Automotive Reference Guide**.
