---
description: 'Customer MDM Solution: In large heterogenous enterprise
  landscapes, customer data is authored and stored in various systems
  across the enterprise such as the e-commerce system, the CRM system,
  the ERP system, etc. These systems provide valuable functions making
  it necessary that users continue to work in them. However, business
  processes, such as placing an order for a product, can often span
  multiple applications.'
title: '\[%=Heading.Level1%\]'
---

Match and Merge Webservice
==========================

In large heterogeneous enterprise landscapes, customer data is authored
and stored in various systems such as the e-commerce system, the CRM
system, the ERP system, etc. These systems provide valuable functions
making it necessary that users continue to work in them. However,
business processes, such as placing an order for a product, can often
span multiple applications. For instance, an order may come in via the
e-commerce system but be fulfilled by the ERP. This can often cause
problems due to significant dependencies on the consistency and
timeliness of data synchronization between applications. If the delivery
address for a customer is changed in the e-commerce system, it must also
be changed in the ERP, so the order can successfully be delivered.
Therefore, it is essential to create a tighter coupling between
operational systems and the MDM system, so that the customer data is
synchronized, as needed. This tight coupling is possible with a
Coexistence-Style MDM implementation, where centrally governed records
are created and updated in a large heterogeneous enterprise landscape.

In the Coexistence methodology, multiple systems containing the master
data must operate at the same time. The customer data is authored and
stored in various external sources while being synchronized to the MDM
system. This is accomplished in STEP through the synchronous,
request-response based web service for golden record creation and
update. This process involves deduplication, conflict resolution, and
validation operations, resulting in the creation / update of golden
records or rejection of the create / update. Updates to the data can be
done in the source system and any external systems that masters customer
data. STEP synchronizes the content of golden records back to the source
systems, keeping every source up to date with data contributed from any
source. This can be done either via direct integration with source
systems or publishing to a data warehouse both for synchronization and
for further analytics.

For the ability to only search STEP for existing records before new ones
are created in external systems, see the **getSimilarObjects** topic in
the supplementary documentation[ here]{.mcFormatColor
style="color: Blue;"}.

Web service for golden record creation and update use cases {#web-service-for-golden-record-creation-and-update-use-cases conditions="Primary.Web"}
-----------------------------------------------------------

Web service for golden record creation and update use cases {#web-service-for-golden-record-creation-and-update-use-cases-1 .RNNoTOC conditions="Primary.Print"}
-----------------------------------------------------------

Use case 1 -- Business to Business (B2B)

**Scenario 1 -- Reject creation or update**

Pedro, from the marketing team, is responsible for converting marketing
leads into retailer accounts. He needs to create, and
update retailers in the CRM and ERP based off of results from a
marketing campaign.

Pedro thinks the address information he gathered will be sufficient for
future business needs.  He doesn't realize how poor some of the address
data is and is unaware that some of the retailers gathered during the
marketing campaign are duplicates of existing retailers that have active
orders.  Pedro believes they are all new retailers to ACME and
thinks the leads collected are useable.  He doesn't realize some of the
retailers he collected during his campaign are no longer in
operation under the name collected.  The retailers have been acquired or
have gone out of business. The CRM and ERP are disjointed systems at
ACME with Pedro only having access to the CRM.  Changes to data are not
always propagated efficiently between the two systems.

As a result, Pedro causes operational inefficiencies with substantial
cost overhead in returned mail due to the poor address data.
He creates a poor customer
experience when creating duplicate retailers in the landscape. 
Duplicate retailers may be contacted by multiple different sales people
unaware of the existing relationship with the retailer. 
Additionally, updates to existing retailers may change the records in a
negative way. Pedro engenders operational inefficiencies when retailers
that do not meet the quality criteria are created.  This costs the sales
team both time and money when they pursue non-useable retailers. ACME
provides a poor customer experience as it struggles to keep retailers in
sync, accurate and up to date in both the CRM and ERP.

The following are examples of some solutions:

**As-is**

With the current System landscape, Pedro is unable to reject the
creation of records in the CRM when records that don't meet the
quality criteria are being created.  He also is unable to
reject duplicates during creation.  Additionally, when changes are made
to records in the CRM the ERP does not always reflect the most recent
version.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/AsIsPedroCoexistenceUseCase.png)

**To-be**

With the request-response web service for coexistence style CMDM in
place, Pedro is able to reject the creation or update of records during
the process.  This allows the business to reject potential duplicates
and records that do not meet quality criteria.  The problem is addressed
at the root, ensuring smoother operations throughout the entire
landscape.  Additionally, when the CRM notifies the ERP of changes to
records, the ERP can pull the missing master data from STEP with the
confidence that it is accurate and up to date.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/ToBePedroCoexistenceUseCase1.png)

