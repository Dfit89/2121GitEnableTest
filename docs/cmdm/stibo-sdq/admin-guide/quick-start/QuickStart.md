---
description: 'Stibo SDQ Admin Guide: Stibo SDQ requires a degree of
  setup that many Salesforce admins may already be undertaking. This
  quick start guide skips all of that setup.'
title: '\[%=Heading.AnyLevel%\]'
---

Introduction to the Stibo SDQ Admin Guide
=========================================

For experienced Salesforce administrators, the following guide will
provide a quick overview of how to start using Stibo SDQ. For more
information into the capabilities and functionality of Stibo SDQ, see
the **Stibo SDQ User Guide** or the expanded **Stibo SDQ Admin Guide**.
Prior to starting this setup, it is recommended that you send an API key
request via email to StiboSDQ\@stibosystems.com. This process may take
up to 48 hours to return the keys.

For the majority of this configuration guide, the examples will be
demonstrated in Lightning Experience.

Install Stibo SDQ
=================

As with any Salesforce app, install the Stibo SDQ app by searching for
\'Stibo SDQ\' in the Salesforce App Exchange. Select the option of
\'Install for Admins Only.\' This selection limits the configuration of
Stibo SDQ to just administrators.

![](../../../../../Resources/Images/CMDM/AdminGuide/InstallOptions-70%25.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/InstallOptions.png)

When installing, a list of external permissions will be requested.
Accept these permissions, and the app will install.

![](../../../../../Resources/Images/CMDM/AdminGuide/Initial%20Setup/Approve%20Third-Party%20Access.png)

This installation process may take over ten minutes. Salesforce will
email you when it is installed and ready.

Configure Desired Themes
========================

In Stibo SDQ, each feature package is called a theme. Each theme is
configured completely separate from the others.

In this guide, each theme\'s configurations will be explained. To
configure any of the themes, select \'Settings\' under the desired theme
from the left menu pane.

![](../../../../../Resources/Images/CMDM/AdminGuide/ThemeOptions-Reduced.png)

Once the first theme is configured, admin users will no longer see the
previous image. Instead, they will need to click into the settings of
each additional theme to configure.

![](../../../../../Resources/Images/CMDM/AdminGuide/Settings.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/ThemeOptions.png)

The following three themes are currently available:

-   Real-time Contact Data Validation Theme
-   Master Data Management Theme
-   Dun & Bradstreet Enrichment Theme

Real-Time Contact Data Validation Theme
---------------------------------------

Ensuring quality data requires knowing that the provided data is
actually valid. Through three different channels---address, email, and
phone validations---this theme allows for real-time, instant data
checking.

To validate user data, the following services are used:

-   Phone: https://www.hlrlookup.com
-   Email: https://api.experianmarketingservices.com
-   Address: https://api.everythinglocation.com

When selecting the \'Configure Data Quality\' option, the following
screen displays. This screen can also be reached via the \'Settings\'
option on the left menu pane.

![](../../../../../Resources/Images/CMDM/AdminGuide/DataQualityConfig.png)

It should be noted that you may add combinations of these data quality
items. The API keys and passwords should be in the email from
StiboSDQ\@stibosystems.com.

Under the Address settings, the **Default Country** field is a default
country to auto-populate when an end user enters address data as shown
in the **Address Validation** section ([here]{.mcFormatColor
style="color: Blue;"}) of the **Stibo SDQ User Guide**. When no
selection is made, the default country will display as \'United States
of America.\' Users may also select a different country if the default
does not apply to their entered address. Under the phone settings
section, the **Default Country Phone Code** field is a default country
phone code to auto-populate when an end user enters phone data as shown
in the **Phone Validation** ([here]{.mcFormatColor
style="color: Blue;"}) section of the **Stibo SDQ User Guide**. While it
is not required to enter a default country phone code, it is highly
recommended for users to specify one so that the system will have
something to fall back on if the field is not populated.

Once the Real-time Contact Data Validation theme is configured, you will
need to create / modify a user profile, some custom fields, and map the
Salesforce objects to the Stibo Systems objects. Also, some buttons need
to be overridden and some Visualforce pages need to be enabled. To do
these, see the following sections titled **Configure User Profile** for
permissions and to enable Visualforce pages, **Setting up Custom
Fields**, **Overriding Buttons**, and **Configure Mappings between
Salesforce and Stibo SDQ**.

