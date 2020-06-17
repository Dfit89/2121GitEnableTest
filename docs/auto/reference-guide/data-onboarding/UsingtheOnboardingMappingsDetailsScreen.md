---
description: 'Automotive Solution: Describes the key features included
  in Onboarding Mappings Details Screen.'
title: '\[%=Heading.Level1%\]'
---

Using the Onboarding Mappings Details Screen
============================================

The Onboarding Mappings Details screen allows users to view and edit
Mapper Configurations in Web UI. Key features include:

-   Can view existing mapping plugin and its configuration
-   Can create new mapping plugins
-   Can define Onboarding / Outboarding of objects or attributes or LOVs
-   Can define global configurations for the selected Mapper
    Configuration setup entity

Mapper Configuration setup entity can be configured to meet different
Onboarding and Offboarding requirements in Onboarding Mappings Details
screen.

Creating Mapping Plugins
------------------------

Before adding any plugin for the Mapper Configuration in Onboarding
Mappings Details screen, it is essential that the plugins that need to
be listed in the Onboarding Mappings Details screen are configured
within the Mappings parameter of Onboarding Mappings Details Screen
Properties. For more information, see topic **Onboarding Mappings
Details Screen**[ here]{.mcFormatColor style="color: Blue;"}.

1.  With the required Mapper Configuration selected, click on **New
    mapping** within the Mappings tab of the Onboarding Mappings Details
    screen.

![](../../Resources/Images/Data%20Onboarding/23.png)

1.  Select the desired type of mapping plugin, and a screen is displayed
    prompting the user to further configure the plugin. For example, in
    the screenshot below, a screen is displayed when the Attribute
    Mapping plugin is selected. For more information on configuring the
    individual mapping plugin, see section XXXXX

![](../../Resources/Images/Data%20Onboarding/24.png)

3.  When done configuring the plugin, click **Save** button available at
    the bottom of the screen. The newly added mapping plugin is listed
    within the Mappings tab of the Onboarding Mappings Details screen
    (as shown below). [(Up to xxx plugins can be created per Onboarding
    Mappings Details Screen.)]{.italic
    conditions="Primary.Under Construction"}

The **Delete**, **Duplicate** and **Reset** buttons present at the below
toolbar will delete / duplicate / reset the Mapper Configuration, NOT
the individual mapping plugin rows within the configuration. If the user
does not want to be able to delete the Mapper Configuration in Web UI,
then do not configure the **Delete** Action.

![](../../Resources/Images/Data%20Onboarding/25.png)

The action button available in the bottom of the Onboarding Mappings
Details screen is applicable for the Mapper configuration setup entity
configured by the admin within the Buttons parameter of Onboarding
Mappings Details Screen Properties as required by the user. The
**Duplicate**, **Delete**, **Reset** buttons will NOT duplicate / delete
/ reset the Plugin, instead it duplicates / deletes / resets the mapper
configuration setup entity itself. So caution must be taken while
setting the action button access to the user as it would accidentally
duplicate / delete / reset the whole mapper configuration setup entity
itself.

Managing Mapping Plugins
------------------------

All of the created Mapping plugins are listed in a table format within
the Mappings tab of the Onboarding Mappings Details screen for the
selected Mapper Configuration. The user can create, test, and delete the
mapping plugins within the Mappings tab of the Onboarding Mappings
Details screen.

### Deleting an Existing Mapping Plugin {#deleting-an-existing-mapping-plugin style="margin-top: 6mm;"}

1.  Select the Mapping plugins by clicking on the checkbox available at
    the left side of the listed Mapping plugins. A **Delete mapping**
    button will be displayed at the top bar (as shown below).

![](../../Resources/Images/Data%20Onboarding/26.png)

1.  Click on the **Delete mapping** button, and the mapping plugin will
    be deleted from the table.

### Testing a Mapping Plugin {#testing-a-mapping-plugin style="margin-top: 6mm;" conditions="Primary.Under Construction"}

Mapping plugins are tested

### Disabling Mapping Plugin {#disabling-mapping-plugin style="margin-top: 6mm;" conditions="Primary.Under Construction"}
