---
description: 'Stibo SDQ User Guide: Once the MDM theme is applied and
  configured, Data Stewards can click the Stibo SDQ tab within
  Salesforce to access Clerical Review functionality, where potential
  duplicates can be manually reviewed and/or merged if a user determines
  they are actual duplicates. '
title: '\[%=Heading.AnyLevel%\]'
---

Clerical Review for Data Stewards
=================================

Once the MDM theme is configured, Data Stewards can click the Stibo SDQ
tab within Salesforce to access Clerical Review functionality, where
potential duplicates can be manually reviewed and/or merged if a user
determines they are actual duplicates.

The clerical review page offers many features such as Task Assignment
and Task Priorities. The purpose of these features is to offer the tools
necessary for an organization to design a workflow where multiple people
can work together to monitor, assign, prioritize, and complete tasks
associated to managing and cleaning up duplicate records.

Within this section the features and functionality pertaining to
clerical review for data stewards is described. These option are found
on the Stibo SDQ Landing Page within the following MASTER DATA
MANAGEMENT menu options:

-   Home
-   Clerical Review
-   Manual Merge Requests

For information on the configuration and settings available within the
Stibo SDQ Landing Page, see the **Stibo SDQ Admin Guide**.

Navigating Master Data Management

User functions available for the \'MASTER DATA MANAGEMENT\' menu within
the Stibo SDQ tab:

-   Home
-   Clerical Review
-   Manual Merge Request

In the example below, all three Stibo SDQ themes are configured,
therefore the options for all three of the available themes are
displayed. The red arrows indicate the menu options Data Steward users
would commonly access.

For more information on these functions, see the **Master Data
Management** section ([here]{.mcFormatColor style="color: Blue;"}) of
this guide.

![](../../../../../Resources/Images/CMDM/User%20Guide/Stibo%20Systems%20Data%20Quality%20Application%20page.png)

Because setup is customizable, and some features many not be available,
if your display is different than what is shown in this guide, contact
your system administrator for more information.

Home
----

Once the Master Data Management theme is configured, the Home page will
display by default when the Stibo SDQ tab is selected. Also, clicking
the Home menu option will display the Home page where clerical review
tasks and reports can be accessed.

In the example below, the Stibo SDQ tab is selected, and the Home page
displays. Within the Home page, a clerical review Tasks widget is
displayed. The Tasks widget displays currently open clerical review
tasks, and filtering options.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Clerical%20Review%20Home.png)

Tasks can be filtered to display the following: All, Assigned to me, and
Unassigned. Additionally, for each of those filters, tasks can also be
filtered by the following priority levels: All, High, Medium, and Low.

As selections are made within the Tasks filters, the count of Clerical
Review tasks changes. In the example above, All tasks for All priority
levels are selected, and the count of \'7\' tasks is displayed to the
right of the \'Clerical Review\' hyperlink.

Once tasks are filtered as desired, and the Clerical Review hyperlink is
clicked, the Clerical Review page will display according to the task
filters that were applied.

Clerical Review
---------------

Clerical Review tasks allow Data Stewards to determine how to handle
records flagged as potential duplicates. Records can be flagged as
potential duplicates automatically or manually.

Clerical Review tasks are created when STEP identifies potential
duplicate data, and clerical review tasks are automatically created
within the Stibo SDQ tab. This automation helps users to focus only on
conflicts that require manual intervention, automating the rest. For
more information on how potential duplicate data is identified, see the
**Automatic Background Deduplication** section ([here]{.mcFormatColor
style="color: Blue;"}) of this guide.

Manually created clerical review tasks occur when a user creates them
from the Manual Merge Requests page. For more information, see the
**Manual Merge Request** section below.

This section describes the available features, and functions for the
Clerical Review page.

Clerical Review Features

Clicking the Clerical Review menu option displays a Clerical Review page
where the following features are available.

1.  Select All
2.  Select Task
3.  Assignment Filters
4.  Priority Filters
5.  Priority
6.  Information
7.  Manually Created Task Warning
8.  Task Table

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Clerical%20Review%20Page%20Features.png)

