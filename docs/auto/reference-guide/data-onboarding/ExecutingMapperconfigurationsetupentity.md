---
description: 'Automotive Solution: Describes methods to trigger the
  mapper configuration setup entity.'
title: Executing Mapper Configuration Setup Entity
---

Executing Mapper Configuration Setup Entity
===========================================

The Mapper Configuration Setup Entity can be executed in the following
ways:

-   By executing through Mapper Action button (this is the recommended
    method in the Web UI as it will be faster)
-   By executing through the Onboarding Comparison Screen [
    here]{.mcFormatColor style="color: Blue;"}
-   By a background process with an automated import
-   By configuring it in a business rule and executing the business rule
    on the source object

Prerequisites
-------------

It is assumed that the admin user has knowledge of STEP administrative
functions and experience working in System Setup, including creating and
editing business rules, workflows, and Web UIs. This section targets
only the specific information needed for a knowledgeable STEP admin user
to execute the Mapper Configuration in different possible ways. For more
introductory material of these concepts, see the **Business Rules**
([here]{.mcFormatColor style="color: Blue;"}), **Workflows**
([here]{.mcFormatColor style="color: Blue;"}) and **Web User
Interfaces** ([here]{.mcFormatColor style="color: Blue;"}) sections of
**STEP Online Help**.

Before any Mapper Configuration is executed, the relationship must be
established through references between the Source object to the Target
object.

Before any Mapper Configuration is e4xecuted, it is necessary that the
configuration aspects of the Data Onboarding solution in both the
workbench and the Web UI are completed. For more information about
creating and configuring the mapper configuration setup entity, see the
**Data Onboarding Automation Solution Initial Setup**
([here]{.mcFormatColor style="color: Blue;"}),and the **Configuring Web
UI for Data Onboarding Automation solution**([here]{.mcFormatColor
style="color: Blue;"}) topics within this section.

Executing Through Mapper Action Button
--------------------------------------

This process involves defining an action button called **Mapper Action**
to hold the Mapper Configuration setup entity, and configuring the
action button in required screens. Clicking on the action button will
initiate the Mapper Configuration setup entity on the selected node.

The **Mapper Action** button can be configured to be available within
the Source object screen, or any other places that allows the action
button to be executed (e.g., run as a bulk update on a Collection, or
initiate the action button with a node selected in the Search by Card
screen). For the ease of understanding, this document depicts an example
of configuring the Mapper Action button in the Node Detail screen that
is configured to view the Source object.

Following are the steps to configure the Mapper Action button.

1.  In the Web UI designer, navigate to the screen that requires the
    Mapper Action button to be configured \> Buttons \> go to
    component \> Button Properties.

 

2.  Click **Add** next to the Actions field that is available within the
    Buttons Properties to access the Add Component dialog.

![](../../Resources/Images/Data%20Onboarding/175.png)

3.  Find **Mapper Action** and click **Add**, and the Mapper Action
    Properties dialog will be displayed.

![](../../Resources/Images/Data%20Onboarding/176.png)

4.  Populate the parameters as detailed below:

-   **Button Type:** Select from ICON\_AND\_TEXT, ICON, and TEXT using
    the Button Type dropdown. If the user choose to select TEXT or
    ICON\_AND\_TEXT and the Label parameter is empty, the default text
    \'Run Mapper\' will display.

```{=html}
<!-- -->
```

```{=html}
<!-- -->
```
-   **Label:** This parameter defines the text that the user wants to
    appear in the button that is displayed on screen.
-   **Mapper Configuration:** Required parameter to specify the Mapper
    Configuration setup entity that needs to be executed. Click the
    ellipses button
    ![](../../../../Resources/Images/Buttons/ellipsis.png){.img_intext}
    to find and select the Mapper Configuration setup entity that is
    available in the system.
-   **Report Changes:** This parameter is checked by default. Having
    this parameter checked ensures that the changes effected by the
    execution of the associated Mapper Configuration setup entity is
    displayed in the message dialog (explained below) and also in the
    Corner Bar Warning Notifications Component. With the parameter
    checked, the \'\'Mapping Complete - Mapping has been completed with
    X Error(s), X Warning(s) and X Message(es)\'\' message with the
    \'Click for details\' link will display in the message dialog (as
    shown below). If this parameter is left unchecked, any errors and
    warnings encountered in the execution of the Mapper Configuration
    setup entity will not be displayed, and the message dialog displays
    as \'Mapping Complete.\'
