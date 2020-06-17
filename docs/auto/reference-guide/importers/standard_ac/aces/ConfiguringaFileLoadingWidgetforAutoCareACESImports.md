---
description: 'Automotive Solution: Describes how to configure a File
  Loading Widget for AutoCare ACES Imports so that Web UI users can
  import ACES files into STEP using a File Loading Widget. '
title: '\[%=Heading.AnyLevel%\]'
---

Configuring a File Loading Widget for AutoCare ACES Imports
===========================================================

When configured, Web UI users can import ACES files into STEP using a
File Loading Widget. Users can also monitor the progress of imports
using a Status Selector Homepage Widget and a Node Details component.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

Before starting to configure the Web UI portion of this solution, an
IIEP for an AutoCare ACES Importer must be configured within workbench.
For more information, see the **Configuring an IIEP for ACES Imports**
topic[ here]{.mcFormatColor style="color: Blue;"}.

Additionally, it is helpful to know how to add a widget to a Web UI
Homepage. Details on how to do this can be found in the **Adding Widgets
to a Homepage** topic in the **Getting Started** documentation[
here]{.mcFormatColor style="color: Blue;" conditions="Primary.Web"}.

Configuration

Configuration {#configuration conditions="Primary.Web"}
-------------

Each screenshot example within this section provides recommended values
for the parameters and AutoCare ACES Importer.

This topic describes how to configure a File Loading Widget so that
users can drag and drop AutoCare ACES files onto a File Loading Widget
on a Web UI Homepage.

If Easy Setup actions for the AutoCare solution have been completed as
described in the **3. Run Easy Setup of Standards** topic of
**Automotive Quick Start Guide**[ here]{.mcFormatColor
style="color: Blue;"}, then the \'SUPPLIER DATA IMPORTS\' File Loading
Widget will automatically be added to the AutoCare Web UI Homepage as
shown in the examples below. Otherwise, the steps below can be used to
complete configuration.

1.  In the designer, select an existing File Loading Widget to be used,
    or add a new File Loading Widget to the Homepage Widget Grid
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
    and select **AutoCare ACES Application Inbound Endpoint** (the IIEP
    created for AutoCare ACES Application imports).

![](../../../../Resources/Images/Importers/Standard_AC/9.png)

If the desired IIEP does not display in the dropdown, then it can be
created using the steps described in the **Configuring an IIEP for ACES
Imports** topic[ here]{.mcFormatColor style="color: Blue;"}.

1.  Optionally, provide a label to be displayed within the drop zone of
    the widget.

In the example below:

-   A File Loading Widget labeled as \'SUPPLIER DATA IMPORTS\' is
    displayed above its configurations.
-   The File Loading Widget and its configurations are shown with the
    default configurations provided automatically when Easy Setup
    actions for the AutoCare component are completed.
-   An IIEP for AutoCare PIES imports is added within the same File
    Loading Widget as the IIEP for the AutoCare ACES imports.

![](../../../../Resources/Images/Importers/Standard_AC/10.png){.Inch6}

5.  Click the **Save** and **Close** buttons to save the changes and
    close the designer.
