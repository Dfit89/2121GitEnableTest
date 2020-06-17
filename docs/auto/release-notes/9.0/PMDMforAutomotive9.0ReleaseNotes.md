---
description: 'Automotive Solution: PMDM for Automotive 9.0 Release
  Notes'
title: PMDM for Automotive 9.0 Release Notes
---

PMDM for Automotive 9.0 Release Notes {#pmdm-for-automotive-9.0-release-notes style="text-align: center;"}
=====================================

Release Date: July 6, 2018 {#release-date-july-6-2018 style="text-align: center;"}
--------------------------

Document Overview
-----------------

Stibo Systems is excited to share the Automotive 9.0 solution, built
using the recently released STEP 9.0 MP2 platform.

### Audience

This document is intended for use by active PMDM for Automotive users
and serves to describe the new and enhanced features provided by the
release. It does not serve as a replacement for the STEP Online Help nor
the Automotive Quick Start Guide and Automotive Reference Guide, which
include additional information on previously existing system
functionality, as well as more detailed explanations and step-by-step
instructions for use, when applicable.

### Content

This document describes the changes between the current and previous
release.

Some functionality is controlled via component activation, which may
include licenses and/or component installations, and may not be
available on a particular system. Please direct questions to your Stibo
Systems account manager or partner manager.

Announcement {#announcement .MPNDocumentation}
------------

Application Editor (Application Search Screen) deprecated / withdrawn

To improve overall functionality and the user experience when editing,
viewing, and/or managing applications, the \'Application Manager
Screen\' has been created to replace the functionality previously
offered by the automotive tool known as the \'Application Editor.\' The
tool was created using the \'Application Search Screen\' component. Now,
the \'Application Search Screen\' has been deprecated / withdrawn, and
is no longer supported. Instead, please use the \'Application Manager
Screen.\' Additionally, it is important to note that a separate
component \'Application Editor Screen\' does exist and is used to view
and edit part and assembly applications.

For more information, see the new **Application Manager** section of the
**Automotive Reference Guide** found within the **Solution Enablement**
section of **STEP Online Help**[ here]{.mcFormatColor
style="color: Blue;"}.

Additionally, customers should read the Release Notes for STEP 9.0, the
June (MP1) and July (MP2) Maintenance Patch Notes, as well as the
Platform and Software Support Changes release note for additional
information[ here]{.mcFormatColor style="color: Blue;"}.

With every STEP release, typically some STEP components get deprecated,
removed, or desupported for various reasons. Anything with a user impact
has been called out in the applicable release note and may require
special attention and user action before upgrading to STEP 9.0 MP2.

New Features {#new-features .MPNNewFeatures}
------------

Stibo Systems has enhanced the PMDM for Automotive solution in a number
of areas:

### All Standards

PRODOC note: MEDU PRODOC- 1395 New Competitor and OE Numbers Solution

The automotive functionality now includes a competitor and OE numbers
solution that makes it easy to maintain data related to both competitor
and OE part numbers. This not only helps users more easily view, edit,
and create competitor and/or OE part number references for specific
parts, but also suggest potential matches. In other words, when
configured, STEP can suggest potential matches for competitor and/or OE
part numbers based on existing competitor and/or OE part number
references and/or matching part numbers within STEP. This occurs when a
part is selected, STEP looks at the configured Reference Types and
displays their targets, attribute values, and/or metadata.

![](../../Resources/Images/Competitor%20OE%20Number/1.jpg)

When these are configured as shown above, Web UI users can:

1.  View existing competitor and/or OE part number references and
    related data.
2.  View competitor and/or OE part number reference suggestions and
    related data.
3.  View information about the suggested part number.
4.  Add competitor and/or OE part number references manually.
5.  Add competitor and/or OE part number references from suggestions.
6.  Remove existing competitor and/or OE part number references.
7.  Remove competitor and/or OE part number references from suggestions.

For more information see the **Competitor and OE Numbers Solution**
section of the **Automotive Reference Guide** found within the
**Solution Enablement** section of **STEP Online Help**[
here]{.mcFormatColor style="color: Blue;"}.

AutoCare {#autocare .RNNoTOC}
--------

PRODOC note: MEDU RDCUST-2929 ACES conditions / attribute names no
longer use the ACES prefix

To improve users\' ability to find and view ACES conditions /
attributes, the default attribute names are no longer prefixed with
\'ACES.\' When Easy Setup actions are used for new environments, the
attributes\' names will no longer be prefixed with \'ACES.\'

In the example below, the AutoCare ACES attributes are displayed in
System Setup before and after this change. On the left, the \'ACES Body
Num Doors\' attribute name is selected, and on the right, the same
attribute is selected, but displays as \'Body Num Doors.\'

![](../../Resources/Images/Release%20Notes/ACESPrefixREmoved.jpg)

**Existing Implementations**: Optionally, manually update the name of
the ACES attributes to no longer contain the \'ACES\' prefix.

TecDoc {#tecdoc .RNNoTOC}
------

PRODOC note: MEDU RD-11591 Omit search structures

To reduce the amount of unused TecDoc data being imported, a new
parameter (Omit search structures) has been added to the TecDoc
Reference Importer. Previously, all Search Trees were imported, and now
these can all be omitted. The parameter is available as a checkbox when
editing the \'TecDoc Reference Import Conversion\' Business Rule within
the TecDoc Reference import workflow. The parameter is displayed in the
second screenshot below.

PRODOC note: MEDU RD-11468 Import only the generic articles needed

To reduce the amount of unnecessary TecDoc generic articles being
imported into STEP, the TAF conversion service now includes a new filter
parameter (Generic article filter). Previously, all of the generic
articles had to be imported, and now only those selected within the
filter are imported. The parameter is available when editing the
\'TecDoc Reference Import Conversion\' Business Rule.

In the example below, the 0003 Product Hierarchy is shown including many
Articles, the editing of the \'TecDoc Reference Import Conversion\'
Business Rule is displaying the \'Generic article filter\' parameter
with the \'Air Mass Sensor\' and \'Glow Plug\' generic articles selected
for import, and the results are the 0003 Product Hierarchy is shown with
only the \'Air Mass Sensor\' and \'Glow Plug\' articles.

![](../../Resources/Images/TecDoc/1.jpg)

![](../../Resources/Images/TecDoc/TecDocArticleFiltering.jpg)

![](../../Resources/Images/TecDoc/3.jpg)

Bugfixes {#bugfixes .MPNBugFix}
--------

PRODOC note: MEDU RDCUST-2969 Corrected exception handling when running
multiple import threads

Previously, the \'Set Import Status Attributes\' business action had
exception handling that erroneously caused the importer to fail in some
scenarios where import threads were run in parallel. Users experienced
an error message of : \'Transaction already marked for rollback only.\'
Now, the exception handling has been corrected, and the importer should
not erroneously display this error.

[PRODOC note: MEDU RDCUST-2943]{style="font-weight: normal;"} Corrected
line break display when using the Application Set Assembly component
within an Application Manager

Previously, when multiple attributes were added to the Attribute List
parameter in the Application Set Assembly header component used within
the Application Manager, the attribute names and values were displayed
in the results table without any line breaks. Now, the attribute name is
displayed in bold, the non-bold attribute value follows, and each new
attribute is displayed on a new line.

PRODOC note: MEDU RDCUST-2949 Corrected the display of the Create
Application button when \'Lazy\' loading is enabled on a Sub Screen Tab
Page

Previously, when the \'Lazy\' loading parameter was enabled on a Sub
Screen Tab Page that was used to display an Application Editor Screen,
the Create Application action button would no longer display. This has
been corrected so that the Create Application button displays whether or
not the \'Lazy\' parameter is enabled.

AutoCare

PRODOC note: MEDU RDCUST-2768 Corrected the way the VCdb importer
handles model IDs

Previously, the VCdb importer would create the Model ID based on the
Model Name value, and did not consider the Make. This is an issue for
those Model Names that occur across multiple makes, because it results
in those Models being referenced to the wrong Make classification
folder.

For example, the 200 model is offered by many different manufacturers
(i.e., Audi, Chrysler, Griffith, Mercedes-Benz, Packard). Upon import,
the Audi 200 would be created as a child classification folder beneath
the Audi classification folder (since it was the first make with the 200
model listed within the import). Then when the Chrysler 200 was
processed, it would erroneously be added to the Audi 200 classification
folder.

Now, the importer considers the Make in the Model ID structure, and the
Model Names that occur across multiple makes are properly created within
their own Make classification folder.

Though this fix was implemented for 8.3 MP1, it has also been backported
to STEP 8.2 MP3 + Automotive 8.2 MP4. The recipe to patch with 8.2 MP3
is: [to:hotfix/317/issue-317137-HOTFIX-2540.spr]{.commandfont}

TecDoc

PRODOC note: MEDU RDCUST-2987 Corrected how the importer handles
TD\_LOV-DocumentType values

Previously, the TD\_LOV-DocumentType values were created when the Easy
Setup actions are completed, but the Reference data importer was not
reading and updating the values upon import. Now, the Reference Data
importer reads and updates STEP with the TD\_LOV-DocumentType values
from TAF table 014.

PRODOC note: MEDU RDCUST-2954 Corrected an exception that was thrown
when using an Application Manager component without TecDoc Reference
data privileges

Previously, an exception error would display when a user without TecDoc
Reference data privileges used an Application Manager Condition Header
Component within Web UI. Now, this is resolved so that users do not
experience an error message.

PRODOC note: MEDU RDCUST-2985 Correct Country group ID created

Previously, during the conversion state errors would occur because the
correct country group ID was not created. Now, Easy setup actions will
create the correct Country group ID (TD\_CountryGroup) and add it as a
valid target type for \'TD\_SupplierArticleToCountry\' classification
reference.

**Existing Implementations**: Manually add the \'TD\_CountryGroup\' as
the valid target type for the \'TD\_SupplierArticleToCountry\'
classification reference.

Documentation Updates {#documentation-updates .MPNDocumentation}
---------------------

Improve Application Manager search accuracy with automotive plugins

A new section of documentation has been added to help users improve
search accuracy when using the Application Manager. When a business
condition is configured with the \'Check path for missing attribute\'
plugin, search result accuracy can be improved for specific part types.
This is accomplished by allowing the data model to include a
relationship between conditions on applications and different vehicle
configurations. This can be helpful when specific part types do not
apply to certain vehicle configurations. Additionally, it allows the Web
UI Application Manager to search for applications with conditions for
all sub models. For more information, see the **Business Condition:
Check Path for Missing Application** topic[ here]{.mcFormatColor
style="color: Blue;"} within the **Business Rules** section of the
**Automotive Reference Guide** found within the **Solution Enablement**
section of **STEP Online Help**.

This topic is currently available via the Automotive Reference Guide
PDF, but will not be available in STEP Online Help until 9.0 MP3 is
released.

Automotive guides no longer include Application Editor section

Now that the Application Search Screen (also known as \'Application
Editor\' ) is no longer supported, the \'Application Editor\' section
has been removed from all Automotive documentation. For information on
the all new Application Manager Screen, see the **Application Manager**
section[ here]{.mcFormatColor style="color: Blue;"} of the **Automotive
Reference Guide** found within the **Solution Enablement** section of
**STEP Online Help**.

Improve efficiency and automate some actions with automotive-specific
Business Rules

To improve efficiency, and potentially automate some actions, several
automotive business rule plugins are available. For more information,
see the **Automotive Business Rule Plugins** section[
here]{.mcFormatColor style="color: Blue;"} of the **Automotive Reference
Guide** found within the **Solution Enablement** section of **STEP
Online Help**.

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive baseline update can be installed with the following
recipe:

[to:automotive/7.0/automotive-7.0.10.spr]{.commandfont}

The above recipe is only compatible with the core 9.0 MP2 baseline
([to:step/trailblazer/step-9.0-mp2.spr]{.commandfont}).

Please contact your Stibo Systems account manager or your partner
manager for additional information on upgrading to or installing the
PMDM for Automotive 9.0 release.
