---
description: 'Customer MDM Solution: This topic explores a collection of
  use cases for centralized B2B. '
title: Centralized B2B Use Cases
---

Centralized B2B Use Cases
=========================

Below we can see actual challenges and solutions in place for several
use cases.

Scenario 1: Direct Customer Onboarding
--------------------------------------

### Who

[Philip]{.bold}, a Category Manager at BlueBox Retailer, serves as the
primary contact for the company's manufacturers and suppliers with a
focus on the household cleaning supplies product line.

[Lance]{.bold}, a Sales Representative for CleanGoods, has the
responsibility of validating the legitimacy of BlueBox Retailer as a
prospective customer that CleanGoods Manufacturer wishes to do business
with. This may involve validating against third-party syndicated data
analytic companies (i.e., Nielsen TDLinx or IRI) which provide insight
on the prospect's business operations, retail sales data, corporate
structures, and information on individual retail locations.

[Kathy]{.bold}, a Controller from the Finance team, runs validations of
the prospective customer including a credit check, which may also
contain usage of third-party data providers (i.e., Dun & Bradstreet).
Such validations enable CleanGoods Manufacturer in identifying any type
of fraudulent activity.

[George]{.bold}, a Logistics Specialist, is responsible for determining
how to fulfill the order. This involves evaluating a number of factors
such as projected order frequency, product assortment, volume, stock,
package type, geography, etc. to determine how the customer is to
receive the products.

The role of the [MDM Specialist]{.bold} serves as the primary owner of
the CMDM system and approves all changes submitted by the various
departments during the onboarding process.

### What

