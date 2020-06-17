---
description: 'Automotive Solution: Describes how to configure an
  Attribute Search Field component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Attribute Search Field
======================================

The Attribute Search Field will search for attribute values that is
valid for the vehicle / assembly or part for each standard dependent on
which object type has been selected. For example, in the AutoCare
standard, if a PIES Item object (Part) is selected, then the Attribute
Search Field will by default search only on the attribute(s) that are
valid for the Base Vehicle objects (Vehicle) to display (e.g. VCdb
Year). Or in the TecDoc standard, if a Vehicle Type (PC) object
(Vehicle) is selected, then the Attribute Search Field will by default
search only on the attribute(s) that are valid for the Supplier Article
objects (Part) to display (e.g. Country Inclusion, Housing Type, etc.).
If a root node has been configured in the Root Nodes parameter, then the
Attribute Search Field will only search below the configured root
node(s). To add the Attribute Search Field component within the Search
Fields parameter:

1.  From the Faceted Search Node Picker Dialog Properties dialog, click
    the **Add** button next to the Search Fields parameter field, and
    the Add Component dialog will display.

![](../../Resources/Images/Application%20Editor/40.png)

1.  Click **Attribute Search Field** from the list of components.

```{=html}
<!-- -->
```
1.  Click the **Add** button, and the Attribute Search Field Properties
    will display, as shown below.

![](../../Resources/Images/Application%20Editor/30.png)

**Attributes:** This required field allows users to add an attribute
criterion to their search. All attribute validation base types (e.g.,
Text, Number, List Of Values) are allowed. to find and select the
required attribute. The selected attribute must be valid for the object
type that is intended for search, and the attribute value must be
populated on that object in order for it to display correctly. The Name
of the attribute will be displayed in the Faceted Search dialog.

**Minimal Suggestion Length:** This required field determines the
minimum number of characters that needs to be typed in the typeahead
field so that the associated facet starts suggesting the values in the
dropdown matching with the typed characters.

1.  Once the required parameters are populated, click the **Add** button
    to return to the Faceted Search Node Picker Dialog Properties and
    **Save** the configuration. Optionally add another search field.

Below is an example of a configured Attribute Search Field component:

![](../../Resources/Images/Application%20Editor/31.png)
