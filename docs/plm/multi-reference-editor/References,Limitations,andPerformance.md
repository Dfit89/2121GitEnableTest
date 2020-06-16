---
description: 'PLM Solution: Below is the explanation of Removing
  References, and any limitations or performance considerations when
  working with the Multi-Reference Editor.'
title: '\[%=Heading.Level1%\]'
---

References, Limitations, and Performance
========================================

This topic details how to remove references as well as any limitations
or performance considerations when working with the Multi-Reference
Editor.

Remove Reference
----------------

This functionality will remove the selected reference to Requirements or
Parameters.

In the private label food solution, some requirements are used in 90% of
projects. Once the user has started the revision process, some
references to requirements or parameters must be deleted.

Limitations
-----------

The only attribute validation base type(s) that are supported in the
current React components are:

-   Number
-   Text
-   ISO Date
-   LOV (single and multi-valued)

Only the edit mode is supported.

Performance Considerations
--------------------------

A lot of business actions / functions are executed in the new \'Create
Reference\' and \'Edit Reference\' dialogs. The performance will depend
on how the business actions / functions are configured.
