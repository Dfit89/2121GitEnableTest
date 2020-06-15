---
description: 'For the Suppliers to be able to onboard Products via PDS,
  the schema used for the PDS channel needs knowledge about the Supplier
  facing product hierarchy, the set of Supplier relevant attributes and
  asset references etc., as defined in PMDM for Retail. This section
  contains information about how this can be controlled in PMDM for
  Retail.'
title: '\[%=Heading.AnyLevel%\]'
---

Vendor Data Onboarding - Setup
==============================

Initial Setup for Vendor Data Onboarding Module
-----------------------------------------------

Contact your Stibo Systems account manager or partner manager for
information on activating the PMDM for Retail solution:

-   PMDM: STEP 10.0 (or greater)
-   Service activation (license, PDS channel)
-   Install and configure the module

Some of the key setup activities are described in the next paragraphs.

More tasks must be performed to make the configuration fully
operational, which will not be handled by your dedicated consultants or
partners.

-   PDS-related data (see below)
-   Suppliers (see below)
-   Matching & linking
-   Users and groups
-   Contexts
-   Asset push
-   OIEP
-   Configure profiling for KPIs

Configuration of the data model for the PDS channel
---------------------------------------------------

For the Suppliers to be able to onboard Products via PDS, the schema
used for the PDS channel needs knowledge about the Supplier facing
product hierarchy, the set of Supplier relevant attributes and asset
references etc., as defined in PMDM for Retail. This section contains
information about how this can be controlled in PMDM for Retail.

When there has been a change to the data model in PMDM for Retail which
is relevant for the PDS channel then it is necessary to make a schema
update in PDS to reflect the change. This can be done as a weekly
scheduled process or on request.

### Supplier facing Product Hierarchy

The selectable product categories in the PDS channel include all nodes
of the object types External Level1 - External Level 6 defined below the
"External Product Hierarchy" node.

The product hierarchy allows for creation of External Source Records
starting at External Level 3.

Packaging Objects (Pallet, Case, Pack) will be created directly below
the "External Packaging" node.

### Attributes

There are three attribute groups where all viewable attribute groups
will be stored: Product Maintenance, Packaging Maintenance and Category
Specific Attributes.

All attributes in the mentioned groups will per default be shown to the
Suppliers in PDS.

If specific attributes in the mentioned attribute groups should not be
shown in PDS then the attributes have to be linked to the "PDS: Hide
From Supplier" attribute group.

### Asset references

The set of asset reference types to display in PDS can be controlled by
setting the "PDS: Relevance" attribute to Yes on the asset reference
type definition for the PDS relevant asset reference types.

### Display sequence of Attributes and Attribute Groups

The "Display Sequence" attribute valid on attribute definitions,
attribute group definitions and on attribute links can be used to
control the display order of attribute groups and attributes within
those groups in PDS.

### Required for Initiate

It might not be necessary that the Supplier fills out the full set of
mandatory attributes before he submits a new Product to PMDM for Retail.
A short description and the GTIN of the Product might be enough for the
Retailer to determine if this is a product they would like to onboard.

The set of attributes being mandatory for initiate is defined by linking
the attributes to the "PDS: Mandatory For Proposal" attribute group.

### Mandatory Attributes

The set of attributes being mandatory for submit after initiate is
defined by linking the attribute to the "PDS: Mandatory For Submit"
attribute group.

Category specific mandatory attributes are controlled using the standard
Mandatory option on the attribute link.

### Category Specific Mandatory Asset References

Category specific asset references that are mandatory will sit on the
product category node itself. The multi-valued "PDS: Mandatory
References" attribute will hold the list of references that are
mandatory on that category.

### Locked Down Attribution

It might be beneficial to be able to lock certain attributes after a
product has been initially onboarded into PMDM for Retail to prevent the
value of these attribute gets changed by the Supplier. To enable this,
the relevant attributes must be linked to the "PDS: Locked After
Proposal" attribute group.

