---
description: 'Automotive Solution: Describes how to easily add new
  application records to a selected part in Web UI.'
title: '\[%=Heading.AnyLevel%\]'
---

Adding New Applications Manually
================================

Users can easily add part applications to a selected part within Web UI.
When the Part Application Editor component is configured and a part is
selected, STEP displays the existing application records and its
attribute values based on the configurations made within the \'Part
Application Editor\' Node Editor component. Whether or not the
application records are displayed, at a minimum a \'Create\' button will
display. This \'Create\' button can be used to manually add a new
application record to the selected part.

In the example below, part VC36115 is selected within the Web UI Tree,
and an \'Application Suggestions\' tab is configured to display existing
applications. Within the results, two applications are displayed along
with the \'Create\' button that allows users to create new application
records.

![](../../Resources/Images/Application%20Suggestions/1.png)

When a user clicks on the \'Create\' button, a Create Application dialog
displays prompting users to select the vehicles / assemblies. Once the
vehicle / assembly name (or ID) is typed in the typeahead field,
available list of vehicles / assemblies will display in the dropdown
list. Alternatively, the user can select the Node Picker icon available
in the right of the typeahead field to select the vehicles / assemblies.
Selecting a listed base vehicle will add the application to the existing
applications list. The user can select multiple vehicles / assemblies in
the dialog to create more than one application records simultaneously.

Following are the IDs of vehicles / assemblies that are valid to be
selected across different standards.

-   AutoCare: AC\_BaseVehicle
-   NAPA: NAPA\_Year
-   TecDoc: TD\_VehicleType(PC) / TD\_VehicleType(CV) / TD\_EngineCode

In the example below, \'2013\' is typed into the typeahead field and the
application records that begin with 2013 are displayed within the
dropdown list.

![](../../Resources/Images/Application%20Suggestions/2.png)

Selecting 2013 Acura ILX and clicking on **OK** adds a new application
record to the existing list of applications, as shown below.

![](../../Resources/Images/Application%20Suggestions/3.png)

If there is an Application Suggestions component configured below the
existing applications list, then the suggestions list too is updated as
new application records are added to the existing applications list.
