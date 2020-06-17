---
description: 'Automotive Solution: Describes missing application
  coverage functionality.'
title: '\[%=Heading.AnyLevel%\]'
---

Missing Application Coverage Functionality
==========================================

PRODOC note: BOND RDCUST-3236 and PRODOC-1661 update topic from
hereApplication coverage is determined by both the Condition and Part
Type values. The existing and missing applications dropdown allows users
to determine if their search should or should not contain existing
and/or missing applications. The following three options are available
for the existing and missing applications dropdown:

-   Existing Applications Only
-   Existing and Missing Applications
-   Missing Applications Only

![](../../Resources/Images/AppMgr/Search%20Functions/Dropdown.png)

To search or report on missing applications, users can select either the
\'Missing Applications Only\' or \'Existing and Missing Applications\'
options from the dropdown located below the search boxes, and to the
left of the Report button.

Though it is not required, it is strongly recommended to include
criteria for at least one Vehicle and one Part Type before conducting a
missing application search. Failure to do so may result in very long
search times, timeout, or inconsistent results.

When users select the \'Missing Applications Only\' option, and the
Search or Report button is clicked, the following occurs:

1.  STEP searches for and displays existing combinations of the vehicles
    and part types defined in the search that do not have applications.
2.  If the Part Type search box is left blank, then the results table
    will display a new row for each combination of the vehicle(s) valid
    for the search criteria and the part types valid for that vehicle
    (and/or any additional search criteria).
3.  If applications exist for the vehicles and part types defined in the
    search, then STEP checks if the applications cover all the different
    configurations of the vehicle. This is found by using attributes
    that are populated and have a validation path. The additional
    configurations of the vehicle(s) are displayed as a new row in the
    results table. For more information about validation paths, see the
    **Automotive Validation Path Functionality** topic
    ([here]{.mcFormatColor style="color: Blue;"}) within this guide.

When the \'Existing and Missing Applications\' option is selected, in
addition to the actions described above, STEP also searches for and
displays existing combinations of the vehicles and part types defined in
the search.

In other words, when a search for missing applications is run, by
selecting either the \'Missing Applications Only\' or \'Existing and
Missing Applications\' option, the populated values on the existing
applications are evaluated to ensure that every option / criteria that
is populated with a value (and included in the attribute group
identified in the \'Application Condition Header - Group\') is
considered for all valid configurations of the selected vehicle(s). Each
combination that is considered valid, and does not have an application,
is displayed as a single row within both the Application Manager results
table, and the Application Coverage Report.

A blank / null value for any option / criteria equates to that option
being valid for ALL values of that option.

For example, consider a vehicle that has two Sub Models, each of which
is available with Gas or Diesel fuel types, and each fuel type has a
valid configuration with each Sub Model; totaling four valid
configurations of this vehicle. Further, assume that only Sub Model and
Fuel Type are populated on the records we are working with (e.g., no
other options have data populated in any of the existing records for the
selected vehicle and part type), and that Sub Model and Fuel Type are
both included in the attribute group identified in the application
condition header. Some of the scenarios based on data population and the
expected missing coverage outcome are as follows:

  [Existing Record]{style="font-weight: bold;"}                                    [Missing Application Record]{style="font-weight: bold;"}
  -------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------
  One record where Sub Model and Fuel Type are null                                None, as the existing record is understood to work for all Sub Model and Fuel Type options
  One record where Sub Model is populated with Sub Model 1 and Fuel Type is null   One record: Sub Model 2 + null Fuel Type
  One record where Fuel Type is populated with Gas and Sub Model is null           One record: null Sub Model + Diesel
  One record where Sub Model is populated with Sub Model 1 and Fuel Type is Gas    Three records: Sub Model 2 + Diesel, Sub Model 1 + Diesel, Sub Model 2 + Gas
  Two records: Sub Model 1 + null Fuel Type, Sub Model 2 + Gas                     One record: Sub Model 2 + Diesel
  No records                                                                       One record with both Sub Model and Fuel Type as null

PRODOC note: VCdb data had to be manually edited to create this scenario
on the 2010 Acura TSX, as it actually has 3 Mfr Body Codes. To test,
edit the Vehicle To Mfr Body Code references on the 2010 Acura TSX
vehicles so that each submodel has at least one vehicle using CU2 and at
least one vehicle using JH4CL9. For the case above, Canada Base = CU2,
Mexico Base = JH4CL9, US Base = CU2, Canada V6 = CU2, US V6 = JH4CL9.

Improving Part Type Accuracy
----------------------------

PRODOC note: MEDU RDUCST-2713 As previously mentioned, the application
data model (Automotive - Application Model) includes a relationship
between conditions on applications and different configurations of
vehicles. This is possible due to the automotive validation path
functionality. However, sometimes the conditions on specific part types
need to be considered to ensure that missing applications display more
accurately.

To implement this improvement, the automotive validation path
functionality and Check Path for Missing Application Business Condition
must be implemented. For more information, see the **Automotive
Validation Path Functionality** ([here]{.mcFormatColor
style="color: Blue;"}) and the **Business Condition: Check Path for
Missing Application** topics ([here]{.mcFormatColor
style="color: Blue;"}) within this guide.

PRODOC note: MEDU Easy setup now creates the attribute: Missing
Applications Conditions. A missing application will display for each
condition related to the part in the search, and each missing
application will display as a single row within both the Application
Manager results table, and the Application Coverage Report. When a
vehicle is available with two different engines, and a part is applied
to engine A, vehicles with engine B will display as a missing
application.
