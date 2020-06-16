---
description: 'PLM Solution: The Change Report Snapshot has been
  configured on an Evaluate Supplier Responses and Supplier Responses
  screens.'
title: '\[%=Heading.Level1%\]'
---

Web UI Configurations
=====================

The Change Report Snapshot has been configured on an Evaluate Supplier
Responses and Supplier Responses screens.

To enable the Change Report functionality in the Web UI, the Product
Summary Card is required. It is an out-of-the-box component that can be
configured to show either a preselected grouping of product information
or a series of data points configured by the user.

Product Summary Card Component in Private Label Food screens
------------------------------------------------------------

The Product Summary Card provides users a collection of product
information display just below the screen title.

Private Label Food and Private Label Food Supplier Web UIs are both
configured with the Product Summary Card component. It is a very helpful
functionality to end-users since in the private label food solution
different objects are used in a project, so different groups of
information can be displayed based on the object in use, user role, and
process state (task).

The following are examples of Primary Summary Card configurations in
Private Label Food Solution.

### Supplier Recipe Response

![](../../../Resources/Images/Solution%20Enablement/PLM/WebUI1.png)

### Supplier Label Response

![](../../../Resources/Images/Solution%20Enablement/PLM/WebUI2.png)

### Supplier Packaging Response

![](../../../Resources/Images/Solution%20Enablement/PLM/WebUI3.png)

The Change Report component requires a license and is enabled in the
Secondary Summary Card Section. Change Report component needs to be
selected in the Secondary Summary Card and a Snapshot configuration
specified.

![](../../../Resources/Images/Solution%20Enablement/PLM/webUI4.png)

The Secondary Summary Card section has been configured with parameters:

-   Show Change Report: Checkbox enabled to display the Change Report
    button to the right of the Product Summary.
-   Snapshot Configuration: (Snapshot configuration to be used). A
    parameter will be added to allow searching for a Snapshot
    Configuration. No other object types will be allowed.
-   The Snapshot Configuration is used for the entire Web UI screen. It
    determines the contexts to capture data from and a customer-defined
    Event ID (e.g., supplier response or internal review) to identify
    the snapshot.
-   Snapshot recorders can be created for each Web UI or for processing
    logic, workflow. They can be configured according to each customer
    requirements.
-   On each snapshot recorder, on the Product to Classification Link
    Type \'SnapshotRecorder,\' there are metadata attributes maintained.
    These determine factors about the Change Report so that each time
    the snapshot recorder is re-used, the information can be different.

For more information on attributes needed for snapshot recorders and
Change Reports see the **Objects, References, and Attributes for Change
Reports** topic in the **Change Reports** segment of the **PLM for
Admins** section of the **Product Lifecycle Management** documentation[
here]{.mcFormatColor style="color: Blue;"}.
