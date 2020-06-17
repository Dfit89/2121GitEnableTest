---
description: 'Automotive Solution: Describes how to configure a
  Hierarchy Search Field component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Hierarchy Search Field
======================================

The Hierarchy Search Field will search for parent objects of the base
vehicle or part in order to narrow down the search for each standard
dependent on which object type has been selected. For example, in the
AutoCare standard, if an application record has to be created for the
selected PIES Item object (Part), then the Hierarchy Search Field can be
configured to search for the Make/Model to display all of the Base
Vehicle objects (Vehicle) for the selected Make/Model. Or the Make/Model
can be selected to further narrow down the list of Years that are
available for that Make/Model.

If a root node has been configured in the Root Nodes parameter, then the
Hierarchy Search Field will only search below the configured root
node(s). For example, the Light Duty Vehicle root node can be added so
that the search will only be performed to include Light Duty vehicles
but excluded all other vehicle types (Medium/Heavy Duty, Powersports,
etc.).

To add and configure the Hierarchy Search Field component within the
Search Fields parameter:

1.  From the Faceted Search Node Picker Dialog Properties dialog, click
    the **Add** button next to the Search Fields parameter field and the
    Add Component dialog will display.

![](../../Resources/Images/Application%20Editor/41.png)

1.  Click **Hierarchy Search Field** from the list of components.
2.  Click the **Add** button, and the Hierarchy Search Field Properties
    will display three required fields and one optional field, as shown
    below.

![](../../Resources/Images/Application%20Editor/34.png)

**Field Name:** This optional field lets the user provide a label for
the facet associated with the Hierarchy Search Field that best
communicates to the user what criteria are available for selection
within the facet. By default, the label is set to 'Hierarchy.'

**Parent Object Type:** Determines the parent object type that a user
can select within the Hierarchy facet. to find and select the object
type for the objects that exist in the vehicle hierarchy or part
hierarchy, and should be displayed for a user as a parent object to
select within the facet dropdown. One such example of the parent object
is the Make object of the vehicle.

**Child Object Type:** Determines the child object type that a user can
select within the Hierarchy facet. to find and select the object type
that is the child of the object type that has been defined in the Parent
Object Type parameter, and should be displayed for a user as a child
object to select within the facet dropdown. One such example of the
child object is the Model object of the vehicle.

**Minimal Suggestion Length:** This required field determines the
minimum number of characters that needs to be typed in the typeahead
field so that the associated facet starts suggesting the object name in
the dropdown matching with the typed characters.

1.  Once the required parameters are populated, click the **Add** button
    to return to the Faceted Search Node Picker Dialog Properties and
    **Save** the configuration. Optionally add another search field.

Below is an example of a configured Hierarchy Search Field component:

![](../../Resources/Images/Application%20Editor/35.png)
