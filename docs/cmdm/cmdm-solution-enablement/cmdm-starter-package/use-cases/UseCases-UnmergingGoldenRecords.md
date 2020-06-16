---
description: This CMDM Solution Enablement topic covers the logic for
  unmerging golden records that were incorrectly considered duplicates.
title: '\[%=Heading.Level1%\]'
---

Use Cases - Unmerging Golden Records
====================================

In these use cases, the data steward Stew is responsible for overseeing
the unmerge of customer records within different scenarios.

Simple Unmerge
--------------

ACME continues to operate with source systems feeding new customer
records and updates into their MDM system. During this time, Stew
continually reviews and merges or rejects potential duplicates as
needed. ACME's call center receives a complaint from an existing
customer stating that their order never arrived at their shipping
address. Stew has been asked to investigate the customers record to
deduce why the order never arrived. In Web UI, Stew searches and finds
the associated customer record. Based on revision date, he can tell that
the customer has been recently updated and notices that the customer has
two source record IDs associated with their records. Stew navigates to
the source traceability tab and notices that all the address attributes
were taken from one source record and the last edited date matches this
source system\'s merging date. This tracing leads Stew to believe that
another customer may have been incorrectly merged causing the shipping
address to be mistakenly updated.

Stew must now unmerge the two records which includes determining which
attribute values belong to each newly separated golden record.

Enhanced Unmerge
----------------

Due to continued customer complaints, ACME has decided to implement a
new workflow-based procedure to allow for employees in the call center
to directly initiate unmerge requests. Stew is still responsible for
handling the unmerges but will now have an easier time of monitoring and
investigating the requests.

While investigating an unmerge request, Stew notices that the customer
involved still has open orders with ACME. After further investigation,
Stew realizes this is a valid request, and the customer needs to be
unmerged. Before doing so, Stew must verify with the ERP team to
determine which orders and invoices belong to the respective records.
With this information obtained, Stew can now make informed decisions to
unmerge the customer record.

With a single customer record now becoming two separate records, the
downstream systems must be notified. Within ACME's system landscape, the
MDM system will now send out two golden record to the ERP. The ERP must
now handle this update by creating two new records, surviving the
appropriate invoices to them, and deactivating the previously incorrect
customer record. Once the records have migrated to downstream systems,
Stew must now verify that they were received correctly. Stew navigates
to the new records in each surrounding system and verifies the unmerged
records are being accepted. Stew then submits the unmerge task as
finalized.

 

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/UnmergeDataFlow.png)

1.  A call center employee submits an unmerge request.
2.  The request results in a single customer record splitting into two
    unique records.
3.  The two newly created accurate golden records are synced to
    downstream systems.
