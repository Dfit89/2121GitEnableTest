---
description: 'Customer MDM Solution: In a CMDM system, data governance
  is important to ensuring that data in the system stays within a set
  quality standard.'
title: Data Governance
---

Data Governance
===============

Data governance is the overall management of the availability,
usability, integrity, and security of data used within an enterprise. A
sound data governance program is driven by a governing body or council,
which encompasses stakeholders from across the business, including data
stewards. It includes a defined set of procedures, policies, and a plan
to execute on those procedures.

Realization of corporate data governance is largely motivated by a
desire to improve business operations and performance by gaining better
oversight and management of corporate information. While a data
governance program institutes policies and processes designed to produce
more accurate and consistent data throughout an organization, it
primarily becomes the job of the data steward to put those policies and
processes into practice by ensuring compliance. It's through governance
and enforcement of said policies where you are ultimately supporting
business process integrity, which in turn drives positive business
outcomes.

Data Quality Policies {#data-quality-policies conditions="Primary.Web" madcap="http://www.madcapsoftware.com/Schemas/MadCap.xsd"}
---------------------

Data Quality Policies {#data-quality-policies-1 .RNNoTOC conditions="Primary.Print" madcap="http://www.madcapsoftware.com/Schemas/MadCap.xsd"}
---------------------

Data policies allow users like data stewards to define thresholds, and
monitor breaches and deviations in the quality of the existing data as
well as incoming data.

Data quality policies apply Metrics on Datasets to measure the quality
of data. Thresholds define when users must be notified.

Policies enable data stewards to proactively monitor data. Data stewards
can define policies to ensure data completeness, uniqueness, accuracy
and more.

For more information, see the **Data Policies** topic in the **Data
Governance** documentation[ here]{.mcFormatColor style="color: Blue;"}.

Existing Data vs Incoming Data

Existing Data Policies evaluate data that exists in STEP each night.
Incoming Data Policies only evaluates the incoming data from an Inbound
Integration Endpoint of the Merge Golden Record type, allowing early
warnings if the source system starts sending bad data.

Data Quality Dimensions {#data-quality-dimensions conditions="Primary.Web" madcap="http://www.madcapsoftware.com/Schemas/MadCap.xsd"}
-----------------------

Data Quality Dimensions {#data-quality-dimensions-1 .RNNoTOC conditions="Primary.Print" madcap="http://www.madcapsoftware.com/Schemas/MadCap.xsd"}
-----------------------

With Data Quality there are dimensions that need to be considered which
are key cogs in driving the definition of Data Quality Policies.

Data Quality dimensions are not to be confused with language dimensions,
country dimensions, etc. that are platform-specific concepts.

Data Quality policies help organizations to ensure that data quality
complies with the business\' expectations.

Data quality policies use logical metrics on customer data to test the
quality threshold. These thresholds show a simplified view of the metric
performance. If data quality does not comply with the policy, a data
policy breach will be recorded. These policies will also update when the
data quality returns to normal expectations.

With these policies, data stewards are able to proactively monitor,
control, and maintain customer data from within CMDM. Data stewards can
build policies to ensure data completeness, uniqueness, accuracy, and
more.

Examples of data quality dimensions are:

-   Accuracy-- Is the data verified, accurate and up to date? Our 3rd
    party integrations can now verify aspects of party data using the
    very latest trusted reference sources.
-   Completeness-- What data is missing or unusable? Is all the
    necessary data present?
-   Timeliness - The degree to which data represents reality from a
    required point in time - Is data available at the time needed?

Metrics define the specifics of how to measure data quality.

For use cases with data governance concepts, see the **ACME Holding
Group Example Case** topic in this documentation[ here]{.mcFormatColor
style="color: Blue;"}.
