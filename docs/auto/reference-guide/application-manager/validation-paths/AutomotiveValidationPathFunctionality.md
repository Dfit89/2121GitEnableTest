---
description: 'Automotive Solution: Describes Automotive Validation Path
  functionality and how it is used for Search Box Criteria, Options on
  Applications, Missing Applications, Advanced Filtering, and Workbench
  Configurations. '
title: '\[%=Heading.AnyLevel%\]'
---

Automotive Validation Path Functionality
========================================

Having the optional automotive validation path functionality in place
ensures Application Manager users are able to select valid
configurations when selecting criteria for their search, applicating
parts to vehicles, adding / editing options for applications, and
maintaining missing applications. The premise behind the concept is that
when some level of \'valid configuration\' data for vehicles is
provided, the Application Manager is able to intelligently decipher
those.

Data for an automotive validation path is represented in STEP via a
series of objects, references, and attributes. The values for those
attributes and references are stored on the Vehicle Configuration
objects, and the Application to Base Vehicle reference is applied to the
individual application. Regardless of the model / standard you are
working in, the system always evaluates the automotive validation path
by beginning with the Base Vehicle / assembly object used in application
records.

For example, for the Fuel Type attribute (AC\_ACESFuelType), the
validation path is configured as:

    child.reference[type:'AC_VehicleToEngineConfig'].attribute[id:'AC_VCdbFuelType']

This automotive validation path is determined by:

1.  Identifying the application and following the ACES Application To
    Base Vehicle reference (AC\_ACESApplicationToBaseVehicle) to the
    Base Vehicle object type (AC\_BaseVehicle).
2.  Examining all vehicle children (AC Vehicle) of the Base Vehicle.
3.  Following the Vehicle To Engine Config reference
    (AC\_VehicleToEngineConfig) on the vehicle to the target object.
4.  Evaluating the value of the VCdb Fuel Type attribute
    (AC\_VCdbFuelType) that is stored on the Engine Config object
    (AC\_EngineConfig).

After running Easy Setup, the application data model (Automotive -
Application Model) includes configuration for object types and link
types that define the relationship between different configurations of
vehicles and conditions on applications. This relationship data is
captured within the Automotive Validation Path attribute.

Within the AutoCare model, the validation path attribute is populated on
some standard ACES vehicle options during Easy Setup when the attribute
and/or reference modeling option is first created. This allows many
features (including validation error handling) to be available within
the Application Manager intelligent search interface, and results table
value editor. Details on these features can be found within the
**Intelligent Search Interface** ([here]{.mcFormatColor
style="color: Blue;"}) and **Results Table and Toolbar**
([here]{.mcFormatColor style="color: Blue;"}) topics within this guide.

This section addresses:

-   **Validation Path Functionality and Search Box Criteria**
    ([here]{.mcFormatColor style="color: Blue;"})
-   **Validation Path Functionality and Options on Applications**
    ([here]{.mcFormatColor style="color: Blue;"})
-   **Validation Path Functionality and Missing Applications**
    ([here]{.mcFormatColor style="color: Blue;"})
-   **Validation Path Functionality and Advanced Filtering**
    ([here]{.mcFormatColor style="color: Blue;"})
-   **Workbench Configurations Related to Validation Path**
    ([here]{.mcFormatColor style="color: Blue;"})
