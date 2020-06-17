---
description: 'Automotive Solution: Describes how an IIEP for TecDoc
  Reference Data imports is automatically created when the TecDoc Easy
  Setup actions are completed. '
title: '\[%=Heading.AnyLevel%\]'
---

Configuring an IIEP for TecDoc Reference Data Imports
=====================================================

If the Easy Setup actions for the TecDoc Component model have been
completed, then the configurations explained within this topic have been
set up automatically. The purpose of this topic is to detail those
settings as to assist admins in adjusting their solution where
necessary.

An Inbound Integration Endpoint (IIEP) can be configured in workbench to
help automate the process of importing TecDoc Reference data into STEP.
Once an IIEP is configured for TecDoc Reference data imports, reference
data files can be imported after they are uploaded either to a
configured hotfolder on an application server, or to a File Loading
Widget on a Web UI Homepage. For more information, see the **TecDoc
Reference Data Importer** topic[ here]{.mcFormatColor
style="color: Blue;"}.

This section describes how to configure an IIEP that can allow for the
automated processing of TecDoc Reference data files. Each screenshot
example within this section provides recommended values for the TecDoc
Reference Data Importer and the parameters displayed.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

It is expected that anyone configuring an IIEP for use with a TecDoc
Reference Data Import is familiar with the configuration and other
processing of standard inbound integration endpoints. For more
information, see the **Inbound Integration Endpoints** topic within the
**Data Exchange** section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration Steps

Configuration Steps {#configuration-steps conditions="Primary.Web"}
-------------------

1.  Go to System Setup, select and then right-click the **Inbound
    Integrations Endpoints** setup group, and click **Create Inbound
    Integration Endpoint**.
2.  Once the Inbound Integration Endpoint Wizard displays, populate each
    parameter with values that best identify the IIEP. By default, all
    parameters display blank, and the following fields are mandatory:
    Endpoint ID, Endpoint Name, and User.

In the example below, a \'TecDoc Reference Data Import\' user was
created prior to configuring this IIEP. This is recommended to more
easily track when this IIEP is responsible for changes to data.

![](../../../../Resources/Images/Importers/Standard_TD/Reference/11.jpg)

For more information about the parameters, see the **IIEP - Identify
Endpoint** topic within the **Inbound Integration Endpoint** section of
**STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

1.  Click the **Next** button, and the Choose Receiver parameters will
    display. By default, the parameters are populated as recommended and
    shown below, except the Hotfolder parameter. This mandatory
    parameter must be populated with a hotfolder name before the Next
    button will enable. The value within this parameter will be used to
    create the new hotfolder on the application server, once the Finish
    button is clicked.

![](../../../../Resources/Images/Importers/Standard_TD/Reference/12.jpg)

For more information about the parameters, see the **IIEP - Choose
Receiver** topic within the **Inbound Integration Endpoint** section of
**STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

1.  Click the **Next** button, and the Configure Endpoint parameters
    will display. By default, the parameters are populated as
    recommended and shown below, except the following:

-   Processing Engine
-   Maximum number of old processes
-   Maximum age of old processes

![](../../../../Resources/Images/Importers/Standard_TD/Reference/13.jpg)

The Import Flow Processor is only responsible for picking up files from
the configured hotfolder, creating an Entity controller object, and
updating the Entity with the Import Flow State BGP\'s and Status. The
Import Flow Processor works with the Background Process Service for each
workflow state to handle the import of a file. The IIEP / Import Flow
Processor is NOT responsible for actually importing the content of the
file, the BGP in each state does that processing. If a new Processing
Engine is created through the Extension API, then it **cannot** be used
with the automotive import framework.

-   Click the dropdown option for the \'Processing Engine\' parameter
    and select the **Import Flow Processor** option.

```{=html}
<!-- -->
```
-   Optionally, update the values for the \'Maximum number of old
    processes\' and \'Maximum age of old processes\' parameters to those
    shown above.

For more information about the parameters, see the **IIEP - Configure
Endpoint** topic within the **Inbound Integration Endpoint** section of
**STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

5.  Click the **Next** button, and the Configure PreProcessor parameter
    will display. By default, the parameter is populated as recommended
    and shown below.

![](../../../../Resources/Images/Importers/Standard_TD/Supplier/c4.jpg)

For more information about the parameter, see the **IIEP - Configure
PreProcessor** topic within the **Inbound Integration Endpoint** section
of **STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

1.  Click the **Next** button, and the Configure Processing Engine :
    Configuration parameters for the Import Flow Processor will display.
    By default, only the File Attachment ID parameter is populated as
    shown below.

![](../../../../Resources/Images/Importers/Standard_TD/Reference/14.jpg)

The prior Configure Endpoint step determines the options available for
the Configure Processing Engine step.

-   Click the \'File type\' parameter, dropdown and select the **TecDoc
    Reference Data** option.
-   Within the \'ID Prefix\' parameter, enter a prefix value to easily
    identify import entities created by this IIEP.
-   for the \'Import root entity\' parameter, and select the \'Import
    Flow Root\' node (or a desired root entity) This is the location
    where the import entities created by this IIEP will be stored.
-   for the \'Workflow\' parameter, and select the **TecDoc Reference
    Import** workflow or a desired workflow.

It is possible to use a workflow that is not created by Easy Setup
actions to handle an import file in a way that better fits an
organizations needs. However, along with creating the workflow and
selecting it within the Workflow parameter shown above, all the states
for that workflow must be created along the processing steps of the file
(i.e., Validation, Conversion, Import). Use of the Extension API is
required to write the processing steps.

7.  Click the **Next** button, and the Schedule Endpoint parameters will
    display. By default, \'Never\' is selected. Optionally, update the
    values to those shown below.

![](../../../../Resources/Images/Importers/Standard_TD/Supplier/c6.jpg)

For more information about the parameters, see the **IIEP - Schedule
Endpoint** topic within the **Inbound Integration Endpoint** section of
**STEP Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

8.  Click the **Next** button, and the Configure Error Reporter
    parameter will display. By default, the parameter is populated as
    recommended and shown below.

![](../../../../Resources/Images/Importers/Standard_TD/Supplier/c7.jpg)

For more information about the parameter, see the **IIEP - Configure
Error Reporter** topic within the **Inbound Integration Endpoint**
section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

1.  Click the **Finish** button, the Inbound Integration Endpoint Wizard
    will close, and the newly created endpoint will display within
    workbench.

An endpoint must be enabled before it can start processing data. For
more information, see the **Running an Inbound Integration Endpoint**
topic within the **Inbound Integration Endpoint** section of **STEP
Online Help**[ here]{.mcFormatColor style="color: Blue;"}.

If users need to access the IIEP via a Web UI, then the IIEP must be
configured within a File Loading Widget. For more information, see the
**Configuring a File Loading Widget for Reference Data Imports** topic[
here]{.mcFormatColor style="color: Blue;"}.
