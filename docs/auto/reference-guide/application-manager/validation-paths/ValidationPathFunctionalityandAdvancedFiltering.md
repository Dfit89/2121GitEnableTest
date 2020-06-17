---
description: 'Automotive Solution: Describes how Automotive Validation
  Path affect the Advanced Filtering option.'
title: '\[%=Heading.AnyLevel%\]'
---

Validation Path Functionality and Advanced Filtering
====================================================

PRODOC note: MEDU RDCUST-2352 and RDCUST-2329 Validation Path spec,
RDCUST-2713 Great info in description

This can be helpful when searching for a part type that only pertains to
specific configurations of a vehicle. For example, this type of
relationship can be helpful when searching for spark plugs for a 2013
Audi A3, and the result table lists both Gas and Diesel engines.

Since Diesel engines do not use spark plugs, listing the Diesel engines
as missing application coverage for spark plugs is inaccurate. However,
when the \'Missing Application Conditions\' attribute is used in
conjunction with the \'Check path for missing application\' business
condition, and a validation path, the results table will no longer
display the inaccurate option.

For more information about the \'Check path for missing application\'
business condition, see the **Business Condition: Check Path for Missing
Application** topic ([here]{.mcFormatColor style="color: Blue;"}) within
the **Automotive Reference Guide**.

 

 

In the example below, the Application Manager search panel is enabled to
search for personal cars, the Make/Model search box contains the Toyota
criterion, and the Engine search box contains the \'1.5L L4, 1453CC,
89CID\' criterion. Once the cursor is placed within the Year search box,
only those years that Toyota manufactured personal vehicles with the
\'1.5L L4, 1453CC, 89CID\' engine display for selection.

![](../../../Resources/Images/AppMgr/YearDropdown.png)