### Attribute Help Text

It is possible to show description of attributes and asset references to
the Suppliers in PDS by using the "PDS: Description" attribute being
valid for attribute definitions and asset reference definition.

Setup of new Suppliers
----------------------

Before a Supplier can submit product data from PDS the Supplier has to
be created in PMDM for Retail.

A few objects must be created per supplier and a few configuration
options needs to be defined per Supplier.

To setup a new Supplier the following steps are needed:

1.  Create a new Supplier User Group below the Suppliers user group.

As part of this process, the Supplier Classification is created by
selecting the parent for the Supplier Classification below the
"Suppliers" classification node.

1.  Create a User below the new Supplier User Group.

This user is used by PDS to authenticate against PMDM for Retail.

1.  Set the value of the "PDS: Is Service Account?" attribute to "Yes"
    on the new User.

This will start a process which will link the user to the "PDS: Service
Accounts" user group and add the User ID to the "PDS: Service Account"
attribute on the Supplier Classification.

1.  On the Supplier Classification the following attributes should be
    maintained:

-   **Supplier ID and Supplier Name** - Used to identify the Supplier
    and to ensure uniqueness.
-   **Type of Supplier** - Used for information purpose when comparing
    sources for a Golden Record.
-   **General Handling of New Source Records** - Controls if new
    External Source Records from this Supplier should be automatically
    approved in PMDM for Retail or if the Buyer needs to manually
    approve the product data before onboarding the Product.
-   **General Handling of Updated Source Records** - Controls if a
    change to an existing External Source Records from this Supplier
    should be automatically approved in PMDM for Retail or if the Buyer
    needs to manually approve a change before it is considered for
    promotion by the Matching and Linking process.
-   **General Rank For Supplier and General Rank Type Of Supplier** -
    Used by the Matching and Linking survivorship rules to control the
    preferred order of source when promoting product data to the Golden
    Record.

**Rank Type Of Supplier has the following options**: "Approved Content
Source" (AC) and "Non-Approved Content Source" (NA).

**Rank For Supplier has the following options**: 1, 2, 3, 4, 5.

The values of the two attributes are concatenated into a single Source
Rank For Promotion value which is used by the survivorship rules when
promoting product data to the Golden Record.

The preferred order of sources configured in the survivorship rules in
PMDM for Retail is:

MDM, AC1, AC2, AC3, AC4, AC5, NA1, NA2, NA3, NA4, NA5, NA99

where:

MDM: Internal Source Record

AC1-5: Approved Content Source

NA1-5: Non-Approved Content Source

NA99: Used if no Rank Type or Rank is defined for the supplier.

**Example**:

Attribute A has the value "Yes" on a source having AC2 as Source Rank
For Promotion.

The survivorship rules check the sources in the defined preferred order.
First it checks the Internal Source Record which doesn't have a value
for Attribute A. It continues to look for a source with AC1 but that
External Source Record does not have a value for Attribute A either. So
it continues by looking for a source with AC2. Finally, a value for
Attribute A is found so this value will be promoted to the Golden Record
and it will skip looking for values on lower ranked sources.

For some Suppliers it might be required to be able to overwrite the
general source record handling and product data ranking on all Products
below specific Product Hierarchy nodes. This can be done by linking a
node from the External Product Hierarchy to the Supplier Classification
using the Category Ranking For Supplier link type. The link will have
the following meta-data attributes: Category Handling of New Source
Records, Category Handling of Updated Source Records, Category Rank for
Supplier and Category Rank Type of Supplier.

5.  The Supplier Classification must be approved.

This will start a process which will generate a unique supplier
identifier in the "PDS: Supplier Identifier" attribute on the Supplier
Classification.

6.  The "PDS: Supplier Identifier" value generated within a minute of
    the initial approval of the Supplier Classification is what the
    Supplier needs for authentication when adding the channel in PDS.
