---
description: 'Automotive Solution: Automotive Solution: PMDM for
  Automotive 9.2 Release Notes'
title: PMDM for Automotive 9.2 Release Notes
---

PMDM for Automotive 9.2 Release Notes {#pmdm-for-automotive-9.2-release-notes .MPN}
=====================================

Release Date: September 06, 2019 {#release-date-september-06-2019 style="text-align: center;"}
--------------------------------

New Features {#new-features .MPNNewFeatures}
------------

PRODOC note: RDCUST- 3674New \'Mapper Action\' button to execute Mapper
Configuration setup entity

A new \'Mapper Action\' button has been added for configuration on the
Source object screen to start a Mapper Configuration setup entity.
Previously, the \'Initiate Business Action\' button was used to execute
a Mapper Configuration setup entity from the Source object. The unique
features of this action button include:

-   A required parameter called \'Mapper Configuration\' that allows the
    user to directly configure the Mapper Configuration setup entity in
    the action button.
-   The \'Run Before Action\' parameter that allow users to configure a
    business action. The configured business action gets executed before
    the Mapper Configuration setup entity is executed.

![](../../Resources/Images/Release%20Notes/92RN1.png)

-   A status message dialog that will display when the user clicks on
    the action button. This dialog shows the execution status of the
    Mapper Configuration and configured business action execution in the
    top center of the screen. More details on the status of the
    execution can be seen either by clicking \'Click for details\' link
    in the message dialog or by accessing through the Corner Bar Warning
    Notifications icon
    (![](../../../../Resources/Images/WebUserInterfaces/MAIN/WarningIcon1.png)).

![](../../Resources/Images/Release%20Notes/92RN7.png)

PRODOC note: RDCUST- 3674New \'Enable\' and \'Disable\' buttons to
enable / disable the Mapping plugins

Two new buttons to enable / disable the Mapping plugin is available
within the Mappings tab of the Onboarding Mappings Details screen. These
buttons are useful when there are multiple Mapping plugins added in the
Mapper Configuration setup entity and if one or multiple mapping plugins
need to be temporarily deactivated (and then reactivated).

![](../../Resources/Images/Release%20Notes/92RN6.png)

PRODOC note: RDCUST- 3709Added support for \'Application Comment\' table
header component on \'Application Editor Screen\'

\'Application Comment\' is a table header component that can be
configured within the Application Manager results table using a Node
List component to display comments. Previously, this table header
component was available to be configured only in the Application Manager
screen. Now, this table header component is also available in the
Application Editor Screen (Parts) / (Vehicles). Users can configure the
component in the Application Editor Screen (Parts) / (Vehicles) \> Node
List \> Multi Edit Display Mode \> Headers parameter.

![](../../Resources/Images/Release%20Notes/92RN3.png)

PRODOC note: RDCUST- 3621Added support to PCdb Importer to handle PIES
EXPI attributes

Previously, step 1 of AutoCare Easy Setup created all of the PIES
Extended Product Information (EXPI)
(AC\_PIESExtendedProductInfoSegmentEXPI) attributes as either Text or
Numeric Text validation. But since PIES attribute data was moved to be
Coded Values provided within the PCdb file, the attributes that were
getting created by Easy Setup would never get updated.

Now, AutoCare Easy Setup has been updated to only create the
AC\_PIESExtendedProductInfoSegmentEXPI root attribute group. And PCdb
importer has been updated to create all of the attribute groups and
attributes, including List Of Values for the attributes that should have
LOV validation.

The newly created attributes reside within the following attribute
groups:

-   Core Returns
-   Hazardous Material
-   Part Item
-   Regulation
-   Return
-   Shipping
-   Stock

![](../../Resources/Images/Release%20Notes/92RN5.png)

The following attributes will now have LOV validation:

  ExpiCode   ExpiCodeDescription
  ---------- -------------------------------------------------
  CTO        Country of Origin (Primary)
  CTP        Country of Origin 2
  CTQ        Country of Origin 3
  CTR        Country of Origin 4
  CTS        Country of Origin 5
  EMS        Emission Code
  GCT        Green Certification, Regulation or Standard Met
  GPV        Additional Green Attributes
  LIF        Life Cycle Status Code
  LIS        Life Cycle Status Description
  MSR        SDR Required Flag
  NAF        NAFTA Preference Criterion Code
  NPC        National Popularity Code
  NPD        National Popularity Description
  PRC        Product Condition
  STA        Stock Status
  TAX        Taxable
  WD2        Warranty Distance UOM
  WS1        Warranty Special
  WS2        Warranty Special UOM
  WT2        Warranty Time UOM

**Existing Implementations:** For the users who do not have any
attribute values in the PIES EXPI attributes, manually delete all
attributes below the AC\_PIESExtendedProductInfoSegmentEXPI attribute
group, and import the latest PCdb file. The new attribute groups, LOVs,
and attributes will be created.

For the users who have existing attribute values for PIES EXPI
attributes, manually export the attribute values, change the validation
for the attributes that should be List Of Values instead of Text
validation, and reimport the attribute values.

Bugfixes {#bugfixes .MPNBugFix}
--------

### All Standards

PRODOC note: RDCUST- 3678Fixed the Edit Information dialog available
within all mapping rows to allow new text lines in a single entry

Previously, when entering a text in the Edit Information dialog
available within mapping rows, pressing the Enter key would directly
close the dialog instead of creating a new text line. The user had to
manually move the cursor in the editing field and press Enter to create
a new text line. Now, this issue is resolved and pressing the Enter key
would create a new line in the editor instead of closing the dialog.

PRODOC note: RDCUST- 3698 and 3650Corrected the inaccuracy of displaying
warning message in the Mapping Guide window of Application Mapping and
Object to Object Mapping

After the Source STEP path and Target STEP path is defined in the
Application Mapping and the Object to Object Mapping, the system
evaluates the validity match between the Source STEP path and the Target
STEP path. A hyperlink text explaining the reason for the validity match
/ mismatch gets displayed within the Mapping Guide window. Previously,
the system was failing to recognize and report some validity mismatch
and was erroneously reporting as \'Valid Configuration.\' Now, the
Mapping Guide is updated to correctly detect and report the validity
mismatch status for both Application Mappings and Object to Object
Mappings.

PRODOC note: RDCUST- 3698 and 3650Disabled \'Suppress\' checkbox option
available within the Mapping Guide window when there is a validity match
between Source and Target

All Mappings provide an option to suppress the validation mismatch
warning message by clicking on the \'Suppress\' checkbox in the Mapping
Guide window. Previously, the \'Suppress\' checkbox option was displayed
even if there was no validation mismatch warning message. Now, the
Mapping Guide window is updated to not to display the \'Suppress\'
checkbox option when there is a correct validity match.

PRODOC note: RDCUST- 3698 and 3650An info message is displayed when the
user hovers the cursor over the \'Suppress\' checkbox option available
within the Mapping Guide window

Now, the Mapping Guide window displays the info \'*Will visually
suppress any data type match warnings on the mapping. It has no
practical effect.*\' when the user hovers the cursor over the
\'Suppress\' checkbox option available within the Mapping Guide window.

PRODOC note: RDCUST- 3660Updated Mapper Configuration global settings to
be able to export / import Mapper Configurations

Previously, the Mapper Configurations were not able to be exported or
imported into the system. Now, the Mapper export / import has been fixed
to handle global settings correctly in order to be able to export /
import Mapper Configurations.

PRODOC note: RDCUST- RDCUST-3706Corrected \'Value editor\' dialog to
allow closing of the dialog in \'Application Competitor or OE Part
Numbers\' table header component

With the \'Application Competitor or OE Part Numbers\' table header
component configured within the Application Manager screen, when the
user clicks on the displayed Competitor / OE Part Number cell, the
\'Value editor\' dialog showing information on Competitor / OE Part
Numbers is displayed. Previously, this dialog did not include any
closing button to directly close the dialog. Now, two new buttons,
**OK** and **Cancel**, are made available within the dialog to
facilitate the closing of this dialog.

PRODOC note: RDCUST- RDCUST-3706Corrected \'Value editor\' dialog to
allow closing of the dialog in \'Suggested Part Number\' table header
component

With the \'Suggested Part Number\' table header component configured
within the Application Manager screen, when the user clicks on the
suggested part number cell, the \'Value editor\' dialog showing all the
suggested part number is displayed. Previously, this dialog did not
include a closing button to directly close the dialog. Now, two new
buttons, **OK** and **Cancel**, are made available within the dialog to
facilitate the closing of this dialog.

PRODOC note: RDCUST-3707Corrected Application Mapping plugin to be able
to execute business action configured within \'Business action executed
on new applications\' parameter

The \'Business action executed on new applications\' parameter available
within the Application Mapping plugin allow users to configure a
business action that runs while executing the Mapper Configuration setup
entity containing this Application Mapping plugin. Previously, some
configured business actions were not being executed. Now, this issue is
resolved to allow running all the business actions configured in the
\'Business action executed on new applications\' parameter.

PRODOC note: RDCUST- 3739 Corrected an Internal Server error that
displayed while sorting / filtering \'Application Approval Status\'
table header results in the Application Manager screen

Corrected an Internal Server error (*Error communicating with the STEP
server. Unexpected error. Please contact your system administrator*)
that displayed when the user clicks on the \'Application Approval
Status\' table header for sorting / filtering the missing applications
search results in the Application Manager screen. Now, the user can sort
/ filter all the search results (existing, missing, and existing and
missing applications) via \'Application Approval Status\' table header.

PRODOC note: RDCUST- 3739 Corrected Object to Object Mapping plugin to
not create any inactive references when \'Child\' option was selected
within \'Mapping type\' parameter

\'On Target,\' \'Child,\' and \'Reference\' are the options that can be
populated within the \'Mapping type\' parameter. The \'Reference Type\'
parameter is used only when the \'Reference\' option is selected within
the \'Mapping type\' parameter. This parameter allows the user to select
the reference type that should be used to establish the reference
between the Target object and the newly created objects. Previously,
when a reference type was defined within the \'Reference Type\'
parameter with the \'Reference\' option populated in the \'Mapping
type\' parameter, if the \'Mapping type\' is then changed to \'Child\'
option, then executing the Mapping plugin would still try use the
specified Reference Type to create inactive references. This would throw
a Mapping Error indicating that it failed to create the references. Now,
this issue is resolved to not create any inactive references.

![](../../Resources/Images/Release%20Notes/92RN2.png)

PRODOC note: RDCUST-3731Updated \'Application Suggestion Info\' table
header to no longer display an info icon if there is no info to give

For better visual display, \'Application Suggestion Info\' table header
component in the Application Manager Screen has been updated so that it
no longer displays an info icon
(![](../../Resources/Images/Release%20Notes/92RN4.png)) if there is no
info to give. Also, the info is no longer shown on mouse hover, but on a
click, so that the popup will appear (and disappear) on a click.

PRODOC note: RDCUST-3697Fixed NPE generated in the Application Mapping
plugin related to invalid validation paths

Previously when working in the Application Mapping plugin, a null
pointer error would be generated if you attempted to execute the
associated Mapper Configuration when the following condition was met:

-   The validation path included a reference, and the path had a typo of
    some sort and/or otherwise indicated a reference that does not exist

This has been corrected so that a proper runtime exception is thrown
that indicates the invalid reference.

PRODOC note: RDCUST-3613Corrected the Application Manager to retain the
state of the screen when a hyperlink is clicked and the user returns to
the Application Manager screen through back navigation button of the
browser

Based on the table headers configured in the Application Manager screen,
the search result displays many information (Parts, Vehicles, etc.) of
the application which are in the form of hyperlinks. Clicking on the
hyperlink would leave the Application Manager screen and navigate into
another defined screen. Previously, when the user navigates to another
screen by clicking on the hyperlink and then returns to the screen by
clicking on the Back navigation button of the browser, the Application
Manager screen was not holding the exact previous state of the search
cards in the screen. Now, the Application Manager screen is updated to
remember the state of the search cards so that the user can navigate
back to the Application Manager from other screens with the previous
state of the search cards retained.

PRODOC note: RDCUST-3710Corrected the way the \'Mappings Manager\' bind
handles empty target values

Previously, when using the addValueMapping method in the \'Mappings
Manager\' bind within the \'Execute JavaScript\' operation to map a
source value to an empty target value would result in a stack trace
error indicating:

com.stibo.core.domain.businessrule.plugin.BusinessRulePluginException:
com.stibo.core.domain.impl.value.FrontCompactSoftMultiValueImpl.addValue
cannot be invoked with an empty string value

Now, this issue is resolved to fix the option to delete multi values
with an empty string in mapper and no longer throw a stack trace error.

PRODOC note: RDCUST-3458Updated Mapping Guide window in all the Mapping
plugins to align and readjust to the browser size

For better visual display, the Mapping Guide window in all the Mapping
plugins has been updated so that all the Mapping Guide window should
automatically readjust to the browser size, or a vertical and horizontal
scroll bar is added so that they do not overlap one another.

### AutoCare

PRODOC note: RDCUST-3613Corrected the problem with exporting PIES Items
with ACES application containing multivalued attribute

Previously, when a PIES Item with ACES application containing a
multivalued attribute was included in the export, the PIES export would
generate a STEPXML file instead of a zipped PIES file. Now, this issue
is corrected to generate a zipped PIES file in every PIES export.

**Hotfix recipe compatible with STEP 9.1 MP6 + Automotive 9.1 MP2:**
[to:hotfix/365/issue-365937-HOTFIX-3315.spr]{.commandfont}

PRODOC note: RDCUST-3700Improved performance for Delta Calculation in
ACES Importer in Automotive 8.2 MP4

An existing fix makes it possible to correct the Oracle optimizer hint
used when doing attribute value searches in the drill-down search
framework. The same fix has been backported to Automotive 8.2 MP4 to
improve the performance of the Delta Calculation state in the ACES
Import.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2
MP4:**[to:hotfix/298/issue-298000-HOTFIX-2120.spr]{.commandfont}

PRODOC note: RDCUST-3684Updated VCdb Importer to handle complete VCdb
file of May month version

On May 31st, 2019, AutoCare introduced six new Vehicle Type Groups and
114 new Vehicle Types in its complete VCdb file. The May month complete
VCdb file did not contain any Make / Model / Year for the new Vehicle
Types, so when importing the complete VCdb file, it would create a lot
of empty vehicle type folders with no vehicle objects. The issue is
fixed to not create any vehicle type objects if the vehicle types do not
contain any Makes.

Users will not encounter this problem if the individual Light Duty VCdb
files are imported, this is because the new Vehicle Type Groups are not
included in the Light Duty VCdb file. And these new Vehicle Type Groups
are removed from the June complete VCdb file by AutoCare.

**Hotfix recipe compatible with STEP 8.2 MP3 + Automotive 8.2
MP4:**[to:hotfix/367/issue-367344-HOTFIX-3360.spr]{.commandfont}

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Enhancement of the PMDM for Automotive online help documentation is
continuous, and updates are released with each maintenance patch. When
these updates are significant and/or include high-level content
reorganizations, they are communicated within the patch notes.

PRODOC note: PRODOC- XXXNew Data Onboarding Solution documentation

The new **Data Onboarding Solution** section addresses using and
configuring the data Onboarding / Outboarding solution. It also includes
the details on Mapping functionalities and couple of generic use cases
to help understand the area of usage of this solution. The documents can
be found within the **Automotive Reference Guide**[ here]{.mcFormatColor
style="color: Blue;"}.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.21.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible with the following STEP 9.2 baseline
recipe:

[to:step/trailblazer/step-9.2-mp1.spr]{.commandfont}

Once an Automotive add-on is installed to a base STEP system, the base
system cannot be upgraded without upgrading the Automotive add-on at the
same time. Additionally, when upgrading any base STEP system that has
any Automotive add-on installed, both install recipes must be prepared
at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
