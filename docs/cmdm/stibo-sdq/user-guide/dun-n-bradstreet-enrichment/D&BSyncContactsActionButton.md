---
description: 'Stibo SDQ User Guide: Once a DUNS Number is established,
  the DnB Sync Contacts action button is used to search for potential
  contact persons. When appropriate contact candidates are found, this
  action button can be used to easily add the contact records to the
  Salesforce Business Account. The DnB Sync Contacts action button
  (shown below), can be accessed by clicking the action button dropdown
  arrow when viewing an account in Salesforce Lightning Experience. '
title: '\[%=Heading.AnyLevel%\]'
---

D&B Sync Contacts Action Button
===============================

Once a DUNS Number is established, the D&B Sync Contacts action button
is used to search for potential contact persons. When appropriate
contact candidates are found, this action button can be used to easily
add the contact records to the Salesforce Business Account. The D&B Sync
Contacts action button (shown below), can be accessed by clicking the
action button dropdown arrow when viewing an account in Salesforce
Lightning Experience.

In order to enable the full functionality of the D&B Sync Contacts
action button, it is expected that a user has already performed a DUNS
Lookup and assigned a DUNS Number to the account. For more information,
see the **DUNS Lookup Action Button** topic ([here]{.mcFormatColor
style="color: Blue;"}) within this guide.

If the user clicks the D&B Sync Contacts option from the dropdown and
the selected account does not have a valid DUNS Number, then an error
will display. For more information, see the **Missing DUNS Number**
section below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/D&BSyncContactsMenuOption.png)

For more information on configuring the D&B Contacts Sync action button
to display in Salesforce, see the **D&B Buttons** setup section of the
**Stibo SDQ Admin Guide**.

When a user selects the D&B Sync Contacts action button, Stibo SDQ
performs a contact lookup for principal contacts associated with the
given account using the DUNS Number against the D&B database. If the
operation fails, the user will be prompted for the missing DUNS Number.
If the operation successfully completes, then the \'Contacts sync\' page
will display.

Missing DUNS Number
-------------------

If a DUNS Number is not provided within the account details, a \'Missing
DUNS Number\' error will display (as shown below).

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/DB%20Sync%20Contacts%20Missing%20DUNS%20Number%20Error.png)

When this message displays, click the **Cancel** button to return to the
account details page, and use the DUNS Lookup action button to acquire a
proper DUNS Number.

If the DUNS Number displays within the account details, but the Missing
DUNS Number error message displays, then there is empty DUNS Number
passed to the operation. When this occurs the system administrator needs
to confirm the correct mapping configurations are in place.

D&B Contacts Sync Page
----------------------

The D&B Contacts sync page allows users to determine which contact data
from the Dun & Bradstreet database should be pulled into the Salesforce
account.

When a user selects the D&B Sync Contacts action button for an account
with a valid DUNS Number, Stibo SDQ performs a contact-lookup for
principal contacts associated with the given account. This is
accomplished by searching for the DUNS Number assigned to the current
account against the D&B database. The results display within the
Contacts sync page.

In the example below, the Contacts sync page consists of the following
elements:

1.  Group field
2.  Group name column
3.  Count column
4.  Group checkbox
5.  Back button
6.  Pull Contacts button

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/Contact%20Sync%20for%20Stibo.png)

1\. Group Field

The Group field parameter allows users to choose from a dropdown list
how contacts are grouped within the page.

In the example below, the contacts can be grouped by Job Title,
Organization, and Job Title Level.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/Group%20Field.png)

2\. Group Name Column

The group name column displays the group name based upon the Group field
selection.

In the example above, \'Job Title\' is selected for the Group field
parameter. Therefore the column is labeled \'JOB TITLE\', and the
contact groups are displayed in alphabetical order based upon their job
title grouping.

3\. Count Column

The count column displays with the \'COUNT\' label for all of the Group
field selections. The COUNT column displays the total number of
individual contacts within the group.

In the example above, many Job Title groups contain only one contact.
However it is easy to see the \'Account Executive\' group contains three
contacts.

4\. Group Checkbox

To the left of each group name is a checkbox. Once enabled, the group
will expand to display the following contact details:

-   NAME
-   JOB TITLE
-   RESPONSIBILITY
-   Displays additional information as to the contacts job
    responsibility.
-   MARKETABILITY
-   Indicates if the contact record does or does not satisfies D&B
    marketability rules.
-   EMAIL
-   Indicates if the contact record does or does not contain an email
    address.
-   PHONE
-   Indicates if the contact record does or does not contain a phone
    number

In the example below, the \'Account Executive\' group is enabled, and
three rows of contact data are displayed with each of their contact
checkboxes enabled.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/D&BSyncContactsGroupCheckboxEnabled.png)

For this screen, the red and/or green icons do NOT indicate contact data
validity. The green checkbox only indicates that contact information is
provided, and the red icon only indicates that contact data is NOT
provided.

By default when the group checkbox is enabled, the individual contact
checkboxes are enabled. Clicking on the individual checkbox when it is
enabled, will remove the blue checkbox, indicating it is not selected to
be pulled into Salesforce.

Multiple groups (or partial groups) can be selected.

5\. Back Button

Users can click the back button to return to the account details page.

6\. Pull Contacts Button

After selecting the desired contacts, a user can pull them into
Salesforce by clicking the **Pull Contacts** button. Once the contacts
have been pulled into Salesforce a confirmation screen will display.

In the example below, three contacts have been selected to be pulled
into the Stibo Systems, Inc. account within Salesforce, the Pull
Contacts button was clicked, and the confirmation screen displays as
shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/ContactSyncPullContactsButton.png)

PRODOC note: MEDU: When a selected contact has at least one Email or
Phone, the enrichment will be executed in CNTCT\_PLUS mode. Whereas when
a selected contact does not have neither an Email nor a Phone, the
enrichment will be executed in the more efficient CNTCT mode.

If the Pull Contacts button is selected, and a contact has not been
selected, then the \'Select at least one contact to pull\' error will
display (as shown below).

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/ContactSyncErrorWhenNoRecord.png)

After contacts have been successfully pulled from Dun & Bradstreet, they
can be found along with any preexisting contact data for the account.