MDM Theme
---------

Master Data Management users may connect to their STEP platform to
manage automatic removal of duplicate accounts and contacts as well as
perform associated data steward functions. To configure the MDM theme,
enter your STEP URL, STEP username, STEP password, and the associated
context that will be used as supplied by Stibo Systems. The **Search
Before Create** section uses the following fields:

-   **Threshold:** Matching threshold. This should be set to 50 or
    higher. The Threshold number should be determined as a part of
    tuning the STEP matching processes.
-   **Maximum Results Count:** 20 is the recommended setting.
-   **Account Matching Algorithm:** This information is supplied by
    Stibo Systems.
-   **Person Account Matching Algorithm:** This field is only displayed
    when the Person Account option is enabled within Salesforce. This
    information is supplied by Stibo Systems.
-   **Contact Matching Algorithm:** This information is supplied by
    Stibo Systems.

![](../../../../../Resources/Images/CMDM/AdminGuide/MDM-Settings.png)

Select **Save**, and the MDM theme will be configured. However, unless
remote sites were configured, this error will display:

![](../../../../../Resources/Images/CMDM/AdminGuide/ErrorMessageRemote.png)

Remote Site Settings

Navigate to the Remote Site Settings page by going to Setup \> Security
\> Remote Site Settings. Click the \'New Remote Site\' button.

![](../../../../../Resources/Images/CMDM/AdminGuide/RemoteSiteButton.png)

In the Remote Site Edit section, name the site whatever you wish. In the
Remote Site URL, enter the STEP host URL. Afterward, create a second
Remote Site Settings with the Salesforce host URL. Finally, add a third
remote site with the Salesforce host name prefixed with the package
namespace.

STEP Host

In the following example, the Remote Site Name is **Stibo** with the
Remote Site URL as **http://salesint-dev1.scloud.stibo.com**.

![](../../../../../Resources/Images/CMDM/AdminGuide/AddRemoteSite-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/AddRemoteSite.png)

Salesforce Host

In the following example, the Remote Site Name is **Self** with the
Remote Site URL as **http://eu9.salesforce.com**.

![](../../../../../Resources/Images/CMDM/AdminGuide/SalesforceRemoteSiteAccess-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/SalesforceRemoteSiteAccess.png)

Salesforce Host Prefixed with Package Namespace

In the following example, the Remote Site Name is **self\_prefix** with
the Remote Site URL as **https://stibo-dq.eu9.visual.force.com/**.

![](../../../../../Resources/Images/CMDM/AdminGuide/SalesforcePrefixRemoteSite-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/SalesforcePrefixRemoteSite.png)

One additional element to the MDM theme is that the **Connection
Status** section contains the Integration Endpoint Status. How this is
configured differs if your Salesforce organization uses Person Accounts
or not. The Stibo Systems contact will provide you the required
information.

Custom Settings

Navigate to the Custom Settings and \'Select Manage.\'

![](../../../../../Resources/Images/CMDM/AdminGuide/CustomSettingManage-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/CustomSettingManage.png)

Select Edit on the Custom Settings management screen.

![](../../../../../Resources/Images/CMDM/AdminGuide/CustomSettingsEdit-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/CustomSettingsEdit.png)

The settings edit screen will display. Select the
\'ApplicationModelsMaster\' checkbox, and fill in the
IntegrationEndpointsToTrack field with the information supplied by Stibo
Systems. Select \'Save.\'

![](../../../../../Resources/Images/CMDM/AdminGuide/IntegrationEndpointConfig-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/IntegrationEndpointConfig.png)

Verify

On the MDM theme settings screen, the associated integration endpoints
will be populated at the bottom.

![](../../../../../Resources/Images/CMDM/AdminGuide/EndpointActivated.png)

Once the MDM theme is configured, you will need to create / modify a
user profile, some custom fields, and map the Salesforce objects to the
Stibo Systems objects. To do these, see the following sections titled
**Configure User Profile** for permissions and to enable Visualforce
pages, **Setting up Custom Fields**, **Overriding Buttons**, and
**Configure Mappings between Salesforce and Stibo SDQ**.

