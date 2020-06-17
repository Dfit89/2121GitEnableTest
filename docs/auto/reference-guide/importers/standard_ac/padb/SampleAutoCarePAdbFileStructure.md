---
description: 'Automotive Solution: Introduces the AutoCare PAdb sample
  file structure.'
title: '\[%=Heading.AnyLevel%\]'
---

Sample AutoCare PAdb File Structure
===================================

PRODOC note: Details can be found at PRODOC-1248

The intention of this topic is to introduce the basic AutoCare PAdb file
structure and the way the objects are built in the system when a PAdb
file is imported into the system.

Currently, the Automotive solution supports import and export of PAdb
version files:

The below mentioned figure describes the basic flow of the project from
the PAdb provided by the Auto Care Association through the several
primary processes of creating the necessary LOVs, matching the required
Units of Measure, creating the PAdb attributes and linking the PAdb
attributes to the Part Terminologies (sometimes referred to and
configured as Part Type in STEP) as dictated by the PAdb.

![](../../../../Resources/Images/Importers/Standard_AC/57.png)

Delivering PAdb Files

The PAdb is made up of eight tables (8 pipe-delimited text files ) that
when used together with an already existing PCdb Parts table, define a
standardized source of Automotive Aftermarket Part Attributes including
their validation and Part Type linkages. An archiving program (such as
WinZip, or Windows XP \'Compressed (zipped) Folders\') is used to
compress the files into a single ZIP archive. So the PAdb file is always
with a \'.zip\' extension. The naming convention of the Zip file usually
be in the standardized format 'AAIA PAdb ASCII YYYYMMDD' where YYYYMMDD
represents the year, month and the date. Example: AAIA PAdb ASCII
20180427

The following 8 pipe-delimited text files are available within the PAdb
Zip file.

-   MetaData.txt
-   MetaUOMCodes.txt
-   PartAttributeAssignment.txt
-   PartAttributes.txt
-   PartAttributeStyle.txt
-   PartTypeStyle.txt
-   Style.txt
-   Version.txt

The way it is structured is demonstrated in the screenshot below.

![](../../../../Resources/Images/Importers/Standard_AC/58.png)

The relation between each of the text file is demonstrated with the ER
(Entity Relation) diagram in the screenshot below.

![](../../../../Resources/Images/Importers/Standard_AC/59.png)

The Information regarding the PAdb Attribute validations will be sourced
from three tables (.txt files) namely: PartAttributes.txt,
PartAttributeAssigment.txt and MetaData.txt

A description of each of these eight tables (.txt files) follows below.

### MetaData.txt

This file contains the attribute value validation rules and is joined to
PartAttributeAssignment.txt (described below in this topic). The
relationship between MetaData.txt to PartAttributeAssignment.txt is a
One-to-Many with each record in MetaData.txt potentially being
referenced by many distinct records in PartAttributeAssignment.txt

In the .txt file the last four fields, DataType, MinLength, MaxLength
and Decimals are used to determine the broadest validation necessary for
creating PAdb attributes in STEP

The MetaData.txt file contains seven columns / headers. The table below
explains each of the .

  Header       Description
  ------------ ----------------------------------------------------------------------------------------------------------------
  MetaID       Provides the Primary Key and unique identifier for the combination of fields 2 through 7 throughout the table.
  MetaName     Provides the text Name of Entry.
  MetaDescr    Provides the text Description of Entry.
  MetaFormat   Provides the Abbreviated Format Description.
  DataType     Provides the Basic Data Type (Text, Integer, Alphanumeric, Decimal, etc).
  MinLength    Provides the Minimum Length Limit (Length of characters).
  MaxLength    Provides the Maximum Length Limit (Length of characters).

### PartAttributeAssignment.txt

The Price Sheet Header Segment is used to define from zero to any number
of price sheets. When exchanging pricing data with a trading partner, it
is recommended to define at least one Price Sheet Header. The
\<PriceSheetNumber\> defined in the Price Sheet Header segment will be
referenced within the Price Segment for an individual PIES Item record.

The Price Sheet Header Segment is defined within the \<PriceSheets\>
tag. This segment is an optional looping segment within the
specification, meaning there may be zero instances of this segment in a
PIES file. If this segment is used, there must be one or more instances
of a child \<PriceSheet\> \</PriceSheet\> loop. Multiple loops of a
\<PriceSheet\> \</PriceSheet\> section may be used to define multiple
Price Sheets.

A sample PIES Sheet Header Segment and a screenshot of how the segment
is populated in STEP are displayed below.

``` {.PreIndent space="preserve"}
<PriceSheets>
        <PriceSheet MaintenanceType="A">
            <PriceSheetNumber>2017WD</PriceSheetNumber>
            <PriceSheetName>2017 WD Prices</PriceSheetName>
            <SupersededPriceSheetNumber>2016WD</SupersededPriceSheetNumber>
            <CurrencyCode>USD</CurrencyCode>
            <PriceZone>Western</PriceZone>
            <EffectiveDate>2017-03-07</EffectiveDate>
            <ExpirationDate>2018-03-07</ExpirationDate>
        </PriceSheet>
    </PriceSheets>
```

![](../../../../Resources/Images/Importers/Standard_AC/35.png){.Inch6}

![](../../../../Resources/Images/Importers/Standard_AC/31.png)

### PIES Item Segment (ITEM)

The Item segment is the core looping (or repeating) segment within the
PIES standard. Each instance of this segment is responsible for defining
individual Item Part Numbers (which are also called PIES Items).

All \<Item\> instances are contained within the parent \<Items\>
element. For each Item Part Number (PIES Item) to be defined, a new
instance of \<Item\> and its child elements are initiated. Many of the
child elements under \<Item\> are themselves segments of PIES which are
defined later in this topic.

The following XML sample code shows the upper level \<Items\> element
and the beginning of a single instance of \<Item\>. The child elements
are part of the logical grouping known as the Item Segment. Further
segments continue from the end of this code sample.

A sample PIES XML PIES Item structure and a screenshot of how it is
populated in STEP is displayed below.

``` {.PreIndent space="preserve"}
<Items>
        <Item MaintenanceType="A">
            <HazardousMaterialCode>Y</HazardousMaterialCode>
            <BaseItemID>VC21</BaseItemID>
            <ItemLevelGTIN GTINQualifier="UP">11234567890123</ItemLevelGTIN>
            <PartNumber>VC21499</PartNumber>
            <BrandAAIAID>DKGX</BrandAAIAID>
            <BrandLabel>Wako</BrandLabel>
            <SubBrandAAIAID>DMST</SubBrandAAIAID>
            <SubBrandLabel>SubBrand Label</SubBrandLabel>
            <ACESApplications>Y</ACESApplications>
            <ItemQuantitySize UOM="EA">1</ItemQuantitySize>
            <ContainerType>BO</ContainerType>
            <QuantityPerApplication Qualifier="VAR" UOM="EA">1</QuantityPerApplication>
            <ItemEffectiveDate>2010-08-13</ItemEffectiveDate>
            <AvailableDate>2010-08-13</AvailableDate>
            <MinimumOrderQuantity UOM="EA">123</MinimumOrderQuantity>
            <ManufacturerProductCodes>
                <Group>02347</Group>
                <SubGroup>A</SubGroup>
            </ManufacturerProductCodes>
            <AAIAProductCategoryCode>199456</AAIAProductCategoryCode>
            <UNSPSC>11223348</UNSPSC>
            <PartTerminologyID>5696</PartTerminologyID>
            <VMRSCode>123000789</VMRSCode>

            <Descriptions> … </Descriptions>
            <Prices>   …   </Prices>
            <ExtendedInformation> … </ExtendedInformation>
            <Packages> … </Packages>
            <PartInterchangeInfo> … </PartInterchangeInfo>
            <DigitalAssets> … </DigitalAssets>
            <Kits> … </Kits>
        </Item>
    </Items>
```

![](../../../../Resources/Images/Importers/Standard_AC/32.png)

#### PIES Description Segment

The Description segment allows you to send zero or as many descriptions
of an Item record part number (PIES Item). The flexibility to send
multiple descriptions on a single PIES Item is possible because of the
capabilities inherent in XML\'s looping structure. The Description
segment (\<Descriptions\>...\</Descriptions\>) is an element group
available within the \<Item\> tag. To sendmultiple descriptions about an
individual Item part number (PIES Item), a user can loop (repeat) the
\<Description\> element, changing the \'DescriptionCode\' attribute as
well as the string value for the Description.

A sample PIES Description Segment and a screenshot that shows how it is
populated in STEP is displayed below.

``` {space="preserve"}
<Descriptions>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="MKT">MKT</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="EXT">EXT</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="INV">INV</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="SHO">CKENGSENS</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="ABR">ABR</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="KEY">Sensor Engine Check</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="ASC">ASC</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="DEF">DEF</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="SHP">SHP</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="DES">Check Engine Light Sensor</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="LAB">LAB</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="ASM">ASM</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="VMR">VMR</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="UNS">UNS</Description>
```

``` {space="preserve"}
<Description MaintenanceType="A" DescriptionCode="SLA">SLA</Description>
```

``` {space="preserve"}
</Descriptions>
```

![](../../../../Resources/Images/Importers/Standard_AC/33.png)

![](../../../../Resources/Images/Importers/Standard_AC/21.png)

#### PIES Price Segment PRCE

The Pricing Segment is defined by the PIES XML parent element
\<Prices\>. Within this element group, there may be multiple instances
of \<Pricing\> that define a single pricing instance. This element takes
a \'Price Type\' as an attribute indicating which type of price the
following child elements needs to be defined in.

To supply multiple prices (price types) for an Item Part Number (PIES
Item), the user needs to repeat the \<Pricing\> XML structure and
redefine the new loop with the \'Price Type\' attribute.

A sample PIES Price Segment and a screenshot of how it is populated in
the STEP system is displayed below.

``` {space="preserve"}
<Prices>
                <Pricing MaintenanceType="A" PriceType="WD1">
                    <PriceSheetNumber>2017WD</PriceSheetNumber>
                    <CurrencyCode>USD</CurrencyCode>
                    <EffectiveDate>2008-10-22</EffectiveDate>
                    <ExpirationDate>2012-10-22</ExpirationDate>
                    <Price UOM="PE">10</Price>
                </Pricing>
            </Prices>
```

![](../../../../Resources/Images/Importers/Standard_AC/34.png){.Inch6}

![](../../../../Resources/Images/Importers/Standard_AC/22.png)

#### PIES Extended Product Info Segment (EXPI)

The Extended Product Information (EXPI) Segment is designed to relay
information about an Item Part (PIES Item). The PIES Extended Product
Info Segment contains information ranging from \'Country of Origin\' to
\'Warranty Terms\'.

The format of the data expressed in the \'EXPI Data\' field
(\<ExtendedProductInformation\>) is dependent on the \'EXPI Code\'
selected.

To express information covering multiple (or one) \'EXPI Codes\', the
\<ExtendedProductInformation\> element is looped once for each code. Any
and all instances of \<ExtendedProductInformation\> are grouped under
the \<ExtendedInformation\> element.

A sample PIES Extended Product Info Segment and a screenshot of showing
how it is populated in STEP is displayed below.

``` {space="preserve"}
<ExtendedInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="HSB">01</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="HAC">HAC</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="CTS">FR</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="LIF">0</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="NAF">1</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="HTS">02</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="HZ1">12</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="TAX">Y</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="LIS">Proposed</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="TMC">AB</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="NPD">Top 60%</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="NPC">A</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="WS2">LF</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="WS1">SR</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="WD2">MI</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="CXP">12</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="RST">GA</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="CPN">CPN</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="WT2">MO</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="CGR">CGR</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="WT1">36</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="CCL">CCL</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="MSR">Y</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="RCT">Marietta, GA</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="MSD">MSDS26426</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="RCS">Cobb, GA</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="EMS">1</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="RPC">30060</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="CTR">GB</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="CTQ">DE</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="CTP">DK</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="CTO">US</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="OSN">OSN</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="OEP">OEP</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="OEM">OEM</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="REF">Y</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="PTS">PTS</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="PTN">PTN</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="OSP">OSP</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="WD1">500</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="RET">RET</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="REM">N</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="STA">S</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="PLM">20</ExtendedProductInformation>
                <ExtendedProductInformation MaintenanceType="A" EXPICode="PLC">100</ExtendedProductInformation>
            </ExtendedInformation>
```

![](../../../../Resources/Images/Importers/Standard_AC/36.png)

![](../../../../Resources/Images/Importers/Standard_AC/23.png)

### Packaging Segment (PACK)

The Packaging Segment is used to express various volumetric details for
different packaging levels of PIES Items. Package information is grouped
within the \<Packages\> child element of \<Item\>. Each instance of the
\<Package\> element (looped beneath \<Packages\>) and its child elements
corresponds to a distinct \'Package UOM\'. This UOM, or Unit of Measure,
identifies the type of packaging the data element contains.

The consumer-level package (UOM type "PK") should always be defined if
possible. The consumer-level pack can be defined, for example, as the
Item Part in the packaging used for in-store display and stocking. This
is the package level that an individual consumer may purchase.

The sample XML code below shows the Packaging Segment in relation to the
other segments defined to this point, and the screenshot below shows the
way it is populated in the system.

    <Packages>
                    <Package MaintenanceType="A">
                        <PackageLevelGTIN>12345000451747</PackageLevelGTIN>
                        <ElectronicProductCode>4A.356E414.B351C7.AD331A465</ElectronicProductCode>
                        <PackageBarCodeCharacters>005555010</PackageBarCodeCharacters>
                        <PackageUOM>PK</PackageUOM>
                        <QuantityofEaches>1</QuantityofEaches>
                        <Dimensions UOM="CM">
                            <Height>10.2</Height>
                            <Width>3.6</Width>
                            <Length>2.0</Length>
                        </Dimensions>
                        <Weights UOM="PG">
                            <Weight>12.5</Weight>
                            <DimensionalWeight>45</DimensionalWeight>
                        </Weights>
                        <WeightVariance>90</WeightVariance>
                        <HazardousMaterial> … </HazardousMaterial>
                    </Package>
                </Packages>

![](../../../../Resources/Images/Importers/Standard_AC/24.png)

### Hazardous Material Package Segment (HAZM)

Hazmat information is relayed due to different Hazmat rules and
regulations, each of which may depend on the type of package a product
is using. For instance, a product may have one set of regulations (or
none) at the Consumer Pack level, but a completely different set of
government regulations may apply if the package is a Case or Pallet of
product. Regulations may change as well depending on the transportation
method used when shipping a product.

The Hazardous Material Package Segment does not repeat as a loop of
\<Item\>. Rather, this segment is a looping structure within the
\<Packaging\> segment.

The sample XML code below shows how a single instance of the Hazardous
Material Package Segment, defined by the \<HazardousMaterial\> parent
element, falls within the Packaging Segment (\<Package\>), and the
screenshot below shows how it is populated in the system.

``` {space="preserve"}
<HazardousMaterial MaintenanceType="A" LanguageCode="EN">
                        <ShippingScope>INT</ShippingScope>
                        <Bulk>N</Bulk>
                        <RegulatingCountry>US</RegulatingCountry>
                        <TransportMethod>R</TransportMethod>
                        <Regulated>Y</Regulated>
                        <Description>Hazmat Description</Description>
                        <HazardousClass>2.2</HazardousClass>
                        <HazardousMaterialCodeQualifier>D</HazardousMaterialCodeQualifier>
                        <HazardousMaterialClassCode>1.4</HazardousMaterialClassCode>
                        <HazardousMaterialDescription>Hazardous</HazardousMaterialDescription>
                        <ShippingName>Great Lakes Shipping</ShippingName>
                        <UNNAIDCode>027455</UNNAIDCode>
                        <HazardousPlacardNotation>Caution</HazardousPlacardNotation>
                        <WHMISCode>B.4</WHMISCode>
                        <WHMISFreeText>Caution</WHMISFreeText>
                        <PackingGroupCode>III</PackingGroupCode>
                        <RegulationsExemptionCode>4</RegulationsExemptionCode>
                        <TextMessage>Be careful</TextMessage>
                        <OuterPackageLabel>ORM-AIR</OuterPackageLabel>
                    </HazardousMaterial>
```

![](../../../../Resources/Images/Importers/Standard_AC/25.png)

#### Kits Segment (KITS)

The Kits Segment is defined by the \<Kits\> parent element which
contains the child element \<KitComponent\>. This element contains child
elements that define the component parts and supporting data.

If the item is a kit or set, the Kit Segment of PIES conveys the part
numbers contained in a kit or set Bill of Materials (BOM).

Kits are defined as an assemblage of parts or equipment that serve the
specific purpose of performing a full maintenance procedure or function.
An assembly of parts needed to repair a carburetor, or an assembly of
parts needed to rebuild an engine are examples of kits.

A Set is a group or collection of things that belong together, resemble
one another, or are usually found together. A range of tools (such as a
drill bit set, or a tool assortment), or a battery booster cable set are
examples of sets.

The Kits Segment allows the data sender to express what components are
in a particular kit. To express multiple components within a Kit, the
elements within the Kit Segment repeat as many times as necessary to
identify all components.

A sample Kits Segment and a screenshot showing how it is populated on
STEP is displayed below.

``` {space="preserve"}
<Kits>
                <Kit MaintenanceType="A">
                    <ComponentPartNumber IDQualifier="VN">VC36004</ComponentPartNumber>
                    <ComponentBrand>DKGX</ComponentBrand>
                    <Description DescriptionCode="SHO" LanguageCode="EN">CKENGSENS</Description>
                    <QuantityInKit UOM="EA">2</QuantityInKit>
                    <SequenceCode>1</SequenceCode>
                </Kit>
                <Kit MaintenanceType="A">
                    <ComponentPartNumber IDQualifier="VP">VC36009</ComponentPartNumber>
                    <ComponentBrand>DKGX</ComponentBrand>
                    <Description DescriptionCode="SHO" LanguageCode="EN">CKENGSENS</Description>
                    <QuantityInKit UOM="EA">1</QuantityInKit>
                    <SequenceCode>2</SequenceCode>
                </Kit>
            </Kits>
```

![](../../../../Resources/Images/Importers/Standard_AC/26.png)

### Interchange Segment (INTE)

The Interchange Segment in PIES is used to relay interchange data for
the Item Part Number (PIES Item) in relation to alternative Brand Owner
Part Numbers. The Interchange part number is also known as Competitor /
OE Number in STEP system. The segment is defined by the
\<PartInterchangeInfo\> grouping element. Within \<PartInterchangeInfo\>
is the \<PartInterchange\> element which contains the child elements
that define an interchange. \<PartNumber\> element instance is repeated
as many times as necessary to identify all components.

All interchange part numbers are defined by both the interchange part
number and a \'Brand AAIAID\'. The \'Brand AAIAID\' value for the
interchange supplier can be found in the industry supported Brand table.
If a brand code value is not present in the Industry Brand Code table,
the use of \'ZZZN\' is permitted until such time as a \'Brand AAIAID\'
is created for the Brand in question. In such an instance, the \'Brand
Label\' value should be populated for clarity. Using \'ZZZN\' and a
\'Brand label\' should be used as a last resort not as standard practice
as the Brand table is updated frequently.

As with some of the other segments described above, to express multiple
interchanges for an Item Part Number, the \<PartInterchange\> element is
repeated as many times as necessary to identify all interchanges.

A sample Interchange Segment and a screenshot showing how it is
populated in STEP is displayed below.

``` {space="preserve"}
<PartInterchangeInfo>
                <PartInterchange MaintenanceType="A" LanguageCode="EN">
                    <TypeCode>O</TypeCode>
                    <BrandAAIAID>BBTB</BrandAAIAID>
                    <BrandLabel>Great Lakes</BrandLabel>
                    <PartNumber>GL26409</PartNumber>
                    <QualityGradeLevel>P</QualityGradeLevel>
                    <InterchangeNotes>Yellow indicator light</InterchangeNotes>
                    <InternalNotes>May be difficult to remove</InternalNotes>
                </PartInterchange>
            </PartInterchangeInfo>
```

![](../../../../Resources/Images/Importers/Standard_AC/27.png)

### Digital Asset File Information Segment (ASST)

The Digital Asset File Information Segment is used to relay information
about many different media types which support the PIES Item. The
\'Asset Type\' field is used to identify what type of digital asset is
being defined.

This segment is defined by the \<DigitalAssets\> grouping element. Below
this element is the \<DigitalFileInformation\> element which contains
corresponding child elements (fields) used to express the defined values
for a digital asset. As with other segments, to supply information for
multiple digital assets for a PIESItem, the \<DigitalFileInformation\>
element and its child elements are repeated for each digital asset.

A sample Digital Asset File Information Segment and a screenshot showing
how it is populated in STEP is displayed below.

``` {space="preserve"}
<DigitalAssets>
                <DigitalFileInformation MaintenanceType="A" AssetID="Asset456" LanguageCode="EN">
                    <FileName>VC21499_P04</FileName>
                    <AssetType>P04</AssetType>
                    <Representation>R</Representation>
                    <Resolution>96</Resolution>
                    <Background>CLI</Background>
                    <OrientationView>BAC</OrientationView>
                    <Details>Details/Description</Details>
                    <FilePath>images\SVlight.tif</FilePath>
                    <URI>www.stibo.com</URI>
                    <FileDateModified>2008-04-11</FileDateModified>
                    <EffectiveDate>2008-04-11</EffectiveDate>
                    <ExpirationDate>2012-04-11</ExpirationDate>
                    <Country>US</Country>
                </DigitalFileInformation>
                
            </DigitalAssets>
```

In the screenshot below, the Asset ID 'VC21499\_P04' is linked to the
PIES Item 'VC21499' via the reference type 'PIES Item To Product Image.'

![](../../../../Resources/Images/Importers/Standard_AC/28.png)

Asset details are listed under the PIES Assets folder based on the input
data in the PIES file as shown in the screenshot below.

![](../../../../Resources/Images/Importers/Standard_AC/29.png)

### Output

Upon successful import, based on the value within the
\<PartTerminologyID\> tags in input files, a PIES Item will be created /
modified. An example of PIES Item 'VC21499' (ID:
AC\_PIESItem\_DKGX\_VC21499) created under Object \'Check Engine Light
Sensor\' (ID: AC\_PIESPCdbPartTerminology\_5696\_DKGX) with its various
attribute values and reference type (as explained above) is shown below.

![](../../../../Resources/Images/Importers/Standard_AC/30.png)

The automotive importers do not delete any objects. They mark objects as
new, delete, or change through change flags.
