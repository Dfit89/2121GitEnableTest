---
description: 'Stibo SDQ Admin Guide: This appendix topic shows how to
  set up Email notifications for reporting errors in Stibo SDQ.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring Email Notifications
===============================

Salesforce Administrators may configure notifications to be emailed to
their account when an error is triggered. To configure these
notifications:

1.  Create an Email Template
2.  Create an Email Alert
3.  Create the Process that uses the Email Alert

Create an Email Template
------------------------

1.  Open Setup \> Email Templates
2.  On the Email Templates page, select \'New Template.\'

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/EmailTemplatesNew.png)

1.  Select \'Custom (without using Letterhead)\' and click Next.

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/CustomTemplateCreate.png)

1.  Enter an Email template name, check the \'Available for Use\'
    checkbox, and then select Next.

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/NameEmailTemplate.png)

1.  On the \'Create HTML version\' step of the process, enter a Subject
    for the email template as well as the following two parameters:

-   {!stibo\_dq \_\_ErrorLog\_\_c.stibo\_dq \_\_Severity\_\_c}

-   {!stibo\_dq \_\_ErrorLog\_\_c.stibo\_dq \_\_Message\_\_c}

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/BuiltHTMLTemplate.png)

6.  Click Next, and then on the \'Create text-only version step,\'
    select Save.

Create an Email Alert
---------------------

1.  Navigate to Setup \> **Email Alerts**, and create a New Email Alert.

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/CreateNewEmailAlert.png)

1.  Configure the Email Alert. Provide a description (1), and ensure
    that the Object type is an Error Log(2). Select the email template
    that was created above(3). Select the desired Salesforce users, and
    click Add (4). Up to 5 addresses can be added to this box (5).
    Select Save to save the email alert(6).

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/EmailAlert.png)

Create the Process that Uses the Email Alert
--------------------------------------------

Navigate to Setup \> Process Builder, and click \'New\' on the right
side of the \'My Processes\' page.

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/MyProcessPage.png)

A \'New Process\' dialog will display. Name the process and API name
(1). Then, on the \'The process starts when\' dropdown, select **A
record changes** (2). Finally, select \'Save\' (3).

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/NewProcessCallOut.png)

From the process builder diagram, select \'+Add Object.\'

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/DiagramStep1.png)

On the \'Choose Object and Specify When to Start the Process\' panel,
select **ErrorLog** for \'Object\' and **only when a record is created**
for the \'Start the Process\' option. Select \'Save.\'

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/ChooseObjectAndStartTime.png)

From the diagram, select \'+ Add Criteria\' (2).

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/DiagramStep2.png)

Add the Criteria name (1), and you may receive notifications for errors
with a specific severity. To add that, select \'Find a field\...\' on
the \'Field\' option of the Set Conditions section (2).

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/AddCriteria.png)

On the \'Select a Field\' panel, select \'Severity\' then click
\'Choose.\'

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/SelectaFieldSeverity.png)

From the \'Value\' field of the \'Set Conditions\' section, select the
desired severity to receive notifications.

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/SetCriticalValue.png)

Select **Save** to keep these settings.

On the immediate actions step (3), select \'+ Add Action.\'

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Stibo%20SDQ/DiagramStep3.png)

Define the action type as follows:

-   Action Type - Email Alerts (with a name)
-   Email Alert - Search for the previously created email alert.

Select the **Save** button.

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/DefineActions.png)

Then, select the \'Activate\' button on the top right of the Process
Builder.

![](../../../../../Resources/Images/CMDM/AdminGuide/Appendix/ActivateProcess.png)
