---
description: 'Stibo SDQ User Guide: Because Stibo SDQ integrates tightly
  with STEP to continuously monitor the creation of new contacts /
  accounts in Salesforce (when the MDM theme is applied), Stibo SDQ can
  be configured to provide both background deduplication, and clerical
  review task creation automatically. This allows for multiple processes
  to occur in the background so that when STEP identifies duplicate
  data, it can be automatically merged, and when STEP identifies
  potential duplicate data, then clerical review tasks can be
  automatically created and displayed within the Stibo SDQ tab. '
title: '\[%=Heading.AnyLevel%\]'
---

Automatic Background Deduplication
==================================

Because Stibo SDQ integrates tightly with STEP to continuously monitor
the creation of new contacts / accounts in Salesforce (when the MDM
theme is applied), Stibo SDQ can be configured to provide both
background deduplication, and clerical review task creation
automatically. This allows for multiple processes to occur in the
background so that when STEP identifies duplicate data, it can be
automatically merged, and when STEP identifies *potential* duplicate
data, then clerical review tasks can be automatically created and
displayed within the Stibo SDQ tab.

PRODOC note: I think this info might be good for the ADMIN Guide:

Within STEP, the auto threshold setting determines that matches above
the configured level will lead to the linking of the record into an
entity that contains all Account records that are a match. From that
Entity, a Golden Record can be either persisted or dynamically created
in real time based on all attribute values from linked member records
based on pre-configured attribute value survivorship rules.

Within Stibo SDQ, objects matched above the clerical review threshold
but below the auto threshold can be directed to the Clerical Review
tasks, which allows Data Steward users to manually decide within
Salesforce if there is an actual match between two records.

Below are the different types of matching scenarios:

**High-Volume Automatic Matching:** Uses an auto-link threshold and
calculated match score to reduce the need for manual intervention when a
match score is above a certain confidence interval. This approach
naturally requires careful tuning of the matching algorithm.

**Clerical Review:** Allows all matches above a specified threshold
(i.e., a Clerical Review threshold) but below the auto-link threshold to
be automatically sent through a clerical review workflow within
Salesforce. This is useful when it is essential to not have false
positive matches. For more information, see the **Clerical Review for
Data Stewards** section ([here]{.mcFormatColor style="color: Blue;"}) of
this guide.

If necessary, the auto threshold setting can be tuned to better suit
your organizations needs.
