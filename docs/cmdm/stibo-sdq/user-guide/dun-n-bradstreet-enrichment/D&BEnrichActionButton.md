---
description: 'Stibo SDQ User Guide: Once a DUNS Number is established,
  the DnB Enrich action button is used to automatically enrich the
  account with Dun & Bradstreet data that a system administrator has
  pre-configured. The DnB Enrich action button (shown below) can be
  accessed by clicking the action button dropdown arrow when viewing an
  account in Salesforce Lightning Experience. '
title: '\[%=Heading.AnyLevel%\]'
---

D&B Enrich Action Button
========================

Once a DUNS Number is established, the D&B Enrich action button is used
to automatically enrich the account with Dun & Bradstreet data that a
system administrator has pre-configured. The D&B Enrich action button
(shown below) can be accessed by clicking the action button dropdown
arrow when viewing an account in Salesforce Lightning Experience.

In order to enable the full functionality of the D&B Enrich Action it is
expected that a user has already performed a DUNS Lookup and assigned a
DUNS Number to the account being enriched. For more information, see the
**DUNS Lookup Action Button** topic ([here]{.mcFormatColor
style="color: Blue;"}) within this guide.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/D&BEnrichButton.png)

For more information on displaying the D&B Enrich action button, see the
**D&B Buttons** setup section of the **Stibo SDQ Admin Guide**.

When a user clicks the D&B Enrich action button, Stibo SDQ performs a
lookup against the D&B database. If the operation successfully
completes, then the account detail page will display with its data
enriched.

In the example below, the following fields were automatically updated
after the D&B Enrich button was clicked: Global Ultimate Duns Number,
Global Ultimate Business Name, Type, Industry, Website, Sales Revenue
Amount, Marketability Indicator, Primary SIC Description, FEIN
Registration Business Name, FEIN Tax ID Number, Competitor Organization
Sales Revenue, Financial Statement Period, Incorporation Year, and Major
Industry Category.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/D&BEnrichButtonResults.png)

If the selected account does not have a valid DUNS Number, and the D&B
Enrich button is clicked, then one of the following errors will display.

-   No match found for the requested DUNS Number.
-   Missing DUNS Number.

No Match Found for the Requested DUNS Number

If the DUNS Number provided within the account details is not sufficient
for the D&B Enrich process, then an error message will display as shown
below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/D&BEnrichment%20error%20message.png)

This could indicate the DUNS Number is incorrect. Click the **Back**
button (shown above) to return to the account details page, delete the
DUNS number, and use the DUNS Lookup action button to acquire a proper
DUNS Number.

Missing DUNS Number

If no DUNS Number is provided within the account details, then an error
will display as shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/Missing%20DUNS%20Number%20Error.png)

Click the **Back** button (shown above) to return to the account details
page, and use the DUNS Lookup action button to acquire a proper
DUNS Number.

If the DUNS Number displays within the account details, but the Missing
DUNS Number error occurs, then there is an empty DUNS Number passed to
the operation. When this occurs, the system administrator needs to
confirm the correct mapping configurations are in place.
