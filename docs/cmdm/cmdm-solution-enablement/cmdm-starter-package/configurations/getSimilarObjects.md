---
description: 'Customer MDM Solution: This topic covers how to send and
  receive calls using the getSimilarObject method.'
title: '\[%=Heading.AnyLevel%\]'
---

getSimilarObjects
=================

Business users in external systems throughout the enterprise may need to
check if customer records already exist. By using the getSimilarObjects
SOAP API call, the business can search to see if similar records exist
and prevent duplicates from being created at the point of entry.

Considerations
--------------

The getSimilarObjects call employs the matching functionality to produce
the potential duplicate results returned in the response. For this
reason, certain aspects of the solution must be appropriately paired for
the call to function.

For more information, see the **Search Before Create** topic of the
**Matching, Linking, and Merging** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Configuration
-------------

The matching configuration may need to be altered slightly to support
the getSimilarObjects call including even creating additional Match
Codes and Match Algorithms. It is important to examine the current
matching landscape to determine the alterations needed.

Determine the Match Algorithm to be used

The Match Algorithm being used to create and manage golden records may
not always be the best Match Algorithm to use for the getSimilarObjects
call. Consider if the business needs of the external system align with
the business needs of the existing governing Match Algorithm.

Who should make the decision when reviewing potential duplicates, a
person or a machine? If a person such as a Customer Service
Representative in an external system will be asking customers confirming
questions about the data that is found, a looser Match Algorithm may be
desired. If a machine is making the decision, there is no need for a
looser Match Algorithm than the existing governing Match Algorithm
because the decision will be made solely on the score.

To configure match codes and match algorithms to support
getSimilarObjects, see the get SimilarObject Match Codes and Match
Algorithms of the **Search Before Create** topic of the **Matching,
Linking, and Merging** documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Sample getSimilarObjects Calls
------------------------------

Sample calls for an Organizational Customer, a Contact Person, and an
Individual Customer are included as part of the initial configuration.
Households have been excluded as they are generally not created in
systems external to the CMDM system.

Organizational Customer

The Organizational Customer getSimilarObjects call uses the Organization
Matching Algorithm to identify potential duplicate Organization
Customers. For the incoming values to be compared, an Email, a Phone, or
an Organization Name and a Zip Code must be provided.

Request

    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://stibo.com/step/ws/step/1.0" xmlns:ns1="http://stibo.com/step/ws/types/1.0" xmlns:out="http://www.stibosystems.com/step/outputtemplate">

``` {space="preserve"}
  <soapenv:Header/>
```

``` {space="preserve"}
  <soapenv:Body>
```

``` {space="preserve"}
    <ns:getSimilarObjectsRequest>
```

``` {space="preserve"}
      <ns:accessContext>
```

``` {space="preserve"}
        <ns1:userName>StiboCMDM</ns1:userName>
```

``` {space="preserve"}
        <ns1:password>StiboCMDM</ns1:password>
```

``` {space="preserve"}
        <ns1:contextUrl>step://context?id=Context1</ns1:contextUrl>
```

``` {space="preserve"}
        <ns1:workspaceUrl>step://workspace?id=Main</ns1:workspaceUrl>
```

``` {space="preserve"}
      </ns:accessContext>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=LegalName</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>Saval Foods</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputStreet</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>6740 DORSY</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputCity</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>Elkridge</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputState</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>MD</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve" conditions="Primary.Print" madcap="http://www.madcapsoftware.com/Schemas/MadCap.xsd"}
-- Continued on next page --
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputZip</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>21075</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputCountry</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>US</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
       <ns:objectTypeURL>step://objecttype?id=OrganizationCustomer</ns:objectTypeURL>
```

``` {space="preserve"}
       <ns:matchingAlgorithmURL>step://matchingalgorithm?id=OrganizationMatchingAlgorithm</ns:matchingAlgorithmURL>
```

``` {space="preserve"}
       <ns:searchThreshold>1</ns:searchThreshold>
```

