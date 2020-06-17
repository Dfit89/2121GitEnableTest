---
description: 'Automotive Solution: The Attributes stage of the
  Onboarding Comparison Screen displays the attributes related to the
  Source object against the Target object on the same screen. The screen
  is designed to showcase the similarities / differences between the
  Source object attributes and the Target object attributes based on the
  rule defined on the Mapper rows of the Attribute Mapping plugin for
  the configured Mapper Configuration setup entity.'
title: '\[%=Heading.AnyLevel%\]'
---

Using Attributes Stage
======================

There are a number of reasons that Onboarding the attribute values from
the Source object to the Target object is a fundamental part of most
business models, such as Onboarding attribute values from an object
belonging to the Supplier hierarchy to an object belonging to the Own
hierarchy. Certain attributes (e.g., price) may be simply copied or
sometimes an attribute transformation is applied before updating the
Target object attribute.

Instead of users manually switching between the Source and the Target
objects for comparing the attributes, the Attributes stage of the
Onboarding Comparison Screen displays the attributes related to the
Source object against the Target object on the same screen. The screen
is designed to showcase the similarities / differences between the
Source object attributes and the Target object attributes based on the
rule defined on the Mapper rows of the Attribute Mapping plugin for the
configured Mapper Configuration setup entity.

The Attribute stage of the Onboarding Comparison Screen displays all the
active Attribute Mapping plugin along with their active Mapper rows that
are available within the configured Mapper Configuration setup entity.
This stage displays only the Source and the Target object\'s attributes
that are defined in each active Mapper rows of the Attribute Mapping
plugin(s). Each Attribute Mapping plugin will have a dedicated canvas
called \'Attribute Mapping plugin canvas\'. The options available within
each canvas allows users to individually decide what rule of the Mapper
Configuration setup entity should be executed for the selected Source
object that in turn effects the related Target object attributes.

This section addresses features and functionalities that are only
specific to the Attributes stage of the Onboarding Comparison Screen.
For information on the general functionalities of the Onboarding
Comparison Screen, see the **Using Onboarding Comparison Screen
Interface** topic ([here]{.mcFormatColor style="color: Blue;"}) within
this guide.

The Attributes stage of the Onboarding Comparison Screen is composed of
the following:

![](../../../Resources/Images/Data%20Onboarding/209.png)

1.  **Source object name:** Displays the name of the Source object.
2.  **Progress Tracker:** The titles of all the stages that make up the
    Onboarding display beneath the number of the stage which displays in
    a circle. The number of the stage will be highlighted blue when
    selected. Users may navigate between the stages by clicking on
    either the stage number or stage labels that display. The
    highlighted stage shows the current stage of the Onboarding process
    in the Onboarding Comparison Screen. In the screenshot above, the
    Onboarding Comparison Screen displays the Attributes stage.
3.  **Comparison table toolbar:**

![](../../../Resources/Images/Data%20Onboarding/210.png)

Contains action buttons related to the Attributes stage of the
Onboarding Comparison Screen. Available action buttons are hard coded to
always display in the toolbar and cannot be configured in any way.

-   **Select all / Clear all:** The \'Clear all\' button displays when
    one or more rows are selected using the \'Mapping plugin / Mapper
    row selection boxes.\' When no rows are selected, the \'Select all\'
    button will display. Clicking the \'Clear all\' button will remove
    the selections within the \'Mapping plugin / Mapper row selection
    boxes.\' Clicking this button will not clear the values in the
    comparison table, but rather disables the selection of \'Mapping
    plugin / Mapper row selection boxes.\' Clicking the \'Select all\'
    button enables all the \'Mapping plugin / Mapper row selection
    boxes\'.
-   **Hide Equal / Show Equal:** This action helps in finding out the
    row that has the Source object attribute and Target object attribute
    of equal values. The Comparison table is defaulted to always display
    these rows. It is to be observed that the rows that has the Source
    object attribute and Target object attribute of equal values does
    not include a row selection box (as shown below). However, clicking
    on the \'Hide Equal\' button will hide such rows that has same
    values in the Source object attribute and Target object attribute.
    When the table displays with these rows compressed, the \'Show
    Equal\' button will display within the toolbar instead of the \'Hide
    Equal\' button.

