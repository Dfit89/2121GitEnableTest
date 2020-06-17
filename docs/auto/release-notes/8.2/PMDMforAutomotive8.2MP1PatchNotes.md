---
description: 'Automotive Solution: PMDM for Automotive 8.2 MP1 August
  2017 Maintenance Patch Notes '
title: PMDM for Automotive 8.2 MP1 August 2017 Maintenance Patch Notes
---

PMDM for Automotive 8.2 MP1 Patch Notes {#pmdm-for-automotive-8.2-mp1-patch-notes .MPN}
=======================================

Release Date: August 2, 2017 {#release-date-august-2-2017 style="text-align: center;"}
----------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST-2206, 2209Added support for explicit deletions in
ACES Importer

Previously, deletions were only supported via complete replacement
scenarios (SubmissionType=FULL). Now, deletions can also be carried out
using an explicit delete (action=D) when a standard update file
(SubmissionType=UPDATE) is supplied.

PRODOC note: RDCUST-2159, 2165, 2162, 2163Added support for recent
format changes in AutoCare reference data

Beginning in April 2017, AutoCare released some minor format changes in
the reference data files (PCdb, PAdb, VCdb, Qdb, and Brand). The
corresponding importers have been updated to support these changes. A
complete list of changes is available upon request, but is not listed in
these notes as all changes were insignificant. For example, the PCdb
Category.txt file is now called Categories.txt, and the order of columns
in the Codemaster.txt file was changed.

Bugfixes {#bugfixes .MPNBugFix}
--------

PRODOC note: RDCUST-1998, 2105Added Javadoc for import flow

Previously, the import flow package was included in the Extension API,
but the Javadoc was not available for it. This has been added and all
documentation can be found in the Extension API Javadoc for the
com.stibo.importflow.domain.extension package.

PRODOC note: RDCUST-2207Corrected handling of unidentified Supplier in
ACES Importer

Updated ACES Importer to error during conversion if the brand(s) in the
input file are identified as needing to take Supplier into consideration
and Supplier cannot be parsed from the file name. Previously, when
Supplier needed to be identified and could not be, the file would import
successfully with Supplier indicated as Unknown.

PRODOC note: RDCUST-2246Corrected handling of Notes in ACES Importer

Previously during Application ID generation, the ID of a Note was used
rather than the text. As ID is an optional parameter on a Note, this
could lead to cases where an application would be skipped as a duplicate
because the Note was not recognized properly due to the missing ID
information. The ACES Importer has been updated to include the Note text
(rather than the ID) in the generation of the hash function that is used
in an application record ID. As this changed the algorithm of the
application ID generator, **all previously imported application records
should be deleted and re-imported to match the new ID generation
pattern.**

PRODOC note: RDCUST-2080, 2081Labels added to Bulk Updates and Delete
actions in Web UI Application Editor

Previously, the Bulk Applications Updates and Delete Application actions
available in the Application Editor in Web UI did not contain any
default labels, and manually entered labels would not render on the
screen. This has been corrected so that a default label is present for
both actions, and when the default is overwritten, it is shown on the
screen.

PRODOC note: RDCUST-2083Corrected Application Asset Reference header in
Web UI Application Editor

Previously, when adding the Application Asset Reference header to the
application results table, it would display with \"Not configured\" as
the header. This has been corrected so that \'Application Asset
Reference\' is displayed as the default header, which can be updated via
configuration.

PRODOC note: RDCUST-2086Corrected presentation of null options in the
Web UI Application Editor

Previously, when adding an option via the Condition header in the
application results table, in some cases if an option was selected but
no value applied, the table would display \'null.\' This has been
corrected so that the cell remains unpopulated if no value is applied.

PRODOC note: RDCUST-2148Corrected behavior of the part selection cell in
the Web UI Application Editor

Previously, the part selection cell (e.g., Part Number) included a node
picker so that users could browse and select a part. This was
unintentionally removed and users were only able to select parts via
typing in the cell. This has been corrected so that the node picker is
again available when clicking in the cell.

PRODOC note: RDCUST-2148Corrected handling of Engine and Axle in TecDoc
Export

The TecDoc TAF 2.4 Exporter did not handle the export of engine or axle
criteria correctly. This has been fixed so that they are exported
properly.

PRODOC note: RDCUST-2211Added warning for delete records in an ACES FULL
file in the ACES Importer

When the Submission Type of an ACES file=FULL, it means that all records
in the input file should comprise the full set of data in the database,
per the replacement rules for that system. Therefore, deletions are not
supported in replacement scenarios (e.g., Submission Type = FULL or
Submission Type = UPDATE and Partial Replacement is selected as the
replacement method). Previously, if a deletion is passed in a FULL file
(e.g., action=\"D\"), the record was skipped but the user was not
notified that this had occurred. The importer has been updated so that
the Conversion execution report now includes a warning for any records
that are skipped due to being deletions when a replacement scenario is
in effect.

PRODOC note: RDCUST-2099Fixed bug with multi-valued attribute handling
in Web UI Application Record Editor

When working with multi-valued attributes in the criteria / option
editor within the Application Record Editor, adding multiple values for
an attribute would generate an exception. This has been corrected.

PRODOC note: RDCUST-20448Corrected issue with Date attributes in Web UI
Application Record Editor

Using the Condition Group Header in the editor, attributes with
validation type \'ISO Date\' or \'ISO Date and Time\' were being
displayed using the client browser locales (date format) not system
locales like in other components (e.g., Attribute Value Header), which
resulted in validations errors. This has been fixed to display \'ISO
Date\' and \'ISO Date and Time\' attributes with system locales (like
other Web UI components).

PRODOC note: RDCUST-2088Compressed View button added to Application
Record Editor Web UI screens where it was missing

The Compressed / Normal View button (label changes as the view modes are
toggled between) was missing from several Web UI screens that use the
application editor. Specifically, the screens designed for viewing
applications from a vehicle / assembly or part / article were missing
the option. This has been added to all screens where it was missing. The
Web UI easy setup option should be re-run for any standards that had
been previously set up to have the button added.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

**to:automotive/7.0/automotive-7.0.3.spr**

Note that the above recipe is compatible only with the STEP 8.2 baseline
release (to:step/trailblazer/step-8.2.spr).

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
