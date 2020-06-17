---
description: 'Automotive Solution: '
title: '\[%=Heading.AnyLevel%\]'
---

Data Onboarding
===============

PRODOC note: MEDU PDO-1464

PRODOC note: MEDU RDCUST- 2976 As an admin user I want to be able to go
to a screen to setup the configuration of the onboarding. In this screen
it will be possible to see the already existing mappings / plugins and
what they contains. It should also be possible to choose to create a new
plugin from this screen.

This is also where I, as an admin user, will define my global
configuration for the onboarding of this particular format (f.ex TecDoc
-\> Own Model). The minimum configuration required is an object source
and an object target with a reference. design
https://app.zeplin.io/project/584e71ddd996399118a1dfb7/dashboard?seid=5b83d28b654881b2d05064a1

PRODOC note: MEDU 9/11/2018 Sprint Demo CVWI Phase I (no UX yet). 3
Plugins Application Plugin, Attribute Mapping Plugin, Object to Object
Mapping. You can move TecDoc Text block and move it to other objects of
TD. You can map any application (ie, Own, TD, AC, NAPA) to any other
application (ie, Own, TD, AC, NAPA).

Within the automotive industry, it is often difficult to organize
supplier and/or competitor data across different automotive industry
standards and data models. The Data Onboarding solution helps to provide
tools for suppliers and retailers to be able to map data from one
industry standard to another, or to and from your own data model. This
is done be setting up mapping configurations to onboard or outboard
objects from one standard to another standard as defined by the user.

The mapping functionality can copy and/or transform data from one STEP
object to another STEP object. The data can be as simple as copying
attribute values, or as complex as retrieving data from the source
object to create an entirely new product or classification hierarchy.

The actual data mapping is executed via Business Rules and/or Background
processes inside a workflow or upon approvals. After initial
configuration, Web UI users can view, edit, and create Mapper
Configuration setup entities and Mapper plugins to better handle the
automation of data onboarding.

The Data Onboarding solution is used within an Onboarding Mappings
Detail Screen.

This section addresses

-   Prerequisites
-   Configuring Data Onboarding solution[ here]{.mcFormatColor
    style="color: Blue;"}
-   Configuring Web UI for Data Onboarding solution[
    here]{.mcFormatColor style="color: Blue;"}
-   Executing Mapper Configuration setup entity[ here]{.mcFormatColor
    style="color: Blue;"}
-   Mapping plugins[ here]{.mcFormatColor style="color: Blue;"}
-   Mapping plugins use case overview [ here]{.mcFormatColor
    style="color: Blue;"}

Prerequisites

Prior to implementing the Data Onboarding Automation solution, the
following items included in the list below should be carefully
considered when planning the data onboarding solution.

-   Source Object Type
-   Target Object Type
-   Reference Type

Validation types for the different object types being used must be
carefully considered prior to implementing this solution. For example,
\...
