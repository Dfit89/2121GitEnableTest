---
description: 'Customer MDM Solution: The Matching Algorithm is typically
  configured first, followed by the Match Codes.'
title: '\[%=Heading.Level1%\]'
---

Configuring Matching Algorithms and Match Codes
===============================================

The Matching Algorithm is typically configured first, followed by the
Match Codes.

Matching Algorithm Configuration {#matching-algorithm-configuration .RNNoTOC}
--------------------------------

The Matching Algorithm should be tailored to the data, and strive for
precision. The CMDM initial configuration includes four pre-configured
Matching Algorithms that can be used as a foundation to build a client
organization\'s Matching solution:

-   Individual Customer ([here]{.mcFormatColor style="color: Blue;"})
-   Organization Customer ([here]{.mcFormatColor style="color: Blue;"})
-   Contact Person ([here]{.mcFormatColor style="color: Blue;"})
-   Household ([here]{.mcFormatColor style="color: Blue;"})

For more information, see the Algorithm & Match Codes topics.

When configuring the Matching Algorithm, it is important to consider the
impact that Thresholds have on match results. If the Clerical Review
threshold is set too high, a large amount of false negatives may be
generated. Similarly, if the Auto Threshold is set too low, false
positives could be generated. If the initial Matching configuration
produces false negatives and/or false positives, the Thresholds should
be reevaluated during the Match Tuning sessions.

For more information on configuring a Matching Algorithm, see the
**Configuring Matching Algorithms** section of the **Matching, Linking,
and Merging** documentation[ here]{.mcFormatColor style="color: Blue;"}.

Match Codes Configuration {#match-codes-configuration .RNNoTOC}
-------------------------

Match Codes should aim to ensure that anything given a high score by the
algorithm is included, and that only those records that may score high
get compared. The Match Codes should be considering the same data points
that the Match Criteria does. This ensures that the comparison pool that
Match Codes generate is relevant to the data points the Match Criteria
is matching on.

For example, if the Match Criteria is matching on a combination of
Person Name and Address, it is not recommended to generate Match Codes
based on unrelated attributes (e.g., Phone and Email).

Example Match Codes

Typical attributes used to generate Match Codes for Individual (B2C)
solutions include Name, Address, Email, and Phone. For Organization
(B2B), these attributes potentially include Name, Address, Phone, DUNS
(D&B Number), and Tax Identifier.

Email

Email is often used to narrow the pool of potential match candidates.
The Email Match Code Generator may be selected to work in conjunction
with an Email normalizer to auto-generated email match codes.

Example: A customer with the email \"InesJung\@armyspy.com\" becomes the
Match Code \"EMAIL\#INESJUNG\@ARMYSPY.COM\".

Phone

Phone shares many of the same benefits that email provides.

Example: A customer with the phone number \'(931) 839-9039\' becomes the
Match Code \"PHONE\#19318399039\".

In this example, the phone number normalizer is configured to default
the country code to US.

Address

Address is often used in combination with person name or organization
name. It is fairly unique if the full address is used, but has low
uniqueness if only part of the address is used.

The accuracy of addresses varies (i.e., one entry may include suite no.
while another may not). When matching, techniques like edit distance is
used on city and street. Because of this, and the fact that accuracy
varies, the full address does not make a good match code, as it will
likely lead to false negatives.

Addresses are often abbreviated (\'st\' for street or station, etc.) in
complex patterns that cannot be uniquely resolved easily. For high
accuracy of address matching, it is therefore recommended to use STEP's
Address standardization capabilities, which are integrated to Loqate.

The match code generator for addresses provides the following address
combinations:

-   ZIP code + Street Name
-   Metaphone3 City + Street Name

Example: The match codes for \"134 Trace Lane, Lawrenceville, GA,
30046\" would be \"ADDRESS\#30046+TRACELANE\" or
\"ADDRESS\#LRNSFL+TRACELANE\"

Name and Address

Combining elements of a person name and elements of an address is often
a good way to create Match Codes that are sufficiently unique, without
causing false negatives. However, multiple permutations are often
required to avoid false negatives.

Example: Kimberly Kaine resides at 134 Trace Lane, Lawrenceville, GA,
30046. Her corresponding match code would be \"INDIVIDUAL\#K+K+30046+134
TRACE\".

Other examples of Name and Address combination Match Codes:

-   First Name initial + Metaphone3 Last Name + ZIP code
-   Last Name initial + Metaphone3 First Name + ZIP code
-   First Name initial + Metaphone3 Last Name + Metaphone3 City
-   Last name initial + Metaphone3 First Name + Metaphone3 City
-   First name initial + Last Name initial + ZIP code + Street name
-   First Name initial + Last Name initial + Metaphone3 City + Street
    Name

For more information on configuring Match Codes, see the **Configuring
Match Codes** section of the **Matching, Linking, and Merging**
documentation[ here]{.mcFormatColor style="color: Blue;"
conditions="Primary.Web"}.

Initial Configuration Match Codes

The CMDM initial configuration includes four pre-configured sets of
Match Codes that correspond to the four Matching Algorithms mentioned in
the above section:

-   Individual Customer ([here]{.mcFormatColor style="color: Blue;"})
-   Organization Customer ([here]{.mcFormatColor style="color: Blue;"})
-   Contact Person ([here]{.mcFormatColor style="color: Blue;"})
-   Household ([here]{.mcFormatColor style="color: Blue;"})

For more information, see the Algorithm and Match Codes topics.
