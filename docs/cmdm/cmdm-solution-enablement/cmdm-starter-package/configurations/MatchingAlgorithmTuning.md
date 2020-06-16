---
description: 'Customer MDM Solution: This topic covers the match tuning
  process.'
title: Matching Algorithm Tuning
---

Matching Algorithm Tuning
=========================

Algorithm Tuning begins during the build phase of the implementation.
Early on in this process, it is common to find a large number of invalid
matches making it past the Auto-Merge threshold while valid matches fall
short of the Clerical Review threshold. Thus, the ultimate goal of the
algorithm tuning sessions is to perfect the matching logic\'s accuracy
so that good and bad matches score within the appropriate thresholds.

Considerations
--------------

When developing a Matching strategy, it is important to consider the
client organization\'s data and the potential challenges the algorithm
will have to account for.

The following considerations and challenges are commonly encountered
when implementing Matching.

### Using Real Data

Algorithm Tuning is highly data-dependent, so real production data from
each source system must be made available for analysis. Customer Data is
required at key points during the implementation:

-   10-100 records for Data Modeling
-   20% of total data volume for Algorithm Tuning
-   100% of total data volume for go-live

#### Obtaining Data

Solution Consultants should expect delays in receiving customer data.
They should work with the client organization early in the process to
define the data to be delivered and push to get it as early as possible.
There may be both technical and process reasons for holding up data
delivery. The ETL team may have issues in staging data from the source
systems, and the legal or security team may introduce their own delays.

Solution Consultants should establish a delivery date that the client
organization agrees on and emphasize that delays to that date will delay
critical-path tasks.

Having access to real production data is a critical dependency to
starting the Algorithm Tuning tasks.

Data from all sources must be included. Data quality and characteristics
can vary from source system to source system, so getting samples from
all sources is critical. This includes samples of all object types in
scope as well as data captured through different means (call center,
web, mobile, etc.)

Other considerations for sampling data:

-   Data that crosses regions
-   The age of records (recently created records vs records created 20
    years ago)
-   Records updated recently vs records that have not been updated in
    years

#### Handling Data

Solution Consultants should work with the client organization to
determine the level of security needed around the data they provide.
Note that the client may be held to a higher degree of security due to
the regulation in their industry.

#### Data Quality Revelations

Before Algorithm Tuning starts, the customer data should be analyzed to
determine its quality and characteristics. This analysis will help in
determining the baseline algorithm configuration. The Solution
Consultant should analyze the data for attribute completeness (percent
populated), bad (or anonymous) data values populated, and any patterns
in the data that may be instructive for Algorithm Tuning. The quality
and characteristics of data can differ between sources, so data from
each source system should be analyzed.

It should be expected that matching will reveal Data Quality issues that
were not previously known. This should be viewed as uncovering
opportunities to improve data rather than a problem or a setback to the
overall project timeline.

### Stakeholder Input

It is important to have both the data steward and data owner present
during Sample Pair Review sessions. For more information about Sample
Pair Review, see the **Process** section below.

In this context, the data steward is the business user who has been
tasked with the formation and execution of policies for the management
of data and metadata. The data owner is the business user who typically
has a direct line of responsibility for a functional area.

There are several personnel considerations to make during the sample
pair review process:

-   It is recommended that the consultant be present on-site for the
    Sample Pair Review sessions. Due to the highly interactive nature of
    these discussions, being on-site helps facilitate the process.
-   Data Owners from different functional areas within the organization
    may have differing opinions on matching requirements. It may be
    difficult to get consensus among these various Data Owners.
-   Some more sophisticated client organizations may introduce a Data
    Governance Board that can assist with reaching consensus among the
    Data Owners.

It is important to set expectations with the client organization that
while those implementing the initial configuration can provide guidance,
it is the organization\'s responsibility to determine which customer
records should match and which should not.

However, Solution Consultants should not expect a client organization to
be able to articulate their matching requirements. To arrive at a
baseline algorithm configuration, a discussion with the client should
occur focusing on what their priorities are for generating Golden
Records. The Sample Pair review sessions will help facilitate the
discussion around finalizing matching requirements.

### False Positives vs False Negatives

Before tuning begins, it is important to discuss with the client
organization if false positives or false negatives would be preferred.
It is much easier to identify false positives than false negatives in
the pair export. Therefore, it is recommended to start with a wide net
and narrow the Match Criteria during tuning. However, ultimately client
organizations will generally prefer false negatives over false positives
once the algorithm is finalized.

### Clerical Review

Keep in mind that any records below the auto-threshold and above the
clerical review threshold will be placed in clerical review for manual
review. It is important to discuss with the client organization what
types of potential duplicates will be evaluated as part of clerical
review and the volume of records that are acceptable. Client
organizations with a low volume such as B2B organizations may want a
looser algorithm where most or sometimes all records are reviewed
manually. Client organizations with a high volume such as B2C
organizations may want little to no records reviewed manually.

