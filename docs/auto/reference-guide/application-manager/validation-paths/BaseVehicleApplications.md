---
description: 'Automotive Solution: Describes how Base Vehicle
  applications are stored within Workbench.'
title: '\[%=Heading.AnyLevel%\]'
---

Base Vehicle Applications
=========================

Part application data is not applied to Vehicle object types (i.e.,
**1996 Dodge Viper, GTS, United States**) but rather to Base Vehicle
object types (i.e., **1996 Dodge Viper**). Thus, an application is
applied to the parent of the Vehicle object type.

In the example below, the **1996 Dodge Viper** Base Vehicle object type
is displayed along with its four children vehicle object types

![](../../../Resources/Images/1996DodgeViperBaseVehicle.png)

In order to know all valid body style configurations for a Base Vehicle
object type, all child vehicles (the \'Base\' and \'GTS\' vehicles for
the United States and Canada) must first be evaluated. In doing this, it
can be seen that the 1996 Dodge Viper Base Canada and United States
models have a **2 door, Convertible** body style (as shown below)
whereas the 1996 Dodge Viper GTS Canada and United States models have
the **2 door, Coupe** body style (as previously mentioned).

![](../../../Resources/Images/QS/1996DodgeViperBase.png)

Therefore the **1996 Dodge Viper Base Vehicle** object type has two
valid body style configurations; both have only 2 doors, but the body
type can be either Coupe or Convertible. If a user tries to provide an
application for the vehicle that specifies \'4\' doors or a \'Sport
Utility\' Vehicle body style, it would be allowed, but also invalid.
