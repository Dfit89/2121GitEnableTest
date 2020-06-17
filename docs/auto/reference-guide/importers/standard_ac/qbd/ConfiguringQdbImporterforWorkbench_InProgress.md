---
description: This section provides details of configuring a Qdb Importer
  in STEP workbench.
title: Configuring a Qdb Importer in Workbench
---

Configuring Qdb Importer In Workbench
=====================================

This section provides details for configuring a Qdb importer in STEP
workbench.

### Prerequisites

It is expected that anyone configuring a Qdb IIEP is familiar with the
configuration and other processes of normal Inbound Integration
Endpoints. For more information on Inbound Integration Endpoints, see
the **Inbound Integration Endpoint** section of the **Data Exchange**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

### Configuring a Qdb IIEP

1.  In System Setup, right-click the Inbound Integrations Endpoints
    setup group, and click **Create Inbound Integration Endpoint**.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/CreatInboundInteg.png)

1.  The Inbound Integration Endpoint wizard will display. Enter in all
    needed information.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/Inbound%20INtegrationEndpoint.png)

1.  Click the **Next** button to display **IIEP - Choose Receiver**, and
    fill in any necessary fields.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/ChooseReceiver.png)

1.  Click the **Next** button to display the **IIEP - Configure
    Endpoint**. In the Processing Engine field, select from the dropdown
    \'**Import Flow Processor**\' as the processing engine.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/ConfigurineEndpoint.png)

1.  Click the **Next** button to display the **IIEP - Configure
    PreProcessor**, and select any if needed.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/ConfigurePreProcessor.png)

1.  Click the **Next** button to display the **IIEP - Configure
    Processing Engine**. Fill in any needed fields.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/ConfigureProcesEngine.png)

The \'Qdb Data\' option must be selected in File type dropdown. The
\'AutoCare Qdb Import\' workflow must be selected in Workflow field.

1.  Click the **Next** button to display the **IIEP - Schedule
    Endpoint** and configure appropriately.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/ScheduleEndpoint.png)

1.  Click the **Next** button to display the **IIEP - Configure Error
    Reporter** and enter any needed information.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/ConfigureErrorReporter.png)

1.  Click **Finish**. The endpoint is created and appears in the setup
    group.

The endpoint must be enabled before it can start processing data.

![](../../../../Resources/Images/Importers/Standard_AC/Qdb/AutoCareQDBEndpoint.png)
