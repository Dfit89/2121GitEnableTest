---
description: 'Customer MDM Solution: In a CMDM system, the contained b2c
  use cases explain the data flow.'
title: 'Business-to-Customer Coexistence Use Case'
---

Business-to-Customer Coexistence Use Case
=========================================

#### Scenario 1 - Marriage

In this scenario, Catherine Yu lives in Texas and is a customer of
ACME who enjoys the experience of discovering the latest clothing trends
offered within ACME's physical (B&M) stores.

Catherine occasionally shops on ACME's e-commerce site due to the online
exclusive promotions and friendly in-store return policy. Having
recently gotten engaged, Catherine signed up for ACME's customer loyalty
program so she can take advantage of additional loyalty perks and
savings in order to save for the wedding and honeymoon.

Sandra manages Catherine's order from a B2C e-commerce site which
contains no address validation, allows multiple accounts to be created
for a single customer, and lacks any form of de-duplication of customer
records. Lacking address validation leads to missed order deliveries
which damages brand reputation. Allowing multiple customer accounts of a
single record due to no deduplication leads to loss of cross sell
opportunities as an email or sales catalog may be sent based off the
information of an old account. Deduplicating and consolidating these
records allow all contact information to be available on a single
entity, eliminating errors caused by multiple conflicting entities

Charles Johnson, Catherine's fiancé, is from Michigan and is an
occasional shopper of ACME brand clothing.  As a loyalty program member,
Charles has decided to take advantage of recent promotions in
preparation for their wedding. Upon marriage, Catherine has
chosen to take Charles' last name and moved to Michigan with Charles.

Customer data gathered in physical stores are managed by a CRM
platform which associates credit card payments to specific customers to
ensure faster processing and confirmation or receipt delivery, while
customer data gathered from the e-commerce site is managed by an
e-commerce system. Customer loyalty sign-ups are tracked by
a different CRM platform that is owned and maintained by the marketing
department.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%204a.png)

Because ACME's multiple CRM and SAP systems are siloed and are not
synched with one another there is no automated capability for ACME to
identify that Catherine Yu and Catherine Johnson are the same customer. 
ACME also does not have a straightforward way to identify customers who
have relocated to a different address.

Furthermore, ACME would like to be able to identify customer groupings
as households in order to minimize wasted marketing mailings and to
better target buyer behaviors.

As these challenges are currently not addressed, several problems arise:

-   For every seasonal marketing campaign, mailings that are sent to
    Catherine end up at her old address in Texas which causes her to
    miss out on certain promotions and even important rebate checks.
-   Charles gets some of the same marketing mailings but since he's not
    a big shopper, he ends up throwing them out before Catherine sees
    them.
-   Even after Catherine had to call into the ACME call center to update
    her address, ACME still sent double of every marketing mailing to
    Catherine and Charles even though they live together which adds to
    the frustration in Charles' and Catherine's customer experience.

**Current Data Flow**

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%204b.png)

The e-commerce system is unable to identify that Catherine Yu and
Catherine Johnson are the same customer. This leads to three separate
records being created. No connection between Catherine and Charles has
been identified.

**To-Be Data Flow**

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%204c.png)

The CMDM system can identify that Catherine Yu is the same customer as
Catherine Johnson and will merge them into a single golden record.
Additionally, CMDM will be able to identify the Johnson Household based
on a shared last name and address. The household concept allows
marketing to avoid redundant mailings and better target offers and
promotions.

#### Scenario 2 - E-Commerce

Sandra is responsible for managing orders coming from the new B2C
e-commerce site, as well as returns. She succeeds when she can deliver
the right product to the right customer at the right time.

ACME Company's goal is to make it as easy as possible for customers to
buy their products. If customers do not remember their log in, they can
create a new user and then place the order, or even place smaller orders
without creating a user. Customers must also provide their delivery
address.

Poor data quality has created several challenges for ACME Company,
preventing them from achieving their goal:

-   Addresses are not validated before the order is sent to logistics,
    leading to a lot of products delivered to wrong addresses or not
    arriving to the right customer at the right time.
-   Sometimes customers accidentally misspells their address or leave
    out vital information.
-   Duplicates are and will continue to be created in the e-commerce and
    ERP systems.
-   Neither the e-commerce system or ERP can check for duplicates,
    obfuscating how much a customer actually buys from ACME.
-   Customers do not receive their orders in a timely manner (or at
    all).
-   Inconsistent customer experience, as duplicate accounts may lead to
    orders not being associated between duplicates.

These issues result in:

-   Low data quality of delivery locations leads to instances of
    \'return to sender\' and double shippings, causing increased costs.
-   Poor customer experience due to orders not arriving in a timely
    manner.
-   Lost revenue and loss of customers. If the products are not
    delivered in a timely manner, customers will buy products from
    elsewhere.
-   Increased returns.
-   Duplicate records carry operational and analytical consequences.
    Operationally, the correct delivery address may be available on a
    duplicate record. This leads to customer frustration if ACME is not
    considering that record when shipping. Analytically, reports may be
    skewed as duplicate records cause a single customer to be weighed
    multiple times during analytics.

**Current Data Flow**

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%205a.png)

The customer places orders that are processed out of an e-commerce
system. The customer and order details are sent to the ERP system for
processing and to get shipments out. Currently, there are no validations
being done on the provided address. This causes customers to not receive
their purchases in a timely manner or not at all. Additionally,
shipments may be returned to sender causing increased costs.

**To-Be Data Flow**

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/Use%20Case%205b.png)

The CMDM solution is integrated with Loqate to verify and standardize
addresses. This increases address quality, reducing instances of
\'return to sender\' and deliveries shipped to the wrong address. Using
Loqate as a webservice, the addresses can be standardized at the point
of entry in the Ecommerce system. Additionally, an Ecomm administrator
can manage customer accounts and have addresses standardized without
directly interacting with STEP.