To finish configuring the MDM theme, a number of setups must be
completed on the STEP side. These extra setup steps include making a
Salesforce System Administrator account and an associated Security token
available. Note that disabling this account or the Security token will
cause the MDM aspect of Stibo SDQ to fail. Contact Stibo Systems to
begin this work.

Dun & Bradstreet Enrichment Theme
---------------------------------

The Dun & Bradstreet Enrichment theme allows Dun & Bradstreet (D&B) to
enrich Salesforce accounts with D&B information. Using your D&B account
information, complete the settings on the Dun & Bradstreet Settings
page. Two fields requiring configuring are the Match Confidence field
and the Exclude field.

**Match Confidence:** Affects the DUNS Lookup action button. By default
this is set to \'10 (Very high)\'. When a user is performing a DUNS
lookup, they can change the Match Confidence setting.

The following Match Confidence options are available:

-   10 (Very high)
-   9 (High)
-   8 (Medium)
-   7 (Moderate)
-   6 (Low)
-   5 (Very Low)
-   4 (Absent)

**Exclude:** Affects the DUNS Lookup action button. By default all of
the options are enabled. When a user is performing a DUNS lookup, they
can change the Exclude settings. For more information, see the **Refine
Lookup Search Page** in the **Stibo SDQ User Guide**.

![](../../../../../Resources/Images/CMDM/AdminGuide/Dun&BradstreetSettings-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/Dun&Bradstreet/Dun&BradstreetSettings.png)

Select the **Save** button. The settings will be saved with the service
ready to validate data.

Once the D&B Enrichment theme is configured, you will need to create /
modify a user profile, some custom fields, and map the Salesforce
objects to the Stibo Systems objects. To do these, see the following
sections titled **Configure User Profile**, **Setting up Custom
Fields**, **Button Overrides** to create D&B actions and add them to the
Salesforce pages, and **Configure Mappings between Salesforce and Stibo
SDQ**.

Configuring User Profiles
=========================

Stibo SDQ introduces new features for standard users and Data Stewards.
Standard users must be given access to certain Salesforce objects, so
that they can get access to Real-Time Validation, D&B Enrichment, and
Search Before Create features. Data Stewards must be setup as System
administrators, so that they can access the Stibo SDQ Landing Page tab.
The standard users who need to create records and may need access to
some of the Visualforce pages will need a separate group with specified
privileges to just see and access what they need.

The MDM theme also requires a System Administrator account, see the
\'Verify\' subsection of the \'MDM Theme\' section for more details.

The following permissions are required for standard users:

-   Access to the Visualforce pages so that standard users can validate
    and enrich data and create new records
-   Access to the Error log object to allow these users to handle errors
    that may arise
-   Access to Apex so that the code may run properly

Select Profile
--------------

Navigate to the Users settings option in Setup. Then, create a new
profile or select an existing profile that should have access to the
Stibo SDQ native Salesforce functionality.

![](../../../../../Resources/Images/CMDM/AdminGuide/NewProfileOption.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/CloneProfile.png)

The next sections will show how to assign the appropriate permissions to
the standard user profile.

Visualforce Page Access
-----------------------

From the profile page, select the \'Enabled Visualforce Page Access\'
option. This action will send you to the \'Enabled Visualforce Page
Access\' panel. Select \'Edit\' to add permissions.

![](../../../../../Resources/Images/CMDM/AdminGuide/EnabledOptions.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/EnableVisualforcePanel.png)

Add the following permissions by pressing the \'Add\' arrow after
selecting the permission from the left pane. It will move to the right
pane. The permissions are:

1.  stibo\_dq.AccountValidation

2.  stibo\_dq.ContactValidation

3.  stibo\_dq.DnBAccountChangeCriteria

4.  stibo\_dq.DnBAccountEnrich

5.  stibo\_dq.DnBAccountLookup

6.  stibo\_dq.DnBAccountLookupEnrich

7.  stibo\_dq.DnBSyncContacts

8.  stibo\_dq.SBCAccountSearch

9.  stibo\_dq.SBCAccountSearchForm

10. stibo\_dq.SBCContactSearch

