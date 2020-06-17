---
description: 'Automotive Solution: Supported Versions and Formats'
title: '\[%=Heading.AnyLevel%\]'
---

Supported Versions and Formats
==============================

The following are the supported import and export versions and/or
formats for the various automotive standards.

If there is only one format for the data type and the format itself is
not versioned, \'Format is not versioned\' is listed.

Generic

-   **Asset Exporter:** Format is not versioned (generic exporter not
    specific to any standard). .

AutoCare

-   **ACES Exporter:** ACES 3.0, ACES 3.2 and ACES 4.0
    ([here]{.mcFormatColor style="color: Blue;"})

```{=html}
<!-- -->
```
-   **ACES Importer:** All ACES 3.X versions are supported for import,
    though all are validated against the 3.2 schema.

Changes between the various 3.X versions are minimal so in most cases
this will result in a successful import. However, the schema for the
\'ApprovedFor\' element in the header changed with 3.2 so attempting to
load a file for an earlier version that includes the \'ApprovedFor\' tag
will fail schema validation. This can be corrected by removing the
\'ApprovedFor\' element from the header, or manually updating the
version to be 3.2.

-   **Brand Table Importer:** All three flat file formats are supported
    (original, with revision date, and with sub-brands and revision
    date) ([here]{.mcFormatColor style="color: Blue;"})
-   **PAdb Importer:** ASCII ([here]{.mcFormatColor
    style="color: Blue;"})
-   **PCdb Importer:** ASCII ([here]{.mcFormatColor
    style="color: Blue;"})
-   **PIES Exporter:** PIES 6.5, PIES 6.7 and PIES 7.0
    ([here]{.mcFormatColor style="color: Blue;"})

```{=html}
<!-- -->
```
-   **PIES Importer:** PIES 6.5, PIES 6.7 and PIES 7.0
    ([here]{.mcFormatColor style="color: Blue;"})
-   **Qdb Importer:** ASCII ([here]{.mcFormatColor
    style="color: Blue;"})
-   **VCdb Importer:** ASCII ([here]{.mcFormatColor
    style="color: Blue;"})

NAPA

-   **Application Exporter:** Format is not versioned
    ([here]{.mcFormatColor style="color: Blue;"})
-   **Application Importer:** Format is not versioned
-   **Asset Reference Exporter:** Format is not versioned
-   **MPCC / Attribute Exporter:** Format is not versioned
-   **MPCC / Attribute Importer:** Format is not versioned
-   **Interchange Exporter:** Format is not versioned PRODOC note: MEDU
    RDUCST-2678
-   **Interchange Importer:** Format is not versioned
-   **Translation Importer:** Format is not versioned
-   **Valid Vehicles Importer:** Format is not versioned

TecDoc

-   **Reference Data Importer:** TAF 2.4 using either the ZIP or 7z
    formats ([here]{.mcFormatColor style="color: Blue;"})
-   **Supplier Data Exporter:** TAF 2.4
-   **Supplier Data Importer:** TAF 2.4 using either the ZIP or 7z
    formats ([here]{.mcFormatColor style="color: Blue;"})

PRODOC note: MEDU Removed per BEJA email 11/12/2017 Reference Data
Exporter: TAF 2.4 there is no reason users would want the reference data
exported. They get it from TecDoc. \#DUH