-   **Run Before Action:** This parameter allows the user to configure a
    business action. The configured business action gets executed before
    the Mapper Configuration setup entity is executed.

5.  Click the **Add** button to close the Mapper Action Properties
    designer screen.

```{=html}
<!-- -->
```
6.  Click the **Save** button in the designer and **Close**.

A status message dialog will be displayed when the user clicks on the
action button that is configured in any screen. This dialog shows the
execution status of the Mapper Configuration and configured business
action execution in the top center of the screen. More details on the
status of the execution can be seen either by clicking the \'Click for
details\' link in the message dialog, or by accessing through the Corner
Bar Warning Notifications icon.

![](../../Resources/Images/Release%20Notes/92RN7.png)

Executing by Onboarding Comparison Screen
-----------------------------------------

This process involves configuring an Onboarding Comparison Screen to
hold the Mapper Configuration and then access this screen for the Source
object through multiple ways. This type of execution provides an option
for the user to preview the changes affecting the Target object even
before the data is onboarded. The Onboarding Comparison Screen allows
users to assess each of the changes, and gives the user an option to
accept or reject the changes that will affect the Target object.
Additionally, this screen also provides users an option to exclude any
Mapping plugin being executed for any required Source object on its
subsequent import.

1.  Create and configure a Onboarding Comparison Screen. For the full
    set of instructions on configuring the Onboarding Comparison Screen,
    see the **Configuring Onboarding Comparison Screen** documentation.
2.  Review and implement the most common ways to use Onboarding
    Comparison Screen as described in **Using Onboarding Comparison
    Screen Interface** topic within this guide.
3.  Execute the Mapper Configuration setup entity through Onboarding
    Comparison Screen as described in **xxxxx** topic.

Executing by a Background Process
---------------------------------

This method of execution is also considered as the automatic onboarding
method. This process involves creating a new state in the Import
workflow to hold a Mapper Configuration setup entity that gets
automatically executed whenever there is a new import. After the file is
imported in the system, the Onboarding background process runs a drill
down search for the following:

-   To identify *all* the **Source objects** in the system that has the
    change flag attribute value set to \'true.\' The change flag
    attribute is configured in the \'Changed attribute\' parameter
    (explained below). The Source object(s) belong to the object type
    configured in the \'Source\' parameter that is available within the
    \'Setup\' tab of the Onboarding Mappings Details screen for the
    selected Mapper Configuration setup entity (an example shown below).

When executing through this method, the background process executes the
Mapper Configuration setup entity on *every source objects residing in
the system* that has the change flag attribute value set to \'true.\'
*Not* just the source objects in the importing file.

![](../../Resources/Images/Data%20Onboarding/220.png)

-   To identify the **Reference type** configured in the \'Reference\'
    parameter which is available within the \'Setup\' tab of the
    Onboarding Mappings Details screen for the selected Mapper
    Configuration setup entity (an example shown below).

![](../../Resources/Images/Data%20Onboarding/221.png)

-   To identify the **Target object** belonging to the object type
    configured in the \'Target\' parameter which is available within the
    \'Setup\' tab of the Onboarding Mappings Details screen for the
    selected Mapper Configuration setup entity (an example shown below).
    If the Target object does not exist to run the Mapper Configuration
    on, then it can be made possible to create a Target object based on
    the condition defined in the \'Target Hierarchy\' Parameter.

![](../../Resources/Images/Data%20Onboarding/222.png)

Once the Onboarding background process identifies the Source object,
Target object, and the reference linking the Source object with the
Target object, then the Mapper Configuration setup entity will be
executed only on the identified results. This way, Onboarding background
process eliminates execution of the Mapper Configuration on all other
objects in the system than those that actually requires to be updated.

To execute the Mapper Configuration by a background process, the
following configuration is needed:

These levels of configuration are explained in detail below. For more
information on creating / editing the business action and workflows, see
the **Business Action** section ([here]{.mcFormatColor
style="color: Blue;"}), and the **Workflows** section
([here]{.mcFormatColor style="color: Blue;"}) of the **STEP Online
Help**.

### Configuring the Onboarding state to execute Mapper Configuration setup entity in the Workflow

