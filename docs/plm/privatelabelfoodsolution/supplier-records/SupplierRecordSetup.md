---
description: 'PLM Solution: For the Private Label Food Supplier Record
  functionality, a Supplier Record needs the following configurations to
  be enabled.'
title: '\[%=Heading.Level1%\]'
---

Supplier Record Setup
=====================

For the Private Label Food Supplier Record functionality, a Supplier
Record needs the following configurations to be enabled:

-   A required data model for storing information for Supplier Record
    ([here]{.mcFormatColor style="color: Blue;"})
-   A business library for creating a record of the submitted bid as an
    HTML document ([here]{.mcFormatColor style="color: Blue;"})
-   A business rule to send an email to the supplier with the submitted
    bid ([here]{.mcFormatColor style="color: Blue;"})
-   A business rule for creating an asset with the submitted bid record
    ([here]{.mcFormatColor style="color: Blue;"})
-   Changes to Private Label Food Supplier Response workflow
    ([here]{.mcFormatColor style="color: Blue;"})
-   Changes to Private Label Food Supplier Web UI ([here]{.mcFormatColor
    style="color: Blue;"})

The Supplier Record functionality use standard STEP platform
capabilities, and does not need additional Web UI components. Business
Rules are used to create a HTML record of the supplier bid.

-   An InDesign server is not required since this solution does not use
    InDesign.
-   Implemented business rules can be extended by a customer to include
    additional information or to do format changes.
