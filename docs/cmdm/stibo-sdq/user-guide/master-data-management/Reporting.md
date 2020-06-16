---
description: 'Stibo SDQ User Guide: First part of MDM is home screen,
  where we can see how many tasks there are. We use tasks when we want
  to remind ourselves or someone else about the activity that needs to
  be done. To create and assign Task first we need to find duplicate
  records for Account or Contact. In order to do that, we must go to
  Manual Merge Request Page, find duplicates, and then create new task.'
title: '\[%=Heading.AnyLevel%\]'
---

Reporting
=========

Stibo SDQ Reporting is displayed on the Stibo SDQ Home page once the MDM
theme is configured, and is the main entry point for Data Stewards who
need remove duplicates using the Clerical Review and Manual Merge
Requests functions. Reporting displays beneath the Clerical Review
Tasks, and provides an overview of performance factors pertaining to the
automated deduplication that runs in the background.

For each of the record types: Account, Contact and Person Account (if
activated), two charts will be displayed:

![](../../../../../Resources/Images/CMDM/User%20Guide/Reporting/Reporting%20Account%20Organizations%20Matching%20Overview.png)

![](../../../../../Resources/Images/CMDM/User%20Guide/Reporting%20Contacts.png)

![](../../../../../Resources/Images/CMDM/User%20Guide/Reporting/Reporting%20Person%20Accounts.png)

Matching Overview
-----------------

The pie chart reports on records that have passed through the automatic
matching and deduplication process in the last two days. Each record
examined will receive one of the following statuses:

-   **Auto Match:** The record has been automatically deduplicated and
    merged with another record.
-   **Clerical Review:** The record is in or has passed through Clerical
    Review.
-   **Non Match:** The record was examined but identified as a unique
    record.

Whenever a records data is changed, the deduplication process will
examine the record, causing a large total number of records to display
for the Matching Overview. This is not necessarily a need for concern,
but rather an indication of general activity.

The Matching Overview report can be used to give a snapshot of the
efficiency of the deduplication routine. This is done by comparing the
size of the different slices in the Pie Chart:

-   If the \'Non Match\' slice is large (relatively speaking), then this
    indicates that few duplicates have been identified and that Real
    Time Deduplication works as it should. Naturally, other factors
    (e.g., in case of a bulk load of records into the Salesforce
    instance) may cause the relative number of Non Match records to
    decrease.
-   Comparisons of the \'Auto Match\' and \'Clerical Review\' slices
    indicate how many potential duplicates need to go through a manual
    Clerical Review, as opposed to being automatically matched.

Duplicate Records Auto-matched
------------------------------

The Duplicate Records Auto-matched report can be used to look for sudden
changes in the number of duplicates that are being created either by
users or via bulk import. The line chart reports the number of records
that have been identified as duplicates and merged by the automatic
deduplication process within the last 11 days.

If Real Time Deduplication is working as it should, and if its manual
entering is the main source for new records, the line should be low and
stable.
