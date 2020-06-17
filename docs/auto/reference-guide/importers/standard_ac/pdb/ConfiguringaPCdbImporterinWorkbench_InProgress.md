---
description: This section provides details of configuring a PCdb
  Importer in STEP Workbench.
title: Configuring a PCdb Importer in Workbench
---

Configuring a PCdb Importer in Workbench
========================================

This section provides details of configuring a PCdb Importer in STEP
Workbench.

### Prerequisites

It is expected that anyone configuring a PCdb IIEP is familiar with the
configuration and process of normal Inbound Integration Endpoints. For
more information on Inbound Integration Endpoint, see the Inbound
Integration Endpoint section of the Data Exchange documentation[
here]{.mcFormatColor style="color: Blue;"}.

### Configuring a PCdb IIEP

1.  In System Setup, right-click the Inbound Integrations Endpoints
    setup group, and click **Create Inbound Integration Endpoint**.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/CreateInboundIntegration.png)

1.  The Inbound Integration Endpoint wizard displays. Fill in any needed
    information.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/IdentifyEndpoint.png)

1.  Click the **Next** button to display **IIEP - Choose Receiver**, and
    fill in all needed fields.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/ChooseReceiver.png)

1.  Click the **Next** button to display **IIEP - Configure Endpoint**.
    Select the processing engine as 'Import Flow Processor' from the
    dropdown, and enter in any Processing, Context, or Queue Settings
    needed.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/ConfigureEndpoint.png)

1.  Click the **Next** button to display **IIEP - Configure
    PreProcessor**, and select the appropriate preprocessor.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/COnfigPreProcessor.png)

1.  In the **IIEP - Configure Processing Engine** wizard in the **File
    type** dropdown, select the 'PCdb Data' option. Additionally in the
    Workflow field, select 'AutoCare PCdb Import' by clicking on the
    ellipses button (...).

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/ConfigureProcessingEngine.png)

1.  Click the **Next** button to display **IIEP - Schedule Endpoint**.
    Select the appropriate scheduling needed for the IIEP.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/ScheduleEndpoint.png)

1.  Click the **Next** button to display **IIEP - Configure Error
    Reporter**, and configure appropriately.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/Configure%20Error%20Reporter.png)

1.  Click **Finish**. The endpoint is created and appears in the setup
    group. The endpoint must be enabled before it can start processing
    data.

![](../../../../Resources/Images/Importers/Standard_AC/PCdb/StandaredINtegrationEndpoint.png)