Continued on next page.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/ToBePedroCoexistenceUseCase2.png)

Use Case 2 -- Business to Customer (B2C)

**Scenario 1 -- Call Center Update**

Maria, from the call center, is responsible for taking ACME orders over
the phone. She needs to associate a customer to orders in the CRM by
either updating an existing customer or creating a new customer
based off of the information provided during her phone calls.

Maria believes that the delivery address and the email
address information she enters for the customers are correct.  When in
fact she and the other customer service representatives frequently make
typos or don't enter the information properly such as Peachtree Street
vs Peach Tree Street. She is not able to determine if the customer
already exists in the enterprise landscape with existing orders.
Maria believes that any changes she makes to existing customers in the
CRM are automatically updated for their orders.

Maria causes operational inefficiencies with substantial cost
overhead in undelivered orders and in billing issues due to the poor
address data.  Operational inefficiencies also exist with missed cross
sell and up sell opportunities when email promotions are not delivered.
She provides a poor customer experience, due to her lack of knowledge of
other engagements with the same customer. ACME customers have a poor
customer experience because despite calling the call center to update
their information they are not seeing the changes reflected in their
orders.

The following are examples of some solutions:

**As-is**

With the current system landscape, Maria is unable to standardize and
validate incoming information.  She has a difficult time determining if
the customer already exists and syncing changes to existing customers
between the CRM and ERP.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/AsIsMariaCoexistenceUseCase1.png)

**To-be**

With the request-response web service for coexistence style CMDM in
place, Maria is able to standardize and validate incoming
information during the creation / update process.  From there, STEP is
able to determine if duplicates exist for the customer, then update the
existing customer based on the survivorship rules in place and send the
changes to the customer back to the CRM.  The CRM can then notify the
ERP which can poll STEP for the current customer information.  This
keeps the customer accurate and up to date throughout the landscape.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/ToBeMariaCoexistenceUseCase1.png)

Continued on next page.

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/Data%20Flow/ToBeMariaCoexistenceUseCase2.png)

