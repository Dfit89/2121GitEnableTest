---
description: 'Automotive Solution: Describes Automotive Business Rule
  Plugins.'
title: '\[%=Heading.AnyLevel%\]'
---

Automotive Business Rule Plugins
================================

A number of business rule plugins are provided to assist in extending
the core Automotive solution. This section addresses many of the
Automotive business rule plugins as they are available when configuring
Business Actions and Business Conditions.

Prerequisites

It is assumed that the admin user has knowledge of STEP administrative
functions and experience working in System Setup, including creating and
editing business rules, workflows, and Web UIs. This section targets
only the specific information needed for a knowledgeable STEP admin user
to identify and configure the Automotive-specific business rule plugins.
For more introductory material of these concepts, see the **Business
Rules** ([here]{.mcFormatColor style="color: Blue;"}), **Workflows**
([here]{.mcFormatColor style="color: Blue;"}) **Web User Interfaces**
([here]{.mcFormatColor style="color: Blue;"}) sections of **STEP Online
Help**.

Business Action Operations

Business Action Operations {#business-action-operations conditions="Primary.Web"}
--------------------------

+----------------+----------------+----------------+----------------+
| Menu           | [Operation     | Components     | [Descriptio    |
|                | Nam            | required for   | n]{style="font |
|                | e]{style="font | use            | -size: 10pt;"} |
|                | -size: 10pt;"} |                |                |
+================+================+================+================+
| Automotive     | Change         | Application    | [Allows users  |
|                | assembly       | Manager, Bulk  | to use a Bulk  |
|                |                | Update action  | Updates action |
|                |                | button         | button within  |
|                |                |                | an Application |
|                |                |                | Manager to     |
|                |                |                | change the     |
|                |                |                | assembly /     |
|                |                |                | vehicle of one |
|                |                |                | or more        |
|                |                |                | existing       |
|                |                |                | applications.  |
|                |                |                | Will not       |
|                |                |                | change the     |
|                |                |                | assembly of a  |
|                |                |                | missing        |
|                |                |                | application.   |
|                |                |                | For more       |
|                |                |                | information,   |
|                |                |                | see **Business |
|                |                |                | Action: Change |
|                |                |                | Assembly**[[   |
|                |                |                | here           |
|                |                |                | ]{style="font- |
|                |                |                | size: 9pt;"}]{ |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
|                |                |                | ]{style="f     |
|                |                |                | ont-weight: no |
|                |                |                | rmal;"}[PRODOC |
|                |                |                | note:          |
|                |                |                | RDCUST-1245    |
|                |                |                | and            |
|                |                |                | RDCUST-988]{st |
|                |                |                | yle="font-weig |
|                |                |                | ht: normal; fo |
|                |                |                | nt-size: 9pt;" |
|                |                |                | condi          |
|                |                |                | tions="Primary |
|                |                |                | .PRODOC Note"} |
+----------------+----------------+----------------+----------------+
| [Automoti      | Change part    | Application    | [Allows users  |
| ve]{style="fon |                | Manager, Bulk  | to use a Bulk  |
| t-size: 9pt;"} |                | Update action  | Updates action |
|                |                | button         | button within  |
|                |                |                | an Application |
|                |                |                | Manager to     |
|                |                |                | change the     |
|                |                |                | part for a     |
|                |                |                | selected       |
|                |                |                | application.   |
|                |                |                | For more       |
|                |                |                | information,   |
|                |                |                | see            |
|                |                |                | ]{style=       |
|                |                |                | "font-size: 8p |
|                |                |                | t;"}**Business |
|                |                |                | Action: Change |
|                |                |                | Part** [[[     |
|                |                |                | [              |
|                |                |                | here]{style="f |
|                |                |                | ont-size: 9pt; |
|                |                |                | "}]{style="fon |
|                |                |                | t-size: 8pt;"} |
|                |                |                | ]{style="font- |
|                |                |                | size: 9pt;"}]{ |
|                |                |                | .mcFormatColor |
|                |                |                | style="        |
|                |                |                | color: Blue;"} |
|                |                |                | [.             |
|                |                |                | ]{style="fon   |
|                |                |                | t-size: 8pt;"} |
|                |                |                | PRODOC note:   |
|                |                |                | RDCUST-1244    |
+----------------+----------------+----------------+----------------+
| Automotive     | Change part    | Application    | Allows users   |
|                | type           | Manager, Bulk  | to use a Bulk  |
|                |                | Update action  | Updates action |
|                |                | button         | button within  |
|                |                |                | an Application |
|                |                |                | Manager to     |
|                |                |                | change the     |
|                |                |                | part type for  |
|                |                |                | a selected     |
|                |                |                | application.   |
|                |                |                | [Will not      |
|                |                |                | change the     |
|                |                |                | part type of a |
|                |                |                | missing        |
|                |                |                | application.   |
|                |                |                | For more       |
|                |                |                | information,   |
|                |                |                | see **Business |
|                |                |                | Action: Change |
|                |                |                | Part**         |
|                |                |                | **Type**[[     |
|                |                |                | here           |
|                |                |                | ]{style="font- |
|                |                |                | size: 9pt;"}]{ |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
|                |                |                | ]{style="f     |
|                |                |                | ont-weight: no |
|                |                |                | rmal;"}[PRODOC |
|                |                |                | note:          |
|                |                |                | RDCUST-1245]{  |
|                |                |                | style="font-we |
|                |                |                | ight: normal;" |
|                |                |                | condi          |
|                |                |                | tions="Primary |
|                |                |                | .PRODOC Note"} |
+----------------+----------------+----------------+----------------+
| Automotive     | Copy           | Application    | Allows users   |
|                | application to | Manager, Bulk  | to use a Bulk  |
|                | other assembly | Update action  | Updates action |
|                |                | button         | button within  |
|                |                |                | an Application |
|                |                |                | Manager to     |
|                |                |                | copy one or    |
|                |                |                | more existing  |
|                |                |                | applications   |
|                |                |                | to another     |
|                |                |                | assembly /     |
|                |                |                | vehicle. For   |
|                |                |                | more           |
|                |                |                | information,   |
|                |                |                | see **Business |
|                |                |                | Action: Copy   |
|                |                |                | Application to |
|                |                |                | Other          |
|                |                |                | Assembly**[[   |
|                |                |                | here           |
|                |                |                | ]{style="font- |
|                |                |                | size: 9pt;"}]{ |
|                |                |                | .mcFormatColor |
|                |                |                | style="color:  |
|                |                |                | Blue;"}.PRODOC |
|                |                |                | note:          |
|                |                |                | RDCUST-1243    |
+----------------+----------------+----------------+----------------+
| Automotive     | Copy           | Application    | Allows users   |
|                | application to | Manager, Bulk  | to use a Bulk  |
|                | other part     | Update action  | Updates action |
|                |                | button         | button within  |
|                |                |                | an Application |
|                |                |                | Manager to     |
|                |                |                | copy one or    |
|                |                |                | more existing  |
|                |                |                | applications   |
|                |                |                | to another     |
|                |                |                | part. For more |
|                |                |                | information,   |
|                |                |                | see **Business |
|                |                |                | Action: Copy   |
|                |                |                | Application to |
|                |                |                | Other Part**[[ |
|                |                |                | here           |
|                |                |                | ]{style="font- |
|                |                |                | size: 9pt;"}]{ |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
|                |                |                | PRODOC note:   |
|                |                |                | RDCUST-1242    |
+----------------+----------------+----------------+----------------+
| Automotive     | Copy           | Application    | Allows users   |
|                | applications   | Manager, Bulk  | to use a Bulk  |
|                | to related     | Update action  | Updates action |
|                | parts          | button         | button within  |
|                |                |                | an Application |
|                |                |                | Manager to     |
|                |                |                | copy one or    |
|                |                |                | more existing  |
|                |                |                | applications   |
|                |                |                | to one or more |
|                |                |                | related parts. |
|                |                |                | For more       |
|                |                |                | information,   |
|                |                |                | see **Business |
|                |                |                | Action: Copy   |
|                |                |                | Applications   |
|                |                |                | to Related     |
|                |                |                | Parts**[[      |
|                |                |                | here           |
|                |                |                | ]{style="font- |
|                |                |                | size: 9pt;"}]{ |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
|                |                |                | PRODOC         |
|                |                |                | note**:**      |
|                |                |                | RDCUST-1013    |
+----------------+----------------+----------------+----------------+
| Automotive     | Copy           | Anywhere a     | Allows users   |
|                | classification | bulk update    | to update the  |
|                | hierarchy to   | can be run     | product        |
|                | product        |                | hierarchy to   |
|                | hierarchy      |                | match the      |
|                |                |                | classification |
|                |                |                | hierarchy. The |
|                |                |                | operation has  |
|                |                |                | the ability to |
|                |                |                | disregard the  |
|                |                |                | classification |
|                |                |                | prefix in      |
|                |                |                | order to       |
|                |                |                | create the     |
|                |                |                | product        |
|                |                |                | hierarchy      |
|                |                |                | using a        |
|                |                |                | defined        |
|                |                |                | product        |
|                |                |                | prefix. Can be |
|                |                |                | used after a   |
|                |                |                | VCDB update    |
|                |                |                | has created    |
|                |                |                | new vehicles   |
|                |                |                | within the     |
|                |                |                | yellow         |
|                |                |                | classification |
|                |                |                | folders to     |
|                |                |                | create blue    |
|                |                |                | hierarchy      |
|                |                |                | nodes.         |
|                |                |                |                |
|                |                |                | **CAUTION**:   |
|                |                |                | Object Types   |
|                |                |                | need to be     |
|                |                |                | similar in     |
|                |                |                | that they      |
|                |                |                | should have    |
|                |                |                | the same ID    |
|                |                |                | (without the   |
|                |                |                | prefix).       |
|                |                |                |                |
|                |                |                | PRODOC note:   |
|                |                |                | Disregard the  |
|                |                |                | prefix in      |
|                |                |                | classification |
|                |                |                | H and go       |
|                |                |                | create the     |
|                |                |                | product H      |
|                |                |                | using the      |
|                |                |                | defined        |
|                |                |                | product        |
|                |                |                | prefix.        |
|                |                |                | Caution:       |
|                |                |                | object types   |
|                |                |                | need to be     |
|                |                |                | similar.       |
|                |                |                | Object types   |
|                |                |                | should have    |
|                |                |                | same ID except |
|                |                |                | for prefix.    |
|                |                |                | Run it for one |
|                |                |                | vehicle. Uses  |
|                |                |                | bulk update.   |
|                |                |                | When you run a |
|                |                |                | VCDB import    |
|                |                |                | and there are  |
|                |                |                | new vehicles   |
|                |                |                | that you want  |
|                |                |                | to bring from  |
|                |                |                | the yellow     |
|                |                |                | folder to the  |
|                |                |                | blue           |
|                |                |                | folder\...     |
|                |                |                | RDCUST-1966    |
+----------------+----------------+----------------+----------------+
| Automotive     | Generate       | Application    | PRODOC note:   |
|                | TecDoc         | Manager,       | Do not         |
|                | Accessory list | Mapper         | document until |
|                | in mapper      |                | the Mapper is  |
|                |                |                | documented     |
+----------------+----------------+----------------+----------------+
| Automotive     | Generate       | Application    | PRODOC note:   |
|                | TecDoc         | Manager,       | Do not         |
|                | Partslist in   | Mapper         | document until |
|                | mapper         |                | the Mapper is  |
|                |                |                | documented     |
+----------------+----------------+----------------+----------------+
| Automotive     | Map attribute  | Application    | PRODOC note:   |
|                | values         | Manager,       | Do not         |
|                |                | Mapper         | document until |
|                |                |                | the Mapper is  |
|                |                |                | documented     |
+----------------+----------------+----------------+----------------+
| Automotive     | Move ACES      |                | Moves all ACES |
|                | Applications   |                | applications   |
|                | for PIES Part  |                | from one PIES  |
|                |                |                | Item to        |
|                |                |                | another by     |
|                |                |                | following a    |
|                |                |                | reference      |
|                |                |                | between the    |
|                |                |                | parts. For     |
|                |                |                | more           |
|                |                |                | information,   |
|                |                |                | see **Business |
|                |                |                | Action: Move   |
|                |                |                | ACE            |
|                |                |                | S Applications |
|                |                |                | for PIES       |
|                |                |                | Part**[[       |
|                |                |                | h              |
|                |                |                | ere]{style="fo |
|                |                |                | nt-size: 9pt;" |
|                |                |                | conditions="P  |
|                |                |                | rimary.Web"}]{ |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
+----------------+----------------+----------------+----------------+
| Automotive     | Set Condition  |                | Links          |
|                | Links on Part  |                | application    |
|                | Types          |                | conditions /   |
|                |                |                | options to     |
|                |                |                | part types to  |
|                |                |                | assist in      |
|                |                |                | configuring    |
|                |                |                | display        |
|                |                |                | options in the |
|                |                |                | Web UI         |
|                |                |                | Application    |
|                |                |                | Record Editor. |
|                |                |                | For more       |
|                |                |                | information,   |
|                |                |                | see **Business |
|                |                |                | Action: Set    |
|                |                |                | Condition      |
|                |                |                | Links on Part  |
|                |                |                | Types**[       |
|                |                |                | here]{         |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
|                |                |                |                |
|                |                |                | PRODOC note:   |
|                |                |                | See Validation |
|                |                |                | Path Spec -    |
|                |                |                | Remember       |
|                |                |                | training about |
|                |                |                | path! Assist   |
|                |                |                | user in        |
|                |                |                | applying the   |
|                |                |                | links to       |
|                |                |                | control how    |
|                |                |                | things display |
|                |                |                | in Application |
|                |                |                | Manager.       |
|                |                |                | (double check  |
|                |                |                | documentation  |
|                |                |                | and patch      |
|                |                |                | notes)         |
+----------------+----------------+----------------+----------------+
| Automotive     | Sync ACES      |                | Synchronizes   |
|                | Applications   |                | all ACES       |
|                | between PIES   |                | applications   |
|                | Parts          |                | between two    |
|                |                |                | PIES Items by  |
|                |                |                | following a    |
|                |                |                | reference      |
|                |                |                | between the    |
|                |                |                | parts. For     |
|                |                |                | more           |
|                |                |                | information,   |
|                |                |                | see **Business |
|                |                |                | Action: Sync   |
|                |                |                | ACES           |
|                |                |                | Applications   |
|                |                |                | Between PIES   |
|                |                |                | Parts**[       |
|                |                |                | [here          |
|                |                |                | ]{style="font- |
|                |                |                | size: 9pt;"}]{ |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
+----------------+----------------+----------------+----------------+
| Automotive     | Unique         |                | Calculates a   |
|                | application    |                | unique value   |
|                | record         |                | based on the   |
|                | constraint     |                | part, assembly |
|                |                |                | and the        |
|                |                |                | conditions for |
|                |                |                | the            |
|                |                |                | applications.  |
|                |                |                | PRODOC         |
|                |                |                | note**:** MEDU |
|                |                |                | RDCUST-1250    |
+----------------+----------------+----------------+----------------+
| Import flow    | Run background |                | PRODOC note:   |
|                | process action |                | See Reference  |
|                |                |                | Guide, BA that |
|                |                |                | starts a BGP.. |
|                |                |                | and connects   |
|                |                |                | it back to the |
|                |                |                | WF its started |
|                |                |                | from.          |
+----------------+----------------+----------------+----------------+
| Import flow    | Set import     | Workflow:      | Allows for the |
|                | status         | Import State   | implementation |
|                | attributes     |                | of change      |
|                |                |                | flags; a way   |
|                |                |                | for users to   |
|                |                |                | view what data |
|                |                |                | has been       |
|                |                |                | created or     |
|                |                |                | changed due to |
|                |                |                | an import.     |
|                |                |                | Must be used   |
|                |                |                | within the     |
|                |                |                | Import state   |
|                |                |                | of a workflow. |
|                |                |                | For more       |
|                |                |                | information,   |
|                |                |                | see **Business |
|                |                |                | Action: Set    |
|                |                |                | Import Status  |
|                |                |                | Attributes**[[ |
|                |                |                | h              |
|                |                |                | ere]{style="fo |
|                |                |                | nt-size: 9pt;" |
|                |                |                | conditions="P  |
|                |                |                | rimary.Web"}]{ |
|                |                |                | .mcFormatColor |
|                |                |                | style="c       |
|                |                |                | olor: Blue;"}. |
+----------------+----------------+----------------+----------------+
| Import flow    | Set import     |                | PRODOC note:   |
|                | status         |                | MEKO if the    |
|                | attributes     |                | object has     |
|                | (for reference |                | changed for a  |
|                | type)          |                | specific       |
|                |                |                | reference      |
|                |                |                | type\...Object |
|                |                |                | A has          |
|                |                |                | attribute \"My |
|                |                |                | ref type has   |
|                |                |                | changed.\"..   |
|                |                |                | and when a     |
|                |                |                | reference is   |
|                |                |                | added or       |
|                |                |                | deleted (True) |
+----------------+----------------+----------------+----------------+
| Import flow    | Set overall    |                | PRODOC note:   |
|                | status         |                | in Web UI the  |
|                |                |                | upper half of  |
|                |                |                | screen. Any    |
|                |                |                | State can call |
|                |                |                | these          |
+----------------+----------------+----------------+----------------+
| Import flow    | Set status for |                | PRODOC note:   |
|                | state          |                | in Web UI the  |
|                |                |                | lower half of  |
|                |                |                | screen. Any    |
|                |                |                | State can call |
|                |                |                | these          |
+----------------+----------------+----------------+----------------+

Business Condition Operations

Business Condition Operations {#business-condition-operations conditions="Primary.Web"}
-----------------------------

+----------------------+----------------------+----------------------+
| [Menu]{style         | [[Operation          | [Description]{style  |
| ="font-size: 10pt;"} | Name]{style="font-   | ="font-size: 10pt;"} |
|                      | size: 10pt;"}]{style |                      |
|                      | ="font-size: 10pt;"} |                      |
+======================+======================+======================+
| Automotive           | Validate Application | Prevents any         |
|                      |                      | applications from    |
|                      |                      | being imported that  |
|                      |                      | do not have both a   |
|                      |                      | part type and        |
|                      |                      | vehicle / assembly   |
|                      |                      | that exists in the   |
|                      |                      | STEP database. When  |
|                      |                      | a record is found    |
|                      |                      | that does not meet   |
|                      |                      | the condition, an    |
|                      |                      | error is written to  |
|                      |                      | the execution report |
|                      |                      | of the import        |
|                      |                      | process and the      |
|                      |                      | record is not        |
|                      |                      | imported. This       |
|                      |                      | condition is         |
|                      |                      | automatically        |
|                      |                      | created and added to |
|                      |                      | the Import state of  |
|                      |                      | the relevant         |
|                      |                      | workflow when the    |
|                      |                      | Easy setup of the    |
|                      |                      | import process has   |
|                      |                      | been run. For more   |
|                      |                      | information, see     |
|                      |                      | **Business           |
|                      |                      | Condition: Validate  |
|                      |                      | Application**.       |
+----------------------+----------------------+----------------------+
| Automotive           | Check path for       | Improves the         |
|                      | missing application  | accuracy of          |
|                      |                      | Application Manager  |
|                      |                      | search results       |
|                      |                      | involving specific   |
|                      |                      | part types by        |
|                      |                      | allowing the data    |
|                      |                      | model to include a   |
|                      |                      | relationship between |
|                      |                      | conditions on        |
|                      |                      | applications and     |
|                      |                      | different vehicle    |
|                      |                      | configurations. This |
|                      |                      | can be helpful when  |
|                      |                      | specific part types  |
|                      |                      | do not apply to      |
|                      |                      | certain vehicle      |
|                      |                      | configurations. For  |
|                      |                      | more information,    |
|                      |                      | see **Business       |
|                      |                      | Condition: Check     |
|                      |                      | Path for Missing     |
|                      |                      | Application**[       |
|                      |                      | [here]{              |
|                      |                      | style="font-size: 9p |
|                      |                      | t;"}]{.mcFormatColor |
|                      |                      | st                   |
|                      |                      | yle="color: Blue;"}. |
+----------------------+----------------------+----------------------+
| [TecDoc]{styl        | TecDoc reference     | PRODOC note:         |
| e="font-size: 9pt;"} | start condition      | Supposed to prevent  |
|                      |                      | the start of         |
|                      |                      | reference data       |
|                      |                      | import if there is a |
|                      |                      | supplier data import |
|                      |                      | running. Set in the  |
|                      |                      | workflow. Rejects    |
|                      |                      | the import (but the  |
|                      |                      | error does not       |
|                      |                      | display within our   |
|                      |                      | import list screen). |
|                      |                      | Set by Easy Setup go |
|                      |                      | to the WF and see    |
|                      |                      |                      |
|                      |                      | For more             |
|                      |                      | information, see     |
|                      |                      | **Business           |
|                      |                      | Condition: TecDoc    |
|                      |                      | Reference Start      |
|                      |                      | Condition**[[        |
|                      |                      | here]{               |
|                      |                      | style="font-size: 9p |
|                      |                      | t;"}]{.mcFormatColor |
|                      |                      | st                   |
|                      |                      | yle="color: Blue;"}. |
+----------------------+----------------------+----------------------+
| [TecDoc]{styl        | TecDoc supplier      | PRODOC note:         |
| e="font-size: 9pt;"} | start condition      | Supposed to prevent  |
|                      |                      | the start of         |
|                      |                      | reference data       |
|                      |                      | import if there is a |
|                      |                      | supplier data import |
|                      |                      | running. Set in the  |
|                      |                      | workflow. Rejects    |
|                      |                      | the import (but the  |
|                      |                      | error does not       |
|                      |                      | display within our   |
|                      |                      | import list screen). |
|                      |                      | Set by Easy Setup go |
|                      |                      | to the WF and see    |
|                      |                      |                      |
|                      |                      | For more             |
|                      |                      | information, see     |
|                      |                      | **Business           |
|                      |                      | Condition: TecDoc    |
|                      |                      | Supplier Start       |
|                      |                      | Condition**[[        |
|                      |                      | here]{               |
|                      |                      | style="font-size: 9p |
|                      |                      | t;"}]{.mcFormatColor |
|                      |                      | st                   |
|                      |                      | yle="color: Blue;"}. |
+----------------------+----------------------+----------------------+
