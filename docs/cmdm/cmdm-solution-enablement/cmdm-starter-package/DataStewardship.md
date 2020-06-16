---
description: 'Customer MDM Solution: The data steward has many
  responsibilities and tasks to perform in the Web UI.'
title: Data Stewardship
---

Data Stewardship
================

Data stewardship in a CMDM application is performed by two distinct
roles: data stewards and business users. Each role requires the
configuration of different Web UI screens to perform certain tasks. In
this topic, these two roles (and the tasks performed by each) will be
defined. Web UI configuration guidelines will also be provided.

When configuring any Web UI, consult the Web UI documentation[
here]{.mcFormatColor style="color: Blue;"}. This documentation contains
details on how to add various components of the Web UI.

Role of the Data Stewards
-------------------------

Experienced data stewards must be provided with the proper tools to
ensure data quality.

These tasks include:

-   Clerical Review - Data Stewards can review potential duplicates.
-   Manually maintaining records - Data Stewards update and edit records
    as needed.
-   Monitoring / Data Quality - Data Stewards should review customer
    data quality in the Web UI, and monitor Source system performance.

Data Steward Tasks
------------------

Typically, Data Stewards will need to perform the following tasks:
clerical review, ad-hoc data stewardship, data governance, hierarchy
maintenance, and attribute maintenance.

The online help topics for these tasks are extensive and cover
configuration and typical use.

### Clerical Review

Clerical reviews allow a data steward to approve matched duplicates,
reject erroneously matched records, and reassign tasks that are better
suited for other users.

To assist data stewards in identifying critical issues, Clerical Review
task lists can be filtered to display only high priority tasks. To flag
tasks as high priority, a workflow status flag and accompanying business
condition must be configured on the relevant matching algorithm.

![](../../../../Resources/Images/Solution%20Enablement/CMDM/TaskList.png)

![](../../../../Resources/Images/Solution%20Enablement/CMDM/High%20Priority%20Filter.png)

For more information on clerical reviews, see the **Golden Record
Clerical Review Task List** topic in the **Using a Web UI**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

**Use Cases**

Arthur is a senior data steward responsible for the carrying out several
data management tasks, and must interact with many areas of the Web UI
to do so.

When Arthur begins his day, he will first handle any clerical review
tasks that may have been generated from the previous day's activity.
Some new customers coming into CMDM have a risk flag set to 'yes', this
requires Arthur's immediate attention. Arthur is made aware of these
high priority tasks through a visual cue (see below). Arthur is then
able to enter the task list and filter based on priority. This allows
Arthur to immediately address the high priority clerical reviews, before
continuing with his other tasks.

**Components**

Arthur utilizes the following components to address the story presented
above:

1.  The Primary Navigation Panel - Allows Arthur to see all clerical
    review tasks grouped in one central location. For more information,
    see the **Primary Navigation Panel Component** section of the **Web
    UI** documentation[ here]{.mcFormatColor style="color: Blue;"
    conditions="Primary.Web"}.
2.  Golden Record Clerical Review Task List -- Allows Arthur to address
    deduplication tasks. More specifically, this screen allows for
    merging duplicate records, task reassignment, and rejecting
    potential duplicates.
3.  Advanced Merge -- Allows Arthur to manually dictate survivorship by
    selecting individual attribute values.

Data stewardship requires users to deal with voluminous amounts of data.
To make it easy to manage this data quickly, collections are used.
Collections are created by performing an advanced search then saving the
results. These collections can be used to perform bulk updates as well
as access all these records at will.

For information on collections and how to create queries for searching,
see the **Using Advanced Search** topic in the **Web UI** documentation[
here]{.mcFormatColor style="color: Blue;"}. To use the collections with
ad-hoc bulk updates, see the **Bulk Update Operations** topic of the
**Bulk Update** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

**Use Cases**

Arthur has been tasked with identifying all customers who live in
Florida so they can create a new campaign to market ACME's new swimwear.
Utilizing an advanced search, Arthur can identify these customers and
save them as a collection. Arthur can then export this collection and
send it to the appropriate marketing specialists.

Arthur has been asked to investigate customer email quality to ensure a
successful marketing campaign. Arthur realizes that no validations have
been run to verify email addresses. Utilizing a bulk process, Arthur can
have all customer emails validated (i.e., Experian). This allows
marketing to avoid sending emails to customers with invalid email
addresses. These customers can then be sent a physical letter with the
promotion.

**Components**

Arthur utilizes the following components to address the story above:

1.  Advanced Search Screen - A link from the homepage takes Arthur to an
    advanced search screen, allowing him to customize a search based on
    a variety of options. Collections can be saved once a search is
    made. For more information, see the **Advanced Search** section of
    the **Web UI** documentation[ here]{.mcFormatColor
    style="color: Blue;"}.

![](../../../../Resources/Images/Solution%20Enablement/CMDM/AdvancedSearchConfig.png)

1.  Node Details Screen -- Once a collection is saved it can be accessed
    and viewed via a node details screen. Manual edits of the customer
    data may also be made from this screen. For more information, see
    the **Node Details Screen** section of the **Web UI** documentation[
    here]{.mcFormatColor style="color: Blue;"}.
2.  Export -- Data exports may be made on search results for reporting
    purposes.
3.  Bulk Updates -- Bulk updates may be executed on a collection for
    mass editing.
4.  Collection Content -- Sub screen used to display a list of records
    in a collection.
5.  Source Record Traceability -- Sub screen that allows Arthur to see
    which source system individual attribute values were retrieved from.
    For more information, see the **Golden Record Source Traceability
    Screen** section of the **Web UI** documentation[
    here]{.mcFormatColor style="color: Blue;"}.

### Hierarchy Maintenance