![](../../../Resources/Images/Data%20Onboarding/212.png)

-   **View Source Attribute / Hide Source Attribute:** By default, the
    Comparison table does not display the Source attribute name.
    Clicking the 'View Source Attribute' button will make the Source
    attribute name to be displayed in gray color below their respective
    Target attribute name (as shown below). Meanwhile, the 'Hide Source
    Attribute' button will compress the Source attribute name displayed
    below their respective Target attribute name. However, the Source
    attribute value will always remain to be displayed in the
    \'\[Supplier\] values\' column irrespective of the display /
    suppression of the Source attribute name. When the table displays
    the Source attribute name, the \'Hide Source Attribute\' button will
    display within the toolbar instead of the \'View Source Attribute\'
    button.

![](../../../Resources/Images/Data%20Onboarding/211.png)

-   **View Attribute ID / Hide Attribute ID:** By default, the
    Comparison table does not display the Source / Target attribute ID.
    Clicking the 'View Attribute ID' button will make the attribute ID
    surrounded by parentheses to be displayed next to the Source /
    Target attribute name. The following screenshot shows an example of
    the attribute ID displayed for both the Source object and the Target
    object.

![](../../../Resources/Images/Data%20Onboarding/213.png)

 

4.  **Number of effecting changes:**

![](../../../Resources/Images/Data%20Onboarding/214.png)

Lists the total possible number of Target object attributes that could
have change in the existing value.

4.  **Attribute Mapping plugin canvas:** Each active Attribute Mapping
    plugin(s) that are available in the Mapper Configuration setup
    entity will have a dedicated section in the Attributes stage, and
    each individual section is called as Attribute Mapping plugin
    canvas. Each Attribute Mapping plugin canvas is identified by their
    respective plugin name. Each canvas includes active Mapper rows
    belonging to that Attribute Mapping plugin. In the example below, a
    canvas is identified by the Attribute Mapping plugin name called
    \'Copy Attribute Values.\'

![](../../../Resources/Images/Data%20Onboarding/219.png)

In the example above, the current value of the Target attribute \'Own
Text\' will be replaced by the value \'AC2493,\' therefore it is
highlighted with red color in the table. And the value of the Target
attribute \'Number Multi Valued\' will not be changed, therefore it is
not highlighted in the table.

Each Attribute Mapping plugin canvas consists of the following:

-   Mapping Plugin row selection box
-   Auto Update switch
-   Expand / collapse arrow
-   Mapper row selection boxes

All the above mentioned options are explained in detail in the later
section of this topic.

2.  **Mapping Plugin row selection box:** Allows for selection of each
    Attribute Mapping plugin that are displayed in the Attributes stage
    of the Onboarding Comparison Screen. Selecting the checkbox also
    selects all the Mapper rows displayed within the respective
    Attribute Mapping plugin canvas.
3.  **Auto Update switch:** Activating this will ensure that all the
    Mapper rows listed in this canvas will automatically be included for
    execution in all future Onboarding for the selected Source object.
    The settings applied in this switch will be defaulted for all
    methods of future execution and is applicable only for the selected
    Source object. It is set to inactive as default. When the switch is
    turned On, the Mapping plugin row selection box (along with their
    included Mapper rows selection box(es)) is selected and are grayed
    out. That means no individual deselection of the Mapper rows are
    allowed and the whole of the mapper rows listed within the canvas
    are executed on the particular Source object.

After turning On / Off the Auto Update switch in any Mapping canvas, the
user should click the **Onboard** button (that is available in the in
the lower right corner of the Confirm stage) to save changes made to the
Auto Update switch in the Onboarding Comparison Screen. As stated
previously, users may safely navigate between the stages in Onboarding
Comparison Screen without losing unsaved selections, but users should
not exit Onboarding without first navigating to the final screen and
clicking the Onboard button.