11. stibo\_dq.SBCContactSearchForm

![](../../../../../Resources/Images/CMDM/AdminGuide/AddPermissionsforVisualforce-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/AddPermissionsforVisualforce.png)

Select \'Save\' to add these permissions.

Error Log Object Access
-----------------------

Ensure that the Error Logs Custom Object has the creating and reading
permissions. To do that, edit the profile that was modified in the last
section.

Navigate to the \'Custom Object Permissions\' section, then check the
\'Read\' and \'Create\' boxes.

![](../../../../../Resources/Images/CMDM/AdminGuide/CreateObjectPermissions.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/CreateObjectPermissions2.png)

Selecting \'Create\' will automatically add the \'Read\' permission.

Select the \'Save\' button at the bottom to add these permissions.

Apex Class Access
-----------------

To add Apex Class Access, select the Enabled Apex Class Access option
near the top of the profile.

![](../../../../../Resources/Images/CMDM/AdminGuide/EnabledApexAccess.png)

Select the Edit button on the Enabled Apex Class Access panel, and add
the following permissions.

1.  stibo\_dq.AddressAutocomplete

2.  stibo\_dq.Validator

![](../../../../../Resources/Images/CMDM/AdminGuide/EditApexAccess.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/AddedApexClassPermissions.png)

Select \'Save,\' and the permissions will be added to the profile.

Setting Up Custom Fields
========================

The Validation Status and Validation Timestamp are required fields in
the Data Quality output section to create a record to show if a data
object was validated and when this validation was performed. However,
these two fields are not standard Salesforce fields and must first be
created with custom fields. The custom fields may be used in any
mapping. For an idea of the fields that may be needed for mapping, see
the address, email, and phone section of the **Configure Mappings**
section of this guide.

Users are strongly advised against manual modification of those fields\'
values. They are used for making the decision of whether validation
happens or not.

Users should prefix the Status and Timestamp field to be prefixed with
the unique identifier for the field / fields that are being validated in
addition to \'Validation\' and \'Status\' or \'Timestamp,\' depending on
which field you are creating. Status fields should be of type \'Text
Area\' and Timestamp fields should be of type \'Date / Time.\'

The following examples show how Validation Status and Validation
Timestamps work with various objects.

1.  Billing Address fields would look something like this. This should
    be repeated for all address types, such as Mailing, Other, etc.
    where address validation is activated.

-   Validation Status field

Field Label: Billing Address Validation Status

Field Name: Billing\_Address\_Validation\_Status

Field Type: Text Area

![](../../../../../Resources/Images/CMDM/AdminGuide/BillAddressStatus.png)

-   Validation Timestamp field

Field Label: Billing Address Validation Timestamp

Field Name: Billing\_Address\_Validation\_Timestamp

Field Type: Date/Time

![](../../../../../Resources/Images/CMDM/AdminGuide/BillAddressTimestamp.png)

1.  Email

-   Validation Status field

Field Label: Email Validation Status

Field Name: Email\_Validation\_Status

Field Type: Text Area

![](../../../../../Resources/Images/CMDM/AdminGuide/EmaiStatus.png)

-   Validation Timestamp field

Field Label: Email Validation Timestamp

Field Name: Email\_Validation\_Timestamp

Field Type: Date/Time

![](../../../../../Resources/Images/CMDM/AdminGuide/EmailTimestamp.png)

3.  Phone validation would look like this. This should be repeated for
    all phone types, such as Home, Mobile, etc., where address
    validation is activated.

-   Validation Status field

Field Label: Phone Validation Status

Field Name: Phone\_Validation\_Status

Field Type: Text Area

![](../../../../../Resources/Images/CMDM/AdminGuide/PhoneStatus.png)

-   Validation Timestamp field

Field Label: Phone Validation Timestamp

Field Name: Phone\_Validation\_Timestamp

Field Type: Date/Time

![](../../../../../Resources/Images/CMDM/AdminGuide/PhoneTimestamp.png)

If the user wants to map an API field to a custom field, it is required
that this a custom field is of type which can contain text (String)
(e.g., Text, Text Area, Text Area(Long), Text Area(Rich), etc.) because
all of the response field values are returned as String. The max length
of that field may vary based on the length of the result, which this
field may contain. Most fields will work fine with Text Area.

