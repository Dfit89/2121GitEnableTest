---
description: 'Automotive Solution: Describes how options on applications
  are stored within Workbench in relation to the Automotive Validation
  Paths concept.'
title: '\[%=Heading.AnyLevel%\]'
---

Options on Applications
=======================

On an application, an attribute or reference exists to model each data
point in a valid configuration. For the **Vehicle To Body Style Config**
reference type an attribute for **Body Num Doors** and **Body Type**
exists (similar to the configuration classification object shown above).

In the workbench example below, the dropdown for the **Body Type**
attribute displays all the available body types that can be chosen for
the selected application.

![](../../../Resources/Images/QS/BodyTypeOptions.png)

Though the workbench could be used to select any one of the available
options, this would be done without the safeguarding of the intelligent
automotive validation path functionality, and therefore is not
recommended. Applications are not intended to be created nor edited in
the workbench. Instead, a robust results table and value editor are
provided within an Application Manager Web UI screen.

Within a Web UI Value editor, users can view and select only the valid
options for the vehicle they are working with. In the example below, the
Application Manager results table \'Value editor\' is displayed for the
**1996 Dodge** **Viper** Base Vehicle, and only the **Convertible** and
**Coupe** options display for selection in the dropdown.

![](../../../Resources/Images/QS/DodgeViperBodyTypeWebUI.png)

When an application is created, validation paths are available for
conditions / options stored as either attributes or references. However,
each has its own configuration, as described below.

Options / Conditions Stored as Attributes
-----------------------------------------

When the data model uses an attribute to store the vehicle option /
criteria, the automotive validation path data is managed as described
below.

Easy Setup creates an Automotive Validation Path attribute
(AutomotiveValidationPath). This attribute is made valid as metadata on
the attribute basic object type, making it available for population on
any attribute.

![](../../../Resources/Images/QS/AttValidationPath.png)

Regardless of the model / standard you are working in, the system always
evaluates the automotive validation path by beginning with the Base
Vehicle / assembly object used in application records.

In the example above, the automotive validation path data within the
data model is determined by:

1.  Identifying the application and following the ACES Application To
    Base Vehicle reference (AC\_ACESApplicationToBaseVehicle) to the
    Base Vehicle.
2.  Examining all vehicle children of the Base Vehicle.
3.  Following the Vehicle To Body Style Config
    (AC\_VehicleToBodyStyleConfig) reference on the vehicle to the Body
    Style Config target object.
4.  Evaluating the value of the VCdb Body Num Doors attribute
    (AC\_VCdbBodyNumDoors) on that target object.

Syntax

The syntax of the automotive validation path is a series of commands,
each separated by a period (.). Using the child, reference, ID (shown
below), and attribute elements (including IDs of the applicable
references and attributes to be followed), an automotive validation path
can be applied to any attribute for which the data is modeled in STEP.
When the vehicle option is modeled using an attribute, the final element
of the syntax should always be an attribute where the value should be
retrieved.

Options / Conditions Stored as References
-----------------------------------------

When the data model uses a reference to store the vehicle option /
criteria, the automotive validation path data is managed as described
below.

The Automotive Validation Path attribute described in the previous
section is still relevant. When created by Easy Setup, the attribute is
made valid on the Reference Type basic object type (in addition to the
attribute basic object type). Thus, the Automotive Validation Path
attribute can then be populated on any reference.

![](../../../Resources/Images/QS/ReferenceValidationPath.png)

In the example above, the automotive validation path data within the
data model is determined by:

1.  Identifying the application and following the ACES Application To
    Base Vehicle reference (AC\_ACESApplicationToBaseVehicle) to the
    Base Vehicle.
2.  Examining all vehicle children of the Base Vehicle.
3.  Following the Vehicle To Engine Config reference
    (AC\_VehicleToEngineConfig) on the vehicle to the Engine Config
    target object.
4.  Following the Engine Config To Engine Base reference
    (AC\_EngineConfigToEngineBase) from the Engine Config Object (which
    are now considered sources of the Engine Config To Engine Base
    reference) to the Engine Base target object.
5.  Retrieving the STEP Name of the Engine Base object to be displayed
    in Application Manager.

Syntax

The syntax of the automotive validation path is a series of commands,
each separated by a period (.). Using the child, reference, ID, and
attribute elements (including IDs of the applicable references and
attributes to be followed), an automotive validation path can be applied
to any reference for which the data is modeled in STEP. When the vehicle
option is modeled using a reference, the final element of the syntax
should always be an ID of the reference where the STEP Name should be
displayed.
