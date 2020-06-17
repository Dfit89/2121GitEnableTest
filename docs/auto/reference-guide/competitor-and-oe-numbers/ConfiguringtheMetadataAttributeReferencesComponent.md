---
description: 'Automotive Solution: Describes how to configure the
  Metadata Attribute References component.'
title: '\[%=Heading.AnyLevel%\]'
---

Configuring the Metadata Attribute References Component
=======================================================

PRODOC note: Documented based on PAKA explanation video on Zoom. Video
recording available. Incorporate Nife Review comments from Mail

The Metadata Attribute References component is configured as a table
header in many Web UI components. It is used to display the metadata
attributes value of Reference and Link types within the Part Number
References, Part Number Suggestions, Advanced Part Number References,
and Advanced Part Number Suggestions components.

It is expected that anyone configuring the Metadata Attribute References
component as a table header is familiar with the process required to add
table headers into components, as basic concepts for accessing and
adding the table headers are not covered in this section.

Configuration Steps

Below are the steps required to configure the Metadata Attribute
References component within a Part Number References or Part Number
Suggestions component. Each of the parameters for the Metadata Attribute
References Properties are described below.

1.  In the Web UI Designer, navigate to the Table Header / Header
    parameter for the component that will display metadata attributes.
    The example below displays the Table Header parameter within the
    Part Number References Properties dialog.

![](../../Resources/Images/Competitor%20OE%20Number/94.png)

1.  Click the **Add** button found beneath the Header field (screenshot
    shown above), and the Add Component dialog will display(as shown
    below).

![](../../Resources/Images/Competitor%20OE%20Number/91.png)

1.  Search for and select the \'Metadata Attribute References\', click
    **Add**, and the Metadata Attribute References dialog will display
    (as shown below). Parameter options are explained below:

![](../../Resources/Images/Competitor%20OE%20Number/92.png)

**Attribute:**The only mandatory parameter for this component. To select
an attribute, click the ellipsis to the right of the Attribute field. A
Select Node(s) dialog will appear and an attribute can be selected by
browsing and navigating down to the desired attribute or by using the
search feature.

**Dimensions:** By default, the parameter is blank. Optionally, to
configure column width and height, select \'Table Header Dimensions.\'

**Label:** Override the attribute name by adding new text that will
display in its place. By default, the component title comes from the
name of the configured attribute.

**Mandatory:** This parameter is used in Multi Edit Display mode to
visually prompt the user to add a value for the defined metadata
attribute displayed in the attribute table header. If \'Visually
Mandatory\' is selected from the dropdown, the header label will display
with an asterisk (\*), which informs the user a value must be added to
the configured metadata attributes. In the example below, an asterisk
(\*) displays to the right of the metadata attribute \'ATTR Original\'.

![](../../Resources/Images/Competitor%20OE%20Number/93.png)

**Readonly:** Determines if the value field should be editable or read
only.

-   If disabled (default), then users can edit the field
-   If enabled, the metadata attribute value on the screen will be
    locked so end users cannot make edits

**Table Sorting:** By default, the parameter is blank. Optionally,
select from the dropdown values to specify the default sorting order of
the column data.

**Enable Locale Formatting:** Determines if the \'ISO Date\' or \'ISO
Date and Time\' attribute values are displayed per the locale selection.

-   If enabled (not default), the \'ISO Date\' or \'ISO Date and Time\'
    attribute values will be displayed in the manner defined by the
    locale, selection of which is made when logging in.

Additional setup is required to configure the \'Enable Locale
Formatting\' parameter. For more information, see the **Localizable
Dates in Web UI** section of the **Web User Interfaces** documentation[
here]{.mcFormatColor style="color: Blue;"}.

**Show Invalid Inherited Values:** Determines if the inherited attribute
values need to be displayed even if the attribute is invalid to the part
number displayed in the list.

-   If enabled (not default), and the attribute has values inherited
    from the parent, then the inherited attribute value will display
    against the referenced / suggested part number.

**Show LOV IDs:** Determines whether the attribute\'s LOV ID displays
for the end user.

-   If enabled (not default), and the attribute\'s LOV has IDs enabled,
    then the LOV ID will display next to the value.

**No Wrap:** When unchecked, cell content (value of the attribute) will
break, or \'wrap,\' into multiple lines enabling display of as much of
the cell content. When the content in the cell has excess of characters
to display, then the metadata attribute value breaks to a second line,
allowing the display of the whole value.

**Context Help:** Enter help text to display when a user hovers over the
attribute name. Help texts can be used to provide information to end
users about an attribute and how it should be populated. Display of this
text requires that the Display Context Help parameter, described below,
is enabled. More information about the Context Help parameter can be
found in the **Set Component Properties in Web UI** section of the
**Attribute Help Text in Web UI** documentation[ here]{.mcFormatColor
style="color: Blue;"}

**Display Context Help:** Determines if the help text supplied in the
Context Help parameter above should be available to users. This is where
the \'Go to Wiki\' link is displayed when the Wiki Metadata feature is
installed. For more information, see the **Wiki Metadata** topic in the
**System Setup / Super User Guide** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

4.  Click the **Add** button, the newly added component will display
    within the Table Headers / Headers parameter.
5.  Click the **Save** button, and then click the **Close** button to
    close the designer.
