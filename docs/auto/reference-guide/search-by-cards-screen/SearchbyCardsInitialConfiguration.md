---
description: 'Automotive Solution: Search by Card Screen allows users to
  find specific data using multiple search criteria that allows users to
  find the most relevant information to meet their needs.'
title: '\[%=Heading.AnyLevel%\]'
---

Search by Card Initial Configuration
====================================

Search by Card allows users to find specific data by using the sync
between search cards functionality to narrow down the search result and
only see the relevant result.

Search by Card properties can be edited at any time. However, it is best
to configure the properties early on. Removing search criteria later may
impact searches you have already saved. If removed, the saved search
still remains accessible, but the Search button will not be enabled.

The Search by Card link can be added to the Web UI homepage for
convenient user access. In addition, the search criteria panel itself is
configurable so Web UI designers can present users with criteria that
are relevant to their job. It is better to define the search criteria in
a manner that reduces the risk of unintended and restricted searches.

Configuration Prerequisites
---------------------------

It is expected that anyone configuring the Search by Card Screen
component is familiar with the Web UI Designer as basic concepts for
working with the designer are not covered in this section. In addition,
the user must have appropriate privileges to access the designer.
Additional information can be found in the [Designer Access]{.bold}
section of the [Web User Interfaces / Web UI Getting Started]{.bold}
documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.

Configuration Process
---------------------

In the designer, create a new screen by selecting **New**. Select the
**Search by Card Screen** and create a name for the screen in the
\'Screen ID\' field. In the example below, the Screen ID is \'Search by
Card Screen.\' Click **Add**.

The Screen ID you use should be something descriptive (e.g., Search by
Card or Card Search) since this will be the name shown on any design
component list in the Web UI. Screen IDs cannot be reused and must be
unique.

![](../../Resources/Images/Search%20by%20Card%20Screen/1.png)

Once this screen is created, the Search by Card Screen Properties
designer screen displays, which contains the following parameters for
configuration:

![](../../Resources/Images/Search%20by%20Card%20Screen/2.png)

**Title:** To make changes to the default title in the screen, add the
custom text to the Title field. If nothing is added, the Title default
will display as \'Search screen.\'

**Result Object Types:** Allows search results to display only results
of the listed object type. This parameter cannot be left blank. Click
the Add button below the parameter field to browse or search for the
necessary object types.

**Root Nodes:** Defines the root node under which the search needs to be
performed when searching / filtering for specific data. Only results
from those folders that pertain to the root notes that are defined
within this parameter will be displayed. In addition, once the root
node(s) is defined, the search input field displays only suggestions of
objects that belong in the root node that is defined within this
parameter. Click the **Add** button below the parameter field to browse
or search for the necessary root node object(s).

**Search Cards:** This parameter allows adding multiple search boxes
that are displayed as cards within the Search by Card Screen. Of the
available options, Name Search Box and Hierarchy Search Box components
can be added only once and Attribute Search Box can be added multiple
times. The order that the search boxes are listed determines the order
that they will be displayed within the Search by Card Screen. All of the
search boxes require additional configuration. Clicking the Add button
next to the Search Cards parameter displays an Add Component dialog with
the option to add one of the following search boxes: Attribute Search
Box, Hierarchy Search Box, and Name Search Box. Steps for configuring
each search field can be found in their respective sections mentioned
below:

-   Configuring Name Search Box ([here]{.mcFormatColor
    style="color: Blue;"})
-   Configuring Hierarchy Search Box ([here]{.mcFormatColor
    style="color: Blue;"})
-   Configuring Attribute Search Box ([here]{.mcFormatColor
    style="color: Blue;"})

Because Name Search Box and Hierarchy Search Box components can only be
configured once for each Search by Card Screen, adding the search box of
the same type again will cause the Error dialog as shown below to
display, and the Search Cards parameter will remain unchanged.

![](../../Resources/Images/Search%20by%20Card%20Screen/3.png)

**Attribute Filters:** Allows users to define attributes and their
values. The objects that hold these attributes with the defined values
will be excluded from the search result.

**Business Condition:** Optional parameter allowing users to select a
business condition to be run as part of the search process.

**Node List:** The Search by Card Screen Properties is pre-configured
with a Node List in Table Display Mode. Select the \'Node List\' option
in the dropdown and click on the \'go to component\' to add more table
header components in the Node List component. For more information, see
the **Node List Component** topic within the **Web User Interfaces**
section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

Adding Search by Card to the Homepage
-------------------------------------

To add a link to Search by Card on the homepage:

1.  Log in to the Web UI. User must have privileges to edit Web UI
    configurations.
2.  Enter design mode.
3.  The link must now be configured to display in the **Links Widget**.

Select HOMEPAGE from the screen dropdown in the designer and select the
Links Widget in the applicable Widget Grid (found under Home Page
Properties \> Child Components \> Content).

If the Links Widget has never been configured to display on the
Homepage, it will need to be added to a Widget Grid. Details on how to
do this can be found in the **Adding Widgets to a Homepage** topic in
the **Getting Started** documentation of the STEP Online Help[
here]{.mcFormatColor style="color: Blue;" conditions="Primary.Web"}.

1.  Within Links Widget Properties, go down to the Child Components
    section and click the **Add** button.

![](../../../../Resources/Images/STEPPortals/Advancedsearch1.png){.NoColumns}

1.  Choose the Navigation component and click **Add**.
2.  On the Navigation properties screen, click the dropdown available
    towards the right of the Screen field.
3.  Select the desired Search by Card Screen.

![](../../Resources/Images/Search%20by%20Card%20Screen/4.png)

1.  Fill in the Label field with the name that will show on the links
    widget, then click **Add**.

![](../../Resources/Images/Search%20by%20Card%20Screen/5.png)

1.  You can move the Links Widget Child Components up and down based on
    your preference for how they show on the homepage.
2.  Click **Save** in the Properties Configuration dialog box.
3.  The Advanced Search link will now show under Quick Links and is
    identified by the name you gave the link in Step 8.

![](../../Resources/Images/Search%20by%20Card%20Screen/6.png)

Additional information regarding STEP Web UI Designer (entering design
mode, selecting screens to edit, and more) can be found in the [Web User
Interfaces]{.bold} / [Getting Started]{.bold} documentation of the STEP
Online Help[ here]{.mcFormatColor style="color: Blue;"}.

Search by Card Screen is now set up and ready for use.
