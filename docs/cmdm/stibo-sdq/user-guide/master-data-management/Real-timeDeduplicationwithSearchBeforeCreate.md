---
description: 'Stibo SDQ User Guide: With Stibo SDQ\''s powerful \''Search
  Before Create Technology,\'' users have the information they need to
  eradicate duplicates at the point of entry. Prior to creating a new
  record (Business Account, Person Account, and Contact), users are
  prompted to fill in relevant information, and a notification for
  potential duplicates (when applicable) will display for the user. '
title: '\[%=Heading.AnyLevel%\]'
---

Real-time Deduplication with Search Before Create
=================================================

With Stibo SDQ\'s powerful \'Search Before Create Technology,\' users
have the information they need to eradicate duplicates at the point of
entry. Prior to creating a new record (Business Account, Person Account,
and Contact), users are prompted to fill in relevant information, and a
notification for potential duplicates (when applicable) will display for
the user.

When searching for duplicate contacts, only contacts within the same
account are considered. In other words, if a Billy Button is associated
with account \'A,\' and a user creates a new contact named Billy Button
for account \'B,\' then the two Billy Button entries will not be
recognized as duplicates because they are assigned to different
accounts.

If no potential duplicate is identified for a specific contact and/or
account, then the user will be directed to the Contact Edit / Account
Edit page where additional data can be entered.

If one or more potential duplicates are identified for a specific
contact / account, then the user will be directed to a Contact Edit (or
Account Edit) page with an orange warning indicating: \'We found records
that look like potential duplicates. Select an existing record
instead?\'

![](../../../../../Resources/Images/CMDM/User%20Guide/SBC%20Potential%20Duplicates.png)

In the example above potential duplicates have been identified for the
contact \'Billy Button,\' and the Contact Edit page displays with the
orange potential duplicates warning.

Though the example below uses Contacts, the same functionality occurs
when Accounts are used.

Once a list of potential duplicates displays, the following options are
available for the user:

-   Click the **Back** button, returning to the New Contact page without
    creating a new contact.
-   Click the **Cancel** button, returning to the Contacts Recently
    Viewed without creating a new contact / account.
-   Upon review of the potential duplicate list, click on an existing
    contact record within the NAME column. This will open a different
    Contact Edit page, allowing users to view details in order to
    determine if the contact already exists. On this page, additional
    information for the contact and/or account can be viewed and/or
    entered.
-   Click the \'**Create Contact anyway**\' button, the New Contact
    Salesforce page will display, and additional information for the new
    contact can be entered.
