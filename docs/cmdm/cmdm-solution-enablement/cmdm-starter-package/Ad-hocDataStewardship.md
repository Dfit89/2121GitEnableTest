---
description: 'Customer MDM Solution: This topic covers how data stewards
  can use the data profiling functionality.'
title: 'Ad-hoc Data Stewardship'
---

Ad-hoc Data Stewardship
=======================

When dealing with large volumes of data it is often difficult to
identify trends and outliers within a dataset. CMDM's data profiling
functionality allows data stewards to observe data in its current state
and identify patterns and trends. A few examples of when a data steward
would utilize data profiling include:

-   Profiling and analyzing data
-   Investigate a decline in quality of data as reported by data quality
    policies.
-   A potential upstream problem may have been identified.
-   Ensuring address quality of CMDM data
-   For a marketing campaign targeting a group of customers or specific
    geographical region.
-   Increase in return mail or bounced emails.
-   Running a search and seeing the result of the search
-   Determine number of resulting records from the search.
-   See examples of a search that returns a large subset of customer
    records (ex. more than 1 million).
-   See details of the various source systems that serve as input for
    organization records.
-   List all data that came in from Sweden on a Saturday 2 weeks ago.
-   Investigating what an existing collection contains
-   See if an old collection can be deleted.
-   Identify who created the collection. When? Why?
-   Exporting a list of customers
-   1000 records with phone numbers for marketing research.
-   42 million records with address and anonymized data points for a BI
    platform.

Use Case 1: Adhoc Work on Lists of Records

Bruce is a data steward whose primary role is to support and ensure the
quality of customer data for the ACME's marketing team. The Marketing
team is promoting the upcoming season and is running multiple campaigns
which target existing customers residing in specific geographical areas
within the United States. All campaign collateral will be addressed to
each individual customer and sent via both email and direct mail.

Existing data policy monitoring metrics are in place and show that a
sizable percentage of marketing collateral is either returned by the
United States Postal Service (USPS), emails have bounced back, or
contact information is not present. In the last two campaign seasons the
statistical breakdown is as follows:

-   9% of emails have bounced back
-   12% of direct mails were undeliverable and returned

Because the upcoming campaign is targeted towards individuals in a
particular region of the US, the marketing team would like to understand
the quality of contact data for those individuals before rolling out the
campaign. As such, the team has compiled a mailing list comprised of
customers and prospects they would like to mail collateral to.

Bruce's task is to run this campaign list against the current CMDM
database to determine the quality of contact data currently on file.
This determination can be made by seeing if the following requirements
are met:

-   Customer has sufficient contact information
-   Main Address is validated at least once within the last 365 days
-   If address has a low quality, no flyer will be sent
-   Email is validated within the last 120 days
-   If email is no longer valid, a process is started that notifies the
    customer and requests that they update their email address.

To accomplish this, Bruce can create a collection of customer records
based on the mailing list and generate a data profile on the Collection.
He then evaluates the data profile against the requirements.

It is assumed that the profiling configuration Bruce uses includes the
necessary data elements to be analyzed, i.e., Address and Email
attributes.

With the data profiles in place, the CMDM system can highlight the data
quality problems for Bruce, allowing him to report the following back to
the marketing team:

-   4% of the customers did not have mailing addresses.
-   18% of the addresses that are present are incomplete (i.e., missing
    state or zip code).
-   8% of the emails are marked by Experian as \'disposable\',
    indicating the address is associated with a disposable email
    provider. Usually they are unreliable and could potentially be spam
    accounts.
-   4% of the emails are \'illegitimate\', indicating it is highly
    likely they are spam accounts or inactive domains.

Based on this information, marketing may then determine the best course
of action, i.e., to either proceed with the mailing (if the data quality
is acceptable) or place a larger emphasis on an e-campaign if a large
percentage of the target customers only have an email address.

Use Case 2: Investigate a Decrease in Completeness of Contact
Information

Chris is a data steward whose primary task is to continuously monitor
the quality of data within CMDM. A focal data point of Chris'
responsibilities is to monitor overall quality of contact information.
Data quality policies monitor contact information by utilizing a
completeness metric which evaluates completeness of attributes such as
Address, Email, Phone, Last Contact Date, etc.

In the last two weeks, Chris has noticed there has been an increase in
frequency of policy breaches for quality of customer contact
information. Since ACME's marketing strategy includes heavy reliance
upon informing existing customers of the latest products and promotions,
having dependable contact data is a top priority.

Chris would like to use CMDM to profile the records that contain
incomplete contact information to determine what aspects within contact
information are incomplete / missing. Once these customers are
identified, Chris will then:

1.  Provide the results to the marketing team, so they may best
    determine how to proceed with their marketing activities.
2.  Collaborate with marketing in identifying and changing existing
    business processes that caused the capture of incomplete contact
    data so they may address the issue at the source.

By using the profiling capabilities of CMDM, Chris was able to support
the marketing team and their campaign efforts. In doing so, it was
identified that ACME's CRM system, which manages all customer loyalty
programs and sign-ups, was lacking validations to ensure complete and
accurate contact information is captured at the point of entry.
Specifically, the CRM system experienced an issue where city and zip
code information were no longer mandatory as part of the new customer
sign-up process.

Furthermore, the marketing team was able to strategically accommodate
for this in their marketing activities as they awaited resolution of the
issue within the CRM system. Once the issue was addressed, marketing
then proceeded to carry out their campaign with confidence in their data
