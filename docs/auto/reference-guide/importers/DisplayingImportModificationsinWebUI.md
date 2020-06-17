---
description: 'Automotive Solution: Describes how to display import
  modifications in Web UI.'
title: '\[%=Heading.AnyLevel%\]'
---

Displaying Import Modifications in Web UI
=========================================

If additional states are added to any workflow, it may be useful to also
reflect them in the Web UI. If the file will spend more than a few
minutes processing within the state, it may be useful to display the
state to end users so the file does not appear to be missing.

Additionally, if user interaction is required for the file to move to
the next state, it must be accessible to end users so that they can take
action on it. On the other hand, new states that are automated only
(e.g., the system will transition the task into the next state without
any user intervention) do not necessarily need to be displayed to the
end user.

To manage additional import workflow states in the Web UI, two actions
need to be taken:

1.  Add the state to the Homepage Status Selector for the workflow. An
    introduction to status selectors in the Automotive solution is
    provided in the **Automotive Quick Start Guide**
    ([here]{.mcFormatColor style="color: Blue;"}) within the **Solution
    Enablement** section of **STEP Online Help**. Detailed information
    for configuring status selectors is available in the **Status
    Selector Homepage Widget** topic within **STEP Online Help**.
2.  Update the associated workflow screen to display details about the
    state. Each importer has a corresponding workflow screen in Web UI
    called \'\[Standard\]\[Format\]WorkflowScreen,\' (e.g.,
    AutoCareACESApplicationWorkflowScreen). Select that screen in the
    Web UI designer and navigate to the Data Provider to add the states,
    e.g., select the **go to component** link for the Node Editor child
    component \> double click on the **Refreshable Node List** child
    component \> click the **Edit** button for the Data Provider \>
    select the appropriate workflow in the Workflow parameter \> add the
    additional states using the dropdown and **Add** button for the
    States parameter \> **Save**).