1.  **Select All:** Clicking the Select All checkbox will select all the
    tasks displayed per the assignment and priority filters, and allow
    for the merge, reject, link and/or reassignment of selected tasks.
    This is useful when a Data Steward needs to take the same action for
    many tasks at one time. For example, if seven tasks are displayed,
    and the Select All checkbox is enabled, then all seven tasks will
    display with their respective Select Task checkbox enabled. Also,
    deselecting the Select All checkbox will disable the individual
    Select Task checkbox.

If the Select All checkbox is enabled, and a manually created task is
included, then the Merge Selected and Reject Selected buttons will not
be enabled because manually created tasks must be merged using the
Advanced Mode button.

1.  **Select Task:** Clicking the Select Task checkbox will select the
    individual task. This is useful when a Data Steward needs to make
    changes to one or more specific tasks.
2.  **Assignment Filters:** Each of the Assignment filter buttons (All,
    Assigned to me, and Unassigned) can be selected to filter the
    display of tasks by assignment. Automatically created tasks are
    unassigned by default. Clicking the \'Unassigned\' button is useful
    when a Data Steward needs to focus on automatically created clerical
    review tasks.
3.  **Priority Filters:** Each of the Priority filter buttons (All,
    High, Medium, and Low) can be selected to filter the display of
    tasks by priority. This is useful when a Data Steward needs to focus
    on tasks of a certain priority. For example, if many tasks are
    displayed with different priority levels, and the \'High\' priority
    button is clicked, then only those tasks assigned to the logged in
    user with a High priority will be displayed.
4.  **Priority:** Within each task, its priority is listed in the top
    right corner. When a clerical review task is automatically created,
    the default priority is \'Medium.\' Data Stewards can edit the
    priority when creating or reassigning clerical review tasks.
5.  **Information:** Each task has an information icon that when
    clicked, provides more information for task details. In the example
    below the information icon is clicked, and the Task Details page
    displays.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Task%20Details.png)

1.  **Manually Created Task Warning:** When a task has been manually
    created, a blue warning icon will display. This is important because
    manually created tasks can only be resolved using the Advanced Mode
    button. When a user hovers over the blue warning icon, text will
    display as shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Manually%20Created%20Task%20Warning%20hover%20displayed.png)

1.  **Task Table:** The task table displays two or more records
    identified as potential duplicates. Users can hover over the text
    within the table to see more details. In the example below, the
    mouse cursor hovers over part of a mailing address, and the full
    mailing address is displayed within the hover text.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Task%20Table%20Hover%20text.png)

The type of record related to the task determines which columns display
within the table.

If the task relates to Business Accounts, the table will have the
following columns displayed:

-   Account Name
-   D-U-N-S Number
-   Billing Address
-   Shipping Address
-   Account Type
-   Account Phone
-   Account Fax
-   Website

If the task relates to Person Accounts, the table will have the
following columns displayed:

-   Salutation
-   First Name
-   Last Name
-   Mailing Address
-   Other Address
-   Email
-   Account Phone
-   Mobile
-   Other Phone

If the task relates to Contacts, the table will have the following
columns displayed:

-   First Name
-   Last Name
-   Account Name
-   Mailing Address
-   Other Address
-   Title
-   Email
-   Business Phone
-   Mobile Phone

Clerical Review Functions

Once one or more clerical review tasks have been selected, the following
functions are available:

1.  Merge Selected
2.  Reject Selected
3.  Link Selected
4.  Reassign Selected

```{=html}
<!-- -->
```
1.  Advanced Mode

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Clerical%20Review%20Page.png)

1.  **Merge Selected:** Clicking the **Merge Selected** button will
    initiate the following processes for each of the selected tasks:

-   Appoint one record in each task to \'master record.\'
-   Consolidate data from all records in a task to the master record.
-   Associate existing content (e.g., Opportunities, Contacts) from
    \'non-master\' records in a task to the master record.
-   Replace all references to the non-master records with a reference to
    the master record.
