---
description: 'Customer MDM Solution: This topic provides an overview for
  the data flow of a coexistence solution.'
title: '\[%=Heading.Level1%\]'
---

Data Flow for Consolidation and Coexistence CMDM
================================================

Having customer data authored and stored across separate source systems
creates a barrier for achieving a unified and trusted view of customer
data. When data has multiple sources, it can become inconsistent,
inaccurate, outdated, and cause conflicts.

ACME Company has multiple source systems from which customer data
originates. The flow of customer data for ACME Company begins at these
points of entry, each of which is associated with a variety of channels.
These channels include: the company website, phone direct, in-store,
etc. (see Figure 1 below). ACME contains three source systems (Figure
2):

-   E-commerce system for customers who place their orders and
    self-registers via the company's website.
-   ERP system for customers who place orders by phone via ACME
    Company's call center.
-   CRM system for driving seasonal marketing campaigns and financial
    data, which drives in-house financing as well as managing customer
    loyalty programs.

To understand how data flows into STEP and between applications, refer
to the two implementation methodologies: consolidation and coexistence.
For information on how the different implementation methodologies
function, see the **Customer Master Data Management Overview** section
of this documentation[ here]{.mcFormatColor style="color: Blue;"}.

Data enters into STEP through external channels where customers will
provide their information. In section 1 of the image below, these
channels may be through a telephone order, a web order, when they sign
up for a loyalty platform, or when they buy in-store.

After their data is recorded, it is saved to various source systems.
A source system is any system that stores data to be delivered to the
CMDM solution. In this use case, the source systems are the CRM, ERP,
and E-commerce platforms (Figure 2). Once the data is inside of the CMDM
application, data is standardized, matched with existing records, and
golden records are created / maintained. Data will then be stored in a
datastore / data warehouse.

For more details on what happens in Figure 3, see the Application path
image following this section. Also, see the **Matching** topic
([here]{.mcFormatColor style="color: Blue;"}) and the **Loqate** topic
([here]{.mcFormatColor style="color: Blue;"}) of this documentation for
more information.

In a coexistence implementation, the data matched and merged in the CMDM
solution (Figure 3) will be updated back at the source systems (Figure
2) as well as downstream solutions (Figure 4).

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/System%20Flow.png)