Remember, the Auto Update switch is set to inactive as default. If no
Auto Update switch is activated in any of the Mapping canvas (across all
Mapping stages), then the execution of the Mapper Configuration setup
entity continues to function as before and no Mapping canvas will be
excluded from execution. If any Auto Update switch from any of the
Mapping canvas is set active (turned On), then the other Mapping canvas
will be excluded from execution. Care must be taken to check the Auto
Update status of all Mapping canvas across all stages while activating /
deactivating the Auto Update switch.

PRODOC Note: if the Auto Update switch belonging to other Mapping canvas
remains deactivated after activating Auto Update switch in any of the
Mapping canvas, then the future execution of the Mapper Configuration
setup entity *will not* execute any Mapping canvas that has the Auto
Update switch deactivated.

PRODOC Note: Activating this will ensure that all the Mapper rows listed
in this canvas will automatically be included for execution in all
future Onboarding for the selected Source object. The settings applied
in this It is set to inactive as default. Turning On this switch within
the \'Mapping plugin canvas\' will ensure that all the Mapper rows
listed in this canvas will always be executed by default for all future
Onboarding via Onboarding Comparison Screen. When the switch is turned
On, the Mapping plugin row selection box (along with their included
Mapper rows selection box(es)) is selected and are grayed out. That
means no individual selection of the Mapper rows are allowed and the
whole of the mapper rows listed within the canvas is executed.

PRODOC Note: If users have selected the Auto Update switch in any
Mapping canvas to any stage in Onboarding Comparison Screen, on the
Confirm stage the Onboard button in the lower right-hand corner will be
present. Clicking this button is the only way to ensure that Auto Update
switch in the Onboarding Comparison Screen stage is saved. As stated
previously, users may safely navigate between the stages in Onboarding
Comparison Screen without losing unsaved selections, but users should
not exit Onboarding without first navigating to the final screen and
clicking the Onboard button.

2.  **Expand / collapse arrow:** When the arrow is clicked, the Mapping
    plugin canvas where the Mapper rows are listed is collapsed (not
    showing). However, the name of the Mapping plugin and the Auto
    Update switch will still be visible in the canvas (as shown below).
    Clicking the arrow again will expand display of the collapsed Mapper
    rows. This can be beneficial to users who use Auto Update switch
    within the Mapping plugin canvas. If the user already knows the
    Mapper rows that exists within the Mapping plugin canvas, then there
    may be no need to see the Mapper rows each time they navigate to the
    Attributes stage.

![](../../../Resources/Images/Data%20Onboarding/215.png)

9.  **Column Headers:**

Each column header label can be edited as needed by accessing the
Onboarding Comparison Screen Properties designer screen. For information
on editing column headers in the Attribute Mapping plugin canvas, see
the **Configuring Onboarding Comparison Screen** topic within this
guide[ here]{.mcFormatColor style="color: Blue;"}.

![](../../../Resources/Images/Data%20Onboarding/216.png)

By default, the following four column headings are hardcoded to be
always visible within the Attribute Mapping plugin canvas:

-   **Target attributes:** This column displays the name of the Target
    object attributes that are defined as the Target attributes in each
    Mapper rows within the Mapping plugin. This column header label is
    non editable.
-   **Target object current values**: By default, this column header is
    labeled as \'\[Current STEP\] values\'. This column displays the
    current value(s) populated in the Target object attribute. This
    column header can be edited as needed. The values listed within this
    column will display the current value populated in the Target
    object. This column is displayed only in the Attribute Mapping Stage
    of the Onboarding Comparison Screen.
-   **Source object current values:** By default, this column header is
    labeled as \'\[Supplier\] values\'. This column displays the current
    value(s) populated in the Source object attribute. This column
    header can be edited as needed.
-   **Target object new values:** By default, this column header is
    labeled as \'\[Updated STEP\] values\'. This column displays the
    value that gets populated in the Target object attribute after the
    related Mapper Configuration setup entity is executed. This column
    header can be edited as needed.