The exception of the API fields list would be the Validation Timestamp
where this is a Date / Time.

Button Overrides
================

The following section will detail how to create buttons configured
Salesforce actions. In this guide, those actions are changing how the
Create button works.

Create Override
---------------

Admins must customize the Salesforce \'New\' button. To do that, select
Setup \> Object Manager \> Account or Contact \> Buttons, Links, and
Actions \> New. The Override properties screen will display. Change the
Salesforce Classic Override to SBCAccountSearchForm for the Visualforce
page for Accounts. For Contacts, change the Salesforce Classic Override
to SBCContactSearchForm.

This has to be done for either the New Account or both New Account and
New Contact buttons. Person Accounts use Account\'s New button.

![](../../../../../Resources/Images/CMDM/AdminGuide/OverrideProperty.png)

Adding D&B Buttons
------------------

For the D&B Enrichment theme, some D&B buttons must be added to the
details pages.

Navigate to the Object Manager in Setup, and then, navigate to Account
object to add the buttons. In this example, the D&B buttons can be
configured via the Account page (Setup \> Object Manager \> Account \>
Buttons, Links, and Actions).

![](../../../../../Resources/Images/CMDM/AdminGuide/AddButtons.png)

Select the \'New Button or Link\' option to prompt the \'New Button or
Link\' page.

![](../../../../../Resources/Images/CMDM/AdminGuide/NewButtonorLinkOption.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/NewButtonOrLink-DnBLookup.png)

In the above screenshot, the DUNS Lookup button is created and, once
saved, will need to be added to the Account page. The Contact Sync and
Enrichment buttons will also need to be created. The parameters for
these buttons are:

D&B Lookup Button

Label: **DUNS Lookup**

Name: **DUNS\_Lookup**

Display Type: **Detail Page Button**

Behavior: **Display in existing window without sidebar**

Content Source: **Visualforce Page**

Content: **DnBAccountLookup \[stibo\_dq\_DnBAccountLookup\]**

D&B Enrichment Button

Label: **D&B Enrich**

Name: **DnB\_Enrich**

Display Type: **Detail Page Button**

Behavior: **Display in existing window without sidebar**

Content Source: **Visualforce Page**

Content: **DnBAccountEnrich \[stibo\_dq\_DnBAccountEnrich\]**

D&B Sync Contacts Button

Label: **D&B Sync Contacts**

Name: **DnB\_Sync\_Contacts**

Display Type: **Detail Page Button**

Behavior: **Display in existing window without sidebar**

Content Source: **Visualforce Page**

Content: **DnBSyncContacts \[stibo\_dq\_DnBSyncContacts\]**

After creating each button, they will need to be added to the page
layout. To do that, from the Setup \> Object Manager \> Account page,
select **Page Layouts**.

![](../../../../../Resources/Images/CMDM/AdminGuide/Page%20Layouts.png)

On the \'Account Layout\' entry, select the \'Edit\' option.

![](../../../../../Resources/Images/CMDM/AdminGuide/EditAccountLayout.png)

To add buttons to the Classic view, in the Account Layout panel, select
the \'Buttons\' option in the field to the left. Then, select the DUNS
Lookup, D&B Enrich, and D&B Sync Contacts buttons from the buttons
field. These buttons are dragged (left-click and hold the desired button
then, while holding left mouse button slide your mouse to the location)
into the \'Custom Buttons\' section of the Account Detail panel.

![](../../../../../Resources/Images/CMDM/AdminGuide/AddtoAccountLayout-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/AddtoAccountLayout.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/CustomButtonsAdded-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/CustomButtonsAdded.png)

To add buttons for Lightning Experience and the Salesforce1 mobile app,
switch to the \'Mobile & Lightning Actions\' option in the left pane.
Drag the DUNS Lookup, D&B Enrich, and D&B Sync Contacts buttons into the
Salesforce Mobile and Lightning Experience Actions box.

If only one view is used, then there is no requirement to add buttons to
the unused view.

![](../../../../../Resources/Images/CMDM/AdminGuide/MobileandLightingActions.png)

Once completed, the Salesforce Mobile and Lightning Experience will look
like this:

