---
description: 'Automotive Solution: Describes how to configure a File
  Loading Widget for AutoCare PAdb Imports so that Web UI users can
  import PAdb files into STEP using a File Loading Widget. '
title: '\[%=Heading.AnyLevel%\]'
---

Configuring a File Loading Widget for AutoCare PAdb Imports
===========================================================

When configured, Web UI users can import PAdb file into STEP using a
File Loading Widget. Users can also monitor the progress of imports
using a Status Selector Homepage Widget and a Node Details component.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

Before starting to configure the Web UI portion of this solution, an
IIEP for an AutoCare PAdb Importer must be configured within workbench.
For more information, see the **Configuring an IIEP for PAdb Imports**
topic[ here]{.mcFormatColor style="color: Blue;"}.

Additionally, it is helpful to know how to add a widget to a Web UI
Homepage. Details on how to do this can be found in the **Adding Widgets
to a Homepage** topic in the **Getting Started** documentation[
here]{.mcFormatColor style="color: Blue;" conditions="Primary.Web"}.

Configuration

Configuration {#configuration conditions="Primary.Web"}
-------------

Each screenshot example within this section provides recommended values
for the parameters and AutoCare PAdb Importer.

This topic describes how to configure a File Loading Widget so that
users can drag and drop AutoCare PAdb files onto a File Loading Widget
on a Web UI Homepage.

If Easy Setup actions for the AutoCare solution have been completed as
described in the **3. Run Easy Setup of Standards** topic of
**Automotive Quick Start Guide**[ here]{.mcFormatColor
style="color: Blue;"}, then the \'REFERENCE DATA IMPORTS\' File Loading
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

![](../../../../Resources/Images/Importers/Standard_AC/46.png)

1.  Click the dropdown for the Inbound Integration Endpoint parameter,
    and select **AutoCare PAdb Inbound Endpoint** (the IIEP created for
    AutoCare PAdb imports).

![](../../../../Resources/Images/Importers/Standard_AC/47.png)

If the desired IIEP does not display in the dropdown, then it can be
created using the steps described in the **Configuring an IIEP for PAdb
Imports** topic[ here]{.mcFormatColor style="color: Blue;"}.

1.  Optionally, provide a label to be displayed within the drop zone of
    the widget.

In the example below:

-   A File Loading Widget labeled as \'REFERENCE DATA IMPORTS\' is
    displayed above its configurations.
-   The File Loading Widget and its configurations are shown with the
    default configurations provided automatically when Easy Setup
    actions for the AutoCare component are completed.
-   An IIEP for Qdb, Brand, PCdb, and VCdb imports are added within the
    same File Loading Widget as the IIEP for the AutoCare PAdb imports.

![](../../../../Resources/Images/Importers/Standard_AC/48.png)

5.  Click the **Save** and **Close** buttons to save the changes and
    close the designer.
