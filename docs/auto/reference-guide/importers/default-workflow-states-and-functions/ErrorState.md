---
description: 'Automotive Solution: Describes the functions of the Error
  State default workflow state.'
title: '\[%=Heading.AnyLevel%\]'
---

Error State
===========

Files that have failed validation, conversion, or delta calculation will
have the controller end up in the Error state, and it will remain there
until acted on by a user. It is not possible to do further processing of
the file after it has errored, though it can be subsequently reloaded if
needed. As described in the **Automotive Quick Start Guide**, users are
able to view the errors generated in validation, conversion, or delta
calculation by clicking the appropriate background process links to view
the corresponding execution reports. They can also choose to discard the
file, which will transition the file to the Discard File state, which
contains a business rule that automatically removes the controller from
the workflow so that it is no longer displayed in the workflow tasks in
the Web UI.
