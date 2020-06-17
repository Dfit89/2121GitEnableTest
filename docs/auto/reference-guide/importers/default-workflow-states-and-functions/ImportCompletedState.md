---
description: 'Automotive Solution: Describes the functions of the Import
  Completed State default workflow state.'
title: '\[%=Heading.AnyLevel%\]'
---

Import Completed State
======================

When import has completed, the controller object is automatically passed
to the Import Completed state where it will remain until a user takes
action on it. The only option for action is to discard the file, which
passes the controller object to the Discard File state, effectively
removing it from the workflow.
