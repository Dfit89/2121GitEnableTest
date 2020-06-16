---
description: 'Customer MDM Solution: Describes the Marriage and
  Relocation use case.'
title: 'Use Cases - Marriage and Relocation'
---

Use Cases - Marriage and Relocation
===================================

In these use cases, the data steward is responsible for overseeing
customer record updates in the event that two customers get married or
relocate.

Marriage
--------

ACME must update their database in the event that two customers get
married. A pre-existing customer named Catherine Yu got married to
another pre-existing customer, Charles Johnson, and had her last name
and address changed.

In this scenario, the change in status is initially updated in a source
system by a customer service representative within a call center. The
source system feeds this update to STEP, where it is then matched to an
existing record via the source system record ID for Catherine Yu.

Once matched and updated, Catherine Yu is now Catherine Johnson and has
a new address. Additionally, the household is updated to reflect that
Catherine and Charles belong to the same household.

Relocation
----------

ACME must update their database in the event that a customer moves to
another address. In this scenario, Maxie Hadley was a pre-existing
customer who moved from KY to UT. At some point a second record was
created with the new address. STEP automatically identifies that the two
records with different address are the same person.

Once flagged as potential duplicates, a data steward can handle the
deduplication task via a clerical review. Concluding that they are in
fact the same person, the data steward merges the two records into a
single golden record.
