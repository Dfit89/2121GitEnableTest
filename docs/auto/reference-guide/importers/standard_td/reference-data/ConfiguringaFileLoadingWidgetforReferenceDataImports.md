---
description: 'Automotive Solution: Describes how to configure a File
  Loading Widget for TecDoc Reference Data Imports so that Web UI users
  can import TecDoc Reference Data files into STEP using a File Loading
  Widget. '
title: '\[%=Heading.AnyLevel%\]'
---

Configuring a File Loading Widget for Reference Data Imports
============================================================

When configured, Web UI users can import TecDoc Reference Data files
into STEP using a File Loading Widget. Users can also monitor the
progress of Reference Data imports using a Status Selector Homepage
Widget and a Node Details component.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

Before starting to configure the Web UI portion of this solution, an
IIEP for a TecDoc Reference Importer must be configured within
workbench. For more information, see the **Configuring an IIEP for
Reference Data Imports** topic[ here]{.mcFormatColor
style="color: Blue;"}.

Additionally, it is helpful to know how to add a widget to a Web UI
Homepage. Details on how to do this can be found in the **Adding Widgets
to a Homepage** topic in the **Getting Started** documentation[
here]{.mcFormatColor style="color: Blue;" conditions="Primary.Web"}.

Configuration

Configuration {#configuration conditions="Primary.Web"}
-------------

Each screenshot example within this section provides recommended values
for the TecDoc Reference Data Importer and the parameters displayed.

This topic describes how to configure a File Loading Widget so that
users can drag and drop TecDoc Reference Data files onto a File Loading
Widget on a Web UI Homepage.

If Easy Setup actions for the TecDoc solution have been completed as
described in the **3. Run Easy Setup of Standards** topic of
**Automotive Quick Start Guide**[ here]{.mcFormatColor
style="color: Blue;"}, then the \'TECDOC IMPORTS\' File Loading Widget
will automatically be added to the TecDoc Web UI Homepage as shown in
the examples below. Otherwise, the steps below can be used to complete
configuration.

1.  Go to the Web UI Homepage where a File Loading Widget configured
    with the \'TECDOC IMPORTS\' title is configured with a \'Reference\'
    drop area available for users to drag and drop supplier import
    files.

2.  Using Web UI design mode, select an existing File Loading Widget to
    be used or add a new File Loading Widget to the Homepage Widget Grid
    component. For more information, see the **File Loading Widget**
    topic within the **Web User Interfaces** section of **STEP Online
    Help**[ here]{.mcFormatColor style="color: Blue;"}.

```{=html}
<!-- -->
```
1.  Go to the Inbound Integration Endpoint Parameters field, click the
    **Add** button, and the Inbound Integration Endpoint Parameter
    Properties dialog will display.
2.  Click the dropdown for the Inbound Integration Endpoint parameter,
    and select **TecDoc Reference Inbound Endpoint** (the IIEP created
    for TecDoc Reference imports).

![](../../../../Resources/Images/Importers/Standard_TD/Reference/1.jpg)

If the desired IIEP does not display in the dropdown, then it can be
created using the steps described in the **Configuring an IIEP for
TecDoc Supplier Data Imports** topic[ here]{.mcFormatColor
style="color: Blue;"}.

1.  Optionally, provide a label to be displayed within the drop zone of
    the widget.

In the example below:

-   A File Loading Widget labeled as \'TECDOC IMPORTS\' is displayed
    above its configurations.
-   The File Loading Widget and its configurations are shown with the
    default configurations provided automatically when Easy Setup
    actions for the TecDoc component are completed.
-   An IIEP for TecDoc Reference data imports is added within the same
    File Loading Widget as the IIEP for the TecDoc Supplier data
    imports.

![](../../../../Resources/Images/Importers/Standard_TD/Reference/2.jpg)

6.  Click the **Save** and **Close** buttons to save the changes and
    close the designer.
