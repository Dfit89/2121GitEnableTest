---
description: 'Automotive Solution: Onboarding Comparison Screen allows
  users to configure a Mapper Configuration setup entity and compares
  the selected Source object with the Target object in the context of
  the configured Mapper Configuration setup entity.'
title: '\[%=Heading.AnyLevel%\]'
---

Onboarding Comparison Screen
============================

Often in the process of Data Onboarding, a large quantity of data is
being imported and onboarded in the system. Sometimes it is required by
the user to preview the changes affecting the Target object even before
the data is onboarded. The Onboarding Comparison Screen allows users to
preview the onboarding data, assess each of the changes, and provides
users an option to accept or reject the changes that will affect the
Target object.

Onboarding Comparison Screen allows users to configure a Mapper
Configuration setup entity and compares the selected Source object with
the Target object in the context of the configured Mapper Configuration
setup entity. With the Source object selected, users can view the
changes affecting the Target object. Also, an option is provided to
partially / fully accept or reject the affecting changes. If the user
chooses to accept full / partial changes, the Mapper Configuration setup
entity will be executed on the Source object and only the selected
changes will be effected on the Target object.

Generally, the Onboarding Comparison Screen is used if the user
discretion is required towards the acceptance / rejection of the
onboarding changes. If all of the data needs to be onboarded without the
user discretion then the user can choose to use any of the methods
described in the **Executing Mapper Configuration Setup Entity**
([here]{.mcFormatColor style="color: Blue;"}) topic to directly onboard
the data.

The Onboarding Comparison Screen requires an object selection, and can
be configured to be accessed through many different ways, below are the
common ways of accessing it.

-   Configuring in the Search by Card Screen or any other search screen
    using Forward Screen Action button. For more information, see
    **Using Search by Cards Screen with Data Onboarding Tasks** topic
    within this guide[ here]{.mcFormatColor style="color: Blue;"}.
-   Mapping an Onboarding Comparison Screen to be displayed when the
    Source object is selected in the Web UI. For information on mapping
    the screen for a particular object type, see the **Mappings** topic
    within the **Main Properties Overview** section of **STEP Online
    Help**[ here]{.mcFormatColor style="color: Blue;"}.
-   Added as a tab page within another screen that is configured to
    display when the Source object is selected. To add to an existing
    screen, use the Sub Screen Tab Page configuration, described in the
    **Tab Pages** topic in the **Web User Interfaces** / **Web UI
    Getting Started** documentation of **STEP Online Help**[
    here]{.mcFormatColor style="color: Blue;"}.

Prerequisites
-------------

It is expected that anyone configuring the Onboarding Comparison Screen
is familiar with the Web UI Designer, as basic concepts for working with
the designer are not covered in this section. In addition, the user must
have appropriate privileges to access the designer. Additional
information can be found in the [Designer Access]{.bold} section of the
[Web User Interfaces]{.bold} / [Web UI Getting Started]{.bold}
documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.
