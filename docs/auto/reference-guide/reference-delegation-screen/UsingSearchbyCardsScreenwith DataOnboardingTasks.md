---
title: '\[%=Heading.AnyLevel%\]'
---

Using Search by Cards Screen with Data Onboarding Tasks
=======================================================

When properly configured, a user clicking on an object in an Advanced
Search Task List will be routed to a specific screen designated for
display of objects in the particular workflow and state that the object
is currently in.

What follows is an example that a user can utilize as a starting point
to complete their own configuration. The directions and screenshots are
designed under the assumption that the user has already set up all the
screens required.

1.  Log in to the Web UI and enter design mode.

```{=html}
<!-- -->
```
1.  Navigate through the properties to get to the Status Selector you
    will be editing (either Status Selector Sidebar Widget via the Main
    Properties or the Status Selector Homepage Widget). For more
    information, see the **Status Selector Sidebar Widget** in the **Web
    User Interface** documentation[ here]{.mcFormatColor
    style="color: Blue;"}. The [Results Screen]{.bold} for the
    applicable Status Selector should be set up to go to the Advanced
    Search screen. If not, make the selection and click Save.

![](../../../../Resources/Images/STEPPortals/StatusSelector_ResultsScreen.png)

1.  Select the Advanced Search Screen ID from the dropdown (it is Search
    advanced in the example below). Click the checkbox for the [Enable
    Workflow Selection]{.bold} parameter in the Advanced Search Screen
    Properties. Save the selection before going on to the next step.

![](../../../../Resources/Images/STEPPortals/EnableWorkflowSelection.png)

1.  Stay on the Advanced Search Screen Properties screen, and click on
    the Node List \'go to component\' link.
2.  On the Node List properties screen, disable / [uncheck]{.bold} the
    Lookup Screen Type For Navigation parameter. Save these changes.

-   If Lookup Screen Type For Navigation is [unchecked]{.bold}, then the
    object screen selection that is defined under Selection Screens will
    be used as a target screen (e.g., Asset Selection Screen,
    Classification Selection Screen, Product Selection Screen, and
    Entity Selection Screen).
-   If Lookup Screen Type For Navigation is checked, then the screen
    mappings that are defined in the Main Properties screen are used
    when selecting the object from the Node List.

![](../../../../Resources/Images/STEPPortals/LookupScreenNav.png)

7.  Select a Forwarding Switch Screen from the Product Selection Screen
    dropdown. Save the Node List Properties.

8.  From the screen dropdown selector (to the left of the Save button),
    pull up the properties for the screen designated as the Product
    Selection Screen. In this example, it is the
    Screen\_TaskList2\_Forwarding screen.

9.  In the Forwarding Switch Screen Properties, define the workflow
    condition that should show on the screen when selecting an object
    link within a Node List.

-   Click Add to add a mapping. This will open Screen Mapping
    Properties.
-   On Screen Mapping Properties, under the Conditions field, click Add.
-   Select \'Workflow Condition\' from the component list and click Add.
-   Make a State and Workflow selection. Click Add again. Users should
    continue mapping any additional workflow states, if applicable, that
    will be going to the [same ]{.italic}screen. When done, click the
    dropdown for the Screen parameter and make a selection. Click Add.
-   Save the Forwarding Switch Screen Properties.
-   Repeat the steps in the previous bullets as needed.
-   Save any additional changes and close Web UI Designer.

[If mapping is set up for one state in a workflow displayed using a
Status Selector, mappings should be set up for all displayed states of
the workflow to avoid end users seeing a \'No mapping found\' message
when clicking on an object ID in the results set.]{.bold}

![](../../../../Resources/Images/STEPPortals/SwtichScreenWorflowCondition.png){.NoColumns}

The result is that when a user clicks on the a workflow state on the
Status Selector, the results are shown in an Advanced Search Task List.
When a user clicks on the ID for an object in the results set, the
screen is redirected to the forwarding screen that is specified by the
workflow condition.

In the example shown in the screenshots, when a user clicks on the
Review Data state on the Status Selector, the result is shown in the
Advanced Search Task List. When the user clicks on of the ID links, the
screen in this example is redirected to an Items Details screen. See the
screenshots that follow.

![](../../../../Resources/Images/WebUIAdvancedSearch/AdvSearch_TaskList92.png)

If an object is in more than one workflow, or in multiple states in the
same workflow, a \'Select workflow state\' dialog appears for the user
to specify the state they would like to see the object in. Users need to
make a selection or selections using the dropdowns that are active /
available. The top dropdown is for workflow selection, and the bottom
dropdown is for state selection.

![](../../../../Resources/Images/STEPWorkflows/States%20and%20Characteristics/Release74_SelectWorkflowState.png){.NoColumns}

Once selections are made, the user clicks OK and is then redirected to
the designated screen for the selected workflow state.
