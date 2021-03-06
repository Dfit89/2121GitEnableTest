---
description: 'Automotive Solution: Describes the functions of the Ready
  for Import State default workflow state.'
title: '\[%=Heading.AnyLevel%\]'
---

Ready for Import State
======================

When a file has successfully completed validation, conversion, and delta
calculation, the controller object is available in the Ready for Import
state, which is the first state in which user interaction is required
for successful files. If customer-specific reporting has been added to
the implementation, it is likely that reports can be viewed in this
state. Whether or not reporting has been added, the Ready for Import
state is where the user must decide whether to import or reject the
file. If the user rejects the file, it will be moved to the Rejected
state via the Reject transition, which contains a single business rule
to set the overall status of the controller entity. If the user chooses
to import the file, it is moved to the Import state.

Only controller objects with files that have failed a previous process
will end up in the Error state. It is also possible for files to have
warnings and/or errors and still continue successfully through the
process so it is important for users to view the data provided in the
background processes in the Web UI to determine whether or not a file
should be imported.
