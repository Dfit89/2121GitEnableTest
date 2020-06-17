---
description: 'Automotive Solution: Describes the TecDoc Reference Start
  Condition Business Condition. '
title: '\[%=Heading.AnyLevel%\]'
---

Business Condition: TecDoc Reference Start Condition
====================================================

PRODOC note: MEDU RDCUST- 2615, PRODOC- 1240, PRODOC-1239

The TecDoc reference start condition can be used to prevent the start of
a reference data import if a supplier data import is running. Once the
business condition is created, it must be added to the

Previously, TecDoc Easy Setup created the Reference and Supplier
workflows with a Start Condition that contained a Business Rule that
looks for a specific Final state in the workflow. If the specified state
does not exist in the Reference workflow, this would prevent the
Supplier import to be started.

The start condition rule is still available and can be found under the
\'TecDoc\' Business Condition menu if a user wants to manually create a
business rule that controls when to import reference and supplier data.

 

Supposed to prevent the start of reference data import if there is a
supplier data import running. Set in the workflow. Rejects the import
(but the error does not display within our import list screen). Set by
Easy Setup go to the WF and see
