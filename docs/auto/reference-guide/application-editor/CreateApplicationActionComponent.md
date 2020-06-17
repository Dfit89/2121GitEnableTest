---
description: 'Automotive Solution: Create Application Action component
  allows the user to create application records. This component is
  available as a toolbar action for Node Lists.'
title: '\[%=Heading.Level1%\]'
---

Create Application Action Component
===================================

The Create Application Action component enables users to create
application records for the selected vehicle / assembly or part. Meaning
that this component applicates the selected part to the vehicle /
assembly or vice versa. This component is available as a toolbar action
for Node Lists, and one common usage is within the Application Editor
Screen.

Configuring the Create Application Action Component
---------------------------------------------------

When Easy Setup actions are used to create a standard data model, Create
Application Action component is added in the Application Editor Screen
by default. It is the ready-to-use component that allows users to create
application records. Users can further configure this component to their
requirements. Follow the steps described below to add and configure the
Create Application Action component as a toolbar action on a Node List,
or skip to step 3 to directly configure the available Create Application
Action component.

1.  First, add the component. Under Child Components on the Node List
    Properties screen in the designer, click the **Add** button under
    the field for Actions parameter.

![](../../Resources/Images/Application%20Editor/13.png)

1.  Then select **Create Application Action** from the component list.
    Click **Add**.

![](../../Resources/Images/Application%20Editor/14.png)

1.  Once added to the list of actions for the Node List, double-click
    the **Create Application Action** component to configure.

![](../../Resources/Images/Application%20Editor/15.png)

1.  In the Create Application Action Properties dialog, define the
    following optional parameters:

![](../../Resources/Images/Application%20Editor/16.png)

-   **Create Application Business Action**: This parameter lets users
    define a business rule that will be executed on all new
    applications. One example is to configure a business action that
    sets the STEP object Name of the newly created application records.
    When using a business action to set the application record name, it
    is required that the \'Do not set name\' parameter is selected so
    that the name is only set through the configured business action.
-   **Icon Style Class**: This parameter allows a custom icon to be
    displayed on the action button.
-   **Label**: To change the default button label, add the custom text
    to the Label field. If nothing is added, the Label default will
    display as \'Create.\'

This is how the button will display at the top of the Application Editor
Screen:

![](../../Resources/Images/Application%20Editor/5.png)

-   **Node Picker Configuration**: This parameter allows users to define
    root nodes, search tab pages, and a custom title. For details, see
    the **Node Picker Dialog** documentation within the **Web User
    Interfaces** section of **STEP Online Help**[ here]{.mcFormatColor
    style="color: Blue;"}.

The settings made in this parameter are overwritten when the Faceted
Search Configuration parameter is populated with the Faceted Search Node
Picker Dialog component.

-   **Title**: To change the default title of the dialog that appears
    when a user clicks on the Create Application Action button, add the
    custom text to the Title field. If nothing is added, the default
    title will display as \'Create Application.\'

This is how the title will display at the top of the dialog when a user
clicks on the Create Application Action button:

![](../../Resources/Images/Application%20Editor/17.png)

-   **Do not set name**: This parameter provide control over the naming
    convention of the application records that are created via the
    Create Application Action button. If unselected, the STEP name of
    the application record will be created using the default combination
    of Part Number, Part Type, Year, Make, and Model from the system.
    Select this parameter if the STEP Name of the newly created
    application record should be left empty, or if it will be set by the
    business action that is defined in the Create Application Business
    Action parameter.
-   **Faceted Search Configuration**: This parameter, when configured
    with Faceted Search Node Picker Dialog component, acts as a
    replacement for the regular Node Picker component where the user can
    search for the required objects by narrowing down the search result
    using facets. The faceted search fields allow users to search for
    vehicle or part objects based on the object Name, ID, or attribute
    values. Users can configure the faceted search to use all available
    attributes, IDs, or Names. For details, see the **Faceted Search
    Dialog** documentation within this guide[ here]{.mcFormatColor
    style="color: Blue;"}.

Below is an example of how the Faceted search dialog will display when
the user clicks on the Create Application Action button:

![](../../Resources/Images/Application%20Editor/18.png)

Creating applications using Create Application Action
-----------------------------------------------------

The central feature of the Application Editor Screen is the ability to
create an application record on the selected vehicle / assembly or part
(depending upon the type of Application Editor Screen). Follow the steps
described below to create an application record for the selected part in
a Application Editor Screen. The example in this document considers
applicating the Part to the vehicle / assembly.

1.  Select the part that application records should be created for.

Application Editor Screen must be configured to display either as the
Main Screen or as a Sub Screen Tab Page when the part is selected.

In this example, the part \'JK21499\' is selected and the Application
Editor Screen displays the existing application records belonging to
that part.

![](../../Resources/Images/Application%20Editor/19.png)

1.  Click the **Create** button that is available in the toolbar of the
    screen and the Create Application dialog will be displayed as shown
    below:

![](../../Resources/Images/Application%20Editor/17.png)

In the above example, a regular Node Picker Dialog is displayed.
However, the user can configure it to display the Faceted Search Dialog
instead of the regular node picker. For details on how to use the
Faceted Search Dialog, see the **Faceted Search Dialog** documentation
within this guide[ here]{.mcFormatColor style="color: Blue;"}.

1.  Click on the Node Picker icon and select the vehicle / assembly that
    should be applicated to the selected part either by navigating
    through the standard Browse tab or by searching through the Search
    tab. In the example below, vehicle \'1962 Abarth 1000\' is selected.
    Click OK to close the Node Picker dialog.

![](../../Resources/Images/Application%20Editor/20.png)

1.  Click **OK** to close the Create Application dialog.

![](../../Resources/Images/Application%20Editor/21.png)

The result is that the part \'JK21499\' is applicated to vehicle \'1962
Abarth 1000\' and the application record \'JK21499 - Check Engine Light
Sensor - 1962 Abarth 1000\' is created and listed in the Application
Editor Screen (as shown below).

![](../../Resources/Images/Application%20Editor/22.png)
