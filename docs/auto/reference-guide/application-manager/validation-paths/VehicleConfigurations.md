---
description: 'Automotive Solution: Describes how Vehicle Configurations
  are stored within Workbench in relation to the automotive validation
  path functionality.'
title: '\[%=Heading.AnyLevel%\]'
---

Vehicle Configurations
======================

Options for different vehicle configurations are stored within STEP as
attributes on a classification object type. Classification object types
are referenced by Vehicles that are children of the Base Vehicle object
type.

In the example below, the **VCdb Body Num Doors**, and **VCdb Body
Type** AutoCare options are modeled as attributes within the **Body
Style Config** classification object type. The valid configuration for
the \'2 door, Coupe\' consists of \'2\' doors and a \'Coupe\' body type.

![](../../../Resources/Images/QS/BodyStyleConfig.png)

All 2 door coupe vehicles reference the **2 door, Coupe** body style
using the **Vehicle To Body Style Config** Reference Type. A vehicle can
have more than one \'Vehicle To Body Style Config\' reference and if so,
it will display as multiple references on the vehicle (as shown below).

![](../../../Resources/Images/QS/BodyStyleConfigRefs.png)

In the example below, the **1996 Dodge Viper GTS, United States** has
only one valid **Vehicle To Body Style Config** reference target, the
**2 door, Coupe**.

![](../../../Resources/Images/QS/1996DodgeViperRefs.png)

Since only one valid body style exists for this vehicle, it would be
invalid for an application to be supplied for the vehicle where any
other body style was implied. Additionally, within the Application
Manager, it is not possible for a user to select a value other than 2
for the Body Num Doors value, or Coupe for the Body Type value.
