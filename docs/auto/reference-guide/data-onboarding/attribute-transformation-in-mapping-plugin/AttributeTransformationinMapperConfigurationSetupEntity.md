---
description: 'Automotive Solution: Attribute transformations within the
  Onboarding process can be used to transform attribute values, names,
  and IDs of the Target object after Onboarding.'
title: '\[%=Heading.AnyLevel%\]'
---

Attribute Transformation in Mapper Configuration Setup Entity
=============================================================

Attribute transformations within the onboarding process can be used to
transform attribute values, names, and IDs of the target object while
onboarding data from the source object to the target object. When the
Mapping plugin is defined with the source and the target attributes,
users can add an attribute transformation if necessary. As with all
transformations, the source object data is not modified, but the target
object data is altered by the transformations applied. Attribute
transformation can be used to make a set of transformations, and then
apply it in the Mapper rows of the Mapping plugins. Attribute
transformations can be applied only in the following Mapping plugins:

-   Application Mapping plugin
-   Attribute Mapping plugin
-   Concatenator Mapping
-   Object to Object Mapping plugin

Apart from being used in the Mapping plugins, the attribute
transformations can be also applied while defining the ID and name for
the target object hierarchy that are created through the Target
Hierarchy field in the Setup tab of the Onboarding Mappings Details
screen.

Users can perform the following functions with regards to the attribute
transformations in the Target Hierarchy Editor window and the Mapping
Guide window:

-   Create a new attribute transformation and define transformation
    function(s) ([here]{.mcFormatColor style="color: Blue;"})
-   Add, edit, delete, or rearrange the listing order of the
    transformations for an attribute transformation
    ([here]{.mcFormatColor style="color: Blue;"})
-   Test the outcome of the added transformation ([here]{.mcFormatColor
    style="color: Blue;"})

The modifications made to the attribute transformations by accessing it
through the Mapping Guide window / Target Hierarchy Editor window is
global and affects the attribute transformations residing in System
Setup. Meaning, changes made through the Mapping Guide window will have
an impact on every place in the system where the changed attribute
transformation is applied / used on. Before editing any of the existing
attribute transformations, its effect on other places it is being used
must be properly assessed.

This topic explains how to access and create / edit attribute
transformations in Mapper Configuration setup entity. For information on
how to create and configure an attribute transformation in workbench,
see the **Attribute Transformations** section of the **System Setup /
Super User Guide** documentation of **STEP Online Help**[
here]{.mcFormatColor style="color: Blue;"}.
