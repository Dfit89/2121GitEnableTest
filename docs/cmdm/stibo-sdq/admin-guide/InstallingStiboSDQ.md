---
description: 'Stibo SDQ Admin Guide: This Stibo SDQ topic details how to
  install the Stibo SDQ app in Salesforce.'
title: '\[%=Heading.AnyLevel%\]'
---

Installing Stibo SDQ
====================

As with any Salesforce app, install the Stibo SDQ app by searching for
\'Stibo SDQ\' in the Salesforce App Exchange.

1.  At least 48 hours prior to installing Stibo SDQ, request and
    purchase the necessary API Keys from StiboSDQ\@stibosystems.com.

Each theme has its own API key(s) and/or required unique information.
The Real-time contact data validation theme offers a separate API key
for the phone, address, and email validations. In other words, five API
keys are possible for full functionality across all three themes.

1.  Log in to the Salesforce.org where the Stibo SDQ app will be
    installed.
2.  Go to the Salesforce AppExchange \> Search for the Stibo SDQ app.

![](../../../../Resources/Images/Solution%20Enablement/SearchAppExchange.png)

1.  From the \'Stibo Systems Data Quality\' app card, select \'Get It
    Now.\'

![](../../../../Resources/Images/Solution%20Enablement/GetStiboSDQ.png)

1.  When installation starts, choose one of the three installation
    options:

-   Install for Admins Only
-   Install for All Users
-   Install for Specific Profiles

It is recommended to select the option of \'Install for Admins Only.\'
This selection limits the configuration of Stibo SDQ to just
administrators.

![](../../../../Resources/Images/CMDM/AdminGuide/InstallOptions-70%25.png)

![](../../../../Resources/Images/CMDM/AdminGuide/InstallOptions.png)

6.  When installing a list of external permissions will be requested.
    Accept these permissions, and the app will install.

![](../../../../Resources/Images/CMDM/AdminGuide/Initial%20Setup/Approve%20Third-Party%20Access.png)

This installation process may take a little while. Salesforce will email
you when it is installed and ready.

1.  Click the **Continue** button, and an installation progress message
    will display.

In the example below the progress message confirms \'Installing and
granting access to admins Only,\' because the \'Install for Admins
Only\' options was selected (as shown in step 4 above).

![](../../../../Resources/Images/CMDM/AdminGuide/Initial%20Setup/InstallStiboSDQDialog.png)

If the installation attempt exceeds 1 minute, then the following warning
will display:

![](../../../../Resources/Images/CMDM/AdminGuide/Initial%20Setup/InstallStiboSDQDialogTakingALongTime.png)

1.  Clicking the Done button will close the dialog and display the
    Salesforce Installed Packages page.

Once the installation package download is complete, an email will be
sent from support\@salesforce.com to the address associated with the
account profile used to login (as shown in step 2 above).

![](../../../../Resources/Images/CMDM/AdminGuide/Email%20Confirmation.png)

At any time during the installation process, the Salesforce Installed
Packages page can be used to confirm the progress of the installation.
Also, this page can be used to uninstall Stibo SDQ.

Next Steps

After the Stibo SDQ installation has completed, one or more Stibo SDQ
themes must be enabled. To enable Stibo SDQ themes, a system
administrator will need to access the Stibo SDQ App Landing Page and
then configure the settings for the desired themes.

Information on configuring each of the themes can be found within the
respective configuration sections of this guide:

-   **Configuring the Real-time Contact Data Validation Theme**
-   **Configuring the Dun & Bradstreet Enrichment Theme**
-   **Configuring the Master Data Management Theme**
