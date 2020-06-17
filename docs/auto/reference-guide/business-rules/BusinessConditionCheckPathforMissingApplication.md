---
description: 'Automotive Solution: Describes how to use the Check Path
  for Missing Application Business Condition.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Condition: Check Path for Missing Application
======================================================

PRODOC note: MEDU RDUCST-2713, 2733,2732 calculates validation path and
check if one of the values is present in result. Easy Setup Creates the
plugin, but it does not set it up. For AutoCare the Validation Path
Attribute is populated by Easy Setup but TD and NAPA are not. See Word
Doc in 2732 for setup

This business condition improves the accuracy of search results
involving specific part types by allowing the data model to include a
relationship between conditions on applications and different vehicle
configurations. This can be helpful when specific part types do not
apply to certain vehicle configurations. Additionally, it allows the Web
UI Application Manager to search for applications with conditions for
all sub models.

Prerequisites

Prerequisites {#prerequisites conditions="Primary.Web"}
-------------

Easy Setup actions automatically create the Missing Application
Conditions attribute (MissingApplicationConditions) and the \'Check path
for missing application\' plugin; however, configuration is required
prior to use.

When Easy Setup actions are used to create the Missing Application
Conditions attribute (MissingApplicationConditions), the attribute is
also made valid for NAPA MPCC, Part Terminology, and Standard Assembly
GA object types. This validity must be applied manually if the attribute
was created manually.

When Easy Setup actions are completed, the \'Check path for missing
applications\' plugin is created. However, the business condition must
be made valid for the necessary object types.

Improving Search Result Accuracy
--------------------------------

When an Application Manager is used to search for existing and missing
applications for a specific part type, it is possible to get results
that are not accurate based upon the relationship between the vehicle
configuration and options for a part.

![](../../Resources/Images/BRs/AM%20spark%20plug.png)

Once the application coverage is configured to consider the Condition
and Part Type values, then searches like the 2013 Audi A3 example above
will no longer include the DIESEL vehicle configuration results.

Additional examples for part types that can have the Missing Application
Conditions applied are for Coils or Ignition Module part types that are
only valid for **Gas** Fuel Type but not valid for Diesel. Or for Part
Types that are valid for **Gas** Fuel Type but not valid for Electric
vehicles such as Oxygen Sensors, Catalytic Converters, and Mufflers.
While Glow Plug part type is valid only for **Diesel** Fuel Type but not
for Gas or Electric.

For more information, see the **Missing Application Coverage
Functionality** topic within this guide[ here]{.mcFormatColor
style="color: Blue;"}.

For configuration instructions, see the **Configuring the Check Path for
Missing Application in Workbench** topic of this guide[
here]{.mcFormatColor style="color: Blue;"}.
