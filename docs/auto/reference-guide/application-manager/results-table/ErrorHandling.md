---
description: 'Automotive Solution: Describes how error handling related
  automotive validation path functionality is displayed.'
title: '\[%=Heading.AnyLevel%\]'
---

Error Handling
==============

PRODOC note: RDCUST-1573

If an attribute contains an invalid Automotive Validation Path, the
condition attribute with the invalid path will display all available
options, other condition attributes will retain the valid filtered
options in the dropdown list.

If the condition attribute with the invalid path is displayed in its own
column, then a warning icon will be displayed and hovering over the icon
will display a message indicating which reference or attribute contains
the error.

If the condition attribute with the invalid path is not displayed in its
own column, then accessing the value editor will display a yellow square
with the error message below the condition with the invalid path.

In the example below, the ACES Aspiration attribute has an invalid path,
and the error message is displayed.

![](../../../Resources/Images/Importers/Validation%20Paths/ErrorMessage.png)

When using a Mac computer, invalid values (options) do not change style
(gray out, italic font), but are instead represented with three dashes (
\-\--) before the invalid value. For example, in the screenshot below
the ACES Sub Model dropdown on the left is from a PC using the Chrome
browser, and the dropdown on the right is from a Mac using the Chrome
browser. This problem exist only on Mac computers for both Safari and
Chrome browsers. PRODOC note: RDCUST-2431 Application Condition Header -
Individual column header plugin and Application Condition Header - Group
column header plugin

![](../../../Resources/Images/AppMgr/Mac%20poor%20display%20of%20invalid.png)
