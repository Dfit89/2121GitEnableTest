---
description: 'Stibo SDQ User Guide: With Stibo SDQ, real-time phone
  validation to check for the validity of a mobile number is conducted
  globally. Additionally, the validation status can be captured along
  with the validation timestamp.'
title: '\[%=Heading.AnyLevel%\]'
---

**Phone Validation**
====================

With Stibo SDQ, real-time phone validation to check for the validity of
a mobile number is conducted globally. Additionally, the validation
status can be captured along with the validation timestamp.

This section addresses:

-   Using Phone Validation
-   Handling Country Codes
-   Phone Data Quality
-   Phone Validation Statuses

Land-line phone number validation is also available for a number of
countries including US / CAN.

Using Phone Validation

Phone validation can be configured to display when creating a new
Business Account, Person Account, and/or Contact.

Once configured, when a phone field is viewed, it will display as any
other. However, once text is entered, and the cursor is moved off of the
phone field, then either a red icon displays indicating the phone number
is invalid, or a green checkbox displays indicating the phone number is
valid.

In the example below, a new contact screen is displayed with a field
labeled \'Mobile Phone.\'

![](../../../../../Resources/Images/CMDM/User%20Guide/Create%20New%20Contact%20Mobile%20Phone%20field.png)

Once text is entered, and the cursor is moved off the Mobile Phone
field, then a processing symbol may briefly display to the left of the
field (as shown below).

![](../../../../../Resources/Images/CMDM/User%20Guide/Mobile%20Phone%20field%20processing.png)

In the example below, an invalid phone number is entered into the Mobile
Phone field, and the red icon displays.

![](../../../../../Resources/Images/CMDM/User%20Guide/PVRedValid.png)

Once a valid phone number is entered into the Mobile Phone field, then a
green checkbox icon displays, as shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/PVGreenValid.png)

There is no need to enter a country code. If no country code is entered,
the phone validation will automatically add a default country code.

If the red or green icons do not display, then the field is not
configured for validation.

In the example above, one phone field is displayed, however there is no
limit to the number of phone validation configurations allowed. For more
information, see the **Configuring Mappings** section of the Enabling
Real-Time Data Validation topic ([here]{.mcFormatColor
style="color: Blue;"}), the Enable Master Data Management Theme topic
([here]{.mcFormatColor style="color: Blue;"}), or the Enable Dun &
Bradstreet Theme topic ([here]{.mcFormatColor style="color: Blue;"})
within the **Stibo SDQ Admin Guide**.

Handling Country Codes

System administrators can configure a default country code, allowing
users to save time when entering phone numbers. If the user needs to
enter a country code that is different from the default, they enter the
correct country code prior to the phone number. For example, if 1 is
specified for the value of the default country code, then the user will
need to enter 770 425 3282 instead of +1 770 425 3282.

Phone Data Quality

Once a phone number is verified, the phone meta data is automatically
enriched by auto-populating fields configured by the system
administrator. These are helpful when creating reports to get an
overview of phone number quality. At a minimum, the following custom
fields are recommended for each phone number type that should be
validated (i.e., Phone, Mobile, Home):

-   Phone Validation Status
-   Phone Validation Timestamp (for the latest validation)

Phone Validation Statuses

The table below describes each validation status.

+-----------------+-----------------+------------+-----------------+
| Phone           | Stibo SDQ Icon  | Error Code | Description     |
| Validation      |                 |            |                 |
| Status          |                 |            |                 |
+=================+:===============:+:==========:+=================+
| Live            | ![](../.        | 0          | Active number.  |
|                 | ./../../../Reso |            |                 |
|                 | urces/Images/CM |            |                 |
|                 | DM/User%20Guide |            |                 |
|                 | /IconGreen.png) |            |                 |
+-----------------+-----------------+------------+-----------------+
| Dead            | ![](..          | 1          | Number          |
|                 | /../../../../Re |            | decommissioned  |
|                 | sources/Images/ |            | by the owning   |
|                 | CMDM/User%20Gui |            | network.        |
|                 | de/IconRed.png) |            |                 |
+-----------------+-----------------+------------+-----------------+
| Inconclusive    | ![](..          | 5          | Unable to       |
|                 | /../../../../Re |            | retrieve a      |
|                 | sources/Images/ |            | response from   |
|                 | CMDM/User%20Gui |            | the network for |
|                 | de/IconRed.png) |            | this number.    |
+-----------------+-----------------+------------+-----------------+
| No Credit       | See Description | 7          | Account has     |
|                 | Column.         |            | insufficient    |
|                 |                 |            | funds to        |
|                 |                 |            | process this    |
|                 |                 |            | request. The    |
|                 |                 |            | following       |
|                 |                 |            | integration     |
|                 |                 |            | error message   |
|                 |                 |            | will display,   |
|                 |                 |            | indicating that |
|                 |                 |            | your credits    |
|                 |                 |            | with the phone  |
|                 |                 |            | validation      |
|                 |                 |            | server have     |
|                 |                 |            | expired.        |
|                 |                 |            |                 |
|                 |                 |            | ![](../../..    |
|                 |                 |            | /../../Resource |
|                 |                 |            | s/Images/CMDM/U |
|                 |                 |            | ser%20Guide/Cle |
|                 |                 |            | rical%20Review/ |
|                 |                 |            | Error%20Warning |
|                 |                 |            | %20Insufficient |
|                 |                 |            | %20Credits.png) |
+-----------------+-----------------+------------+-----------------+
| No Teleservice  | ![](..          | 11         | Number is not   |
| Provisioned     | /../../../../Re |            | able to receive |
|                 | sources/Images/ |            | calls nor SMS   |
|                 | CMDM/User%20Gui |            | messages. This  |
|                 | de/IconRed.png) |            | is usually a    |
|                 |                 |            | number relating |
|                 |                 |            | to a data SIM.  |
+-----------------+-----------------+------------+-----------------+
| Absent          | ![](..          | 27         | Number has not  |
| Subscriber      | /../../../../Re |            | been active for |
|                 | sources/Images/ |            | a short period  |
|                 | CMDM/User%20Gui |            | of time. This   |
|                 | de/IconRed.png) |            | can include a   |
|                 |                 |            | prolonged       |
|                 |                 |            | period of       |
|                 |                 |            | inactivity, and |
|                 |                 |            | when a phone is |
|                 |                 |            | turned off or   |
|                 |                 |            | in Airplane     |
|                 |                 |            | mode.           |
+-----------------+-----------------+------------+-----------------+
| Number Not      | ![](..          | 999        | Number is       |
| Supported       | /../../../../Re |            | invalid for one |
|                 | sources/Images/ |            | or more of the  |
|                 | CMDM/User%20Gui |            | following       |
|                 | de/IconRed.png) |            | reasons: does   |
|                 |                 |            | not contain a   |
|                 |                 |            | valid country   |
|                 |                 |            | code, does not  |
|                 |                 |            | contain a valid |
|                 |                 |            | number range,   |
|                 |                 |            | is too long or  |
|                 |                 |            | too short.      |
+-----------------+-----------------+------------+-----------------+