-   Move the non-master records to the Recycle Bin.
-   Close the Clerical review task and remove it from the Clerical
    Review Task list.

These processes run asynchronously in the background and may take a few
minutes to complete. However, the user will not have to wait. What the
user will see is that after one or more automatically created tasks are
selected, and the Merge Selected button is clicked, the Confirm Merge
dialog will display with a count of the records to be merged. In the
example below, six records are selected to be merged.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Confirm%20Merge%20dialog.png)

Clicking the **Cancel** button (or the white \'X\' in the top right of
the dialog) will close the dialog and return the user to the previous
page.

Clicking the **Confirm** button merges the records, and a green
\'Operations successful\' confirmation dialog will display as shown
below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Merge%20Succesfull%20Green%20dialog.png)

2.  **Reject Selected:** Clicking the Reject Selected button will reject
    any selected tasks. The tasks are closed, and removed from the
    Clerical Review Task lists as well as deleted from Salesforce. The
    records from the task will not be considered as potential duplicates
    again.

After one or more automatically created tasks are selected and the
Reject Selected button is clicked, the Confirm Reject dialog will
display with a count of the records to be rejected. In the example
below, six records are selected to be rejected.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Confirm%20Rejection.png)

Clicking the Cancel button (or the white \'X\' in the top right of the
dialog) will close the dialog and return the user to the previous page.

Clicking the Confirm button ensures the task(s) will no longer display
for clerical review, will close the dialog, and a green \'Operations
successful\' confirmation dialog will display for \'Reject\' and
\'Link\' operations and \'Merge Initiated Successfully\' as shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Merge%20Succesfull%20Green%20dialog.png)

1.  **Link Selected:** Clicking the Link Selected button while selecting
    multiple tasks will create a link between these records. The tasks
    are closed and removed from the Clerical Review Task lists. The
    records from the task will not be considered as potential duplicates
    again.

When the Link Selected action is selected, a confirm link prompt will
pop up confirming that the associated records with these tasks will be
linked.

![](../../../../../Resources/Images/CMDM/User%20Guide/ConfirmLink.png)

Once confirmed, the records associated with these tasks will be on the
account under the Linked Accounts section if configured for the related
record layout.

![](../../../../../Resources/Images/CMDM/User%20Guide/LinkedRecordsonAccount.png)

 

1.  **Reassign Selected:** Clicking the Reassign Selected button will
    allow for one or more selected tasks to be reassigned or given a
    different priority.

After one or more automatically and/or manually created tasks are
selected, and the Reassign Selected button is clicked, then the Assign
Task dialog will display. The \'Assign To\' dropdown can be used to
select a user, and the \'Priority\' dropdown can be used to assign a
different priority (if necessary).

In the example below, user \'Jane Doe,\' and priority \'High\' are
selected.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Assign%20Task%20Dialog.png)

Clicking the Cancel button (or the white \'X\' in the top right of the
dialog) will close the dialog and return the user to the previous page.

Clicking the Save button will close the dialog, and a green \'Reassign
successful\' confirmation dialog will display as shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Reassign%20Successful%20Green%20Dialog.png)

1.  **Advanced Mode:** Clicking the Advanced Mode button will allow for
    one or more potential duplicates to be merged using the Advanced
    Merge functions. Advanced Mode does not automatically determine a
    master record, but rather allows users to pick and choose details
    within different records to be part of the master record.

Manually created tasks can only be merged or rejected using the Advanced
Mode button.

Each Clerical Review task has its own Advanced Merge button, and
clicking the Select All or Select Task checkboxes has no impact on the
Advanced Mode button. Once the Advanced Mode button is clicked, then the
Advanced Merge dialog will display each of the potential duplicate
records side by side, along with the final results displayed within a
PREVIEW COLUMN (as shown below). From here, users can select the record
to be used as the master by enabling the radio button for the \'Master
Record\' row.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/ClericalReviewAdvancedMode.png)

The radio buttons and checkboxes can be used to select the appropriate
data to be merged into the master record. Once the desired data is
selected, clicking the Merge Selected button will result in the display
of a Confirm Merge dialog (as shown below).

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Merge%20Selected%20Confirm%20Merge%20dialog.png)

