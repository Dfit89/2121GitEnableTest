---
description: 'Customer MDM Solution: A getSimilarObject use case for B2B
  acquisitions and finding records with this transition.'
title: '\[%=Heading.AnyLevel%\]'
---

Use Cases - getSimilarObjects Acquisitions
==========================================

Benny, from the sales team, is responsible for retailers and
distributors that have contracts to resell ACME's products.

Benny needs to be able to check if a retailer or distributor already
exists because ACME recently acquired a new company with a separate CRM.

Benny doesn\'t have clear visibility into other systems. He is unable to
identify the record since the record does not exist in his CRM.
Additionally, the other company\'s CRM cannot identify the record based
on a fuzzy match if Benny cannot provide information for an exact match
like a unique identifier.

Benny has difficulty merging records in the ERP system once they\'ve
already been created because they may have orders associated with them.
It is also common that existing records from another system contain
information that is valuable to Benny, in the process where he is
creating the new record. i.e., the customer may have made a purchase
recently, have an open support issue, or in the process of paying debts.
It is therefore of high value to know of the existing record as well as
to prevent creation of duplicate records.

Benny provides a poor customer experience, due to his lack of knowledge
of other engagements with the same customer. Additionally, he is
increasing the risk of poor customer experiences in the future as he
causes multiple copies of the same account with potential inconsistent
data and increased complexity in merging the records at a later time.

Current Duplicate Search

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/DuplicateSearchGraphic.png)

With the current system landscape, Benny has a difficult time
determining if the retailer already exists. This leads Benny to create a
duplicate retailer in his ERP.

To-Be Duplicate Search

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/ToBeDuplicateSearchGraphic.png)

With a CMDM solution in place, all data is fed into STEP. This allows
other systems to make getSimilarObjects calls to STEP to determine if
potential duplicates already exist. Benny can then make an informed
decision to either update an existing record accordingly or create a new
record.
