---
description: 'Automotive Solution: Describes how to configure an Name
  Search Field component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Name Search Field
=================================

The Name Search Field will search for the vehicle / assembly or part to
create an application for each standard dependent on which object type
has been selected. For example, in the AutoCare standard, if a PIES Item
object (Part) is selected, then the Name Search Field will by default
search on the Name of the Base Vehicle objects (Vehicle) to display. Or
in the TecDoc standard, if a Vehicle Type (PC) object (Vehicle) is
selected, then the Name Search Field will by default search on the Name
of the Supplier Article objects (Part) to display. If a root node has
been configured in the Root Nodes parameter, then the Name Search Field
will only search below the configured root node(s). To add the Name
Search Field component within the Search Fields parameter:

1.  From the Faceted Search Node Picker Dialog Properties dialog, click
    the **Add** button next to the Search Fields parameter field, and
    the Add Component dialog will display.

![](../../Resources/Images/Application%20Editor/39.png)

1.  Click **Name Search Field** from the list of components.

```{=html}
<!-- -->
```
1.  Click the **Add** button, and the Name Search Field Properties will
    display, as shown below.

![](../../Resources/Images/Application%20Editor/32.png)

**Field Name:** This optional field allows the user to provide a label
for the facet associated with the Name Search Field that best
communicates to the user what criteria are available for selection
within the facet. By default, the label is set to 'Name.'

**Minimal Suggestion Length:** This required field determines the
minimum number of characters that needs to be typed in the typeahead
field so that the associated facet starts suggesting the names in the
dropdown matching with the typed characters.

1.  Once the component is populated, click the **Add** button to return
    to the Faceted Search Node Picker Dialog Properties and Save the
    configuration. Optionally add another search field.

Below is an example of a configured Name Search Field component:

![](../../Resources/Images/Application%20Editor/33.png)
