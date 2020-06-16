---
description: 'Stibo SDQ User Guide: With Stibo SDQ, real-time phone
  validation to check for the validity of an address is conducted
  globally. Additionally, the validation status can be captured along
  with the validation timestamp.'
title: '\[%=Heading.AnyLevel%\]'
---

Address Validation
==================

With Stibo SDQ, address validation is powered by typeahead search
technology, which enables users to capture a complete and verified
address with minimal key strokes. Address validation is available when
creating Business Accounts, Person Accounts, and Contacts. Address
information is verified against authoritative data sources for over 248
countries including USPS, Canada Post, Royal Mail, Australia Post, La
Poste, New Zealand Post, and Deutsche Post.

This section addresses:

-   Using Address Validation
-   Address Data Quality
-   Address Quality Index
-   Address Validation Statuses

Using Address Validation

Once configured, when users create Business Accounts, Person Accounts,
and/or Contacts using the same Salesforce button they have always used,
they will be able to select valid addresses from an auto-complete
dropdown of any address in the world.

In the example below, within the Search Address Country field, \'United
States of America\' is selected (or is set as the default), and the
first few numbers and letters of an address have been entered. Based
upon the text entered, the three addresses within the selected country
that match the entered text will display in the dropdown. In other
words, by entering a few characters and then selecting the correct
address, a user can easily populate the contact record with valid
address information.

![](../../../../../Resources/Images/CMDM/User%20Guide/Real-time%20Contact%20Data%20Validation/AVAddressTypeAhead.png)

In the example above, the validated address is selected from the
dropdown, and will have either a Verified or Unverified address
validation status. If the correct address does not display within the
dropdown, then users can disable address validation or select an address
that is close to the correct address and then edit the address further.
When address validation is disabled the validation status will be set to
\'Entered Manually.\'

In the example above, one address field is displayed, however there is
no limit to the number of contact data validation configurations
allowed. For more information on how to configure fields for contact
data validation, see the **Configuring Mappings** section of the
Enabling Real-Time Data Validation topic ([here]{.mcFormatColor
style="color: Blue;"}), the Enable Master Data Management Theme topic
([here]{.mcFormatColor style="color: Blue;"}), or the Enable Dun &
Bradstreet Theme topic ([here]{.mcFormatColor style="color: Blue;"})
within the **Stibo SDQ Admin Guide**.

Address Data Quality

Once a valid address is selected, the address data is automatically
enriched by auto-populating fields configured by the system
administrator. These are helpful when creating reports to get an
overview of address quality. At a minimum, the following custom fields
are recommended for each address type that should be validated (i.e.,
Billing, Shipping, Mailing):

-   Address Validation Status
-   Address Validation Timestamp (for the latest validation)
-   Address Verification Code
-   Address Quality Index (AQI)

When the suggested custom fields are configured, it is easy for users to
view the important information about the record. In the example below,
the following Billing related fields are displayed with the contact
details: Address Validation Timestamp, Validation Status, Quality Index,
and Verification Code.

![](../../../../../Resources/Images/CMDM/User%20Guide/Billing%20Address%20Validation%20Fields.png)

Address Quality Index

The table below describes each of the available Address Quality Indexes
(AQI\'s).

  AQI   Address Quality   Explanation
  ----- ----------------- -----------------------------------------------------------------------------
  A     Excellent         Verifiable to at least Premise-level without changes.
  B     Good              Verifiable to at least Thoroughfare-level with minor changes.
  C     Average           Verifiable to at least Locality-level with moderate changes.
  D     Poor              Only verifiable to at least Locality-level with more than moderate changes.
  E     Bad               Not verifiable.

Address Validation Statuses

How a user enters an address affects the address validation status. The
table below describes each address validation status and the details
associated with that status.

Address Validation Status

Description

Verified

A user has selected the validated address from a dropdown.

Address has a Loqate AQI value.

Address has an address quality index (AQI) of Excellent or Good.

Address is verifiable to at least Premise-level without changes or
Thoroughfare level with minor changes.

Unverified

A user has selected the validated address from a dropdown.

Address has a Loqate AQI value.

Address has an address quality index (AQI) of Average, Poor, or Bad.

Address is verifiable to at least Thoroughfare-level with minor changes,
Locality level with average changes, or Locality level with more than
moderate changes.

Entered Manually

[When an address has an Entered Manually validation status, then a user
has disabled address validation, by clicking the
]{style="font-size: 11pt;"}**Enter Address Manually**[ checkbox (as
shown below).]{style="font-size: 11pt;"}

![](../../../../../Resources/Images/CMDM/User%20Guide/Real-time%20Contact%20Data%20Validation/AVAddressInfo.png)

User Preferred

When a user edits an address field after validation, then the validation
status field will be updated with \'User Preferred.\' In the example
below, the \'Billing Address Validation Status\' field has been
configured to store the billing address validation status. Since a user
has edited the Billing Address, the validation status value is set to
\'User Preferred.\'

![](../../../../../Resources/Images/CMDM/User%20Guide/User%20Preferred.png)

For more information on configuring fields for address data enrichment,
see the **Configuring the Real-time Contact Data Validation** section of
the **Stibo SDQ Admin Guide**.