Clicking the Cancel button will close the dialog and return the user to
the previous page.

Clicking the Confirm button will close the dialog, and a green
\'Operation successful\' confirmation dialog will display as shown
below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Confirm%20Operation%20Successful.png)

Optionally, the \'here\' link can be clicked to review the merge record
results.

Manual Merge Requests
---------------------

The Manual Merge Request page allows users to perform a search, add one
or more results to a set of potential duplicates, then create another
search for other records, and add all or some of the search results to
the same set of potential duplicates. This can be repeated, and then the
user can save the list, which will create a clerical review task. Users
can search for Business Accounts, Person Accounts, or Contacts.

To access the Manual Merge Request page, go to the Stibo SDQ Landing
Page and beneath the MASTER DATA MANAGEMENT section, click the Manual
Merge Requests menu option. The page will display as shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Manual%20Merge%20Requests/Manual%20merge%20Requests%20Blank.png)

The \'Search\' field can be used to type in search criteria for Business
Accounts, Person Accounts, or Contacts. After typing in the desired
search criteria, the user can press the Enter key on their keyboard to
start the search. By default, the Business Accounts option is selected.
If any duplicates are found, they will display within the Accounts
section of the Business Accounts tab. Selecting the Person Accounts tab
will display the Person Accounts section, and if any duplicates are
found, they will be displayed without having to press the Enter key
again. The same is true for selecting the Contacts tab.

In the example below, \'stibo\' has been typed into the Search field,
the Enter key has been pressed, and the Business Accounts matching the
entry are displayed.

![](../../../../../Resources/Images/CMDM/User%20Guide/Manual%20Merge%20Requests/stibo%20search%20results.png)

Clicking the **Mark as Duplicate checkbox** within the ACTIONS column
will display the record within the Duplicate Accounts section.

In the example below, the first record in the Accounts section has been
marked as a duplicate, and displays within the Duplicate Accounts
section, along with the **Clear List** and **Save Duplicate Records**
buttons.

![](../../../../../Resources/Images/CMDM/User%20Guide/Manual%20Merge%20Requests/Mark%20as%20Duplicate%20Enabled.png)

Optionally, the search criteria can be cleared, new search criteria
typed into the search field, and the Enter key pressed, resulting in the
new search criteria displaying within the Accounts section. Enabling one
or more Mark as Duplicate checkboxes, will add records to those already
listed in the Duplicate Accounts section. This can be done as many times
as necessary to get the desired records to display within the Duplicate
Accounts section.

In the example below, \'stibo\' text was removed from the Search field,
a portion of the phone number was typed in, the Enter key was pressed,
resulting in the display of a record in the Accounts section.

![](../../../../../Resources/Images/CMDM/User%20Guide/Manual%20Merge%20Requests/Partial%20phone%20search.png)

Clicking the **Clear List** button will remove all the records listed
within the Duplicate Accounts. Also, disabling the Mark as Duplicate
checkbox for a record will remove it from the Duplicate Accounts
section. When the Clear List button is clicked, a confirmation dialog
will display as shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Manual%20Merge%20Requests/Clear%20List%20Confirm%20Dialog.png)

Clicking the **Save Duplicate Records** button will display the Assign
Task dialog, as shown below. This dialog can be used to assign the task
to a user and set priority for the manually created task.

In the example below, user \'Jane Doe,\' and priority \'High\' are
selected.

![](../../../../../Resources/Images/CMDM/User%20Guide/Clerical%20Review/Assign%20Task%20Dialog.png)

Clicking the **Save** button, will allow for the manually created task
to be visible within the Clerical Review Task list.

If only one record is added to the Duplicate Accounts section, and the
Save Duplicate Records button is clicked, then a warning dialog will
display prompting users to add at least 2 records to the Duplicate
Accounts section.

![](../../../../../Resources/Images/CMDM/User%20Guide/Manual%20Merge%20Requests/Warning%20At%20least%202%20records.png)