Coexistence Considerations {#coexistence-considerations conditions="Primary.Web"}
--------------------------

Match and Merge Considerations {#match-and-merge-considerations .RN_notoc conditions="Primary.Print"}
------------------------------

The synchronous, request-response based web service for golden record
creation and update employs the matching functionality, business
actions, and business conditions to produce the information returned in
the response. For this reason, certain aspects of the solution must be
appropriately paired for the call to function.

For more information, see the **Match and Merge Web Service Endpoint**
topic of the **Matching, Linking, and Merging** documentation[
here]{.mcFormatColor style="color: Blue;"}.

Configuration

It is recommended that the same algorithms be used for the match and
merge web service requests.

The provided web service endpoints utilize Loqate to standardize
address, while also include an \'address check\' business condition.
This business condition allows for the rejection of records if a certain
data quality standard is not met.

**Sample Calls**

1.  Create New Contact Person
    -   Required values to identify match:
        -   Name
        -   Address
        -   Email
        -   Phone
2.  Update Existing Individual Customer
    -   Required values to identify match:
        -   Name
        -   Address
        -   Email
        -   Phone

```{=html}
<!-- -->
```
1.  Reject Organization Customer based on failed validation.
    -   Required value for successful validation:
        -   InputStreet

```{=html}
<!-- -->
```
1.  Reject Organization Customer as potential duplicate.
    -   Required values to identify match:
        -   Legal Name
        -   Address

```{=html}
<!-- -->
```
1.  **Request XML (New Contact Person)**

``` {space="preserve"}
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://stibo.com/step/ws/matching/1.0" xmlns:ns1="http://stibo.com/step/ws/types/1.0" xmlns:step="http://www.stibosystems.com/step"> 
   <soapenv:Header/> 
   <soapenv:Body> 
      <ns:matchAndMergeRequest> 
         <accessContext> 
            <ns1:userName>StiboCMDM</ns1:userName> 
            <ns1:password>StiboCMDM</ns1:password>  
            <ns1:contextUrl>step://context?id=Context1</ns1:contextUrl> 
         </accessContext> 
      <webserviceConfigurationID>Request-Contacts</webserviceConfigurationID> 
         <matchAndMergeRecord CorrelationID="9"> 
            <ns1:Entity ParentID="111660" UserTypeID="ContactPerson"> 
               <step:Name>Joanna Nuckols</step:Name> 
               <step:Entity/> 
               <step:EntityCrossReference Type="CustomerSourceSystem" EntityID="SystemX"> 
                  <step:MetaData> 
                     <step:Value AttributeID="SourceRecordID">123</step:Value> 
                  </step:MetaData> 
               </step:EntityCrossReference> 
               <step:Values> 
                  <step:Value AttributeID="FirstName">Joannabbb</step:Value> 
                  <step:Value AttributeID="LastName">Nuckols</step:Value> 
               </step:Values> 
               <step:DataContainers> 
                  <step:DataContainer Type="MainAddressDataContainer"> 
                     <step:Values> 
                        <step:Value AttributeID="InputStreet">195 horseshoe ln</step:Value> 
                        <step:Value AttributeID="InputCity">Missoula</step:Value> 
                        <step:Value AttributeID="InputCountry">USA</step:Value> 
                        <step:Value AttributeID="InputState">MT</step:Value> 
                        <step:Value AttributeID="InputZip">59803</step:Value> 
                     </step:Values> 
                  </step:DataContainer> 
                  <step:MultiDataContainer Type="PhoneDataContainer"> 
                     <step:DataContainer> 
                        <step:Values> 
                           <step:Value AttributeID="PhoneNumber">4065467413</step:Value> 
                        </step:Values> 
                     </step:DataContainer> 
                  </step:MultiDataContainer> 
                  <step:MultiDataContainer Type="EmailDataContainer"> 
                     <step:DataContainer> 
                        <step:Values> 
                           <step:Value AttributeID="EmailField">_jonuckols@aol.com</step:Value> 
                        </step:Values> 
                     </step:DataContainer> 
                  </step:MultiDataContainer> 
               </step:DataContainers> 
            </ns1:Entity> 
         </matchAndMergeRecord> 
      </ns:matchAndMergeRequest> 
   </soapenv:Body> 
</soapenv:Envelope> 
```

**Response XML (New Contact Person)**

``` {space="preserve"}
<S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/"> 
   <S:Body> 
      <ns5:matchAndMergeResponse xmlns:ns2="http://stibo.com/step/ws/types/1.0" xmlns:ns3="http://www.stibosystems.com/step" xmlns:ns4="http://www.stibosystems.com/step/outputtemplate" xmlns:ns5="http://stibo.com/step/ws/matching/1.0"> 
         <matchAndMergeRecord CorrelationID="9"> 
            <ns2:status>PROCESSED</ns2:status> 
            <ns2:matchAndMergeExecutionReport> 
               <ns2:operation>NEW</ns2:operation> 
            </ns2:matchAndMergeExecutionReport> 
            <ns2:Entity UserTypeID="ContactPerson" ID="161574" ParentID="111660"> 
               <ns3:EntityCrossReference EntityID="SystemX" Type="CustomerSourceSystem"> 
                  <ns3:MetaData> 
                     <ns3:MultiValue AttributeID="SourceRecordID"> 
                        <ns3:Value>123</ns3:Value> 
                     </ns3:MultiValue> 
                  </ns3:MetaData> 
               </ns3:EntityCrossReference> 
               <ns3:Values> 
                  <ns3:Value AttributeID="FirstName">Joannabbb</ns3:Value> 
                  <ns3:Value AttributeID="LastName">Nuckols</ns3:Value> 
               </ns3:Values> 
               <ns3:DataContainers> 
                  <ns3:MultiDataContainer Type="EmailDataContainer"> 
                     <ns3:DataContainer ID="161576"> 
                        <ns3:Values> 
                           <ns3:Value AttributeID="EmailField">_jonuckols@aol.com</ns3:Value> 
                        </ns3:Values> 
                     </ns3:DataContainer> 
                  </ns3:MultiDataContainer> 
                  <ns3:MultiDataContainer Type="PhoneDataContainer"> 
                     <ns3:DataContainer ID="161577"> 
                        <ns3:Values> 
                           <ns3:Value AttributeID="PhoneNumber">4065467413</ns3:Value> 
                        </ns3:Values> 
                     </ns3:DataContainer> 
                  </ns3:MultiDataContainer> 
                  <ns3:DataContainer Type="MainAddressDataContainer" ID="161575"> 
                     <ns3:Values> 
                        <ns3:Value Derived="true" AttributeID="CalcFormattedAddress">
```

``` {space="preserve"}
             195 horseshoe ln                        
                 Missoula, MT, 59803        
                 USA
```

``` {space="preserve"}
            </ns3:Value> 
                     </ns3:Values> 
                  </ns3:DataContainer> 
               </ns3:DataContainers> 
            </ns2:Entity> 
         </matchAndMergeRecord> 
      </ns5:matchAndMergeResponse> 
   </S:Body> 
</S:Envelope>
```

1.  **Request XML (Update Individual Customer)**

``` {space="preserve"}
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://stibo.com/step/ws/matching/1.0" xmlns:ns1="http://stibo.com/step/ws/types/1.0" xmlns:step="http://www.stibosystems.com/step"> 
   <soapenv:Header/> 
   <soapenv:Body> 
      <ns:matchAndMergeRequest> 
         <accessContext> 
            <ns1:userName>StiboCMDM</ns1:userName> 
            <ns1:password>StiboCMDM</ns1:password>   
            <ns1:contextUrl>step://context?id=Context1</ns1:contextUrl> 
         </accessContext> 
 <webserviceConfigurationID>Request-Individual</webserviceConfigurationID> 
         <matchAndMergeRecord CorrelationID="9"> 
            <ns1:Entity ParentID="111656" UserTypeID="IndividualCustomer"> 
               <step:Name>Joanna Nuckols</step:Name> 
               <step:Entity/> 
               <step:EntityCrossReference Type="CustomerSourceSystem" EntityID="SystemY"> 
                  <step:MetaData> 
                     <step:Value AttributeID="SourceRecordID">999</step:Value> 
                  </step:MetaData> 
               </step:EntityCrossReference> 
               <step:Values> 
                  <step:Value AttributeID="FirstName">Joanna</step:Value> 
                  <step:Value AttributeID="LastName">Nuckols</step:Value> 
                  <step:Value AttributeID="Gender">Female</step:Value> 
               </step:Values> 
               <step:DataContainers> 
                  <step:DataContainer Type="MainAddressDataContainer"> 
                     <step:Values> 
                        <step:Value AttributeID="InputStreet">195 horseshoe ln</step:Value> 
                        <step:Value AttributeID="InputCity">Missoula</step:Value> 
                        <step:Value AttributeID="InputCountry">US</step:Value> 
                        <step:Value AttributeID="InputState">MT</step:Value> 
                        <step:Value AttributeID="InputZip">59803</step:Value> 
                     </step:Values> 
                  </step:DataContainer> 
                  <step:MultiDataContainer Type="PhoneDataContainer"> 
                     <step:DataContainer> 
                        <step:Values> 
                           <step:Value AttributeID="PhoneNumber">4065467413</step:Value> 
                        </step:Values> 
                     </step:DataContainer> 
                  </step:MultiDataContainer> 
                  <step:MultiDataContainer Type="EmailDataContainer"> 
                     <step:DataContainer> 
                        <step:Values> 
                           <step:Value AttributeID="EmailField">_jonuckols@aol.com</step:Value> 
                        </step:Values> 
                     </step:DataContainer> 
                  </step:MultiDataContainer> 
               </step:DataContainers> 
            </ns1:Entity> 
         </matchAndMergeRecord> 
      </ns:matchAndMergeRequest> 
   </soapenv:Body> 
</soapenv:Envelope> 

 
```

**Response XML (Update Individual Customer)**

``` {space="preserve"}
<S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/"> 
   <S:Body> 
      <ns5:matchAndMergeResponse xmlns:ns2="http://stibo.com/step/ws/types/1.0" xmlns:ns3="http://www.stibosystems.com/step" xmlns:ns4="http://www.stibosystems.com/step/outputtemplate" xmlns:ns5="http://stibo.com/step/ws/matching/1.0"> 
         <matchAndMergeRecord CorrelationID="9"> 
            <ns2:status>PROCESSED</ns2:status> 
            <ns2:matchAndMergeExecutionReport> 
               <ns2:operation>UPDATE</ns2:operation> 
            </ns2:matchAndMergeExecutionReport> 
            <ns2:Entity UserTypeID="IndividualCustomer" ID="161578" ParentID="111656"> 
               <ns3:EntityCrossReference EntityID="SystemY" Type="CustomerSourceSystem"> 
                  <ns3:MetaData> 
                     <ns3:MultiValue AttributeID="SourceRecordID"> 
                        <ns3:Value>999</ns3:Value> 
                     </ns3:MultiValue> 
                  </ns3:MetaData> 
               </ns3:EntityCrossReference> 
               <ns3:Values> 
                  <ns3:Value AttributeID="FirstName">Joanna</ns3:Value> 
                  <ns3:Value AttributeID="LastName">Nuckols</ns3:Value> 
               </ns3:Values> 
               <ns3:DataContainers> 
                  <ns3:MultiDataContainer Type="EmailDataContainer"> 
                     <ns3:DataContainer ID="161579"> 
                        <ns3:Values> 
                           <ns3:Value AttributeID="EmailField">_jonuckols@aol.com</ns3:Value> 
                        </ns3:Values> 
                     </ns3:DataContainer> 
                  </ns3:MultiDataContainer> 
                  <ns3:MultiDataContainer Type="PhoneDataContainer"> 

                     <ns3:DataContainer ID="161580"> 
                        <ns3:Values> 
                           <ns3:Value AttributeID="PhoneNumber">4065467413</ns3:Value> 
                        </ns3:Values> 
                     </ns3:DataContainer> 
                  </ns3:MultiDataContainer> 
                  <ns3:DataContainer Type="MainAddressDataContainer" ID="161581"> 
                     <ns3:Values> 
                        <ns3:Value Derived="true" AttributeID="CalcFormattedAddress">
```

``` {space="preserve"}
             195 Horseshoe Ln 
                 Missoula MT 59803-9702 
                 United States
```

``` {space="preserve"}
          </ns3:Value> 
                     </ns3:Values> 
                  </ns3:DataContainer> 
               </ns3:DataContainers> 
            </ns2:Entity> 
         </matchAndMergeRecord> 
      </ns5:matchAndMergeResponse> 
   </S:Body> 
</S:Envelope>
```

1.  **Request XML (Reject Organization Customer for failed validation)**

```{=html}
<!-- -->
```
    <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://stibo.com/step/ws/matching/1.0" xmlns:ns1="http://stibo.com/step/ws/types/1.0" xmlns:step="http://www.stibosystems.com/step"> 
       <soapenv:Header/> 
       <soapenv:Body> 
          <ns:matchAndMergeRequest> 
             <accessContext> 
                <ns1:userName>StiboCMDM</ns1:userName> 
                <ns1:password>StiboCMDM</ns1:password>   
                <ns1:contextUrl>step://context?id=Context1</ns1:contextUrl> 
             </accessContext> 
     <webserviceConfigurationID>Request-Organizations</webserviceConfigurationID> 
             <matchAndMergeRecord CorrelationID="9"> 
                <ns1:Entity ParentID="111301" UserTypeID="OrganizationCustomer"> 
                   <step:Name>Stibo Systems</step:Name> 
                   <step:Entity/> 
                   <step:EntityCrossReference Type="CustomerSourceSystem" EntityID="SystemX"> 
                      <step:MetaData> 
                         <step:Value AttributeID="SourceRecordID">321</step:Value> 
                      </step:MetaData> 
                   </step:EntityCrossReference> 
                   <step:Values> 
                      <step:Value AttributeID="LegalName">Stibo Systems</step:Value> 
                   </step:Values> 
                   <step:DataContainers> 
                      <step:DataContainer Type="MainAddressDataContainer"> 
                         <step:Values> 
                            <step:Value AttributeID="InputStreet"></step:Value> 
                            <step:Value AttributeID="InputCity">Kennesaw</step:Value> 
                            <step:Value AttributeID="InputCountry">USA</step:Value> 
                            <step:Value AttributeID="InputState">GA</step:Value> 
                            <step:Value AttributeID="InputZip">30144</step:Value> 
                         </step:Values> 
                      </step:DataContainer> 
                      <step:MultiDataContainer Type="PhoneDataContainer"> 
                         <step:DataContainer> 
                            <step:Values> 
                               <step:Value AttributeID="PhoneNumber">7701231234</step:Value> 
                            </step:Values> 
                         </step:DataContainer> 
                      </step:MultiDataContainer> 
                      <step:MultiDataContainer Type="EmailDataContainer"> 
                         <step:DataContainer> 
                            <step:Values> 
                               <step:Value AttributeID="EmailField">stibo@stibo.com</step:Value> 
                            </step:Values> 
                         </step:DataContainer> 
                      </step:MultiDataContainer> 
                   </step:DataContainers> 
                </ns1:Entity> 
             </matchAndMergeRecord> 
          </ns:matchAndMergeRequest> 
       </soapenv:Body> 
    </soapenv:Envelope> 

Response XML (Reject Organization Customer for failed validation)

    <S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/"> 
       <S:Body> 
          <ns5:matchAndMergeResponse xmlns:ns2="http://stibo.com/step/ws/types/1.0" xmlns:ns3="http://www.stibosystems.com/step" xmlns:ns4="http://www.stibosystems.com/step/outputtemplate" xmlns:ns5="http://stibo.com/step/ws/matching/1.0"> 
             <matchAndMergeRecord CorrelationID="9"> 
                <ns2:status>REJECTED</ns2:status> 
                <ns2:matchAndMergeExecutionReport> 
                   <ns2:operation>UPDATE</ns2:operation> 
                   <ns2:recordRejectedBy> 
                      <ns2:rejectedByBusinessCondition> 
                         <ns2:businessConditionID>CheckAddress</ns2:businessConditionID> 
                     </ns2:rejectedByBusinessCondition> 
                   </ns2:recordRejectedBy> 
                </ns2:matchAndMergeExecutionReport> 
                <ns2:Entity UserTypeID="OrganizationCustomer" ParentID="111301"> 
                   <ns3:Name>Stibo Systems</ns3:Name> 
                   <ns3:Entity/> 
                   <ns3:EntityCrossReference EntityID="SystemX" Type="CustomerSourceSystem"> 
                      <ns3:MetaData> 
                         <ns3:Value AttributeID="SourceRecordID">321</ns3:Value> 
                      </ns3:MetaData> 
                   </ns3:EntityCrossReference> 
                   <ns3:Values> 
                      <ns3:Value AttributeID="LegalName">Stibo Systems</ns3:Value> 
                   </ns3:Values> 
                   <ns3:DataContainers> 
                      <ns3:DataContainer Type="MainAddressDataContainer"> 
                         <ns3:Values> 
                            <ns3:Value AttributeID="InputStreet"/> 
                            <ns3:Value AttributeID="InputCity">Kennesaw</ns3:Value> 
                            <ns3:Value AttributeID="InputCountry">USA</ns3:Value> 
                            <ns3:Value AttributeID="InputState">GA</ns3:Value> 
                            <ns3:Value AttributeID="InputZip">30144</ns3:Value> 
                         </ns3:Values> 
                      </ns3:DataContainer> 
                      <ns3:MultiDataContainer Type="PhoneDataContainer"> 
                         <ns3:DataContainer ID=""> 
                            <ns3:Values> 
                               <ns3:Value AttributeID="PhoneNumber">7701231234</ns3:Value> 
                            </ns3:Values> 
                         </ns3:DataContainer> 
                      </ns3:MultiDataContainer> 
                      <ns3:MultiDataContainer Type="EmailDataContainer"> 
                         <ns3:DataContainer ID=""> 
                            <ns3:Values> 
                               <ns3:Value AttributeID="EmailField">stibo@stibo.com</ns3:Value> 
                            </ns3:Values> 
                         </ns3:DataContainer> 
                      </ns3:MultiDataContainer> 
                   </ns3:DataContainers> 
                </ns2:Entity> 
             </matchAndMergeRecord> 
          </ns5:matchAndMergeResponse> 
       </S:Body> 
    </S:Envelope> 

1.  Request XML(Reject Organization Customer as potential duplicate)

``` {space="preserve"}
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns="http://stibo.com/step/ws/matching/1.0" xmlns:ns1="http://stibo.com/step/ws/types/1.0" xmlns:step="http://www.stibosystems.com/step"> 
   <soapenv:Header/> 
   <soapenv:Body> 
      <ns:matchAndMergeRequest> 
         <accessContext> 
            <ns1:userName>StiboCMDM</ns1:userName> 
            <ns1:password>StiboCMDM</ns1:password>   
            <ns1:contextUrl>step://context?id=Context1</ns1:contextUrl> 
         </accessContext> 
         <webserviceConfigurationID>Request-Organizations</webserviceConfigurationID> 
         <matchAndMergeRecord CorrelationID="9"> 
            <ns1:Entity ParentID="111301" UserTypeID="OrganizationCustomer"> 
               <step:Name>Stibo Systems</step:Name> 
               <step:Entity/> 
               <step:EntityCrossReference Type="CustomerSourceSystem" EntityID="SystemY"> 
                  <step:MetaData> 
                     <step:Value AttributeID="SourceRecordID">123</step:Value> 
                  </step:MetaData> 
               </step:EntityCrossReference> 
               <step:Values> 
                  <step:Value AttributeID="LegalName">Stibo System</step:Value> 
               </step:Values>
               <step:DataContainers> 
                  <step:DataContainer Type="MainAddressDataContainer"> 
                     <step:Values> 
                        <step:Value AttributeID="InputStreet">3550 George Busbee pkwy</step:Value> 
                        <step:Value AttributeID="InputCity">Kennesaw</step:Value> 
                        <step:Value AttributeID="InputCountry">US</step:Value> 
                        <step:Value AttributeID="InputState">GA</step:Value> 
                        <step:Value AttributeID="InputZip">30144</step:Value> 
                     </step:Values> 
                  </step:DataContainer> 
                  <step:MultiDataContainer Type="PhoneDataContainer"> 
                     <step:DataContainer> 
                        <step:Values> 
                           <step:Value AttributeID="PhoneNumber">7701231234</step:Value> 
                        </step:Values>
                     </step:DataContainer> 
                  </step:MultiDataContainer> 
                  <step:MultiDataContainer Type="EmailDataContainer"> 
                     <step:DataContainer> 
                        <step:Values> 
                           <step:Value AttributeID="EmailField">stibo@stibo.com</step:Value> 
                        </step:Values> 
                     </step:DataContainer> 
                  </step:MultiDataContainer> 
               </step:DataContainers> 
            </ns1:Entity> 
         </matchAndMergeRecord> 
      </ns:matchAndMergeRequest> 
   </soapenv:Body> 
</soapenv:Envelope>  
```

Response XML (Reject Organization Customer as potential duplicate)

``` {space="preserve"}
<S:Envelope xmlns:S="http://schemas.xmlsoap.org/soap/envelope/"> 
   <S:Body> 
      <ns5:matchAndMergeResponse xmlns:ns2="http://stibo.com/step/ws/types/1.0" xmlns:ns3="http://www.stibosystems.com/step" xmlns:ns4="http://www.stibosystems.com/step/outputtemplate" xmlns:ns5="http://stibo.com/step/ws/matching/1.0"> 
         <matchAndMergeRecord CorrelationID="9"> 
            <ns2:status>REJECTED</ns2:status> 
            <ns2:potentialDuplicate> 
               <ns2:rank>70.0</ns2:rank> 
               <ns2:Entity UserTypeID="OrganizationCustomer" ID="161585" ParentID="111301"> 
                  <ns3:EntityCrossReference EntityID="SystemX" Type="CustomerSourceSystem"> 
                     <ns3:MetaData> 
                        <ns3:MultiValue AttributeID="SourceRecordID"> 
                           <ns3:Value>321</ns3:Value> 
                        </ns3:MultiValue> 
                     </ns3:MetaData> 
                  </ns3:EntityCrossReference> 
                  <ns3:Values> 
                     <ns3:Value AttributeID="LegalName">Stibo Systems</ns3:Value> 
                  </ns3:Values> 
                  <ns3:DataContainers> 
                     <ns3:DataContainer Type="MainAddressDataContainer" ID="161586"> 
                        <ns3:Values> 
                           <ns3:Value Derived="true" AttributeID="CalcFormattedAddress">
```

``` {space="preserve"}
              3550 George Busbee Pkwy NW 
                 Kennesaw GA 30144-6608  
                 United States</ns3:Value> 
                        </ns3:Values> 
                     </ns3:DataContainer> 
                  </ns3:DataContainers> 
               </ns2:Entity> 
            </ns2:potentialDuplicate> 
            <ns2:matchAndMergeExecutionReport> 
               <ns2:recordRejectedBy> 
                  <ns2:rejectedByPotentialDuplicates>true</ns2:rejectedByPotentialDuplicates> 
               </ns2:recordRejectedBy> 
            </ns2:matchAndMergeExecutionReport> 
            <ns2:Entity UserTypeID="OrganizationCustomer" ParentID="111301"> 
               <ns3:Name>Stibo Systems</ns3:Name> 
               <ns3:Entity/> 
               <ns3:EntityCrossReference EntityID="SystemY" Type="CustomerSourceSystem"> 
                  <ns3:MetaData> 
                     <ns3:Value AttributeID="SourceRecordID">123</ns3:Value> 
                  </ns3:MetaData> 
               </ns3:EntityCrossReference> 
               <ns3:Values> 
                  <ns3:Value AttributeID="LegalName">Stibo System</ns3:Value> 
               </ns3:Values> 
               <ns3:DataContainers> 
                  <ns3:DataContainer Type="MainAddressDataContainer"> 
                     <ns3:Values> 
                        <ns3:Value AttributeID="InputStreet">3550 George Busbee pkwy</ns3:Value> 
                        <ns3:Value AttributeID="InputCity">Kennesaw</ns3:Value> 
                        <ns3:Value AttributeID="InputCountry">US</ns3:Value> 
                        <ns3:Value AttributeID="InputState">GA</ns3:Value> 
                        <ns3:Value AttributeID="InputZip">30144</ns3:Value> 
                     </ns3:Values> 
                  </ns3:DataContainer> 
                  <ns3:MultiDataContainer Type="PhoneDataContainer"> 
                     <ns3:DataContainer ID=""> 
                        <ns3:Values> 
                           <ns3:Value AttributeID="PhoneNumber">7701231234</ns3:Value> 
                        </ns3:Values> 
                     </ns3:DataContainer> 
                  </ns3:MultiDataContainer> 
                  <ns3:MultiDataContainer Type="EmailDataContainer"> 
                     <ns3:DataContainer ID=""> 
                        <ns3:Values> 
                           <ns3:Value AttributeID="EmailField">stibo@stibo.com</ns3:Value> 
                        </ns3:Values> 
                     </ns3:DataContainer> 
                  </ns3:MultiDataContainer> 
               </ns3:DataContainers> 
            </ns2:Entity> 
         </matchAndMergeRecord> 
      </ns5:matchAndMergeResponse> 
   </S:Body> 
</S:Envelope> 
```
