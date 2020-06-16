---
description: 'PLM Solution: Snapshots are saved on classification
  objects in JSON strings. One snapshot is captured for each Snapshot
  Recorder that is linked to the Snapshot Configuration for the screen.'
title: '\[%=Heading.Level1%\]'
---

Snapshots
=========

Snapshots are saved on classification objects in JSON strings. One
snapshot is captured for each Snapshot Recorder that is linked to the
Snapshot Configuration for the screen. A reference is created between
the Snapshot and the Snapshot Configuration that created it.

![](../../../Resources/Images/Solution%20Enablement/PLM/Snapshot3.png)

The Snapshot contains all of the data that was defined in the Snapshot
Recorders configuration. The data of the Snapshot is organized by
Recorder.

A Snapshot Configuration reference is created from the snapshot
classification to the desired Snapshot Configuration.

Snapshot Configurations
-----------------------

Snapshot configurations are classifications kept in workbench, used for
screens in Web UI, where they determine which contexts to capture data
from, and any customer-defined change in events. This could be a change
in a workflow state, a trigger by an inbound or outbound integration
endpoint, or a change by derived events through an Event Processor. Once
the defined change in an event has taken place, a snapshot recorder is
used to help take note of the change and record any changes.

![](../../../Resources/Images/Solution%20Enablement/PLM/Snapshot4.png)

See the **Snapshot Configuration** topic in the **Change Reports**
segment of the **PLM for Admins** section of the **Product Lifecycle
Management** documentation[ here]{.mcFormatColor style="color: Blue;"}.
