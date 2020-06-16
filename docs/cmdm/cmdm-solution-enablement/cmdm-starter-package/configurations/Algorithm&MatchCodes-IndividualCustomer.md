---
description: 'Customer MDM Solution: Describes how to configure the
  Individual Customer Match Algorithm and Match Codes.'
title: 'Algorithm & Match Codes - Individual Customer'
---

Algorithm & Match Codes - Individual Customer
=============================================

Matching Algorithm {#matching-algorithm .RNNoTOC}
------------------

The Individual Matching Algorithm delivered as part of the initial
configuration is designed as a match algorithm for Individual Customer
solutions. The most common data to have available for matching
Individual Customers are First Name, Middle Name, Last Name, Address,
Emails, and Phone numbers

This algorithm consists of four normalizers and four matchers, with an
Auto Threshold of 90.0 and a Clerical Review Threshold of 60.0.

For more information on configuring a Matching Algorithm, see the
**Configuring Matching Algorithms** section of the **Matching, Linking,
and Merging** documentation[ here]{.mcFormatColor style="color: Blue;"}.

Normalizers

Normalizers are used to standardize values that are being compared. This
ensures equal formatting is applied, increasing the accuracy of the
comparisons being made. For more information, see the **Decision Table
Normalizers** section of the **Matching, Linking, and Merging**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

Person Name Normalizer

The Person Name Normalizer is configured to normalize the corresponding
first, middle, and last name attributes (e.g., FirstName, MiddleName,
LastName).

For customers with a large, non-English speaking consumer base, it is
recommended to normalize accents and diacritic characters. Such
characters may not \'play well\' with the phonetic encoding of words
(e.g., soundex or metaphone3) during the match process.

Address Normalizer

Because it is recommended to model addresses as data containers, the
Address Normalizer will need to be configured to normalize data
container attributes as defined within the Address component model.

Email Normalizer

Because it is recommended to model emails as data containers, the Email
Normalizer will need to be configured to normalize data container
attributes as defined within the Email component model.

Phone Normalizer

Because it is recommended to model phone numbers as data containers, the
Phone Normalizer will need to be configured to normalize data container
attributes.

Matchers

For general information on configuring Matchers, see the **Decision
Table Matchers** section of the **Matching, Linking, and Merging**
documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.

Person Name Matcher

The Person Name Matcher is largely left with the default settings.
However, an alias table is used to provide an equivalent names table.

Third-party sources may be leveraged to build and enhance the equivalent
names table within STEP. However, it is recommended that the client's
expertise with their customer data be consulted to account for industry
or business specific patterns. For example, if a company is based in
southwestern United States then their equivalent names table may contain
an emphasis on Hispanic name equivalents. Furthermore, equivalent name
values may also be added as a result of a match tuning exercise with the
client's customer data set.

Regarding middle names, an evaluation exercise with the customer is
recommended to review the quality of data they have for customer middle
names. It is possible that middle names are not collected from the
consumers, or only middle initials are required but rarely provided. In
such cases, it is recommended to reconsider the weight of MiddleName.

The names in the equivalent names table provided by the initial
configuration target the US market.

Address Matcher

The Address Matcher utilizes default configuration values.

Email Matcher

The Email Matcher utilizes default configuration values.

Phone Matcher

The Phone Matcher utilizes default configuration values.

Rules

When considering match rules, the recommended strategy is to dissect the
customer's information into the smallest possible portions of data.
These rules should not weigh the sum of *all* the customer's input data,
and should instead be split so that it is possible to optimize each
rule. Careful analysis of the customer dataset is required in order to
determine what combinations of attributes present the best chance of
uniqueness.

Three rules are provided to calculate the final score of the Individual
Matching Algorithm. According to the configured conditions, if all
respective Matchers resolve to true (i.e., scores above 70), then the
algorithm will take the highest scoring rule as the final score of the
algorithm. The rules are comprised of combinations of each Name score,
Address score, Email score, and Phone score. The rules are then
standardized to resolve to a value between 0 and 100.

These rules specifically include:

-   Name & Address
-   Name & Email
-   Name & Phone

In this scenario, Name is used in all three rules because it is common
for family members who use the same email and/or phone number to live at
the same address. Thus email, phone number, or address are not reliably
unique by themselves. By adding Name to these rules we are ensuring the
uniqueness of the individual's name is taken into consideration, in
addition to the other contact information elements.

It is possible to extend a rule by including various other combinations
of matchers. This should be considered if there are specific
requirements or use cases which requires specific combinations of
matchers.

By adding another parameter, you have the ability to identify false
positives. Unique identifiers such as Social Security, Passport, or
Driver's License Numbers may be used as veto rules to further enhance
the quality of the match process.

Other extensions include Date of Birth (DOB), which can be used in
combination with other rules to be less strict on equality. For example,
name and address runs the risk of a father and son having the same name
which would be resolved by considering the date of birth. Additionally,
you can accept lower scores of names and addresses, if DOB is equal.

Survivorship

The following survivorship rules are used by the Individual Customer
Algorithm:

-   **Value: Most Recent**
    -   **Attribute / Attribute Group:** Individual - Most Recent
    -   **Last Edit Date Attribute:** Last Edit Date - Record

```{=html}
<!-- -->
```
-   **Data Container: Most Recent (Emails)**
    -   **Business Condition:** DataContainer Survivorship Email
    -   **Data Container Type:** Emails
    -   **Last Edit Date Attribute:** Last Edit Date - Email

```{=html}
<!-- -->
```
-   **Data Container: Most Recent (Phones)**
    -   **Business Condition:** DataContainerSurvivorshipPhone
    -   **Data Container Type:** Phones
    -   **Last Edit Date Attribute:** Last Edit Date - Phone

```{=html}
<!-- -->
```
-   **Data Container: Most Recent (Main Address)**
    -   **Business Condition:** DataContainer Survivorship Address
    -   **Data Container Type:** Main Address
    -   **Last Edit Date Attribute:** Last Edit Date - Main Address

Data Containers require their own survivorship rules. Additionally, each
Survivorship rule requires a unique Last Edit Date attribute.

Match Codes {#match-codes .RNNoTOC}
-----------

For the Individual Customer entity type, three separate Match Codes are
being generated. While based on the demographics of the customer record,
these Match Codes are composed of: Email, Phone Number, and a
combination of Individual Name and Address.

For information on how to configure Match Codes in STEP, see the
**Configuring Match Codes** section of the **Matching, Linking, and
Merging** documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.

Email Match Code

The Email Match Code is the normalized value of the email address
attribute. Both the username (or local part) of the email and the domain
are normalized to ensure variations of the same email address (as a
result of differing cases or special characters) are accounted for.

It is recommended to add a discernible prefix to each Match Code so the
end-user may easily identify what attribute(s) the Match Code is based
off of. The email Match Code contains the prefix \'EM\~\'.

Phone Number Match Code

The Phone Number Match Code is the normalized value of the individual's
phone number attribute. The normalization removes any parenthesis and
hyphenation in between numbers. Additionally, the area itself has been
removed, leaving only the last 7 digits available as the Match Code.
Phone number Match Code is prefixed by \'PH\~\'.

Address and Name Match Code

The Address and Name Match Code is a combination of elements of the
individual's name and address. For example, the provided Match Code
within the initial configuration is composed of: zip code + the first
letter of the individual's first name + metaphone3 representation of the
individual's last name.

The Address and Name Match Code contains the prefix \'ZINM\~\'.

Configuration Considerations {#configuration-considerations .RNNoTOC}
----------------------------

It is worth considering the use of the Equivalent Values Lookup Table
and Anonymous Value Lookup Table. The Equivalent Value Lookup Table is
used by both Match Codes and the Match Criteria in order to ensure that
values that mean the same thing are evaluated as such. Equivalent values
will score appropriately high, as if the values were actually the exact
same.

Example:

-   Name: Matt = Matthew

Equivalent Values are only used for person & organization names.

The Anonymous Values Lookup Table is also used by both Match Codes and
the Match Criteria in order to ensure that values that are anonymous, or
not meaningful, do not contribute to identifying potential duplicates.
Determining what these values should be is highly dependent on the
organization\'s dataset.

Typically, these values will be default values that users of a Source
System enter when they don't have the correct value, or don't want to
enter a value. The actual anonymous values are not included in the
baseline build of the Customer MDM configuration.

Examples:

-   Phone: 999999999
-   Address: DO NOT USE
