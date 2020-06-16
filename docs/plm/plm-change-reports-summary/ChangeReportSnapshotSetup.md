---
description: 'PLM Solution: A Change Report Snapshot needs a series of
  configurations to be enabled, see below configurations included in
  Private Label Food Change Report Snapshot functionality.'
title: '\[%=Heading.Level1%\]'
---

Change Report Snapshot Setup
============================

A Change Report Snapshot needs a series of configurations to be enabled.
See below the configurations included in Private Label Food Change
Report Snapshot functionality.

-   There is a required data model for storing snapshot definitions and
    snapshots.
-   There is a required format for generating snapshots.
-   There is a dependency on Product Summary Card. Change Report alerts
    will only appear on screens that are configured to use the Product
    Summary Card component.
-   An add-on change-report component and license must be installed on
    your system.
-   A snapshot business rule bind is used to support snapshot recorders.
-   Business Rules are utilized.

Snapshot Data Model
-------------------

The Change Report Snapshot is a fixed model. This model is for storing
snapshot definitions and the snapshots created on data changes.

![](../../../Resources/Images/Solution%20Enablement/PLM/Snapshot%201.png)

See the **Change Reports** documentation in the **Product Lifecycle
Management** documentation for more information on the necessary
objects, references, attributes, business rules, and snapshots needed
for Change Reports Snapshots[ here]{.mcFormatColor
style="color: Blue;"}.

Snapshot Recorder Format
------------------------

The Snapshot Recorder is a product object in STEP which stores a
recorder text that defines which data must be captured in the snapshot.
The format of the recorder text is a JSON string.

The JSON property attributes value is an array of JSON Objects.

For example, the JSON objects array is represented by:\[{},{}\]

    {

    "attributes": [    "PLMDesignSpecificationDescription", "PLMSpecificationName"

    ]

    }

In Private Label Food solution, Snapshots are organized in a one-level
hierarchy :

![](../../../Resources/Images/Solution%20Enablement/PLM/snapshot%202.png)

Snapshot Recorders are linked to one or many Snapshot Configuration(s)
using the product classification link type Snapshot Recorder (ID
SnapshotRecorder). This enables the re-use of Snapshot Recorders on many
screens where the same data should be captured.

On the link between a Snapshot Recorder and a Snapshot Configuration are
metadata attributes that are used to define tabs in the Change Report
(Web UI experience).

For a list of examples of elements that can be included in a snapshot,
see the **Elements in a Snapshot** topic in the **Change Reports**
segment of the **PLM for Admins** section of the **Product Lifecycle
Management** documentation[ here]{.mcFormatColor style="color: Blue;"}.
For more on Snapshots, see the **Snapshots** topic in this
documentation[ here]{.mcFormatColor style="color: Blue;"}.
