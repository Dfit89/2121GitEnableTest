---
description: This Customer MDM (CMDM) topic covers the getSimilarObjects
  web service calls.
title: '\[%=Heading.Level1%\]'
---

getSimilarObjects Search Before Create Call
===========================================

The following section discusses how the getSimilarObjects web service
sends a call when performing a Search Before Create operation. The
getSimilarObjects web service is a SOAP API call.

Overview of the getSimilarObjects Call
--------------------------------------

The getSimilarObjects request defines the criteria for the match and the
information to be returned. The following should be supplied in the
call.

-   **Access Context** - This parameter contains the username and
    password for the user accessing the system. It may optionally
    contain the context and workspace as well.
-   **Values** - The values supplied are used by the matching engine for
    comparison. The propertyURL points to the URL of the attribute ID in
    the system that the value should be associated with for comparison.
-   **Object Type URL** - This parameter is the URL of the object type
    in the system which will be used as a base for comparison.
-   **Matching Algorithm URL** - The URL of the Matching Algorithm in
    the system to perform the comparison.
-   **Export Configuration XML** - This optional section defines the
    information in XML format of the potential duplicates to be returned
    in the response. If excluded from the request, the STEP ID, STEP
    URL, Title, Super Type, Object Type URL, and Score will be returned.
    The records will be returned in order of highest score to lowest
    score.
-   **Search Threshold** - The score threshold of potential duplicates
    to be returned. If the search threshold is 70, only records that
    match the supplied values with a score of 70 or above will be
    returned in the response. The Clerical Review Threshold and the Auto
    Threshold defined in the Matching Algorithm are ignored.
-   **Max Count** - The maximum number of potential duplicates to
    return. If the matching algorithm identifies 100 records that score
    above the Search Threshold and the Max Count is set to 10, only the
    top 10 scoring records will be returned in the response.\]

Complete documentation for Web Services functionality related to
getSimilarObjects can be found in the SOAP API documentation at
\[system\]/sdk or by clicking the **STEP API Documentation** button on
the Start Page. This topic provides some basic information and an
example of a simple SOAP request but should not be considered
comprehensive.

### Node Binds and the getSimilarObjects Web Service

When a getSimilarObjects call is made, a node (permanent object) is not
created in the system. This means that the Match Code cannot get a hold
of the \'Current Object,\' and the Match Algorithm cannot get a hold of
the `first()` node via the Match Expression Context. For results to be
returned, the matching engine needs a way to compare the values in the
call to the values on the existing system nodes. This issue is solved
through Binds.

Binds associate incoming values to attributes in the system allowing the
matching engine to make the appropriate comparisons. All values used in
the Match Code should be defined under the binds flipper. Match Codes
should make use of the `if(node){}else{}` function for values not on the
current object such as the reference being used in the code below.
Additionally, Match Codes must exist on the records in the system for
the \'getSimilarObjects\' call to work.

![](../../getSimilarObjectsCall.png)

![](../../getSimilarObjectSnippet.png)

All values used in the Match Algorithm should be defined under the
Global Binds flipper. This expectation applies to both explicitly
configured attributes and for those configured via component models. If
customer data normalizers are used, the name of the global bind must
match the ID of the corresponding attribute.

If using the Address Normalizer in the Match Algorithm, the following
attributes defined in the Address Component Model should be bound to the
Match Algorithm:\

-   Input Street
-   Input City
-   Input State
-   Input Zip
-   Input Country
-   Country ISO Code

Matching using binds is not optimized for the In-Memory Database
Component.

![](../../GlobalBindsgetSimilarObjects.png)
