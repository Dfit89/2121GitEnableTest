---
description: 'Automotive Solution: Describes how to configure an Name
  Search Box component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Name Search Box
===============================

The Name search box will search for the name of the object that is
intended for search. For example, if the Search by Card Screen is
configured to search for the Base Vehicle objects, then the Name search
box will by default search on the Name of the Base Vehicle objects to
display. If a root node has been configured in the Root Nodes parameter,
then the Name search card will only search below the configured root
node(s). To add the Name Search Box component within the Search Cards
parameter:

1.  From the Search by Card Screen Properties dialog, click the **Add**
    button next to the Search Cards parameter field and the Add
    Component dialog will display.

![](../../Resources/Images/Search%20by%20Card%20Screen/27.png)

1.  Click **Name Search Box** from the list of components.

```{=html}
<!-- -->
```
1.  Click the **Add** button, and the Name Search Box Properties will
    display, as shown below.

![](../../Resources/Images/Search%20by%20Card%20Screen/28.png)

**Card Name:** This optional field allows the user to provide a label
for the card associated with the Name Search Box that best communicates
to the user what criteria are available for selection within the card.
By default, the label is set to 'Name.'

**Minimal Suggestion Length:** This required field determines the
minimum number of characters that needs to be typed in the typeahead
field so that the associated card starts suggesting the names in the
dropdown matching with the typed characters.

1.  Once the component is populated, click the **Add** button to return
    to the Search by Card Screen Properties and Save the configuration.
    Optionally add another search box.

Below is an example of a configured Name Search Box component:

![](../../Resources/Images/Search%20by%20Card%20Screen/29.png)
