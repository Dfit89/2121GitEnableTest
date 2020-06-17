---
description: 'Automotive Solution: Describes how to '
title: '\[%=Heading.AnyLevel%\]'
---

Using Part Type Search Box
==========================

The Part Type Search Box allows users to add one or more part type
criteria to their search. This section addresses functionality that is
specific to the Part type search box. For more information on the
general functionality found within the search boxes, see the **Using
Search Boxes** topic[ here]{.mcFormatColor style="color: Blue;"}.

Within the Part Type Search Box, the typeahead field can be used to
search for part type criteria, and the use of an asterisk will allow for
a wildcard search. Only part type Names are searched, not IDs. The
dropdown list displays criteria options alphabetically. For example, if
\'\*spark plug\' is typed into the field, then the dropdown list
displays the any part type name containing \'spark plug\' alphabetically
(as shown below).

![](../../../Resources/Images/AppMgr/Part%20type%20search%20results%20for%20plug.png)

Additionally, users can browse for the Part Type criteria by clicking
the node picker browse icon located to the right of the Make/Model
typeahead field. In the screenshot below, the Part Type Browse dialog
displays after the node picker browse icon is selected.

![](../../../Resources/Images/AppMgr/NPPT.png)

PRODOC note: MEDU RDCUST-2883 The following functionality was enabled
via RDCUST-2130 but then later changed. When searching on Part Type, the
part type link must be established on an application or part in order
for the applications to be displayed in the search results table. If the
part type link is on the part and the application does not have a link,
then it will inherit from the part. If the application has a link, then
it will override the link that's on the part. For example, if a user is
searching for the Part Type Spark Plugs, and an application is not
linked to Spark Plugs (in AutoCare, the Product to Classification Link
Type ID = AC\_ProductToPartTerminology), then that application will not
display in the search results table.

PRODOC note: MEDU RDCUST-2661 BEJA Sprint demo (2/13/18)When adding
search criteria to the Part Type Search Box, the search criteria added
to the search will auto-populate within the search result records.

PRODOC note: MEDU - Seems like\...the following configurations can
affect the behavior of the Part Type Search box

-   The Product to Classification Link Type
-   Automotive Validation Path
-   **Business Condition: Check Path for Missing Application** topics
    ([here]{.mcFormatColor style="color: Blue;"})