10. **Mapper row selection boxes:** Allows for the selection of each
    individual Mapper rows displayed within each Attribute Mapping
    plugin canvas. To select or deselect attributes individually, select
    a Mapper row by clicking the checkbox shown to the left of the
    Target attributes name. To select multiple rows, either click on
    additional rows or use the Select all action. As soon as a row
    selection is made, the Select all icon switches to a Clear all icon.
    Use this to clear all selections or just click a checkbox again to
    deselect a particular row.

 

11. **Comparison table:** This table displays the similariteis /
    differences between the current Source object attribute values and
    the Target object attribute values, and also displays the value that
    gets be populated on the Target object attribute when the Onboarding
    is completed. This way the user gets a clear picture in deciding
    which attribute value is to be Onboarded. For instance, if a user
    needs to see how an attribute on the Target object could be changed
    over the Onboarding process, the expected change in the Target
    attribute value can be viewed at the table.

```{=html}
<!-- -->
```
11. **Exit Onboarding button:** This button allows user to exit the
    Onboarding process without executing / saving any changes.
12. **Reject Update button:** This button requires the configuration of
    a business action in the Rejected Onboarding Business Action
    parameter that is available within the Onboarding Comparison Screen
    Properties designer screen. The configured business action must be
    defined with an operation that is to be executed on the Source
    object when the user clicks the Reject Update button. Clicking the
    button displays a message (as shown below) on the screen that asks
    for the confirmation to reject the Onboarding process.

![](../../../Resources/Images/Data%20Onboarding/217.png)

If no business action is configured in the Rejected Onboarding Business
Action parameter, then the following message will display at the top of
the screen.

![](../../../Resources/Images/Data%20Onboarding/218.png)

14. **Total count of attributes selected for changes:** Lists the number
    of Mapper rows selected from the Attribute stage for execution.
15. **Next button:** On any stage that is not the Confirm stage, a
    button labeled \'Next\' will display. Clicking the \'Next\' button
    will move the user forward one stage in the Onboarding Comparison
    Screen stages, and will not cause any changes selected to be
    removed. Users may safely navigate between the steps in Onboarding
    Comparison Screen without losing unsaved entries, but users should
    not exit Onboarding Comparison Screen without first navigating to
    the Confirm stage and clicking the \'Onboard\' button.

 

![](../../../Resources/Images/Data%20Onboarding/208.png)

1.  **Source object name:** Displays the name of the Source object.
2.  **Current stage:** This displays that the user is in the Attributes
    stage of Onboarding Comparison Screen.
3.  **Clear all / Select all button:** xxx
4.  **Hide Equal button:** xxx
5.  **View Source Attribute button:** xxx By default, the table results
    display using the \'Normal view.\' Clicking the 'Compressed view'
    button will compress the values displayed in the Options column by
    removing the attribute labels and displaying only the attribute
    values. When the table displays as compressed, the \'Normal view\'
    button will display within the toolbar instead of the \'Compressed
    view\' button.
6.  **View Attribute ID button:** xxx By default, the table results
    display using the \'Normal view.\' Clicking the 'Compressed view'
    button will compress the values displayed in the Options column by
    removing the attribute labels and displaying only the attribute
    values. When the table displays as compressed, the \'Normal view\'
    button will display within the toolbar instead of the \'Compressed
    view\' button.
7.  **Number of affecting attributes:** List the total number of rows
    available for display within the results table.
8.  **Mapping plugin selection boxes:** Allows for selection of one or
    more rows within the table. Selecting at least one row can change
    the action buttons that display within the toolbar.
9.   
10. **Mapping Row Selection Boxes**

When a reference is suppressed, the word \'Suppressed\' displays in the
Suppression column. The word \'Visible\' displays when references are
not suppressed. If a reference cannot be suppressed, the applicable
Suppression cell is disabled with the words \'Cannot be suppressed\' or
\'Inherited\' displayed.