This discussion becomes increasingly important as volumes become larger.
While .5% may sound like an acceptable and small percentage, .5% of 1
million is 5000 tasks that must be reviewed manually. Additionally, if
it is not possible to articulate rules that define a match, it probably
won't be possible for a human to determine if records are a match using
the data provided.

### Start Small

Initially tuning with a full data set may not be advisable when volumes
are large. Instead, tuning should be done in iterations of increasing
volume sizes. As an example, start with 1000 records, eventually go to
100000, and in the end, at least 20% of the full data set should be
taken in to consideration. Make sure to take into account a good
sampling of data such as data from all sources and data captured through
different means. If the volume is small enough, consider tuning using
20%, 30%, 60% and 100% of the total data set.

### Iterations of Review

Each client has a unique data set requiring the match algorithm be tuned
specifically to identify matches in that data. Three or more match
tuning iterations should be expected. It is not uncommon to have 5-6 or
many more iterations.

### Rule Tips

Rules are a set of criteria that must be true for the result to be
assigned. The rules can quickly become complex as varying use cases are
identified in the data. The best way to handle this complexity is to
make the rules simple and easy to understand, especially since there is
no restriction to the number of rules that can be created. Additionally,
the rules should be well documented so that changes to the algorithm are
easier both during tuning and later after go live.

The result should be calculated as a weighted sum of the matchers in
play. Conditions should be used to limit the combinations of matchers in
the weighted sum to no more than two matchers, as else it is typically
not possible to tune to a threshold.

### Re-tuning

It is recommended that the client organization re-engage with the
applicable solution consultants post go-live for new Algorithm Tuning
sessions when any of the following takes place:

-   A new source is added that has different demographic or data
    quality.
-   Substantial increase in False Positives or False Negatives.
-   The Entity Size or Clerical Review Task Size metrics change
    significantly over time.

Process
-------

The Matching Algorithm Tuning process is as follows:

### 1) Configuration

Utilize a Match Tuning configuration to generate a Data Profile. Using
this Data Profile, identify key data points to consider when configuring
a baseline algorithm (Matching Algorithm and Match Codes).

For more information on Matching Tuning and creating a Match Tuning
configuration, see the **Match Tuning** section of the **Matching,
Linking, and Merging** documentation[ here]{.mcFormatColor
style="color: Blue;" conditions="Primary.Web"}.

### 2) Generate Sample Pair

Once the baseline algorithm is configured, generate the Random Sample
Pair spreadsheet via a Match Tuning configuration. This baseline
configuration is just a 'best-guess' configuration based on the analysis
of the customer data so far.

Before the sample pair review can kick-off, the raw data from the output
file should be formatted to make it human readable. The Sample Pair
Formatter Excel sheet can optionally be used on the output file.

To obtain the Sample Pair Formatter Excel sheet, refer to the separately
bundled initial configuration files. Detailed instructions on how to use
this Excel sheet is included within the sheet itself.

### 3) Review Sample Pair

Review the Sample Pairs with the client. Each individual pair gets
either a 'Yes', 'No', or 'Not Sure' indicating whether or not they
should be considered the same entity by the algorithm and linked
together.

The Sample Pair Review process can be a time-consuming task but is
critical in getting the algorithm tuned to meet requirements. Typically,
1,000+ Sample Pairs will need to be reviewed each cycle with the
stakeholders. For some of the iterations, a pair export may be as large
as 1000 records per percentage points of interest.

Once the random sample pair spreadsheet is generated and formatted, it
is vital to review the sample pairs to see how the algorithm evaluates
them. The primary purpose of the review is to assess the confidence of
each merge and modify the thresholds if the scores appear inaccurate.
During the review process, it is also important to consider the
following:

-   The organization should mark each set with a decision as to whether
    (based on the data available) the records should be considered the
    same entity.
-   It is best to approach this task from a 'human' standpoint as
    opposed to creating logic to help you achieve a certain score.
-   This is not a data cleaning task.

The ultimate goal by the end of each Sample Pair Review session is to
improve the quality of the matches found. It is much easier to identify
false positives than false negatives in the pair export. Therefore, it
is recommended to start with a wide net and narrow the Match Criteria
during tuning.

### 4) Tuning the Algorithm

Tune the algorithm based on feedback from the Sample Pair review and
generate a new set of Sample Pairs based on the updated algorithm. This
goal can be achieved by:

-   Adjusting the scoring method and weighting of each scored attribute.
-   Adjusting the relative weighting of scoring across all the scored
    attributes.
-   Adjusting the Auto-Merge and Clerical Review Thresholds.

Repeat steps 2 and 3 for two more cycles (or more, as needed).

