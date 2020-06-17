---
description: This section provides details for configuring a VCdb
  Importer in STEP workbench.
title: Configuring a VCdb Importer in Workbench
---

Configuring a VCdb Importer in Workbench
========================================

This section provides details for configuring a VCdb Importer in STEP
workbench.

### Prerequisites

It is expected that anyone configuring a VCdb IIEP is familiar with the
configuration and other process of normal Inbound Integration Endpoints.
For more information on Inbound Integration Endpoints, see the
**Integration Endpoint** topic of the **Data Exchange** documentation[
here]{.mcFormatColor style="color: Blue;"}.[, see Inbound Integration
Endpoints Setup Requirements ]{.mcFormatColor style="color: Blue;"}

Configuring a VCdb IIEP

1.  In System Setup, right-click the Inbound Integrations Endpoints
    setup group, and click **Create Inbound Integration Endpoint**.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/CreateInboundIntegrationEndpoint.png)

1.  The Inbound Integration Endpoint wizard displays. Enter in any
    needed Identify Endpoint fields.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/IdentifyEndpoint1.png)

For more information about Identify Endpoint, see the **IIEP -- Identify
Endpoint** topic in the **Data Exchange** documentation[
here]{.mcFormatColor style="color: Blue;"}.

1.  Click the **Next** button to display **IIEP - Choose Receiver**.
    Select or fill in any needed information.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/ChooseReceiverHotfolder.png)

For more information on Choose Receiver, see the **IIEP -- Choose
Receiver** topic of the **Data Exchange** documentation[
here]{.mcFormatColor style="color: Blue;"}.

1.  Click the **Next** button to display **IIEP - Configure Endpoint**.
    Select the 'Import Flow Processor' processing engine from the
    dropdown.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/ConfigureEndpointIB.png)

For more information about Configuration Endpoint, see the **IIEP -
Configure Endpoint** topic of the **Data Exchange** documentation[
here]{.mcFormatColor style="color: Blue;"}.

1.  Click the **Next** button to display **IIEP - Configure
    PreProcessor**. Select the appropriate preprocessor if needed.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/ConfigurePreProcessorInbound.png)

For more information about Configure PreProcessor, see the **IIEP -
Configure PreProcessor** topic in the **Data Exchange** documentation[
here]{.mcFormatColor style="color: Blue;"}.

1.  In the **IIEP - Configure Processing Engine** wizard, select the
    'VCdb Data' option from the 'File type' drop down and select the
    workflow 'AutoCare VCdb Import' by clicking on the ellipses button
    (...) in the workflow field.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/ConfigureProcessing%20Engine.png)

For more information about Configure Processing Engine, see the **IIEP -
Configure Processing Engine** topic of the **Data Exchange**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

1.  Click the **Next** button to display **IIEP - Schedule Endpoint**.
    Select the needed schedule.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/ScheduleEndpoint.png)

For more information about Schedule Endpoint, see the **IIEP - Schedule
Endpoint** topic of the **Data Exchange** section of the documentation[
here]{.mcFormatColor style="color: Blue;"}.

1.  Click the **Next** button to display **IIEP - Configure Error
    Reporter**, and configure the desired way to receive error
    reporting.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/ConfigureErrorReporter.png)

For more information about Configure Error Reporter, see the **IIEP -
Configure Error Reporter** topic in the **Data Exchange** documentation[
here]{.mcFormatColor style="color: Blue;"}.

1.  Click **Finish** when done with the wizard setup. The endpoint is
    created and appears in the setup group.

2.  The endpoint must be enabled before it can start processing data.
    For more information, see the **Running Inbound Integration
    Endpoint** topic in the **Data Exchange** documentation[
    here]{.mcFormatColor style="color: Blue;"}.

![](../../../../Resources/Images/Importers/Standard_AC/VCdb/AutoCareVCdb.png)
