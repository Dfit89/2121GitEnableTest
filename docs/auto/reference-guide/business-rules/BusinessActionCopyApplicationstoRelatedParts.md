---
description: 'Automotive Solution: Describes the Copy Application to
  Related Parts Business Action.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Action: Copy Applications to Related Parts
===================================================

This automotive business action allows users to copy one or more
existing applications to one or more related parts by clicking a Bulk
Updates action button within an Application Manager. However, it cannot
copy the part of a missing application, and thus any missing
applications selected when the bulk update is run will be ignored. For
more information, see the **Missing Application Coverage Functionality**
topic ([here]{.mcFormatColor style="color: Blue;"}) within this guide.
Setup is required within both STEP Workbench and Web UI for the action
to be available to users.

Once configured, a Bulk Updates button within an Application Manager can
be used to copy one or more existing applications to one or more related
parts based upon the population of the Part Relation reference type. To
understand the results of the business action, it is important to
understand a Part Relation reference type configuration. This section
will first review a Part Relation reference type configuration, and then
provide the steps for using the business action in Web UI.

### Part Relation Reference Type Configuration

When the Copy applications to related parts business action is applied
within a Web UI, the selected application will be copied to the part(s)
that have the selected application\'s part listed within the reference
type \'Part Relation.\' In other words, the business action will create
applications for any parts that have a relationship with the part used
within the selected application.

For example, when using the References tab in workbench to view part
VC21499 and VC36009, the Part Relation Reference Type can be viewed as
\'VC36112.\'

![](../../Resources/Images/BRs/Copy%20Application%20to%20Related/WBVC21499.png)

With the above configuration in place, the Application Manager can be
used to select an application using part VC36112, and when the Bulk
Updates action button is clicked, applications will be created for the
parts VC21499 and VC36009 (as shown below).

### Steps for Using the Business Action in Web UI

When the Parts Relation Reference Type is populated as shown above, the
steps below can be used to copy an application to related parts using
the Web UI.

![](../../Resources/Images/BRs/Copy%20Application%20to%20Related/WUI.png)

If only one bulk update is configured, then the Bulk Applications
Updates dialog will not display.

1.  Within the configured Application Manager, search for the
    applications to be copied. Select one or more applications with a
    part that uses the Part Relation reference type. For this example,
    part number VC36112 is used.
2.  Click the **Bulk Updates** action button. If more than one bulk
    update is configured then the Bulk Updates dialog will display (as
    shown above), otherwise this dialog is skipped and the copy
    applications to related parts bulk update background process will
    run (skip to step 5 below).
3.  Select the Copy Application To Related Parts radio button from the
    list displayed within the Bulk Applications Updates dialog. For this
    example, \'Copy Application to Related Parts\' is used, but the
    business action name displayed within the list is dependent upon the
    business action\'s Name parameter.

```{=html}
<!-- -->
```
1.  Click the **OK** button and the copy applications to related parts
    business action will run for the selected applications.
2.  Once the background process has completed, click the **Find
    applications** button to display the newly created application(s)
    within the Application Manager results table. For this example,
    notice that two new applications for the related parts have been
    created (as shown below).

![](../../Resources/Images/BRs/Copy%20Application%20to%20Related/3.png)

-   Configuring the Copy Applications to Related Parts Business Action
    in Workbench ([here]{.mcFormatColor style="color: Blue;"})
-   Configuring the Copy Applications to Related Parts Business Action
    in Web UI ([here]{.mcFormatColor style="color: Blue;"})