### 5) Finalize

Make a decision on the final Auto Merge Threshold and Clerical Review
Threshold.

Algorithm Tuning begins during the build phase of the implementation.
Early on in this process, it is common to find a large number of invalid
matches making it past the Auto-Merge threshold while valid matches fall
short of the Clerical Review threshold. Thus, the ultimate goal of the
algorithm tuning sessions is to perfect the matching logic\'s accuracy
so that good and bad matches score within the appropriate thresholds.

This goal can be achieved by:

-   Adjusting the scoring method and weighting of each scored attribute.
-   Adjusting the relative weighting of scoring across all the scored
    attributes.
-   Adjusting the Auto-Merge and Clerical Review Thresholds.

It is important to have both the data steward and data owner present
during algorithm review sessions. In this context, the data steward is
the business user who has been tasked with the formation and execution
of policies for the management of data and metadata. The data owner is
the business user who typically has a direct line of responsibility for
a functional area.

Algorithm Tuning Process {#algorithm-tuning-process .RNNoTOC conditions="Primary.Under Construction"}
------------------------

The Matching Algorithm Tuning process is as follows:

1.  Configuration: Utilize a Match Tuning configuration to generate a
    Data Profile. Using this Data Profile, identify key data points to
    consider when configuring a baseline algorithm (Matching Algorithm
    and Match Codes).
2.  Generate Sample Pair: Once the baseline algorithm is configured,
    generate the Random Sample Pair spreadsheet via a Match Tuning
    configuration. This baseline configuration is just a 'best-guess'
    configuration based on the analysis of the customer data so far.
3.  Review Sample Pair: Review the Sample Pairs with the client. Each
    individual pair gets either a 'Yes', 'No', or 'Not Sure' indicating
    whether or not they should be considered the same entity by the
    algorithm and linked together.
4.  Tuning the Algorithm: Tune the algorithm based on feedback from the
    Sample Pair review, and generate a new set of Sample Pairs based on
    the updated algorithm. Repeat steps 2 and 3 for two more cycles (or
    more, as needed).

```{=html}
<!-- -->
```
1.  Finalize: Make a decision on the final Auto Merge Threshold and
    Clerical Review Threshold.

Before the sample pair review can kick-off, the raw data from the output
file should be formatted to make it human readable. The Sample Pair
Formatter Excel sheet can optionally be used on the output file.

To obtain the Sample Pair Formatter Excel sheet, refer to the separately
bundled initial configuration files. Detailed instructions on how to use
this Excel sheet is included within the sheet itself.

Once the random sample pair spreadsheet is generated and formatted, it
is vital to review the sample pairs to see how the algorithm evaluates
them. The primary purpose of the review is to assess the confidence of
each merge, and modify the thresholds if the scores appear inaccurate.
During the review process, it is also important to consider the
following:

-   The organization should mark each set with a decision as to whether
    (based on the data available) the records should be considered the
    same entity.
-   It is best to approach this task from a 'human' standpoint as
    opposed to creating logic to help you achieve a certain score.
-   This is not a data cleaning task.

The ultimate goal by the end of each Sample Pair Review session is to
improve the quality of the matches found. It is much easier to identify
false positives than false negatives in the pair export. Therefore, it
is recommended to start with a wide net and narrow the Match Criteria
during tuning.

It is important to set expectations with the client organization that
while those implementing the initial configuration can provide guidance,
it is the organization\'s responsibility to determine which customer
records should match and which should not.

The Sample Pair Review process can be a time-consuming task, but is
critical in getting the algorithm tuned to meet requirements. Typically,
1,000+ Sample Pairs will need to be reviewed each cycle.

There are several personnel considerations to make during the sample
pair review process:

-   It is recommended that the consultant be present on-site for the
    Sample Pair Review sessions. Due to the highly interactive nature of
    these discussions, being on-site helps facilitate the process.
-   Data Owners from different functional areas within the organization
    may have differing opinions on matching requirements. It may be
    difficult to get consensus among these various Data Owners.
-   Some more sophisticated client organizations may introduce a Data
    Governance Board that can assist with reaching consensus among the
    Data Owners.

Other Considerations {#other-considerations .RNNoTOC conditions="Primary.Under Construction"}
--------------------

It is recommended that the client organization re-engage with the
applicable solution consultants post go-live for new Algorithm Tuning
sessions when any of the following takes place:

-   A new source is added that has different demographic or data
    quality.
-   Substantial increase in False Positives or False Negatives.
-   The Entity Size or Task Size metrics change significantly over time.

For more information on Matching Tuning and creating a Match Tuning
configuration, see the **Match Tuning** section of the **Matching,
Linking, and Merging** documentation[ here]{.mcFormatColor
style="color: Blue;" conditions="Primary.Web"}.