The Mapper Configuration setup entity *cannot* be executed on any
exiting state in the workflow. To achieve this, a new state after the
Import state needs to be created, and a business action that triggers a
background process to execute the Mapper Configuration setup entity is
added to the newly created onboarding state in the import workflow.
Below are the steps to create and update a workflow to execute the
Mapper Configuration setup entity.

1.  Go to System Setup \> Workflows \> Select the workflow used by the
    importer.

For this example, AutoCare PIES Import workflow is used.

1.  Right-click the respective workflow, select **Edit STEP Workflow**,
    and the STEP Workflow Designer will display.

![](../../Resources/Images/Data%20Onboarding/32.png)

1.  Within the STEP Workflow Designer, create a new state between the
    Import state and Import Completed state. In this example, a new
    state called \'Onboarding\' is created (as shown below). For
    detailed instructions on creating States and Transitions, see
    **Creating a Workflow** topic ([here]{.mcFormatColor
    style="color: Blue;"}) of the **Workflows** section of the **STEP
    Online Help**.

![](../../Resources/Images/Data%20Onboarding/28.png)

1.  Right-click the newly created state (in this case it is
    \'Onboarding\' state), select **Edit State**, and the State Editor
    will display.

![](../../Resources/Images/Data%20Onboarding/29.png)

1.  Within the State Editor, click the **On Entry** tab (as shown
    below).

![](../../Resources/Images/Data%20Onboarding/30.png)

1.  Click on the **Add new Business Action** link to create a local
    action and click the edit button (
    ![](../../Resources/Images/Data%20Onboarding/251.png) ) to open the
    Edit Operation dialog. For more information on creating a business
    rule, see the **Creating a Business Rule or Library** topic
    ([here]{.mcFormatColor style="color: Blue;"}) of the **Business
    Rules** section of the **STEP Online Help**.

![](../../Resources/Images/Data%20Onboarding/249.png)

1.  Use the dropdown menu within the Edit Operation dialog to select
    **Import flow** \> **Run background process action** operation.

![](../../Resources/Images/Data%20Onboarding/250.png)

8.  Select **\[MapperBackgroundService\]** in the dropdown next to the
    Background Process Service field and the following parameters will
    display (as shown above). Configure the following parameters:

-   **QueueID:** Required parameter for all background process actions
    that specifies the queue in which the background process should run.
    By default, this field is empty. In the example above, the value
    \'queue\_Mapping\' is populated. This parameter is specified for the
    action itself, not the particular service within the action, though
    the outcome is the same as each action runs only a single service.
-   **Background Process Service:** Required parameter for all
    background process actions that specifies the background process.
    This should always be populated with \[MapperBackgroundService\].
-   **Changed attribute:** This is the required parameter that must be
    populated with the same attribute that is configured within the
    \'Updated values attribute\' parameter in the \'Set import status
    attributes\' operation. to find and select an attribute that is used
    to identify when an object is changed while importing. When the
    attribute is configured, the system will search for all the source
    objects where the configured attribute holds the value \'true\' and
    executes the Mapper Configuration setup entity on all the objects
    with Changed attribute value = true. For more information on how to
    configure this attribute in \'Set import status attributes\'
    operation, see the **Business Action: Set Import Status Attributes**
    topic of the **Automotive Reference Guide** found within the
    **Solution Enablement** section of **STEP Online Help**[
    here]{.mcFormatColor style="color: Blue;"}.

If the \'Changed attribute\' parameter is not populated with the right
attribute value, then the \[MapperBackgroundService\] will fail with an
exception error. The screenshot below displays the Background Process of
the onboarding state failed with the NullPointerException error.

![](../../Resources/Images/Data%20Onboarding/245.png)

-   **Clear change attribute:** Selecting this parameter will clear the
    flag set in the attribute configured within the \'Changed
    attribute\' parameter after the Mapper Configuration setup entity is
    executed. Checking this parameter prevents the Mapper Configuration
    setup entity being executed multiple times on the same Source object
    over subsequent imports.

The \'Clear change attribute\' parameter has to checked only when it is
decided that the flags marked in the attribute will be of no more use by
any other functionalities. If there are multiple Mapper Configuration
setup entity being executed in the same workflow state, then this
parameter is to be only checked in the last Mapper Configuration setup
entity that gets executed.

-   **Mapper Configuration:** Required parameter to specify the Mapper
    Configuration that needs to be executed.
-   **Force existing target:** Selecting this parameter will allow
    onboarding the data only if the source object has an existing target
    object. Thus, it will not allow creation of new targets irrespective
    of the presence / absence of the target hierarchy defined in the
    Target Hierarchy parameter that is available within the \'Setup\'
    tab of the Onboarding Mappings Details screen. Deselecting this
    parameter will allow creation of the target object if necessary,
    provided that the target hierarchy is defined in the Target
    Hierarchy parameter that is available within the \'Setup\' tab of
    the Onboarding Mappings Details screen.

9.  Click the **Save** button to save and close the configuration.

Alternatively, users can also create a global business action and then
configure that action in the \'Business Rule\' parameter by clicking the
ellipsis button
(![](../../../../Resources/Images/Buttons/ellipsis.png){.img_intext}) to
find and select the business action created to set the Mapper
Configuration after import. But, this method *hinders the performance*
of the onboarding process. It is recommended that a local action is
created in the state and configured accordingly.

Below is an example of how the State Editor should look prior to saving:

![](../../Resources/Images/Data%20Onboarding/248.png)

10. Close the State Editor, and save and close the STEP Workflow
    Designer.

Users *cannot* create multiple local actions to execute multiple Mapper
Configuration setup entity in one single state. If multiple Mapper
Configuration setup entity is to be executed, then the user has to
create multiple onboarding states for each Mapper Configuration setup
entity that is to be executed.

### Monitoring the automated Onboarding process

Monitoring an Onboarding process allows users to view the onboarding
process\' activity and status, and analyze the execution report for
details.

Each onboarding state can have only one business action (Run background
process action). For executing multiple Mapper Configuration setup
entity, user has to create multiple onboarding states for each Mapper
Configuration setup entity. Presence of multiple onboarding states
allows each business actions within them to run as individual background
processes and they all shares the common background process service
(MapperBackgroundService).

As the file is uploaded for an import in the Web UI, the Controller
Entity moves through their associated Import workflow. Users can monitor
the progress using their associated Status Selector Widget on the Web UI
homepage and/or the left side panel. Clicking the Controller icon
displays the Import Details below the Controller list. For information
on how to access the Import Details screen, see the associated importer
topics under the **Importing Automotive Data** section[
here]{.mcFormatColor style="color: Blue;"}.

When the Controller reaches the Onboarding state in the workflow and
executes the Mapper Configuration setup entity on all the Source objects
with Changed attribute value = true, a background process (BGP) will be
generated. and thea corresponding BGP folder is created on the
application server at
/workarea/background-processarea/MappingBackgroungService
directory.Additionally, the Background Process Link column displays a
link to the Background Process Details screen as \'waiting.\'

![](../../Resources/Images/Data%20Onboarding/246.png)

Users can click the \'waiting\' Background Process Link (shown above) to
view the details of the onboarding process within the Background Process
Details screen.

In the example below, the ID \'BGP\_118056\' displays the status as
\'Succeeded\' and has updated one object.

![](../../Resources/Images/Data%20Onboarding/247.png)

Following are the BGP Log output considerations for the automated
onboarding process:

-   Progress of the objects updated is reported per 100 updated objects
-   Any direct failure to onboard an object is reported as an exception
    (this does not stop onboarding of remaining objects)

Executing by a Business Rule
----------------------------

This is an outdated method that is still being used for execution in Web
UI. Users are suggested to use the Mapper Action button instead (as
detailed above in this topic).

This process involves configuring a business action to hold the Mapper
Configuration and run this business action on the source object in
different possible ways. The execution can occur with a business action
inside a workflow, or run on approving the object, or any other places
that can run a business action (e.g., run as a bulk update on a
Collection, or initiating the business action while a node is selected
in Web UI).

1.  Create and configure a business action using the \'Execute mapper
    configuration\' operation. For the full set of instructions on
    configuring the \'Execute mapper configuration\' business action,
    see the **Configuring the Execute Mapper Configuration Business
    Action** documentation[ here]{.mcFormatColor style="color: Blue;"}.
2.  Review and implement the most common ways to use business rules as
    described in **Using Business Rules in STEP** topic within the
    **Business Rules** section of **STEP Online Help**[
    here]{.mcFormatColor style="color: Blue;"}.