``` {space="preserve"}
       <ns:maxCount>10</ns:maxCount>
```

``` {space="preserve"}
     </ns:getSimilarObjectsRequest>
```

``` {space="preserve"}
   </soapenv:Body>
```

``` {space="preserve"}
</soapenv:Envelope>
```

Response

    <S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/">

``` {space="preserve"}
  <S:Body>
```

``` {space="preserve"}
    <ns3:getSimilarObjectsResponse xmlns="http://www.stibosystems.com/step/outputtemplate" xmlns:ns2="http://stibo.com/step/ws/types/1.0" xmlns:ns3="http://stibo.com/step/ws/step/1.0" xmlns:ns4="http://www.stibosystems.com/step">
```

``` {space="preserve"}
      <ns3:similarObjects>
```

``` {space="preserve"}
        <ns2:id>144767</ns2:id>
```

``` {space="preserve"}
        <ns2:url>step://entity?id=144767</ns2:url>
```

``` {space="preserve"}
        <ns2:title>Organization Customer Test</ns2:title>
```

``` {space="preserve"}
        <ns2:type>entity</ns2:type>
```

``` {space="preserve"}
        <ns2:objectType>step://objecttype?id=OrganizationCustomer</ns2:objectType>
```

``` {space="preserve"}
        <ns2:rank>100.0</ns2:rank>
```

``` {space="preserve"}
      </ns3:similarObjects>
```

``` {space="preserve"}
      <ns3:similarObjects>
```

``` {space="preserve"}
        <ns2:id>144575</ns2:id>
```

``` {space="preserve"}
        <ns2:url>step://entity?id=144575</ns2:url>
```

``` {space="preserve"}
        <ns2:title>(144575)</ns2:title>
```

``` {space="preserve"}
        <ns2:type>entity</ns2:type>
```

``` {space="preserve"}
        <ns2:objectType>step://objecttype?id=OrganizationCustomer</ns2:objectType>
```

``` {space="preserve"}
        <ns2:rank>68.625</ns2:rank>
```

``` {space="preserve"}
      </ns3:similarObjects>
```

``` {space="preserve"}
    </ns3:getSimilarObjectsResponse>
```

``` {space="preserve"}
  </S:Body>
```

    </S:Envelope>

Contact Person

The Contact Person getSimilarObjects call uses the Contact Person
Matching Algorithm to identify potential duplicate records. For the
incoming values to be compared, an Organization ID and one of the
following must be provided:

-   an Email,
-   a Phone,
-   a First Name, Last Name, and a Zip Code

The GetSimilarContactOrgID must be bound to the match code for
Organization IDs to be compared.

Request

    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://stibo.com/step/ws/step/1.0" xmlns:ns1="http://stibo.com/step/ws/types/1.0" xmlns:out="http://www.stibosystems.com/step/outputtemplate">

    <soapenv:Header/>

``` {space="preserve"}
  <soapenv:Body>
```

``` {space="preserve"}
    <ns:getSimilarObjectsRequest>
```

``` {space="preserve"}
      <ns:accessContext>
```

``` {space="preserve"}
        <ns1:userName>StiboCMDM</ns1:userName>
```

``` {space="preserve"}
        <ns1:password>StiboCMDM</ns1:password>
```

``` {space="preserve"}
        <ns1:contextUrl>step://context?id=Context1</ns1:contextUrl>
```

``` {space="preserve"}
        <ns1:workspaceUrl>step://workspace?id=Main</ns1:workspaceUrl>
```

``` {space="preserve"}
      </ns:accessContext>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=FirstName</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>Sergio</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=LastName</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>Bennett</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputStreet</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>525 STATE</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputCity</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>York</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve" conditions="Primary.Print" madcap="http://www.madcapsoftware.com/Schemas/MadCap.xsd"}
-- Continued on next page --
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputState</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>PA</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputCountry</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>US</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=EmailField</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>campbell@outlook.com</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=PhoneNumber</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>5323010724</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=GetSimilarContactOrgID</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>144581</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:objectTypeURL>step://objecttype?id=ContactPerson</ns:objectTypeURL>
```