![](../../../../../Resources/Images/CMDM/AdminGuide/SalesforceMobileandLightningButtons-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/SalesforceMobileandLightningButtons.png)

Select the \'Save\' button above the buttons panel to save the changes.

![](../../../../../Resources/Images/CMDM/AdminGuide/SaveLayoutChanges.png)

Configure Mappings between Salesforce and Stibo SDQ
===================================================

Data enters Salesforce by way of user entry. For this data to be
validated, however, it needs to connect to Stibo SDQ. To create this
connection, Salesforce data objects need to be mapped to Stibo SDQ data
objects. Each theme will require its own mappings. Each mapping is
configured by selecting \'Mapping\' below each theme header.

![](../../../../../Resources/Images/CMDM/AdminGuide/MappingOptions.png)

Each mapping will only display when the theme is configured in Settings.

When opening the mapping section, mappings are not preconfigured, so you
must select the \'New Mapping\' button to begin.

![](../../../../../Resources/Images/CMDM/AdminGuide/NewMappings.png)

Select any of the desired options, and follow the email mapping example.
All mappings are configured in the same manner of selecting \'New
Mapping,\' naming it, defining the object type, then mapping the input
and output values.

![](../../../../../Resources/Images/CMDM/AdminGuide/AddEmailMapping-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/AddEmailMapping.png)

With each mapping, provide a name, object type, and input / output
mappings. The following sections will show the needed API fields to
match. More mappings can be added to each section by selecting the \'New
Mapping\' option at the top right of the screen.

The \'New Mapping\' option at the top of the mapping screen is different
from the \'+ New Mapping\' button at the bottom of the mapping screen.
The \'+ New Mapping\' button will add new fields for mapping where as
the \'New Mapping\' creates a new object that collects all the fields.

![](../../../../../Resources/Images/CMDM/AdminGuide/NewMappingButton.png)

\
The appended \'\_\_c\' indicates that the Salesforce field is a custom
one. Two required custom fields are for validation status and timestamp.
The timestamp field must be a date / time format. See the **Setting Up
Custom Fields** section of this document for information on this
process.\
\
In the following examples, any blue option is a suggestion and may be
deleted. The gray field cannot be replaced or removed.

### Real-time Contact Data Validation - Address Mapping

For addresses, the expected input and output API fields to match to are:

![](../../../../../Resources/Images/CMDM/AdminGuide/InputMappings-Address-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/AddressValdationMapping.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/OutputMappings-Address-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/OutputMappings-Address.png)

### Real-time Contact Data Validation - Phone Mapping

For phone numbers, the expected input and output API fields to match to
are:

![](../../../../../Resources/Images/CMDM/AdminGuide/PhoneValidationMapping-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/PhoneValidationMapping.png)

### Real-time Contact Data Validation - Email Mapping

For emails, the expected input and output API fields to match to are:

![](../../../../../Resources/Images/CMDM/AdminGuide/EmailMappings-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/emailMappings.png)

### Master Data Management Theme - Search Before Create Mapping

For \'Search Before Create\', the expected input and output API fields
to match are as follows. Included are the account, the contact, and
person account mappings.

![](../../../../../Resources/Images/CMDM/AdminGuide/AccountSBC_Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/AccountSBC.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/ContactSBC_reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/ContactSBC.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/PersonSBC.png)

### Dun & Bradstreet Enrichment Theme - Lookup Mapping

The output mappings will appear for the user on the DUNS Lookup Survival
Page. For more information, see the **DUNS Lookup Survival Page**
section of the Stibo SDQ User Guide.

![](../../../../../Resources/Images/CMDM/AdminGuide/LookupMappings-DnB-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/LookupMappings-DnB.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/LookupOutputMappings-DnB-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/LookupOutputMappings-DnB.png)

### Dun & Bradstreet Enrichment Theme - Enrichment Mapping

The following screenshot shows some 200+ possible options. The DUNS
Number must be present for D&B Enrichment.

![](../../../../../Resources/Images/CMDM/AdminGuide/DnBEnrichment-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/DnBEnrichment.png)

### Dun & Bradstreet Enrichment Theme - Contact Sync Mapping