Maintaining the company hierarchy is key to ensuring that data can be
correctly represented across the enterprise. Using a hierarchy
visualization implementation helps represent the flow of companies and
how their ownership functions.

For more information on setting up and using a company hierarchy, see
the **Company Hierarchy Visualization and Maintenance** topic of the
**Web UI** documentation[ here]{.mcFormatColor style="color: Blue;"}.

**Use Cases**

A volcanic eruption has destroyed an ACME subsidiary. Arthur has been
asked to remove the subsidiary from ACME's corporate hierarchy.

Arthur navigates the subsidiary in question and selects the hierarchy
tab. From this screen, Arthur can remove the link to its parental
organization using built in functions.

**Components**

Arthur utilizes the following components to address the story above:

1.  Global Search -- Arthur is able to navigate to the subsidiary based
    on source record ID.
2.  Company Data Hierarchy Screen -- This screen allows Arthur to add,
    edit, and remove links throughout the hierarchy. Several different
    views are also available for each hierarchy.

### Attribute Maintenance

Data stewards must create and maintain various attributes and attribute
groups.

For more information on attributes, see the **Attribute and LOV Creation
and Maintenance in Web UI** topic of the **Web UI** documentation[
here]{.mcFormatColor style="color: Blue;"}.

**Use Cases**

Arthur has been notified by management that an upstream SAP system is
now tracking additional financial attributes (Income Verified Flag).
Arthur would like to create this attribute in CMDM, so he will have
access to the most complete view of the customers.

To do so, Arthur will utilize the attribute maintenance screens. First,
Arthur will need to identify the correct party data attribute group.
Since this is new financial data, Arthur decides it belongs best in the
IncomeData group. Arthur selects this group and can create the attribute
using the buttons on the screen.

**Components**

Arthur utilizes the following components to address the story above:

1.  Attribute Group Management Screen -- Using this screen, Arthur can
    view all attributes within the attribute group and judge whether the
    new attribute he wants to create belongs there. For more
    information, see the **Attribute Group Management Screen** section
    of the **Web UI** documentation[ here]{.mcFormatColor
    style="color: Blue;"}.
2.  Attribute Link Editor Screen - Arthur can establish or remove links
    between attributes via this screen. For more information, see the
    **Attribute Link Editor Screen** section of the **Web UI**
    documentation[ here]{.mcFormatColor style="color: Blue;"}.
3.  Attribute Management Screen -- Arthur can create new attributes or
    edit existing ones via the Attribute Management Screen. He can edit
    the attribute details, change the attribute validity, and maintain
    attribute links via various tabs configurable on this screen. For
    more information, see the **Attribute Management Screen** section of
    the **Web UI** documentation[ here]{.mcFormatColor
    style="color: Blue;"}.

**Additional Considerations when Performing Attribute Maintenance**

Import configurations will need to be updated with the appropriate
mappings. Otherwise the new incoming data will not be written to any
attribute.

If the attribute does not fit into any existing attribute groups, a new
group should be created first. If the attribute fits into a current
display group, no Web UI configuration is needed. If it is a standalone
attribute, it will need to be manually added to the appropriate details
screens.

If the attribute should be considered during matching, the algorithms
and/or match codes will need to be adjusted. If the intention is for the
attribute to 'pool' similar customers together, it should be added as a
match code function. If the attribute is intended to be considered by
the algorithm, a new corresponding normalizer and matcher must be added.
Additionally, the rules must be updated to include how the final score
provided by the algorithm is affected. In order for survivorship to
properly execute, the attribute must be placed in the relevant
survivorship groups.

An onboarding process may be considered to verify that all
considerations have been accounted for prior to finalizing new
attribute(s).

If the attribute should be monitored via data governance, required
policies and widgets will need to be updated to account for it.

Role of Business User
---------------------

Experienced business users need to be able to accurately search for
customers to verify information, and export customer data.

### Business User Tasks

Business users need to be able to maintain small areas of the database,
mostly involving searching for customers to find records and exporting
this data.

### Advanced Search and Data Export

Business users need to be able to navigate the large amount of data in
the system. To do this, they need to create customized, granular
searches using a myriad of search criteria.

Nikki, a business user, has been asked to export a list of customers who
have outstanding payments. To do so, Nikki utilizes an advanced search.
Nikki then saves the results to a collection and uses the built-in
buttons to export.

![](../../../../Resources/Images/Solution%20Enablement/CMDM/PastDueDollars.png)

To build these search queries, see the **Using Advanced Search** topic
in the **Web UI** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Once the data is isolated for external support, the data will need to be
exported. For more information, see the **Export Manager** topic of the
**Data Exchange** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

### Manual Edits

Business users may also manually edit customer information within the
Web UI. One example is a business user working within a call center may
receive an updated contact number from a customer. The business user may
edit an existing phone number or add an additional number to the
customer's record.

While working in a call center, Nikki receives a phone call from a
customer. The customer has notified Nikki that they are moving and would
like to update their address to continue receiving promotional mailings.
Nikki is able to look this customer up based on a provided loyalty card
number and manually update the address. Once Nikki saves the address
update, Loqate will trigger and standardize the new address.

Manual edits within the Web UI is generally carried out within the Node
Details Screen.

### Hierarchy Maintenance

Business users may also be responsible for maintaining company
hierarchies.

Maintaining the company hierarchy is key to ensuring that data can be
correctly represented across the enterprise. Using a hierarchy
visualization implementation helps represent the flow of companies and
how their ownership functions.

For more information on setting up and using a company hierarchy, see
the **Company Hierarchy Visualization and Maintenance** topic of the
**Web UI** documentation[ here]{.mcFormatColor style="color: Blue;"}.
