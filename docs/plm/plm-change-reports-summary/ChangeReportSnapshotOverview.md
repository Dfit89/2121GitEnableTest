---
description: 'PLM Solution: In STEP historical versions of objects are
  stored as revisions, supplying a historical ''snapshot'' of an object.
  But the minimum timing threshold is 24 hours, and a revision is made
  when the time is exceeded. '
title: '\[%=Heading.Level1%\]'
---

Change Report Snapshot Overview
===============================

In STEP, historical versions of objects are stored as revisions,
supplying a historical 'snapshot' of an object. For these revisions, the
minimum timing threshold is 24 hours, and a revision is made when the
time is exceeded. This represents a limitation since during the
collaboration process product data can experience multiples changes by
different user roles in a short period of time.

Snapshot Change Report is an alternative to STEP's revisions. In short:

-   A Change Report can detail any changes that have been made during
    user-defined events.
-   Static snapshots are taken and compared to the current data.
-   Customers define which data point(s) to capture and when.
-   They support complex data models like a recipe and packaging
    specification, including reference metadata and nested references.
-   Data model changes will not remove data change history captured in
    the snapshots.
-   A Change report snapshot will not be under revision control so it
    can be deleted at proper intervals, providing clean up to reduce
    object bloat.

See the Change Report Snapshot Setup topic to set up snapshots in this
documentation[ here]{.mcFormatColor style="color: Blue;"}.

 
