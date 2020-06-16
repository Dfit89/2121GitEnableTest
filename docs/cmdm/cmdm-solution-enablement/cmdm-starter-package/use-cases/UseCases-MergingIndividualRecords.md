---
description: 'Customer MDM Solution: Describes the Merge Individual
  Record use case.'
title: 'Use Cases - Merging Individual Records'
---

Use Cases - Merging Individual Records
======================================

In these use cases the data steward is responsible for overseeing the
deduplication of customer records via different merge processes.

Auto-Merge Individual Records
-----------------------------

ACME has several external source systems which contain multiple records
with separate identifiers (source record IDs). Despite these different
identifiers, many of these records are in fact the same individual but
with minor variations in demographic data.

These individual records are sent to STEP and automatically deduplicated
via the configured matching logic, which identifies and merges identical
records. These matched records are then merged and a single golden
record is created.

Original source systems and respective source record IDs are maintained
as part of the golden record for source traceability purposes.

Merge Individual Records
------------------------

ACME has a number of records which are considered potential duplicates
of one another, but the system cannot ultimately determine whether or
not they are true duplicates without the input of a data steward. In
these cases, a data steward must review potential duplicate records and
corresponding demographics to intelligently determine whether they are a
match or not.

Once STEP determines which records are potential duplicates of one
another, a Clerical Review task list is presented to the data steward in
the Web UI. Data stewards may review the demographics of each task to
determine whether the records should be merged. If it is determined that
the tasks are a match then the **Merge** action will merge the records
into a single golden record. If it is determined that the records are
not matches of each other then the **Reject** action will leave the
records unmerged.

For matched records, a single resulting golden record will survive that
contains the source system and source record ID of all records that were
merged. For non-matched records, a Confirmed Non-Duplicate reference
will be established to prevent future clerical review tasks from being
created for the same records. The existing task will also be removed
from the Clerical Review task list / workflow.

Advanced Merge Individual Records
---------------------------------

As an alternative to the **Merge** function described in the above use
case, data stewards can use the **Advanced Merge** option to manually
dictate which demographics survive the merge between two or more
potential duplicates. In addition they can choose to exclude individual
records from the merge.

Once STEP determines which records are potential duplicates of one
another, a Clerical Review task list is presented to the data steward in
the Web UI. Data stewards may select a task, and by clicking **Advanced
Merge**, they are presented with a table view of the associating records
as well as corresponding demographics. As the data steward selects which
demographics will survive the merge and be promoted to the golden
record, a preview column displays the resulting merged golden record.
Additionally, should the data steward determine that one or more records
should not be considered as a potential duplicate, the option to
**Exclude Record** is provided.

The resulting golden record reflects the demographics manually selected
by the data steward. The task is removed from the Clerical Review task
list once the merge is complete.
