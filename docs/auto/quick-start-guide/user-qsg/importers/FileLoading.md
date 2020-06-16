---
description: 'Automotive Solution: Describes file loading.'
title: '\[%=Heading.AnyLevel%\]'
---

File Loading
============

PRODOC note: Per KRMA RDCUST-2145 Add text about loading via the widgets
here once that is released, and show one example widget. e.g., all end
user documentation for the widget should be covered. Documentation for
config of the widget isn\'t needed as a) easy setup creates it b) spec
has informative messages included in the interface so it should
essentially be self-documenting and c) it will eventually become a core
component and the Documentation team will document it in the online help
and we just need to then point to that documentation.

All of the automotive importers use hotfolders to import automotive
data. The automotive integration endpoints automatically create
hotfolders on the application server for file loading.

Users can upload files to hotfolders by accessing the application server
or by using a Web UI configured with a File Loading Widget for the
desired file type.

Uploading Files via the Application Server
------------------------------------------

To upload a file to a specific hotfolder by accessing the application
server:

1.  Access the application server and navigate to
    /upload/hotfolders/\[Importer\].
2.  Drop the file into the folder with a name aligning with the importer
    (e.g., TecDoc Reference Inbound Endpoint should have files dropped
    into the \'TecDocReferenceInputFolder\').
3.  The endpoint will pick up the file at the next scheduled polling,
    and the file load will begin.

The endpoints are created with a default schedule of polling the
hotfolder once per minute, but this setting is adjustable for each
endpoint, so it may vary between importers and implementations.

To understand what happens after the file loads it is important to first
understand how the import workflows operate, which is described in the
**Import Workflow Overview** section[ here]{.mcFormatColor
style="color: Blue;"}.

Uploading Files via Web UI
--------------------------

To upload a file to a specific hotfolder via a Web UI, a File Loading
Widget can be used. For more information, see the **File Loading
Widget** topic within **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}, and the relevant standard specific topics
available within the **Automotive Reference Guide** listed below:

### AutoCare File Loading via Web UI {#autocare-file-loading-via-web-ui conditions="Primary.Under Construction"}

-   Importing Qdb files via Web UI
-   Importing Brand files via Web UI
-   Importing PCdb files via Web UI
-   Importing VCdb files via Web UI
-   Importing PAdb files via Web UI

### NAPA File Loading via Web UI {#napa-file-loading-via-web-ui conditions="Primary.Under Construction"}

-   Importing Vehicle files via Web UI
-   Importing Translation files via Web UI
-   Importing Attribute files via Web UI
-   Importing Application files via Web UI
-   Importing Interchange files via Web UI

### TecDoc File Loading via Web UI

-   Importing Reference Data Files via Web UI ([here]{.mcFormatColor
    style="color: Blue;"})
-   Importing Supplier Data Files via Web UI
