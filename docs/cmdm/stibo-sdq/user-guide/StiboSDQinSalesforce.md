---
description: 'Stibo SDQ User Guide: Stibo SDQ offers native in-app
  functionality that can be used within many existing contact
  data-related Salesforce pages, and the Stibo SDQ Landing Page where
  Stibo SDQ settings, mappings, and clerical review functionality can be
  accessed. Where and how the functionality is used is ultimately up to
  the system administrator, and the configurations they apply. '
title: '\[%=Heading.AnyLevel%\]'
---

Stibo SDQ in Salesforce
=======================

Stibo SDQ offers native in-app functionality that can be used within
many existing contact data-related Salesforce pages, and the Stibo SDQ
Landing Page where Stibo SDQ settings, mappings, and clerical review
functionality can be accessed. Where and how the functionality is used
is ultimately up to the system administrator, and the configurations
they apply.

This section describes the Stibo SDQ Native In-app Functionality and
Stibo SDQ Landing Page.

Stibo SDQ Native In-app Functionality
-------------------------------------

The native in-app functionality offered by Stibo SDQ can be used within
many existing contact data-related Salesforce pages. This includes the
following functionality:

-   Email Validation
-   Address Validation
-   Phone Validation
-   Search Before Create

For example, when the Real-time Contact Data Validation theme is
configured, the native in-app functionality can change the way users
create Business Accounts, Person Accounts, and Contacts by including new
Visualforce pages in the account / contact creation workflow. This
allows users to see whether contact data is valid upon entry. For more
information, see the **Real-time Contact Data Validation** section
([here]{.mcFormatColor style="color: Blue;"}) of this guide.

In the example below, Stibo SDQ phone, email, and address validation
functionality are displayed for an end user within a Salesforce
Visualforce page. Display configurations may vary widely.

![](../../../../Resources/Images/CMDM/User%20Guide/New%20Contact%20Page%20with%20Validation%20and%20Address%20Drop%20down.png)

Additionally the Search Before Create page can display any potential
Account and/or Contact duplicates before the new account and/or contact
is created. For more information, see the **Real-time Deduplication with
Search Before Create** topic ([here]{.mcFormatColor
style="color: Blue;"}) within the **Master Data Management** section of
this guide.

In the example below potential duplicates have been identified for the
contact \'Billy Button,\' and the Contact Edit page displays with the
orange potential duplicates warning.

![](../../../../Resources/Images/CMDM/User%20Guide/SBC%20Potential%20Duplicates.png)

Stibo SDQ Landing Page
----------------------

The Stibo SDQ Landing Page is where system administrators can configure
Stibo SDQ settings and mappings, and Data Stewards can access the Stibo
SDQ clerical review tasks, merge functions, and/or reporting features
when the Master Data Management theme is configured. For more
information, see the **Master Data Management** section
([here]{.mcFormatColor style="color: Blue;"}) of this guide.

Once the Stibo SDQ Landing page is accessed, the Stibo SDQ navigation
menu is visible along the left side of the screen. Below is an example
of how the Stibo SDQ Landing Page and menu options will display prior to
any themes being configured. The menu options are separated into the
following sections: DATA QUALITY, MASTER DATA MANAGEMENT, DUN &
BRADSTREET, and ADVANCED. For details on the menu options available when
a theme is configured, see the themes configuration section of the
**Stibo SDQ Admin Guide**.

![](../../../../Resources/Images/CMDM/User%20Guide/StiboSDQLandingPageNoThemeApplied.png)

Because system administrators can configure the Stibo SDQ tab
differently for each Salesforce instance, the tab may be found within
different Salesforce views. In the example above, the Stibo SDQ tab has
been configured to display to the right of the Home tab within the Sales
app.

After any one of the themes are configured, the configure buttons will
no longer display as shown above. Each themes settings (including the
API key fields) can be accessed by selecting the \'Settings\' menu
option beneath the desired theme.

Using Salesforce Classic to Access the Stibo SDQ Landing Page

Accessing the Stibo SDQ Landing Page can be done using either Salesforce
Classic or Lightning Experience. This section describes how to access
the Stibo SDQ Landing Page using Salesforce Classic.

1.  Login to Salesforce \> Click the add a new tab (**+**), and the
    \'All Tabs\' page will display (as shown below).
2.  Find the \'Stibo SDQ\' tab.

```{=html}
<!-- -->
```
1.  Click the **Stibo SDQ** tab link, and the Stibo SDQ Landing Page
    will display.

![](../../../../Resources/Images/CMDM/AdminGuide/Initial%20Setup/AllTabsClassicViewStiboSDQ.png)

For easy access, it is recommended that system administrators add the
Stibo SDQ tab to a Salesforce view.

Using Lightning Experience to Access the Stibo SDQ Landing Page

Accessing the Stibo SDQ Landing Page can be done using either Salesforce
Classic or Lightning Experience. This section describes how to access
the Stibo SDQ Landing Page using Lightning Experience.

1.  Login to Salesforce \> Click the Launcher button, and the Launcher
    dialog will display (as shown below).

```{=html}
<!-- -->
```
1.  In the \'All Items\' section, click the Stibo SDQ link, and the
    Stibo SDQ Landing Page will display.

![](../../../../Resources/Images/CMDM/User%20Guide/AccessStiboLandingPageLightningExperinceAppLaunch.png)

For easy access, it is recommended that system administrators add the
Stibo SDQ tab to a Salesforce view.
