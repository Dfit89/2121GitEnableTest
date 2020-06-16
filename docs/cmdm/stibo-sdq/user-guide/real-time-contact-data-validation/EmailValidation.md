---
description: 'Stibo SDQ User Guide: With Stibo SDQ, email validation can
  be done in real-time, returning information such as when it was
  validated and confirmed active last.'
title: '\[%=Heading.AnyLevel%\]'
---

**Email Validation**
====================

Stibo SDQ\'s email validation instantly detects syntax errors, verifies
that a domain both exists and is reachable, and validates that the
domain is accepting mail. This ensures your organization can preserve
its sender reputation, because only valid and deliverable emails are
entered and stored in Salesforce when Stibo SDQ is enabled.

This section addresses:

-   Using Email Validation
-   Email Data Quality
-   Email Validation Statuses
-   Email Correction

Using Email Validation

Email validation can be configured to display when creating a new
Business Account, Person Account, and/or Contact.

Once configured, when an email field is viewed, it will display as any
other since there are no indications that the field can validate data.
However, once text is entered, and the cursor is moved off the email
field, then either a red icon displays indicating the email address is
invalid, or a green checkbox displays indicating the email address is
valid.

In the example below, a new contact screen is displayed with a field
labeled \'Email.\' The Email Verbose Description\' and the \'Email
Verbose Output\' will expand upon the results of the validation.

![](../../../../../Resources/Images/CMDM/User%20Guide/Create%20New%20Contact%20Email%20Field.png)

Once text is entered, and the cursor is moved off an Email field, then a
processing symbol may briefly display to the left of the field (as shown
below).

![](../../../../../Resources/Images/CMDM/User%20Guide/Email%20field%20processing.png)

In the example below, an invalid email address is entered into an Email
field, and the red icon displays along with a reason why the data was
invalidated.

![](../../../../../Resources/Images/CMDM/User%20Guide/Real-time%20Contact%20Data%20Validation/EVEmailRedValid.png)

Once a valid email address is entered into an Email field, then a green
checkbox icon displays, as shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Real-time%20Contact%20Data%20Validation/EVEmailGreenValid.png)

Users may also hover over the validation mark to see the verbose text as
well. This functionality means users do not need to map the Verbose
Description fields if they do not need reporting of these values.

![](../../../../../Resources/Images/CMDM/User%20Guide/Real-time%20Contact%20Data%20Validation/hovervalidation.png)

![](../../../../../Resources/Images/CMDM/User%20Guide/Real-time%20Contact%20Data%20Validation/hovervalidation2.png)

If the red or green icons are not displayed, then the field has not been
configured for email validation.

In the example above, one email field is displayed, however there is no
limit to the number of email validation configurations allowed. For more
information, see the **Configuring Mappings** section of the Enabling
Real-Time Data Validation topic ([here]{.mcFormatColor
style="color: Blue;"}), the Enable Master Data Management Theme topic
([here]{.mcFormatColor style="color: Blue;"}), or the Enable Dun &
Bradstreet Theme topic ([here]{.mcFormatColor style="color: Blue;"})
within the **Stibo SDQ Admin Guide**.

Email Data Quality

Once an email address is validated, the email metadata can be
automatically enriched by auto-populating fields configured by the
system administrator. This metadata is helpful when creating reports to
get an overview of email data quality. It is recommended that, at a
minimum, the following fields are applied:

-   Email Validation Status
-   Email Validation Timestamp (for the latest validation)

The following fields that may be displayed returning the reason for the
validation succeeding or failing.

-   Email Verbose Description
-   Email Verbose Output
-   Email Correction

Email Validation Statuses

The table below describes each email validation status. With the bound
Email Verbose Output and Email Verbose Description fields in the
mappings, these Output and Description columns will display as well.

Email Validation Status

Stibo SDQ Icon

Verbose Output

Description

Verified

![](../../../../../Resources/Images/CMDM/User%20Guide/IconGreen.png)

verified

Mailbox exists, is reachable, and not known to be illegitimate or
disposable.

Undeliverable

![](../../../../../Resources/Images/CMDM/User%20Guide/IconRed.png)

mailboxDisabled

Mailbox has been disabled.

mailboxDoesNotExist

Mailbox does not exist at this domain.

mailboxFull

Mailbox is full.

syntaxFailure

Syntax of the email address is incorrect.

Unreachable

![](../../../../../Resources/Images/CMDM/User%20Guide/IconRed.png)

unreachable

Domain is not responding to validation requests or does not have any
active mail servers.

unresolved

Domain cannot be resolved.

Illegitimate

![](../../../../../Resources/Images/CMDM/User%20Guide/IconRed.png)

illegitimate

Seed, spam trap, black hole, technical role account, or inactive domain.

roleAccount

Role accounts such as support@, sales@, info@.

typoDomain

Domain was close to a common domain and although it exists, it is highly
unlikely to be correct.

localPartSpamTrap

Known local portions of the email that may indicate spam traps.

Disposable

![](../../../../../Resources/Images/CMDM/User%20Guide/IconRed.png)

disposable

Domain is administered by a disposable email provider (e.g.,
Mailinator).

Unknown

![](../../../../../Resources/Images/CMDM/User%20Guide/IconGreen.png)

unknown

Unable to conclusively verify or invalidate address.

timeout

Request timed out due to the host domain not responding in time.

acceptAll

Domain is accept-all, thus the username cannot be validated.

relayDenied

Result was validated at the incorrect mail exchanger.

The \'Unknown\' Email Validation Status commonly identifies emails where
there are no indications that the email is not valid but cannot be
confirmed as good (i.e., when an email domain exists, but refuses to
answer), thus the green checkbox icon is used.
