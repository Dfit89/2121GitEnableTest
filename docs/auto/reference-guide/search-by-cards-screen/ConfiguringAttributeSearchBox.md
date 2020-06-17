---
description: 'Automotive Solution: Describes how to configure an
  Attribute Search Box component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Attribute Search Box
====================================

The Attribute Search Box will search for attribute values that are valid
for the object type that is intended for search. For example, in the
AutoCare standard, if a Base Vehicle object is being searched, then the
Attribute Search Box will by default search only on the attribute(s)
that are valid for the Base Vehicle objects to display (e.g. VCdb Year).
If a root node has been configured in the Root Nodes parameter, then the
Attribute Search Box will only search below the configured root node(s).
To add the Attribute Search Box component within the Search Cards
parameter follow the instructions below.

1.  From the Search by Card Screen Properties dialog, click the **Add**
    button next to the Search Cards parameter field.The Add Component
    dialog will display.

![](../../Resources/Images/Search%20by%20Card%20Screen/30.png)

1.  Click **Attribute Search Box** from the list of components.

```{=html}
<!-- -->
```
1.  Click the **Add** button, and the Attribute Search Box Properties
    will display, as shown below.

![](../../Resources/Images/Search%20by%20Card%20Screen/31.png)

**Attributes:** This required field allows users to add one or more
attribute criteria to their search. All attribute validation base types
(e.g., Text, Number, List Of Values) are allowed. to find and select the
required attribute. The selected attribute must be valid for the object
type that is intended for search, and the attribute value must be
populated on that object in order for it to display correctly. The name
of the attribute will display in the configured search box.

**Include Inherited Value:** This checkbox determines the requirement to
include the inherited attribute values in its search criteria. Check the
field to enable searching of the inherited attribute values in the
search card.

**Minimal Suggestion Length:** This required field determines the
minimum number of characters that must be entered into the typeahead
field so the associated card starts suggesting relevant values in the
dropdown.

1.  Once the required parameters are populated, click the **Add** button
    to return to the Search by Card Screen Properties and **Save** the
    configuration. Users may add additional search fields, if needed.

Below is an example of a configured Attribute Search Box component:

![](../../Resources/Images/Search%20by%20Card%20Screen/32.png)
