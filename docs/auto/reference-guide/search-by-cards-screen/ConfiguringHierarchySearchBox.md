---
description: 'Automotive Solution: Describes how to configure a
  Hierarchy Search Box component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Hierarchy Search Box
====================================

The Hierarchy Search Box will search for the parent folder(s) of the
searched object in order to more efficiently gather relevant search
results. For example, in the AutoCare standard, if a Vehicle object is
to be searched for, then the Hierarchy Search Box can be configured to
search for the Make/Model to display all of the Vehicle objects
(Vehicle) for the selected Make/Model.

If a root node has been configured in the Root Nodes parameter, then the
Hierarchy Search Box will only search below the configured root node(s).
For example, the Light Duty Vehicle root node can be added so that the
search will only be performed to include Light Duty vehicles and exclude
all other vehicle types (Medium/Heavy Duty, Powersports, etc.).

To add and configure the Hierarchy Search Box component within the
Search Cards parameter, follow the instructions below:

1.  From the Search by Card Screen Properties dialog, click the **Add**
    button next to the Search Cards parameter field. The Add Component
    dialog will display.

![](../../Resources/Images/Search%20by%20Card%20Screen/23.png)

1.  Click **Hierarchy Search Box** from the list of components.
2.  Click the **Add** button, and the Hierarchy Search Box Properties
    will display.

![](../../Resources/Images/Search%20by%20Card%20Screen/224.png)

**Card name:** This optional field lets the user provide a label for the
card associated with the Hierarchy Search Box. It is a good practice to
label the card that best communicates to the user what criteria are
available for selection within the card. By default, the label is set to
'Hierarchy.'

**Parent Object Type:** Determines the parent object type that a user
can select within the Hierarchy card. to find and select the object type
that should be displayed for the user as a parent object to select
within the typeahead dropdown.

The defined object type should meet all of the following criteria:

-   Should exist as any top-level parent folder for the object type that
    is intended for search.
-   Should be present in the hierarchy of the root node defined in the
    Root Nodes parameter.
-   Cannot be the object type that is intended for search.

**Child Object Type:** Determines the child object type that a user can
select within the Hierarchy card. to find and select the object type
that should be displayed for a user as a child object to select within
the typeahead dropdown.

The defined object type should meet all of the following criteria:

-   Should exist as any top-level parent folder for the object type that
    is intended for search.
-   Should exist as any lower-level folder below the object type defined
    in the Parent Object Type parameter.
-   Should be present in the hierarchy of the root node defined in the
    Root Nodes parameter.
-   Cannot be the object type that is intended for search.

**Minimal Suggestion Length:** This required field determines the
minimum number of characters that must be entered into the typeahead
field so the associated card starts suggesting relevant object names in
the dropdown.

1.  Once the required parameters are populated, click the **Add** button
    (or **Save** button) to return to the Hierarchy Search Box
    Properties and **Save** the configuration.

Below is an example of a configured Hierarchy Search Box component:

![](../../Resources/Images/Search%20by%20Card%20Screen/25.png)

Below is another example of a configured Hierarchy Search Box component:

![](../../Resources/Images/Search%20by%20Card%20Screen/26.png)