For \'Contact Sync,\' the expected input API fields, which are from the
account, and output API fields, which are from the contact record, to
match to are as follows. The DUNS Number must be present for D&B Contact
Sync.

![](../../../../../Resources/Images/CMDM/AdminGuide/ContactSync-DnB-Reduced.png)

![](../../../../../Resources/Images/CMDM/AdminGuide/ContactSync-DnB.png)

Async Validation
================

To take full advantage of the data quality functionality, Data Quality
Mappings with enabled (Web-to-Object) flag are highly recommended, and
all of the validation triggers must be present and active. Select the
checkbox when mapping fields.

![](../../../../../Resources/Images/CMDM/AdminGuide/EnablingAsync.png)

Validation will be performed on:

-   Record Creation, if a value is entered for a field which is
    configured in a Data Quality mapping, and the Validation Status and
    Validation Timestamp fields are empty.

```{=html}
<!-- -->
```
-   Record Modification, if a value is modified for a field which is
    configured in a Data Quality mapping, or if any modification is made
    to the object and there is a field which is configured in a Data
    Quality mapping.

\
This is an asynchronous process and might take some time to be performed
after record saving. If a value is modified for a field which is
configured in a Data Quality mapping and the validation triggers are
present then, before the actual update of the record, Validation Status
and Validation Timestamp fields' values will be set to empty regardless
of if you have Async Validation (Web-to-Object) enabled. Then, only if
you have Async Validation (Web-to-Object) enabled, after a short delay,
validation will be performed and the record will be updated with
relevant data which is configured in the output section of the Data
Quality mapping.\
\
Validation will NOT be performed if the user is creating a record
through Search Before Create functionality and validation has already
been performed on the initial screen.

Account Validation Triggers

Before any input can be validated, triggers must be configured. To
configure triggers for the Account object:

Navigate to Setup \> Object Manager \> Accounts \> **Triggers**.

![](../../../../../Resources/Images/CMDM/AdminGuide/TriggerNavigation.png)