BlueBox Retailer has begun negotiations to procure and resell products
from two CleanGoods lines of business. BlueBox is especially interested
in [CleanGoods\']{.bold} line of household cleaning products as well as
their charcoal line of business.

Philip has been negotiating with Lance, the sales representative from
CleanGoods, in finalizing initial sales terms for their household
products line of business. Once finalized, Lance will initiate the new
customer request to begin the CMDM onboarding / enrichment process.

Part of Lance's responsibility during the onboarding process is to
validate the legitimacy of the customer as a legal business entity. Such
validations may occur outside of the operational MDM. If the results of
the customer validations are favorable, Lance will continue working with
Philip to classify / enrich the new customer record with relevant
information. Such information that Lance requires includes (not limited
to):

-   Trade Channel - How do products reach the end-consumer (i.e.,
    In-store retail, e-commerce, mail order, warehouse stores, etc)?
-   Product Lines - What types of products will Bluebox Retailer be
    purchasing?
-   Line of Business - What particular line(s) of business will BlueBox
    be conducting transactions with?
-   Location Setup
-   All *Ship To\'s*
-   Location information for each physical location CleanGoods
    Manufacturer must deliver products to (e.g., warehouses,
    distribution centers, retail stores, etc.).
-   All *Sell To\'s*
-   Location information for each Sell-To location CleanGoods
    Manufacturer must send invoices to (e.g., Corporate head office,
    regional offices, accounts receivable department, etc.).
-   Financial / accounting information for each Sell-To location, used
    for invoicing purposes.

It may be required that additional processes are kicked off in various
operational systems external to the MDM in order to add additional
information in those systems which do not belong in the MDM system, for
example, it could be that certain data is local to one process and / or
it is most convenient that the data be maintained in the operational
systems.

As part of the onboarding process, Kathy from the Finance department
must ensure finance-related enrichment activities take place. These
activities include conducting credit checks of the customer for any
financing approval by leveraging third-party services such as a Dun &
Bradstreet company profile. Additionally, Kathy may work with Lance
during initial negotiations to provide pricing and trade promotion of
products sold to BlueBox. Pricing usually originates and is maintained
within an ERP system.

Once the customer sales & financial enrichment process is complete,
George from the Logistics department must determine if the customer
requires:

-   Ship to Store
-   Ship to Customer Distribution Center
-   Direct Pick-up at the Manufacturer

Considerations must be given to storage requirements as well as any
regulatory requirements or hazardous material protocols. For example,
some products may only be stored in specific warehouses equipped with
refrigeration or hazardous products may require special shipping and
handling instructions.

### Challenges

The current operational landscape of CleanGoods is rather siloed and
does not provide a means to onboard and enrich customer data in a
centralized way. Due to this, operational data is scattered across
disparate systems with facilitation or governance in place. Each role
may enact their individual governance to manage data integrity with
little to no consciousness of impact to other departments or overall
operations.

Currently, Lance must work with the customer to finalize sales terms and
other commercial considerations, he must then work internally with a
specialist to initiate a new customer request. Kathy from Finance is
then notified via email of the new customer request and must then work
out of ERP to determine exact pricing, and update the financial
portfolio. Should Kathy have any questions for Lance, she must likewise
correspond with him over email or a phone call. Furthermore, the same
process is followed to notify George from Logistics so he may address
delivery and warehousing considerations.

Without a centralized ownership of the onboarding process and governance
in place to ensure validations and regulatory requirements are adhered
to, CleanGoods finds that their data is prone to error, often
duplicated, and leads to unreliable business analytics, regulatory fines
and damage to brand reputation.

The current data flow is illustrated below:

![](../../../../../Resources/Images/SystemSetup/Centralized%20Cases%201.png)

### Solution

With a CMDM solution in place, the responsibilities and activities of
new customer onboarding and enrichment will be facilitated in a
centralized fashion with all the necessary data integrity and governance
in place for a more seamless experience. This ensures operational
efficiency within the new customer onboarding process by leveraging the
capture and enrichment of the right data by the right people at the
right point in time.

Lance will now initiate new customer requests directly within MDM which
runs a *Find Similar* algorithm to proactively ensure uniqueness and
eliminates the risk of introducing duplicate or redundant customer
records.

Lance will enter the terms of sale and all associated information onto
the new customer request, at which point Lance will transfer the
onboarding task (within MDM) to Kathy in Finance for further enrichment.
Kathy will then see the new task within her task list which informs her
that she needs to enrich the same record Lance initiated.

Once the task is assigned to Logistics, George can find all the
information in MDM. This allows him to quickly turn around and establish
a plan to meet the new order requirements. Once logistical information
has been entered a final review is performed by the MDM specialist and
the new customer may be considered as an active customer of CleanGoods.

![](../../../../../Resources/Images/SystemSetup/Centralized%20Cases%202.png)

Scenario 2: Onboarding New Retail Store Locations
-------------------------------------------------

### Who

Same characters as in Scenario 1: Philip, Lance, Kathy, and George.

### What

[BlueBox Retailer]{.bold} is seeking to strategically expand their
footprint in the Southeast region of the United States. In order to beat
their competitors to new markets, executive management has devised plans
to open 12 new BlueBox Retailer locations in suburban neighborhoods of
multiple major metropolitan areas in the Southeast.

The impact of new store locations is that all product line purchase
orders must be amended or supplemented to meet the demand of an entirely
new geographical region. To meet this demand, [Philip]{.bold} has
reached out to CleanGoods Manufacturing.

Philip works with [Lance]{.bold}, a Sales Support Specialist, to provide
the necessary information. Since BlueBox Retailer is a realized
customer, Lance does not need to initiate an onboarding process, but
rather update the existing customer. To do so Lance must:

-   Obtain the physical address of all 12 locations in order to create
    the relevant Ship-To's and Sell-To's.
-   Obtain information on what specific product lines the new stores
    will carry
-   Obtain any additional information specific to these new locations
    (Geographical, new product line availability, order frequency, etc.)

[Kathy]{.bold} from Finance will work with Lance reviewing sales terms
for the new locations. While new locations may have little to no impact
to terms of sale, it is Kathy's responsibility to ensure both parties
are in agreement of the negotiated terms. It is up to CleanGoods'
discretion whether they would provide special allowances to assist in
promoting the BlueBox new store location.

[George]{.bold} from Logistics must determine how to fulfill the order.
This involves evaluating several factors such as projected order
frequency, product assortment, volume, stock, package type, geography,
etc. Since BlueBox Retailer requires that all products be shipped
directly to their stores, George will leverage the new Ship-To's to plan
out routes and scheduling.

The challenges faced by CleanGoods are:

-   Lack of standardized collaboration mechanism between roles /
    departments; everything is transacted over email and/or in person
    notifications
-   Lack of traceability of changes to data over time which leads to
    challenges during investigation and accountability
-   Challenges to data governance leads to poor regulatory adherence and
    decrease in brand reputation

### Challenge

The current data flow of adding new stores and corresponding Bill-to and
Ship-to locations does not provide a dynamic for the various teams to
easily collaborate. Currently, Lance must email the MDM Specialist to
notify of upcoming changes to an existing customer, BlueBox. The MDM
Specialist must then update the customer record in ERP and notify Kathy
to evaluate the financial impacts. Should Kathy have any questions for
Lance regarding the request, she must contact him separately. Lastly,
George must also be notified so he may consider the logistical impact of
multiple new Ship-to locations.

Without a centralized ownership of the maintenance process and
governance in place to ensure validations and regulatory requirements
are adhered to, CleanGoods often finds that their data is prone to
error, duplicated, and leads to unreliable business analytics,
regulatory fines, and damage to brand reputation.

The current data flow is illustrated below:

![](../../../../../Resources/Images/SystemSetup/Centralized%20cases%203.png)

### Solution

With a CMDM system in place, the various departmental responsibilities
of updating an existing customer record is now within a centrally
governed and collaborative solution.

Lance will now be able to edit the existing BlueBox customer record by
adding the necessary location information as well as relevant sales
attribution. Lance may then assign a task to Kathy within the
application.

Kathy will review and reference the updated information to enable her to
finalize any changes necessary to sales terms and related pricing.

Once the task is assigned to Logistics, George is now able to see the
updated Ship-To locations which allows him to quickly turn around and
establish a plan to meet the new order requirements.

The future state data flow is illustrated below:

![](../../../../../Resources/Images/SystemSetup/Centralized%20Cases%204.png)

Scenario 3: Existing Customer in Additional Line of Business
------------------------------------------------------------

### Who

Same characters as in Scenario 1: Philip, Lance, Kathy, and George.

### What

BlueBox Retailer is seeking to expand their in-store selection of
household, consumer-grade charcoal to take advantage of the upcoming BBQ
season. To do so, BlueBox has initiated sales negotiations with
CleanGoods' charcoal line of business under the sub-brand, CleanCoal.
Although BlueBox is an existing customer, onboarding a new line of
business requires a similar governing process as onboarding a new
customer.

Alexander works with Lance to initiate sales negotiations for
CleanCoal\'s line of business. Since there is no need to validate
BlueBox as a legitimate business entity, Lance must determine and update
the following information:

-   Trade Channel - How products reach the end-consumer (i.e., In-store
    retail, e-commerce, mail order, warehouse stores, etc).
-   Product Lines - What types of products will Bluebox Retailer be
    purchasing?
-   Location Set-up - Determine whether existing Ship-To and Sell-To
    locations are sufficient or if new locations are required to be set
    up for the new product line.

As part of the process, Kathy from the Finance department must ensure
finance-related enrichment activities takes place. This may include
working with Lance during sales negotiations to provide pricing and
trade promotion of products sold to BlueBox that is specific to the
CleanCoal line of business. Pricing usually originates and is maintained
within an ERP system.

Once the customer sales & financial enrichment process is complete,
George from the Logistics department must determine if the customer
requires:

-   Ship to Store
-   Ship to Customer Distribution Center
-   Direct pick-up at the manufacturer

Considerations must be given to storage requirements as well as any
regulatory requirements or hazardous material protocols for transporting
and storing charcoal.

### Challenge

The current data flow of adding a new line(s) of business, relevant
sales terms, and corresponding Bill-to and Ship-to locations does not
provide a way for the various teams to easily collaborate. Currently
Lance must email the MDM Specialist to notify of upcoming changes to an
existing customer, BlueBox. The MDM Specialist must then update the
customer record in ERP and notify Kathy to evaluate the financial
impacts. Should Kathy have any questions for Lance regarding the
request, she must contact him separately. Lastly, George must also be
notified so he may consider the logistical impact of multiple new
Ship-to locations.

Without a centralized ownership of the maintenance process and
governance in place to ensure validations and regulatory requirements
are adhered to, CleanGoods often finds that their data is prone to
error, duplicated, and leads to unreliable business analytics,
regulatory fines, and damage to brand reputation.

The current data flow is illustrated below:

![](../../../../../Resources/Images/SystemSetup/Centralized%20Cases%205.png)

### Solution

With a CMDM system in place, the various departmental responsibilities
of updating an existing customer record is now within a centrally
governed and collaborative solution.

Lance will now be able to edit the existing BlueBox customer record by
adding the new line of business as well as relevant sales attributes; he
may then assign a task to Kathy within the application.

Kathy will review and reference the updated information to enable her to
finalize any additions or changes necessary to sales terms and related
pricing.

Once the task is assigned to Logistics, George is now able to see the
updated Ship-To locations which allows him to quickly turn around and
establish a plan to meet the new order requirements.

The future state data flow is illustrated below:

![](../../../../../Resources/Images/SystemSetup/Centralized%20Cases%206.png)
