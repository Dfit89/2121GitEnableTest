---
description: 'Customer MDM Solution: This topic describes the role of
  the customer object type in the CMDM solution.'
title: Customer Object Types
---

Customer Object Types
=====================

What is a Customer?
-------------------

A customer is any individual or organization that purchases from a
business. That said, any individual or organization could potentially
interact with a business in another capacity (e.g., as a supplier or
employee). Because of this, 'Customer' is defined as a role an
organization or an individual has in the interaction with a business.

However, businesses do not typically manage information about
individuals and organizations in a shared model across vastly different
business processes, like procurement (supplier) and sales (customer),
for simplicity's sake. To account for this, 'Customer' is used as a
catch-all entity type that owns all information about individuals and
organizations. For more about customer types, see details about contact
persons below.

### Individual Customer

For an individual customer, the typical customer attributes are:

-   First Name
-   Last Name
-   Addresses
-   Date of Birth
-   Gender
-   Phone Numbers
-   Fax numbers
-   Emails
-   Social Media IDs
-   Loyalty Card Information
-   Government IDs (social security, passport, driver\'s license)

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/IndividualCard.png)

### Organization Customer

For an organizational customer, the typical customer attributes are:

-   Legal Name of the Organization
-   Date of Formation
-   Address
-   Contact Information
-   Main Phone
-   Fax
-   Main Email
-   Website URL
-   GLN / ILN
-   DUNS Number
-   Tax Identification Number
-   Risk Category

Organization customers are often organized in hierarchies. See section
about organization hierarchies below:

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/OrganizationCard.png)

What is a Household?
--------------------

A household is a collection of individuals, which is typically a family,
living in the same home. Each member of the household is considered an
individual customer.

The purpose of these household constructs are to help businesses target
customers that share a household either as a family unit or as
individual customers. This allows the company to limit extraneous
mailing campaigns and aggregate buying patterns.

In the CMDM initial configuration, Households are discovered by matching
and created via Link Golden Records.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/HouseholdImage.png)

Accurately identifying the correct members of a household comes with
natural limitations, as the definition of household is quite vague and
vary from case to case. The data available to determine if specific
people are actually accurately identified as part of the same household
is often rather sparse.

Address and last name are the two most common matching criteria used to
determine households. For more information, see the **Algorithm & Match
Codes - Household** section of this documentation[ here]{.mcFormatColor
style="color: Blue;" conditions="Primary.Web"}.

This approach is intended for situations where accuracy must aim to be
good but both false positives and false negatives can be accepted, such
as with the case of analytics and mailing campaigns.

### Handling Composite Records with Data Containers

A customer record comprises multiple objects. It may have multiple
addresses, emails, and phone numbers, which are all considered part of
the record by users, as well as surrounding systems.

This is not to be confused with hierarchical structures of separate
entities with each containing their own data flow.

Examples of separate entities may include:

-   contact persons for organization customers
-   store branches
-   warehouse locations

Such records are complex structures in themselves that may even
reference or be referenced by other entities.

For more information, see the **Data Containers** topic in the **System
Setup / Super User Guide** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

### Addresses

An address comprises several attributes that define a location. STEP
offers specialized functionality around addresses, such as address
verification via the Address Component Model.

Modeling addresses using data containers makes it possible to manage
more than one address on the same customer / contact person. Data
containers simplify the data modeling by providing a reusable address
definition across multiple object types. When displayed in Web UI,
addresses modeled using data containers can appear as one formatted
value, despite being made of several attributes.

Addresses have metadata associated with them via the Address Component
Model, the CASS address component model, and potentially solution
specific meta data.

### Email Addresses and Phone Numbers

Email addresses and phone numbers should be modeled as data containers,
as it is typical to have multiple phone numbers and email addresses for
the same customer or contact person. It is also common to have meta data
associated to each phone number or email address. The initial
configurations have PhoneType as a Data container key. This allows a
customer to only have one of each type of phone (cell, home, etc).

Handling Confidential Information
---------------------------------

### Credit Card Information

Credit Card information should not be stored in or pass through STEP due
to compliance requirements. It is simpler to store \'Recurring Charge
Subscription IDs\' when integrating to third-party services.

### Bank Account Information

Handling bank account information does not typically require more
security than name and address information.

### Privileges

STEP Privileges to control who has access to what attributes and/or
attribute groups.

### Security

This guide does not cover information security in STEP in a broader
sense, like infrastructure recommendations, encryption strategies, etc.

The sample data provided in the initial configuration provides only main
addresses. There are no delivery addresses.