``` {space="preserve"}
    <ns:matchingAlgorithmURL>step://matchingalgorithm?id=ContactPersonMatchingAlgorithm</ns:matchingAlgorithmURL>
```

``` {space="preserve"}
      <ns:searchThreshold>1</ns:searchThreshold>
```

``` {space="preserve"}
      <ns:maxCount>10</ns:maxCount>
```

``` {space="preserve"}
    </ns:getSimilarObjectsRequest>
```

``` {space="preserve"}
  </soapenv:Body>
```

    </soapenv:Envelope>

Response

    <S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/">

``` {space="preserve"}
  <S:Body>
```

``` {space="preserve"}
    <ns3:getSimilarObjectsResponse xmlns="http://www.stibosystems.com/step/outputtemplate" xmlns:ns2="http://stibo.com/step/ws/types/1.0" xmlns:ns3="http://stibo.com/step/ws/step/1.0" xmlns:ns4="http://www.stibosystems.com/step">
```

``` {space="preserve"}
      <ns3:similarObjects>
```

``` {space="preserve"}
        <ns2:id>149102</ns2:id>
```

``` {space="preserve"}
        <ns2:url>step://entity?id=149102</ns2:url>
```

``` {space="preserve"}
        <ns2:title>(149102)</ns2:title>
```

``` {space="preserve"}
        <ns2:type>entity</ns2:type>
```

``` {space="preserve"}
        <ns2:objectType>step://objecttype?id=ContactPerson</ns2:objectType>
```

``` {space="preserve"}
        <ns2:rank>100.0</ns2:rank>
```

``` {space="preserve"}
      </ns3:similarObjects>
```

``` {space="preserve"}
    </ns3:getSimilarObjectsResponse>
```

``` {space="preserve"}
  </S:Body>
```

    </S:Envelope>

Individual Customer

The Individual Customer getSimilarObjects call uses the
IndividualMatchingAlgorithm to identify potential duplicate Individual
Customers. For the incoming values to be compared, one of the following
attributes must be provided:

-   an Email
-   a Phone
-   First Name, Last Name, and a Zip Code

Request

    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://stibo.com/step/ws/step/1.0" xmlns:ns1="http://stibo.com/step/ws/types/1.0" xmlns:out="http://www.stibosystems.com/step/outputtemplate">

``` {space="preserve"}
  <soapenv:Header/>
```

``` {space="preserve"}
  <soapenv:Body>
```

``` {space="preserve"}
    <ns:getSimilarObjectsRequest>
```

``` {space="preserve"}
      <ns:accessContext>
```

``` {space="preserve"}
        <ns1:userName>StiboCMDM</ns1:userName>
```

``` {space="preserve"}
        <ns1:password>StiboCMDM</ns1:password>
```

``` {space="preserve"}
        <ns1:contextUrl>step://context?id=Context1</ns1:contextUrl>
```

``` {space="preserve"}
        <ns1:workspaceUrl>step://workspace?id=Main</ns1:workspaceUrl>
```

``` {space="preserve"}
      </ns:accessContext>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=FirstName</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>Aarone</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=MiddleName</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value></ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=LastName</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>Kirk</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputStreet</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>6770 West Via Tres Casas</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
-- Continued on next page --
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputCity</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>Tuson</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputState</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>AZ</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputZip</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>85743</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=InputCountry</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>US</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=EmailField</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>fringilla.est@eu.org</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:values>
```

``` {space="preserve"}
        <ns1:propertyURL>step://attribute?id=PhoneNumber</ns1:propertyURL>
```

``` {space="preserve"}
        <ns1:value>(310) 401-1771</ns1:value>
```

``` {space="preserve"}
      </ns:values>
```