The Apex Trigger editing page will load. In the Apex Trigger field,
enter the following code snippet:

    trigger StiboAccountValidationStatus on Account (before insert, before update) {

``` {space="preserve"}
   if (Trigger.isInsert) {
```

``` {space="preserve"}
     stibo_dq.ValidatorTriggerService.prepareSObjects(Trigger.new);
```

``` {space="preserve"}
  } else if (Trigger.isUpdate) {
```

``` {space="preserve"}
      stibo_dq.ValidatorTriggerService.prepareSObjects(Trigger.new, Trigger.oldMap);
```

``` {space="preserve"}
  }
```

``` {space="preserve"}
}
```

Select \'Save,\' and navigate back to the Object Manager \> Account \>
**Triggers** page. Create another new trigger with the following code:

    trigger StiboAccountAsyncValidation on Account (after insert, after update) {

``` {space="preserve"}
 stibo_dq.ValidatorTriggerService.validateSobjects(Trigger.new);
```

    }

Save the trigger.

Contact Validation Triggers

Before any input can be validated, triggers must be configured. To
configure triggers for the Account object:

Navigate to Setup \> Object Manager \> Contact \> **Triggers**.

![](../../../../../Resources/Images/CMDM/AdminGuide/ContactTriggerNavigation.png)

The Apex Trigger editing page will load. In the Apex Trigger field,
enter the following code snippet:

    trigger StiboContactValidationStatus on Contact (before insert, before update) {

``` {space="preserve"}
   if (Trigger.isInsert) {
```

``` {space="preserve"}
     stibo_dq.ValidatorTriggerService.prepareSObjects(Trigger.new);
```

``` {space="preserve"}
  } else if (Trigger.isUpdate) {
```

``` {space="preserve"}
      stibo_dq.ValidatorTriggerService.prepareSObjects(Trigger.new, Trigger.oldMap);
```

``` {space="preserve"}
  }
```

    }

Select \'Save,\' and navigate back to the Object Manager \> Contact \>
**Triggers** page. Create another new trigger with the following code:

    trigger StiboContactAsyncValidation on Contact (after insert, after update) {

``` {space="preserve"}
 stibo_dq.ValidatorTriggerService.validateSobjects(Trigger.new);
```

    }

Save the trigger.

Scheduling a Task Synchronizer
------------------------------

To see and review Clerical review tasks in Stibo SDQ, the Task
Synchronizer must be started and scheduled. This process is done in the
Developer\'s Console.

The Developer\'s Console is most easily accessible from the Classic
Experience. This section will be done in that view.

In Salesforce, open the Developer\'s Console by selecting the user name
dropdown, then selecting \'Developer Console.\'

![](../../../../../Resources/Images/CMDM/AdminGuide/SelectDevelopersConsole.png)

In the Developer Console, select Debug \> **Open Execute Anonymous
Window**.

![](../../../../../Resources/Images/CMDM/AdminGuide/OpenExecutionWindow.png)

Enter the following string, modifying minutes and hour to the desired
time. In the following example, the time will run at 5:30PM, local user
time:

    String minutes = '30';

    String hour = '17';

    System.schedule('StepTaskSynchronizers', '0 ' + minutes + ' ' + hour + ' * * ?', new stibo_dq.TaskSyncScheduler());

Select \'Execute\' to run the code. Note, that if there is other text in
the console, you can highlight the above code then select the \'Execute
Highlighted\' to only run that selected code.

![](../../../../../Resources/Images/CMDM/AdminGuide/ExecuteApex.png)

To check the scheduled jobs, go to Setup \> **Scheduled Jobs**. These
can be unscheduled by deleting it from the UI.

![](../../../../../Resources/Images/CMDM/AdminGuide/ScheduledJobsUI.png)

Configuring the SDQ Tab
=======================

Once the MDM tab is configured, the Salesforce admin should add the
Stibo SDQ tab to the desired views. To add this tab to the top of the
Salesforce page:

Lightning Experience

Go to Setup \> App Manager \> 7 Sales.

![](../../../../../Resources/Images/CMDM/AdminGuide/SaleslineforLightningEditing.png)

At the end of the Sales line, select the dropdown arrow then select
**Edit**.

![](../../../../../Resources/Images/CMDM/AdminGuide/EditLightningView.png)

From the left menu pane, select **Selected Items**.

![](../../../../../Resources/Images/CMDM/AdminGuide/SelectedItemsLeftPanel.png)

The items are all the available tabs that can be added to the top. To do
that, select the items, then select the arrows between the two columns.

![](../../../../../Resources/Images/CMDM/AdminGuide/MoveTabsOver.png)

When a tab is added or removed, the Save and Cancel buttons will
display. When finished, select **Save**.

![](../../../../../Resources/Images/CMDM/AdminGuide/SelectSave.png)

Salesforce Classic

In the Salesforce Classic View, while in Setup, select the Plus symbol
(+) and then select **Customize My Tabs**.

![](../../../../../Resources/Images/CMDM/AdminGuide/SelectCustomizeMyTabs-SalesforceClassic.png)

From this page, select Custom App: **Sales**. The \'Available Tabs\'
column is a list of all tabs that can be added to the top tab panel. The
Selected Tabs column are the tabs that will display. To add or remove
tabs, use the arrows between the two columns. Select **Save** when
finished to save these changes.

![](../../../../../Resources/Images/CMDM/AdminGuide/SelectTabsClassic.png)

 

Because setup is customizable, and some features may not be available,
if your display is different than what is shown in this guide, email
StiboSDQSupport\@stibosystems.com for more information.

Original Starting Guide

1.  For more details on that process see the **Installing Stibo SDQ**
    section of this guide.
2.  Enable the necessary themes by following the respective
    configuration steps found within the following sections of this
    guide:

-   **Configuring the Real-time Contact Data Validation Theme**
-   **Configuring the Dun & Bradstreet Enrichment Theme**
-   **Configuring the Master Data Management Theme**

3.  Configure Access to Visualforce Pages as described in the
    **Configuring Visualforce Pages** section of this guide .
4.  Set up the desired custom objects in Salesforce that are going to be
    mapped to Stibo SDQ. See each of the mapping guides for what some of
    the mapping fields will be.
5.  Configure Mappings between Salesforce objects and Stibo SDQ as
    described in the Configuring Mappings section of this guide.
6.  Optionally configure the SDQ Tab as described in the **Configuring
    the SDQ Tab**.
