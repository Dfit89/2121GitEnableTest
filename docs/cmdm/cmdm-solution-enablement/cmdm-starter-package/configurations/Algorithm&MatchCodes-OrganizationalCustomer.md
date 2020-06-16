---
description: 'Customer MDM Solution: Describes how to configure the
  Organizational Customer Match Algorithm and Match Codes.'
title: 'Algorithm & Match Codes - Organizational Customer'
---

Algorithm & Match Codes - Organizational Customer
=================================================

Matching Algorithm {#matching-algorithm .RNNoTOC}
------------------

The Organization Matching Algorithm delivered as part of the initial
configuration is designed as a match algorithm for Organization Customer
solutions. This algorithm is most relevant in a Business to Business
(B2B) style implementation and consists of two normalizers and two
matchers, with an Auto Threshold of 90.0 and a Clerical Review Threshold
of 60.0.

For more information on configuring a Matching Algorithm, see the
**Configuring Matching Algorithms** section of the **Matching, Linking,
and Merging** documentation[ here]{.mcFormatColor style="color: Blue;"}.

Normalizers

Normalizers are used to standardize values that are being compared. This
ensures equal formatting is applied, increasing the accuracy of the
comparisons being made. For more information, see the **Decision Table
Normalizers** section of the **Matching, Linking, and Merging**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

Organization Name Normalizer

The Organization Name Normalizer for the Organization Algorithm is
configured to normalize only the Legal Name (LegalName) attribute for
organization entities.

Address Normalizer

Because it is recommended to model addresses as data containers, the
Address Normalizer will need to be configured to normalize data
container attributes as defined within the Address component model.

Matchers

For general information on configuring Matchers, see the **Decision
Table Matchers** section of the **Matching, Linking, and Merging**
documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.

Organization Name Matcher

The Organization Name Matcher is used by the algorithm to match on
organization names. This matcher is left with default settings, however
it is recommended that the Organization Name Matcher is tuned to the
specifics of the organization.

Address Matcher

The Address Matcher utilizes default configuration values.

When matching organizations, keep in mind that multiple business
entities may reside at a singular address. For example, Office Buildings
where no suite number is provided.

Rules

When considering match rules, the recommended strategy is to dissect the
customer's information into the smallest possible portions of data.
These rules should not weigh the sum of *all* the customer's input data
(which is likely inefficient), and requires a careful analysis of the
customer dataset in order to determine what combinations of attributes
present the best chance of uniqueness.

There is only one Rule associated with the Organization Algorithm. This
Rule evaluates the scores of the Name and Address matchers. The
resulting score is then weighed against the defined algorithm thresholds
to determine whether the organization record should be created,
auto-merged, or if it requires a clerical review.

Common attributes to match for organizations on include Address, DUNS
(D&B Number), and Tax Identifier.

Survivorship

The following survivorship rules are used by the Organization Algorithm:

-   **Value: Most Recent**
    -   **Attribute / Attribute Group:** Organizations - Most Recent
    -   **Last Edit Date Attribute:** Last Edit Date - Record
-   **Data Container: Most Recent**
    -   **Business Condition:** DataContainer Survivorship Address
    -   **Data Container Type:** Main Address
    -   **Last Edit Date Attribute:** Last Edit Date - Main Address

Data Containers require their own survivorship rules. Additionally, each
Survivorship rule requires a unique Last Edit Date attribute.

Match Codes {#match-codes .RNNoTOC}
-----------

For the Organization Customer entity type, three separate Match Codes
are being generated. While based on the demographics of the organization
record, these Match Codes are composed of the Email, Phone Number, and a
combination of Legal Name and Address.

Since initial demographic data for organizations may be limited prior to
enrichment (for example, Dun & Bradstreet detailed profile), generating
these three Match Codes will help ensure proper identification of
organizations during the match process.

For information on how to configure Match Codes in STEP, see the
**Configuring Match Codes** section of the **Matching, Linking, and
Merging** documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.

Email Match Code

The Email Match Code is the normalized value of the organization's main
contact email address. Both the username (or local part) of the email
and the domain are normalized to ensure variations of the same email
address (as a result of differing cases or special characters) are
accounted for.

It is recommended to add a discernible prefix to each Match Code so the
end-user may easily identify what attribute(s) the Match Code is based
off of. The Email Match Code contains the prefix \'EM\~\'.

Phone Number Match Code

The Phone Number Match Code is the normalized value of the
organization's main contact phone number. The normalization removes any
parenthesis and hyphenation in between numbers. Additionally, the area
itself has been removed, leaving only the last 7 digits available as the
Match Code. Phone number Match Code is prefixed by \'PH\~\'.

Organization Address and Name Match Code

The Organization Address and Name Match Code is composed of: the zip
code + metaphone3 representation of the organization's legal name.

The Organization Address and Name Match Code contains the prefix
\'ZONM\~\'.
