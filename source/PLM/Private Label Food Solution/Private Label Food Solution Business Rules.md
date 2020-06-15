---
description: 'PLM Solution: Below is a table of some example business
  actions, what they do, and where they can be used for the private
  label food solution.'
title: '\[%=Heading.Level1%\]'
---

Private Label Food Solution Business Rules
==========================================

PRODOC note: This topic is \'On Hold.\' Isabel is working on more BRs
and we may or may not need this topic. It is not going to be published
for now as of 1/30/2020.

Below is a table of some example business actions, what they do, and
where they can be used for the private label food solution.

+----------------------+----------------------+----------------------+
| Business Action Name | Description          | Where it is Used     |
+======================+======================+======================+
| PLM Food Award Bid   | Updates the status   | Private Label Food   |
|                      | of the Design        | New Project workflow |
|                      | Specification        |                      |
+----------------------+----------------------+----------------------+
| PLM Food             | Updates the status   | Private Label Food   |
| Cancellation Details | of related objects   | New Project workflow |
|                      | when a project or    | and Private Label    |
|                      | specification is     | Food Product         |
|                      | canceled with date / | Specification        |
|                      | time and user name.  | workflow.            |
+----------------------+----------------------+----------------------+
| PLM Food Cancel      | Move current project | Private Label Food   |
| Project Back To List | to next state and    | New Project workflow |
|                      | navigate back to     |                      |
|                      | task list            |                      |
+----------------------+----------------------+----------------------+
| PLM Food Cancel      | Updates canceled     | Private Label Food   |
| Samples              | samples with date /  | Supplier Responses   |
|                      | time and user        |                      |
|                      | information          |                      |
+----------------------+----------------------+----------------------+
| PLM Food Cancel      | When projects are    | By business rules:   |
| Workflows            | canceled, removes    |                      |
|                      | related variants and | -   PLM Food End     |
|                      | samples from their   |     Project          |
|                      | workflows.           | -   PLM Food End     |
|                      |                      |     Specification    |
+----------------------+----------------------+----------------------+
| PLM Food Continue    | Move current project | Private Label Food   |
| Project Back To List | to next state and    | New Project workflow |
|                      | navigate back to     |                      |
|                      | task list            |                      |
+----------------------+----------------------+----------------------+
| PLM Food Copy        | Copies default       | Private Label Food   |
| Requirements and     | values from links    | Product              |
| Parameters           | between Requirements | Specification        |
|                      | and Parameters to    | workflow, state      |
|                      | the link between     | Specify Details.     |
|                      | variants and the     |                      |
|                      | Requirements or      |                      |
|                      | Parameters           |                      |
+----------------------+----------------------+----------------------+
| PLM Food Create      | Creates a            | Private Label Food   |
| Competitor Product   | competitive product  | New Project workflow |
|                      | and a reference to   |                      |
|                      | it from the Design   |                      |
|                      | Specification        |                      |
+----------------------+----------------------+----------------------+
| PLM Food Create      | Creates variants and | Private Label Food   |
| Product              | relates them, names  | New Project workflow |
| Specification        | them and copies      |                      |
|                      | default values from  |                      |
|                      | Requirements and     |                      |
|                      | Parameters to the    |                      |
|                      | references between   |                      |
|                      | the variants and the |                      |
|                      | Requirements and     |                      |
|                      | Parameters.          |                      |
+----------------------+----------------------+----------------------+
| Private Label Food   | Creates samples for  | Private Label Food   |
| New Project workflow | the variants, names  | New Project workflow |
|                      | them, copies         |                      |
|                      | requirement and      |                      |
|                      | parameter values     |                      |
|                      | from the variant to  |                      |
|                      | the reference from   |                      |
|                      | sample to            |                      |
|                      | requirement or       |                      |
|                      | parameter.           |                      |
+----------------------+----------------------+----------------------+
| PLM Food End Project | Updates status for   | Private Label Food   |
|                      | canceled or          | New Project workflow |
|                      | completed Design     |                      |
|                      | Specifications.      |                      |
+----------------------+----------------------+----------------------+
| PLM Food End Samples | Updates status for   | Private Label Food   |
|                      | canceled or          | Supplier Response    |
|                      | completed samples    |                      |
|                      | (supplier responses) |                      |
+----------------------+----------------------+----------------------+
| PLM Food End Sample  | Ends the sample      | Used in PLM Food End |
| Workflow Update      | workflow and routes  | Samples business     |
|                      | related variants and | rules                |
|                      | Design               |                      |
|                      | Specifications in    |                      |
|                      | other workflows.     |                      |
+----------------------+----------------------+----------------------+
| PLM Food End         | Updates status for   | Private Label Food   |
| Specification        | canceled or          | Product              |
|                      | completed            | Specification        |
|                      | specification        | workflow             |
|                      | variants.            |                      |
+----------------------+----------------------+----------------------+
| PLM Food End         | When the last        | By business rules    |
| Specification        | related variant      | PLM Food End         |
| Transition           | leaves the workflow, | Specification        |
|                      | submit Design        |                      |
|                      | Specification to     |                      |
|                      | Award state of       |                      |
|                      | Private Label Food   |                      |
|                      | New Project          |                      |
|                      | Workflow.            |                      |
+----------------------+----------------------+----------------------+
| PLM Food Evaluation  | Sets the completed   | Private Label Food   |
| Complete             | date / time when the | Product              |
|                      | specification leaves | Specification        |
|                      | the Product          | workflow             |
|                      | Specification        |                      |
|                      | workflow.            |                      |
+----------------------+----------------------+----------------------+
| PLM Food Pending     | Update status of     | Private Label Food   |
| Related Specs        | related design       | Product              |
|                      | specification to     | Specification        |
|                      | show that the        | workflow:            |
|                      | variant has been     |                      |
|                      | specified. When all  | -   PLM Food Update  |
|                      | related              |     Status           |
|                      | specification        | -   PLM Food Pending |
|                      | variants have been   |     Specifications   |
|                      | specified the design |     Transitions      |
|                      | specification will   |                      |
|                      | be transitioned out  |                      |
|                      | of its pending       |                      |
|                      | state.               |                      |
+----------------------+----------------------+----------------------+
| PLM Food Pending     | Workflow transition  | Private Label Food   |
| Specifications       | logic.               | Product              |
| Transitions          |                      | Specification        |
|                      |                      | workflow             |
+----------------------+----------------------+----------------------+
| PLM Food Pending     | This business rule   | Private Label Food   |
| Supplier Response    | will reference two   | New Project workflow |
|                      | other rules that     |                      |
|                      | will be executed     |                      |
|                      | upon entry to        |                      |
|                      | Pending Supplier     |                      |
|                      | Responses state.     |                      |
|                      |                      |                      |
|                      | -   PLM Food         |                      |
|                      |     Supplier         |                      |
|                      |     Response         |                      |
|                      |     Transition       |                      |
|                      | -   PLM Food Update  |                      |
|                      |     Status           |                      |
+----------------------+----------------------+----------------------+
| PLM Food Request     | On selected sample   | -   Private Label    |
| Supplier Follow Up   | update attribute     |     Food Product     |
|                      | Supplier Response    |     Specification    |
|                      | Attribute Routing    |     workflow         |
|                      | also update          | -   Pending          |
|                      | attribute Status of  |     Evaluation state |
|                      | This Response and    |     -Toolbar action  |
|                      | Initiate the Sample  |                      |
|                      | into Supplier        |                      |
|                      | Response workflow.   |                      |
+----------------------+----------------------+----------------------+
| PLM Food Sample      | Update attribute     | PLM Food Samples     |
| Version              | Version number in    | business rules       |
|                      | the current Sample.  |                      |
+----------------------+----------------------+----------------------+
| PLM Food             | Write the number     | Private Label Food   |
| Specification        | \'1\' to variant     | Product              |
| Complete             | attribute Version    | Specification        |
|                      | Number. Update       | workflow             |
|                      | attribute Status of  |                      |
|                      | This Specification   |                      |
|                      | to Specification     |                      |
|                      | completed \[ISO      |                      |
|                      | Date\].              |                      |
+----------------------+----------------------+----------------------+
| PLM Food Submit      | Update attribute     | Private Label Food   |
| Supplier Bid         | Status of This       | Supplier Responses   |
|                      | Response.            | workflow             |
+----------------------+----------------------+----------------------+
| PLM Food Submit      | Update attribute     | Private Label Food   |
| Supplier Follow Up   | Status of This       | Supplier Responses   |
|                      | Response.            | workflow             |
+----------------------+----------------------+----------------------+
| PLM Food Supplier    | When Design          | Private Label Food   |
| Response Transition  | Specification enters | Product              |
|                      | the Pending          | Specification        |
|                      | Suppliers Response   | workflow             |
|                      | state, find all      |                      |
|                      | related variants and |                      |
|                      | transition them to   |                      |
|                      | the Pending Supplier |                      |
|                      | Responses state of   |                      |
|                      | the Private Label    |                      |
|                      | Food Product         |                      |
|                      | Specification.       |                      |
+----------------------+----------------------+----------------------+
| PLM Food Update      | Updates the progress | Private Label Food   |
| Status               | on Design            | New Project workflow |
|                      | Specification,       |                      |
|                      | related variants and |                      |
|                      | related samples as   |                      |
|                      | they move through    |                      |
|                      | their various        |                      |
|                      | workflows.           |                      |
+----------------------+----------------------+----------------------+
| PLM Awarded Bid      | Validate that each   | Private Label Food   |
| Validation           | Label Variant Sample | New Project workflow |
|                      | that is a target of  |                      |
|                      | reference Related    |                      |
|                      | Specification of the |                      |
|                      | current object in    |                      |
|                      | the current state    |                      |
|                      | has \'Y\' or \'N\'   |                      |
|                      | in the attribute     |                      |
|                      | Awarded Bid or has a |                      |
|                      | value in the         |                      |
|                      | attribute Status of  |                      |
|                      | Supplier Responses   |                      |
|                      | hat begin with       |                      |
|                      | \'Canceled\'. If     |                      |
|                      | condition fails      |                      |
|                      | return a warning     |                      |
|                      | message.             |                      |
+----------------------+----------------------+----------------------+
| PLM Food Validate    | Validate that        | Private Label Food   |
| Specification        | reference            | Product              |
|                      | Requirement and      | Specification        |
|                      | reference Parameter, | workflow, Web UI     |
|                      | have target if the   | business action      |
|                      | current object.      |                      |
+----------------------+----------------------+----------------------+
| PLM Food Validate    | Validate Mandatory   | Private Label Food   |
| Supplier Responses   | Requirements         | Supplier Responses   |
|                      | Responses.           |                      |
+----------------------+----------------------+----------------------+
| RemoveFromWorkflow   | Remove current       | All workflows        |
|                      | object from Workflow |                      |
+----------------------+----------------------+----------------------+

Please see your Stibo Systems representative for more information.
