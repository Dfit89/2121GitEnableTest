---
title: '\[%=Heading.AnyLevel%\]'
---

Configuring a Brand Importer in Workbench
=========================================

This section provides details of configuring a Brand Importer in STEP
workbench.

### Prerequisites

It is expected that anyone configuring a PAdb IIEP is familiar with the
configuration and other process of normal Inbound Integration Endpoints.
For more information on Inbound Integration Endpoint, see the **Inbound
Integration Endpoint** topic in the **Data Exchange** documentation[
here]{.mcFormatColor style="color: Blue;"}.

Configuring a Brand IIEP
------------------------

1.  In System Setup, right-click the Inbound Integrations Endpoints
    setup group, and click **Create Inbound Integration Endpoint**.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/IIEPCreate.png)

1.  The Inbound Integration Endpoint wizard displays. Fill in any needed
    information.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/Identify%20Endpoint.png)

1.  Click the **Next** button to display the **IIEP - Choose Receiver**,
    and fill in all needed fields.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/ChooseReceiver.png)

1.  Click the **Next** button to display the **IIEP - Configure
    Endpoint**. Select the processing engine as 'Import Flow Processor'
    from the dropdown menu.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/ConfigureEndpoint.png)

1.  Click the **Next** button to display **IIEP - Configure
    PreProcessor**, and select the appropriate preprocessor.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/ConfigPRocess.png)

1.  In the **IIEP - Configure Processing Engine** wizard select the
    'Brand Data' option from the 'File type' dropdown, and select the
    workflow 'AutoCare Brand Import' by clicking on the ellipses button
    (...) in the workflow field.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/ConfigProcesEng.png)

1.  Click the **Next** button to display **IIEP - Schedule Endpoint**.
    Select the appropriate scheduling needed for the IIEP.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/ScheduleEndpoint.png)

1.  Click the **Next** button to display **IIEP - Configure Error
    Reporter**, and configure appropriately.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/Error%20Reporter.png)

1.  Click **Finish**. The endpoint is created and appears in the setup
    group. Also note that the endpoint must be enabled before it can
    start processing data.

![](../../../../Resources/Images/Importers/Standard_AC/Brand/CreatedBrandIIEP.png)