``` {space="preserve"}
      <ns:objectTypeURL>step://objecttype?id=IndividualCustomer</ns:objectTypeURL>
```

``` {space="preserve"}
      <ns:matchingAlgorithmURL>step://matchingalgorithm?id=IndividualMatchingAlgorithm</ns:matchingAlgorithmURL>
```

``` {space="preserve"}
      <ns:searchThreshold>1</ns:searchThreshold>
```

``` {space="preserve"}
      <ns:maxCount>10</ns:maxCount>
```

``` {space="preserve"}
    </ns:getSimilarObjectsRequest>
```

``` {space="preserve"}
  </soapenv:Body>
```

    </soapenv:Envelope>

Response

    <S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/">

``` {space="preserve"}
  <S:Body>
```

``` {space="preserve"}
    <ns3:getSimilarObjectsResponse xmlns="http://www.stibosystems.com/step/outputtemplate" xmlns:ns2="http://stibo.com/step/ws/types/1.0" xmlns:ns3="http://stibo.com/step/ws/step/1.0" xmlns:ns4="http://www.stibosystems.com/step">
```

``` {space="preserve"}
      <ns3:similarObjects>
```

``` {space="preserve"}
        <ns2:id>152087</ns2:id>
```

``` {space="preserve"}
        <ns2:url>step://entity?id=152087</ns2:url>
```

``` {space="preserve"}
        <ns2:title>(152087)</ns2:title>
```

``` {space="preserve"}
        <ns2:type>entity</ns2:type>
```

``` {space="preserve"}
        <ns2:objectType>step://objecttype?id=IndividualCustomer</ns2:objectType>
```

``` {space="preserve"}
        <ns2:rank>100.0</ns2:rank>
```

``` {space="preserve"}
      </ns3:similarObjects>
```

``` {space="preserve"}
      <ns3:similarObjects>
```

``` {space="preserve"}
        <ns2:id>151889</ns2:id>
```

``` {space="preserve"}
        <ns2:url>step://entity?id=151889</ns2:url>
```

``` {space="preserve"}
        <ns2:title>(151889)</ns2:title>
```

``` {space="preserve"}
        <ns2:type>entity</ns2:type>
```

``` {space="preserve"}
        <ns2:objectType>step://objecttype?id=IndividualCustomer</ns2:objectType>
```

``` {space="preserve"}
        <ns2:rank>84.8</ns2:rank>
```

``` {space="preserve"}
      </ns3:similarObjects>
```

``` {space="preserve"}
      <ns3:similarObjects>
```

``` {space="preserve"}
        <ns2:id>152081</ns2:id>
```

``` {space="preserve"}
        <ns2:url>step://entity?id=152081</ns2:url>
```

``` {space="preserve"}
        <ns2:title>(152081)</ns2:title>
```

``` {space="preserve"}
        <ns2:type>entity</ns2:type>
```

``` {space="preserve" conditions="Primary.Print" madcap="http://www.madcapsoftware.com/Schemas/MadCap.xsd"}
    -- Continued on next page --
```

``` {space="preserve"}
    
```

``` {space="preserve"}
<ns2:objectType>step://objecttype?id=IndividualCustomer</ns2:objectType>
```

``` {space="preserve"}
        <ns2:rank>71.34</ns2:rank>
```

``` {space="preserve"}
      </ns3:similarObjects>
```

``` {space="preserve"}
    </ns3:getSimilarObjectsResponse>
```

``` {space="preserve"}
  </S:Body>
```

``` {space="preserve"}
</S:Envelope>
```

getSimilarObjects Use Cases
---------------------------

The following use cases are examples of how the getSimilarObjects can be
used to create unique records.

Business-to-Business (B2B) Use Case - Scenario 1 B2B Acquisitions
[here]{.mcFormatColor style="color: Blue;"}

Business to Customer (B2C) Use Case - Scenario 1 B2C Preventing
Duplications[ here]{.mcFormatColor style="color: Blue;"}
