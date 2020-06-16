---
description: 'Customer MDM Solution: Describes the B2B Contact
  Management use case.'
title: 'Use Cases - Managing B2B Contacts'
---

Use Cases - Managing B2B Contacts
=================================

In these use cases, the data steward is responsible for managing
organizational contacts (i.e., for vendors, distributors, etc.).

Identifying and Deduplicating Contacts Within the Same Organization
-------------------------------------------------------------------

ACME must ensure that there are no duplicate contact records within the
same customer organization. In this scenario, Sergio Bennett and Serge
Bennet belong to the same organization and are identified as potential
duplicates.

A source system sends a second record for Sergio Bennett with a
different source record ID. STEP evaluates the incoming record and
determines that it is in fact the same contact person for that specific
vendor. Once STEP has determined that Sergio Bennett and Serge Bennet
are one and the same, a data steward can merge them into one record via
clerical review.

Handling Contacts Across Different Organizations
------------------------------------------------

Emma Hoffman was previously a contact person for one of their suppliers,
but now, works for another one ACME is associated with. Since the
organizations are different, when the source system updates STEP with
the new organization contact, Emma Hoffman\'s contact information will
not be deduplicated across both organizations.

A new golden record contact for Emma Hoffman is created for that
supplier and it is not deduplicated against her previously created
golden record.
