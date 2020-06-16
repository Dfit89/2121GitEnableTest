---
description: 'PLM Solution: Below are the current capabilities,
  performance considerations, and Limitations to keep in mind when
  working with Change Reports.'
title: '\[%=Heading.Level1%\]'
---

Capabilities, Considerations, and Limitations
=============================================

Below are the current capabilities, performance considerations, and
limitations to keep in mind when working with Change Reports.

Current Capabilities
--------------------

Some of STEP's Web UI components allow viewing revisions of attribute
values if the component has been configured to show historical revisions
and if the user knows that they should click next to an attribute input
field to see the revisions. Occasional users, like suppliers, may not
remember that access to revision history requires hovering over a blank
spot on the screen.

For PLM, most data used for specifications and responses are stored on
reference metadata. The Web UI component that is most often used is a
multi reference editor, where there is no capability for showing
revisions at all.

Performance Considerations
--------------------------

To mitigate the risk of performance issues, it is recommended that
snapshot recorders are defined to capture only the content that would
change between events. For example, content that is maintained by
internal users does not need to be part of a snapshot when suppliers
submit their responses since user privileges should prevent suppliers
from changing content that is maintained by internal roles.

Limitations
-----------

Change Report alerts will only appear on screens that are configured to
use the Product Summary Card component.

Views of revisions will be limited to the current data and the last
snapshot of the same type (eventId). Specific attributes and references
on Web UI screens that have had changes will not show alerts as part of
this development as there is a dependency on future development for deep
linking.

Content within the Change Report dialog will not consider user
privileges to see the data. All data that was captured in the snapshot
will be shown if a user has privileges to view the change report. It
will be up to each customer to ensure that the data that is defined in a
Snapshot Recorder is appropriate for the users that will use the
screens.
