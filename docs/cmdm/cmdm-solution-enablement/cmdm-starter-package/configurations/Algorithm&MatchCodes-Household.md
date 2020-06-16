---
description: 'Customer MDM Solution: Describes how to configure the
  Household Match Algorithm and Match Codes.'
title: 'Algorithm & Match Codes - Household'
---

Algorithm & Match Codes - Household
===================================

Matching Algorithm {#matching-algorithm .RNNoTOC}
------------------

The Household Matching Algorithm delivered as part of the initial
configuration is designed as a match algorithm for Household entities.
This algorithm is most relevant in a Business to Consumer (B2C) style
implementation and consists of two normalizers and two matchers, with an
Auto Threshold of 90.0 and a Clerical Review Threshold of 80.0. The
Clerical review threshold is both higher and tighter to ensure only
customer records that are extremely likely to belong to the same
household are considered.

It is worth noting that the Household Matching Algorithm utilizes the
Link Golden Record solution engine rather than the Merge Gold Record
approach. This is to ensure that individual customers that are
determined to be of the same household are linked to a separate
household entity object rather than merged.

For details regarding the Household entity and its purpose, see the
**Data Modeling** section of this documentation[ here]{.mcFormatColor
style="color: Blue;" conditions="Primary.Web"}.

For more information on configuring a Matching Algorithm, see the
**Configuring Matching Algorithms** section of the **Matching, Linking,
and Merging** documentation[ here]{.mcFormatColor style="color: Blue;"}.

Normalizers

Normalizers are used to standardize values that are being compared. This
ensures equal formatting is applied, increasing the accuracy of the
comparisons being made. For more information, see the **Decision Table
Normalizers** section of the **Matching, Linking, and Merging**
documentation[ here]{.mcFormatColor style="color: Blue;"}.

Last Name Normalizer

The Last Name Normalizer uses the Words Normalizer, and only evaluates
the Last Name attribute of an individual record. This is because
households are referred to only by the Last Name, or household name.

Address Normalizer

Because it is recommended to model addresses as data containers, the
Address Normalizer will need to be configured to normalize data
container attributes as defined within the Address component model.

Matchers

For general information on configuring Matchers, see the **Decision
Table Matchers** section of the **Matching, Linking, and Merging**
documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.

Name Matcher

The Last Name Matcher is largely left with the default settings. An
equivalent names look-up table is not utilized for Household entities
since last names generally do not have shortened versions or a nickname
alternative.

Address Matcher

The Address Matcher utilizes default configuration values.

Rules

When considering match rules, the recommended strategy is to dissect the
customer's information into the smallest possible portions of data.
These rules should not weigh the sum of *all* the customer's input data
(which is likely inefficient), and requires a careful analysis of the
customer dataset in order to determine what combinations of attributes
present the best chance of uniqueness.

There is only one rule associated with the Household algorithm, which
evaluates the scores of the Name and Address matchers. The resulting
score is then weighed against the defined algorithm thresholds to
determine whether the individual record should be created, auto-linked
to an existing record, or it requires clerical review.

The initial configuration matches on Last Name and Address for
households. Matching on Last Names may be advantageous in identifying
family units within a large population such as a retirement home or a
school. However, in some cases a married couple within a household may
not have the same Last Name. It may be beneficial to make Address weigh
more in scenarios like this.

Conversely, sometimes a large number of customer records with the same
Address should not be considered the same household. This can include
college campuses, retirement homes, and similar institutions. These
scenarios should be handled on a case-by-case basis. However, one
possible approach is to utilize an anonymous words table to anonymize
aforementioned addresses, eliminating addresses from the matching logic
for such records.

Survivorship

The following survivorship rules are used by the Household Algorithm:

-   **Value: Most Recent**
    -   **Attribute / Attribute Group:** Last Name
    -   **Last Edit Date Attribute:** Last Edit Date - Record
-   **Data Container: Most Recent**
    -   **Business Condition:** DataContainer Survivorship Address
    -   **Data Container Type:** Main Address
    -   **Last Edit Date Attribute:** Last Edit Date - Main Address

Data Containers require their own survivorship rules. Additionally, each
Survivorship rule requires a unique Last Edit Date attribute.

Match Codes {#match-codes .RNNoTOC}
-----------

The Household Match Code is generated on the Individual Customer entity
type along with the Individual Match Codes. Since a household is
identified by its last name, the Household Match Code is composed of:
the zip code + metaphone3 representation of the individual's last name.

The Household Match Code contain the prefix \'ZILNM\~\'.
