---
description: 'Automotive Solution: PMDM for Automotive 9.0 MP2 Patch
  Notes '
title: PMDM for Automotive 9.0 MP2 October 2018 Patch Notes
---

PMDM for Automotive 9.0 MP2 Patch Notes {#pmdm-for-automotive-9.0-mp2-patch-notes .MPN}
=======================================

Release Date: October 10, 2018 {#release-date-october-10-2018 style="text-align: center;"}
------------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST- 2594 New Country Handling solution

Within the automotive industry, it is vital to properly maintain parts
data pertaining to country inclusion and/or exclusion to ensure market
specific coverage and legal compliance. The Country Handling solution
helps users view, edit, and create accurate country handling inclusion
and exclusion references for specific parts and applications. This Web
UI solution also prevents users from creating conflicting inclusion
and/or exclusion relationships.

The Country Handling solution can be used within an Application Manager
Results Table via an \'Application Country Handling Table Header\'
component and within a Node Editor screen via \'Country Handling Value\'
component. For more information, see the **Country Handling Solution**
section of **Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

In the screenshot below, the \'Application Country Handling Table
Header\' component is displayed with the default column heading
(Countries) within an Application Manager Results Table.

![](../../Resources/Images/Country%20Incl%20Excl/34.png)

![](../../Resources/Images/Country%20Incl%20Excl/34.png)

In the screenshot below, the \'Country Handling Value\' component is
displayed within a Node Editor screen.

![](../../Resources/Images/Country%20Incl%20Excl/35.png)

![](../../Resources/Images/Country%20Incl%20Excl/35.png)

PRODOC note: MEDU RDCUST- 2809 Application Coverage Report now displays
more

Two table header components have now been added to the Application
Coverage Report. When the \'Application Condition Header - Individual\'
and/or \'Application Competitor or OE Part Numbers\' components are
added to an Application Manager Results Table and the Application
Coverage Report is run, the component headers and their values will
display within the Application Coverage Report. For more information,
see the **Application Coverage Report** topic within the **Automotive
Reference Guide**[ here]{.mcFormatColor style="color: Blue;"}.

PRODOC note: MEDU RDCUST- 3082 New optional parameter added to business
rule plugins

A new optional parameter has been added to the Change part, Change part
type, and Copy application business rules that allows admins to
determine if the existence of a part type should be confirmed before
changing the part for an application.

PRODOC note: MEDU RDCUST- 3194 Application Competitor or OE Part Numbers
component now able to filter display of Attributes, Attribute Groups,
and/or References

Three new parameters have now been added to the \'Application Competitor
or OE Part Numbers\' header component to support filtering of
attributes, attribute groups, and/or references that should not be
displayed within the Application Manager Results Table.

PRODOC note: MEDU RDCUST- 3192 Application Competitor or OE Part Numbers
component can now display your own logo

A new option has now been added to the Application Competitor or OE Part
Numbers component that allows for a Stibo Systems customer\'s own logo
to display in the Make column. This makes it easier for users to
identify their own part information within the list of competitor and/or
OE part numbers.

In the screenshot below, the Stibo Systems\' logo displays as an example
for a customer\'s own logo.

![](../../Resources/Images/Competitor%20OE%20Number/12.png)

![](../../Resources/Images/Competitor%20OE%20Number/12.png)

PRODOC note: MEDU RDCUST- 2136 7-zip file type now valid for TecDoc
imports

TecDoc importers are now easier to use because they handle the 7-zip
file type (the default file type provided from TecAlliance) along with
the .ZIP file type.

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: MEDU RDCUST- 3117 Corrected exception error when using Part
Number References component

Previously, when using the Part Number References component to add a
competitor or OE number to a part, an exception error would display, and
the reference could not me made. Now, this is corrected so that an
exception error no longer displays when the Part Number References
component is used to add a competitor / OE number to a part within a Web
UI.

PRODOC note: MEDU RDCUST- 3144 Import flow added to Extension API
Javadoc

Previously, documentation for the automotive import flow (a plugin type
that can run inside a BGP service having access to all files from the
automotive import flow) was not available within the STEP Javadoc. Now,
the automotive import flow (com.stibo.importflow.domain.extension) can
be found within the Extension API Javadoc.

**Hotfix recipe compatible with STEP 8.3 MP3 + Automotive 8.3 MP2:**
[to:hotfix/325/issue-325501-HOTFIX-2708.spr ]{.commandfont}

PRODOC note: MEDU RDCUST- 3103 Corrected adding Tab Pages to Node Picker
Dialog for Application Set Assembly

Previously, when adding Tab Pages to a Node Picker Dialog for an
Application Set Assembly component within the Application Manager
Results Table, the Add Component dialog did not display. This made it
impossible to complete the necessary configuration of the component.
Now, this is corrected, and the component can be properly configured for
use.

PRODOC note: MEDU RDCUST- 3105 Corrected display of the Application
Competitor or OE Part Numbers component

Previously, when more than one \'Application Competitor or OE Part
Numbers\' component was configured within an Application Manager Results
Table, only the results from the right most component would display
within all iterations of the component. Now, this is corrected so that
more than one \'Application Competitor or OE Part Numbers\' component
can be configured within an Application Manager Results Table and
display the expected results based upon the configurations.

PRODOC note: MEDU RDCUST- 3180 Additionally, when opening the dialog for
this component, and a long list of information was included within the
screen, scroll bars were not included. Therefore, users were not able to
view all of the information and use the component. Now, scroll bars have
been added so that users can view all of the content (no matter its
length) and access all of the component options.

PRODOC note: MEDU RDCUST- 3195 Removed the OK button from the
Application Competitor or OE Part Numbers display

Previously, when the \'Application Competitor or OE Part Numbers\'
component was configured within an Application Manager Results Table,
and a user double clicked to open the dialog, and an OK button displayed
in the bottom right. This OK button resulted in a lot of unnecessary
white space and was not needed since the dialog also included an \'X\'
in the upper right corner that, when clicked, closes the dialog (the
same functionality the OK button offered). Now, the OK button has been
removed allowing for the display to be filled with more usable
information and less wasteful white space.

PRODOC note: MEDU RDCUST- 3116 Corrected Application Manager display of
search box suggestions

Previously, when using the Application Manager search boxes, if a user
placed the cursor into the typeahead field at the bottom of the box more
than once, the dropdown list would not display. Now, this has been
corrected so that any time the cursor is placed into the typeahead field
at the bottom of a search box, the valid dropdown selections will
display.

PRODOC note: MEDU RDCUST- 3111 Corrected Application Manager search
interruption

Previously, when using the Application Manager to search for Make/Model
criteria, running the search, and then adding additional criteria within
the Make/Model search box, the search would be interrupted. Now, this is
corrected so that users can make changes to the search box criteria,
after running a search, and the desired results will display.

PRODOC note: MEDU RDCUST- 3071 Corrected Application Manager Results
Table Reset button

Previously, when editing values within an Application Manager Results
Table, and clicking the Reset button, all of the results within the
table would disappear. Now, this has been fixed so that when the Reset
button is clicked, only the changes made within the Results table are
cleared or reverted back to the original values displayed when the
search was run.

In the screenshot below, the Reset button displays as active because
changes have been made to the Supplier Article cell.

![](../../Resources/Images/Release%20Notes/3071.png)

![](../../Resources/Images/Release%20Notes/3071.png)

PRODOC note: MEDU RDCUST- 3125 Corrected Application Editor screen type
to allow multiple vehicle types

Previously, users were not able to select valid parts when attempting to
create applications for certain vehicle types within an Application
Editor screen. Now, any vehicle object type that is defined as a valid
target in the application reference type can be used to select a valid
part when creating an application through the Application Editor screen
using Data Provider = Assembly Application.

PRODOC note: MEDU RDCUST- 3075 Updated \'Application Set Part\' header
component to warn about configuration error

Previously, it was possible to configure the \'Application Set Part\'
header component in a way that would cause an error message to display
for users. Now, if a user attempts to save this component without the
Attribute parameter populated, an \'INVALID (Headers)\' and a warning
message will display indicating that the screen cannot be saved while
one or more components has configuration errors.

PRODOC note: MEDU RDCUST- 3130 Corrected ID Header component handling of
screen mapping

Previously, when an ID Header component was configured with the \'Enable
Link\' parameter enabled, and a user clicked on the link, an error
message would display notifying the user that the screen trying to load
was invalid. This occurred despite the proper configuration of screen
mappings. Now, this is corrected so that when a screen with the ID
\'productdetails\' exists, and a user clicks the ID Header component
link, then the default productdetails screen displays. Additionally,
when screen mapping for the selected object is configured, and a user
clicks the ID Header component link, then the user will be directed to
the screen ID mapped for that Object Type. However, if the default
productdetails screen ID does not exist, and no additional screen
mapping is configured for the specific Object Type being clicked, then
the following error message will display: \"The configuration for the
screen you are trying to load is invalid and the screen cannot be
displayed: No screen with ID \[productdetails\]\"

In the screenshot below, a Part Number Reference component is configured
to include an ID Header component with the Enable Link parameter
enabled. In the background, the linked Object Type
(AC\_PIESInterchangeItem\_e211) displays along with the error message
that will only display when the default \'productdetails\' screen ID is
not created or the screen mappings are not properly configured for the
selected Object Type.

![](../../Resources/Images/Release%20Notes/3130.png)

![](../../Resources/Images/Release%20Notes/3130.png)

### AutoCare

PRODOC note: MEDU RDCUST- 3124 Corrected PIES 6.5 Exporter\'s retention
of Part Number Source Attribute Value

Previously, when configuring the PIES 6.5 exporter \'Part Number
Source\' parameter with an attribute other than the default
\'AC\_PIES\_ITEMPartNumber,\' the attribute was not retained when saving
the export configuration. Therefore, when the saved export configuration
was used, the expected results were not displayed in the exported file
for the Part Number. Now, the saved export configuration retains the
attribute selection in the \'Part Number Source\' parameter so that the
expected results are displayed.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2 MP4:**
[to:hotfix/325/issue-325279-HOTFIX-2701.spr ]{.commandfont}

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

PRODOC note: PRODOC- 1242New TecDoc Supplier Data Importer documentation

The new **TecDoc Supplier Data Importer** section addresses using and
configuring the TecDoc Supplier Data Importer and can be found within
the **Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

PRODOC note: MEDU PDO-1550 New Country Handling Solution documentation

The new **Country Handling Solution** section addresses using and
configuring the Country Handling solution and can be found within the
**Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.12.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible only with the following STEP 9.0 MP4
baseline recipe:

[to:step/trailblazer/step-9.0-mp4.spr]{.commandfont}

**PRODOC note: MEDU PRODOC- 1572** Once an Automotive add-on is
installed to a base STEP system, the base system should not be upgraded
without upgrading the Automotive add-on at the same time. Additionally,
when upgrading any base STEP system that has any Automotive add-on
installed, both install recipes must be prepared and applied at the same
time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
