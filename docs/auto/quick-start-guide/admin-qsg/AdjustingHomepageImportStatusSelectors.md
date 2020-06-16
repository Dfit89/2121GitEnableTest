---
description: 'Automotive Solution: Describes adjusting Homepage Import
  Status Selectors.'
title: '\[%=Heading.AnyLevel%\]'
---

Adjusting Homepage Import Status Selectors
==========================================

Easy Setup creates a number of workflows to manage imports, along with a
corresponding Web UI homepage widget, in this case, astatus selector,
for each import. Each workflow contains a number of states, though not
all are reflected in the corresponding status selector in Web UI.
Specifically, the initial Validation and Conversion states are omitted
as these states do not produce any interesting results for the end user
if completed successfully. If errors are encountered, they can be viewed
via the Error state. Whether successful or in error, transition out of
these states is automatic so no user intervention is needed.

Furthermore, as described in the subsequent section, some
implementations will likely choose to add additional states to the
workflow which could produce an interesting result for the end user,
such as a Reporting state.

Whether it is needed to display additional existing states or to display
new ones, it may be necessary to adjust the configuration of the status
selectors to display additional states. If so, detailed documentation
for configuring status selectors is available in the **Status Selector
Homepage Widget** topic within the **Workflows in Web UI** section of
the **Web User Interfaces / Web UI Getting Started** documentation of
STEP Online Help[ here]{.mcFormatColor style="color: Blue;"}.
