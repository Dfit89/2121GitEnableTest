---
description: 'Customer MDM Solution: In a CMDM use case, source system
  performance can be monitored to determine data quality downstream.'
title: '\[%=Heading.Level1%\]'
---

Source System Performance
=========================

Bobby is a senior data analyst who is responsible for monitoring and
evaluating the overall performance and quality of customer data for the
many source systems (CRM platforms) within ACME Group subsidiaries.

To help support the upcoming season, Bobby is assisting the marketing
department in streamlining the promotional mailings process and reduce
overhead costs. To do so, Bobby requires the monitoring of address
quality ACME Group possesses for their customers, particularly to
identify quality within source systems to better identify and address
the root problems.

While an existing data quality policy allows for Bobby to gauge the
quality of addresses among the existing data set within ACME Group,
should there ever be a change in how data is captured in one of ACME
Group's many source systems, there is not a good way for Bobby to
realize this in a timely fashion. As such, a stream policy which
monitors data as they come in from individual source systems would allow
Bobby to more easily monitor the behavior/performance of each source
system.

With CMDM, a value metric allows for evaluating of attribute values and
mapping to specific scores. In the scenario of ACME Group's address
quality policy, all customer addresses are verified and standardized via
the Loqate integration which returns an Address Quality Index (AQI). The
AQI is a letter score which of the quality of input address that was
validated against Loqate's database. This letter score is evaluated and
resolved as a corresponding numeric score for the policy to profile and
display against.

The following table shows the evaluation of the AQI:

  Score      Quality     Description                                                                  Policy Score
  ---------- ----------- ---------------------------------------------------------------------------- --------------
  A          EXCELLENT   Verifiable to at least Premise level without changes                         10
  B          GOOD        Verifiable to at least Thoroughfare level with minor changes                 8
  C          AVERAGE     Verifiable to at least Locality level with moderate changes                  6
  D          POOR        Only verifiable to at least Locality level with more than moderate changes   4
  E          BAD         N/A                                                                          2
  \[null\]   N/A         No Address Validation / Quality Index                                        0

With this value metric defined, Bobby can configure individual policies
to evaluate source system performance of customer addresses. He is also
able to be notified of breaches and view the performance of a particular
source system via the policy dashboard:

![](../../../../../../Resources/Images/Solution%20Enablement/CMDM/Dashboard-Data-Policies.png)
