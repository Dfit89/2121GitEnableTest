---
description: 'Automotive Solution: Describes Automotive Validation Path
  functionality and how it is used for Search Box Criteria, Options on
  Applications, Missing Applications, Advanced Filtering, and Workbench
  Configurations. '
title: '\[%=Heading.AnyLevel%\]'
---

Mapping Validation Path Functionality
=====================================

The Mapping Validation Path functionality in the STEP Path Editor dialog
ensures that users are able to select valid Source and Target objects to
define their mapping setup in Object to Object Mapping or Application
Mapping configurations. The premise behind this concept is that when
some level of valid Source STEP Path data (or valid Target STEP Path
data) for objects is provided, the mapping is able to retrieve the ID /
Name / attribute values / references of the object present at the
defined path.

Data for an automotive validation path is represented in STEP via a
series of objects, references, and attributes. The values for those
attributes and references are stored on the Vehicle Configuration
objects, and the Application to Base Vehicle reference is applied to the
individual application. Based on the Source and the Target object type
defined for the Mapper Configuration, the system always evaluates the
Source STEP path (or Target STEP path) and suggests the valid attributes
/ reference types / object types from the system.PRODOC note: add
something to define the Starting Points parameter that displays the
object type that the Validation Path will begin evaluation on in order
to follow the path to retrieve information from.

The Starting Points parameter available in the STEP Path Editor dialog
displays the object type that the Validation Path will begin evaluation
on in order to follow the path to retrieve information from.

This relationship data is captured within the Validation Path field
based on the data model setup that defines the relationship between
different object types.

Each of the elements available within the Keywords field in the STEP
Path Editor dialog is explained in detail below. Note that all elements
are not necessarily used in all requirements. The specific combinations
of elements are chosen depending on how the data needs to be retrieved
from the Source object. PRODOC note: replace the below screenshot with
the latest screenshot available in 9.2MP1 notes. At this hour of
documentation, My flare is neither possible to commit or make changes.

![](../../Resources/Images/Data%20Onboarding/55.png)

-   **attribute\[id:\'\[id\]\'\]**: This element defines the valid
    attribute where a value may be retrieved from the Source object.
    Further configuration is required to define the attribute. Once the
    attribute\[id:\'\[id\]\'\] keyword has been selected, double-click
    on the Validation Path field to select an attribute (only attributes
    valid to the Source object type are displayed) from the Select
    Attribute dialog.

```{=html}
<!-- -->
```
-   **child\[objecttype:\'\[id\]\'\]**: This element allows the user to
    retrieve the data from the child of the object that is displayed in
    the Starting Points parameter. Further configuration is required to
    define the object type and also what value of the child object (ID /
    Name / attribute value /references) is to be retrieved. This element
    should always be accompanied by some of these **id** / **name** /
    **attribute\[id:\'\[id\]\'\]** / **reference\[type:\'\[id\]\'\]**
    elements.
-   **id**: This element retrieves the ID of the defined object.
-   **name** : This element retrieves the name of the defined object.
-   **parent**: This element retrieves the data from the parent of the
    defined object. Further configuration is required to define what
    value of the parent object (ID / Name / attribute value /references)
    is to be retrieved. This element can always be accompanied by **id**
    / **name** / **attribute\[id:\'\[id\]\'\]** /
    **reference\[type:\'\[id\]\'\]** elements.
-   **reference\[type:\'\[id\]\'\]**: This element retrieves the data
    from the referenced object of the defined object. Further
    configuration is required to define the reference type and is also
    required to define what value of the referenced object (ID / Name /
    attribute value /references) is to be retrieved. This element can
    always be accompanied by **id** / **name** /
    **attribute\[id:\'\[id\]\'\]** / **reference\[type:\'\[id\]\'\]**
    elements.
-   **referenceBy\[type:\'\[id\]\'\]**: This element retrieves the data
    from the source object when the defined object is the target object
    of the configured reference. Further configuration is required to
    define the reference type and is also required to define what value
    of the source object (ID / Name / attribute value /references) is to
    be retrieved. This element can always be accompanied by **id** /
    **name** / **attribute\[id:\'\[id\]\'\]** /
    **reference\[type:\'\[id\]\'\]** elements.
-   **text\[\'\[text\]\'\]**: This element lets the user enter a static
    text of the user\'s choice.

For example, for the ACES Body Num Doors attribute
(AC\_ACESBodyNumDoors) stored at the child of the Source object (PIES
Item), the Source STEP path is configured as:

``` {space="preserve"}
child[objecttype:'AC_ACESApplication'].attribute[id:'AC_ACESBodyNumDoors']
```

This Source STEP Path is determined by:

1.  Identifying the source object.
2.  Examining all children with object type AC\_ACESApplication of the
    source object.
3.  Evaluating the value of the ACES Body Num Doors attribute
    (AC\_ACESBodyNumDoors) that is stored on the child object.
