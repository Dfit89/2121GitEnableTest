---
description: 'Automotive Solution: Describes how to configure the Data
  Model in the workbench as a part of configuring Data Onboarding
  Automotive solution.'
title: '\[%=Heading.Level1%\]'
---

Data Onboarding Solution Initial Setup
======================================

PRODOC note: No Tickets created

PRODOC note: Refer to BEJA demo video and NIFE word document in mail.

The Mapper Configuration is the STEP setup entity object, which holds
the definition of what the mapper should do. After the Easy Setup action
is run, a one-time initial setup is required before any Mapper
Configurations can be created. A setup group must be created to hold the
Mapper Configurations. This document describes the process of initial
setup, which constitutes setting up the data model in workbench.

By the end of this configuration in the workbench, a setup group called
\'Mappings\' is created where users can add new Mapper Configurations.
Further configuration of the Mapper Configurations can be only done in
the Web UI. For information on configuring Mapper configurations in the
Web UI, see the **Configuring Web UI for Data Onboarding Solution**
topic[ here]{.mcFormatColor style="color: Blue;"}.

Running the Easy Setup action creates the **Mapper Configuration**
object type under Basic Object Types hierarchy within System Setup tab
as displayed in the screenshot below.

![](../../Resources/Images/Data%20Onboarding/2.png)

Below are the steps for an initial setup in the workbench.

1.  Navigate to **System Setup** \> **Object Types & Structures**,
    select then right-click the **Setup Group type root** node and
    select **New Object Type**.

2.  In the dialog that appears, enter an ID in the ID parameter (e.g.,
    MapperConfigurations), enter a Name in the Name parameter (e.g.,
    Mapper Configurations), then click the **Create** button. This
    creates a setup group object type that will be used for the root
    node of the Mapper Configurations object to store all mapper
    configurations below.

    The sample below illustrates a hierarchy of setup group object
    types. A Setup Group named \'Mapper Configurations\' has been
    created.

    ![](../../Resources/Images/Data%20Onboarding/1.png)

    Once the setup group is made, the \'Mapper Configurations\' basic
    object type must be linked to this newly created node as a child.
    Later, when new Mapper Configurations are created and added to the
    system, they will use this object type.

3.  Navigate to **Object Types & Structures** \> **Basic Object
    Types** \> **Mapper Configuration**, and click the **References**
    tab.

    Under the **Parents** flipper, click **Add Parent**, and in the node
    selector dialog, specify the **Mapper Configurations** node that was
    created in the above step.

![](../../Resources/Images/Data%20Onboarding/3.png)

The next step is to create a new setup group root, where all Mapper
Configurations will be stored below.

Creating a New Setup Group Root

1.  To create the setup group root, navigate to **Maintain** (drop-down
    menu) \> **Insert** \> **Setup Group Root\...**.

2.  Select the \'Mapper Configurations\' object type.

3.  Specify the **ID** and **Name** for the setup group root object. In
    this setup, ID and Name value of \'Mappings\' is entered.

```{=html}
<!-- -->
```
1.  Click [Create]{.bold}.

![](../../Resources/Images/Data%20Onboarding/4.png)

The setup group called \'Mappings\' of the object type \'Mapper
Configurations\' is created. From this newly created node, users can
right-click and add new Mapper Configurations.

Starting with Product MDM for Automotive 9.1-MP1, creating a new Mapper
Configuration can be done through the Web UI by clicking on \'Create new
global mapping\' link in the left panel. For more information, see
**Configuring Mapper Configuration Setup Entity** topic[
here]{.mcFormatColor style="color: Blue;"}

The Mapper Configurations under the setup group \'Mappings\' are stored
in STEP as a setup entity that can be exported and imported as STEP
\<Setup Entity\> objects. It cannot be imported through Excel.
