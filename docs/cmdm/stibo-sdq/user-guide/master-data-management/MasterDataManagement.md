---
description: 'Stibo SDQ User Guide: Master Data Management within Stibo
  SDQ is a theme that allows a Salesforce user to connect to the STEP
  platform.'
title: '\[%=Heading.AnyLevel%\]'
---

Master Data Management
======================

The goal of Stibo SDQ is to keep your organizations data reliable and
accurate. This is best achieved by connecting your Salesforce instance
to a world renowned MDM solution, STEP. The STEP solution is a single
enterprise platform created over twenty years ago by Stibo Systems. STEP
provides a common set of tried and tested functionalities, and operates
in a uniform mode across any data domain. STEP's functional richness,
strong data modeling, and powerful workflows enables companies around
the world to cultivate and maintain a robust information supply chain.

-   Merging Entries
-   In the SDQ app, there are two ways for merging entries: Automatic
    Merge-Simple Merging and Manual Merge-Advance Merging
-   Automatic Merge-Simple Merging is hidden from users. STEP
    automatically selects the Master record, and usually it is the first
    record. When merging is complete, the Master record are saved in the
    SF organization, and other records will be deleted.
-   Manual Merge-Advance Merging is for the user to make manual merge
    requests. This way the user can choose what records to be merged,
    what records to be linked, what information to pull, and which
    record will be the Master Record. Master record are saved in our SF
    organization and other records will be deleted.

PRODOC note: Per BRJE: From a user perspective there are three: 1.
Automatic merge: As described 2. Simple merge - done from the clerical
review page: Initiated manually, but triggers the same functions as the
Automatic merge 3. Advanced Merge: Accessed from the clerical review
page, but else as described. As a side comment: Manual merges can only
be completed using Advanced Merge.

Stibo SDQ allows your users to benefit from the power of STEP while
using Salesforce to perform the following:

-   Automatic Background Deduplication ([here]{.mcFormatColor
    style="color: Blue;"})
-   Real-time Deduplication with Search Before Create
    ([here]{.mcFormatColor style="color: Blue;"})
-   Clerical Review for Data Stewards ([here]{.mcFormatColor
    style="color: Blue;"})
-   Reporting ([here]{.mcFormatColor style="color: Blue;"})
