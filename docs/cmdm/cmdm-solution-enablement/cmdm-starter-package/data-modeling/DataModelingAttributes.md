---
description: 'Customer MDM Solution: This topic describes the attributes
  used as a part of the CMDM data model.'
title: Data Modeling Attributes
---

Data Modeling Attributes
========================

The following section details what attributes are used to create the
data model.

Attribute Groups
----------------

Attributes should be organized into domain specific attribute groups.
Typically, these domains include:

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/AttributeGroups.png)

-   Entity Type: **Address Data Containers**; Domain Folder: **Address
    Data**

  Attribute Name                   Attribute ID
  -------------------------------- ------------------------------
  Formatted Address                CalcFormattedAddress
  Country ISO Code                 CountryISOCode
  City                             InputCity
  Country                          InputCountry
  State                            InputState
  Street                           InputStreet
  Zip                              InputZip
  Latitude                         Latitude
  Longitude                        Longitude
  Quality                          Quality
  Quality Index                    QualityIndex
  Standardized City                StandardizedCity
  Standardized Country             StandardizedCountry
  Standardized Country ISO Code    StandardizedCountryISOCode
  Standardized Formatted Address   StandardizedFormattedAddress
  Standardized State               StandardizedState
  Standardized Street              StandardizedStreet
  Standardized Zip                 StandardizedZip
  Validation Hash                  ValidationHash
  Validation Integration Status    ValidationIntegrationStatus
  Validation Response              ValidationResponse
  Validation Time                  ValidationTime

For US addresses, Address1 should always be used since the US reference
data does not use a postal box. The PostBox field can be used for
countries whose reference data does contain a PO box.

-   Entity Type: **Individual Customer**; Domain Folder: **Individual
    Data**

  Attribute Name             Attribute ID
  -------------------------- ------------------------
  Birth Date                 BirthDate
  CalcAQI                    CalcAQI
  CalcHouseholdMembers       CalcHouseholdMembers
  Calc Individual Name       CalcName
  Name on Collection         CalcNameCollection
  Creation Date              CreationDate
  Credit Limit               CreditLimit
  Deactivated Record         DeactivatedRecord
  First Name                 FirstName
  Gender                     Gender
  Golden Record ID           GoldenRecordID
  Good Person Flag           GoodPersonFlag
  Income                     Income
  Income Update Date         IncomeUpdateDate
  Last Name                  LastName
  LastUpdated                LastUpdated
  Matching Source            MatchingSource
  Middle Name                MiddleName
  Nationality                Nationality
  Past Due Days              PastDueDays
  Past Due Dollars           PastDueDollars
  Risk Flag                  RiskFlag
  Sibling Delinquency Flag   SiblingDelinquencyFlag

For US addresses, \'Address1\' should always be used because US
reference data does not use postbox. The \'PostBox\' field can be used
for countries whose reference data does contain a PO box.

-   Entity Type: Organization Customer; Domain Folder: Organization Data

  Attribute Name       Attribute ID
  -------------------- --------------------
  Account Type         AccountType
  CalcAQI              CalcAQI
  Name on Collection   CalcNameCollection
  CompanyVATNumber     CompanyVATNumber
  Creation Date        CreationDate
  Deactivated Record   DeactivatedRecord
  Employee Size        EmployeeSize
  Golden Record ID     GoldenRecordID
  LastUpdated          LastUpdated
  Legal Name           LegalName
  NAICS Code           NAICSCode
  Revenue Size         RevenueSize
  SIC Code             SICCode

-   Customer Source System Reference Type

  Attribute Name     Attribute ID
  ------------------ ----------------
  Source Record ID   SourceRecordID

-   Entity Type: **Household**

  Attribute Name   Attribute ID
  ---------------- --------------
  Last Name        LastName

Data container types should be created under the domain with which they
are used.

These attributes can be used across different object types, like where
Individual and Organizational Customer records, as well as Contact data
on Individual Customer, Organization Customer, and Contact Person
records.

In accordance with the general guidelines for organizing attributes in
attribute groups, separate attribute groups should also be created for:

-   Displaying in Web UI, to ease Web UI component setup.
-   Each survivorship rule, to provide a clear definition of
    survivorship rules.
-   Each data quality policy, to provide a clear overview of which
    attributes are part of each data quality metric.
-   Each Object Type for each export definition, to provide a clear
    definition of what is exported to where.
-   In accordance to the guidelines around privilege configuration.
-   Each Object Type, to describe what is included in data profiling, to
    ease the profiling configuration.
