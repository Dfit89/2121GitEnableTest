Onboarding Process -- 4 -- The PMDM Aggregates the Data in a Golden Record
==========================================================================

![](../../../Resources/Images/Solution%20Enablement/PMDM/PMDM%20For%20Retail/SourceRecorded.png)

When the External Source Record is approved for further onboarding in
the External Source Record Handling workflow it automatically gets
approved and is send for Matching and Linking.

The Matching and Linking process first creates a match code for the
External Source Record which is used to check if there is already an
existing Product with the same match code in the system. Per default,
the match code is the GTIN of the Product.

It no existing Product with the GTIN is found then the system creates a
new Golden Record and an Internal Source Record for this Product. The
Internal Source Record is used by the Retailer to enrich the Product and
will contain the Retailers own product data like web descriptions, data
from the ERP system etc. If the External Source Record causing the
Matching and Linking process to be executed has corresponding external
packaging objects, then they will be duplicated to internal packaging
objects which will be linked to the created Internal Source Record.

If there is already a Product with the same GTIN then there is a match
and the External Source Record will be linked to the existing Golden
Record.

As part of the process data from all linked sources (External and
Internal Source Records) will be promoted to the Golden Record using a
set of survivorship rules which is defined on the Products matching
algorithm.
