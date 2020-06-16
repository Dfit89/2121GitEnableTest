---
description: 'PLM Solution: The following business rules are necessary
  for the Supplier Records data model.'
title: '\[%=Heading.Level1%\]'
---

Business Rules for Supplier Records
===================================

The following business rules are necessary for the Supplier Records data
model.

Business Library for Creating HTML Document
-------------------------------------------

The business library PLM Food Supplier Record Library constructs an HTML
document and returns it as String.

The main flow of the business library is to call the function
getSupplierResponseRecord() which takes threearguments:

**Argument 1**: Node - the object the HTML document will be created for.
The function expects the object to be one of the following object types,
otherwise an empty HTML document is returned.

-   PLM Sample
-   PLM Packaging Variant Sample
-   PLM Label Variant Sample

**Argument 2**: Indicates if the generated HTML is to be emailed or not.
If the HTML is to be emailed (true) then the print link is not included.
If the HTML is not emailed (false) then the print link is included in
the generated HTML.

**Argument 3**: STEP Manager

Business Rule for Sending Email
-------------------------------

The business action \'PLM Food Email Supplier Record\' creates a
supplier bid record for the current object and sends an email to the
supplier.

It is valid for Sample, Packaging Variant Sample, and Label Variant
Sample object types, and it has three binds:

-   Node for the current object
-   Mailer for the mailer home object
-   Manager for the STEP manager

The business action has a dependency to \'PLM Food Supplier Record
Library\' with the alias PLMFoodSupplierRecordLibrary.

The main flow of the business action is:

-   Get the email address from the attribute PLM Supplier Notification
    Email.
-   Generate a supplier bid response HTML using the
    PLMFoodSupplierRecordLibrary library.
-   Use the mailer home to send the email where the body of the email is
    the HTML document.

Business Rule for Creating Supplier Record Asset
------------------------------------------------

\'PLM Food Create Supplier Record\' business action creates an asset for
the supplier bid record and links it to the Supplier Response (Recipe
Response, Label Response, or Packaging Response).

It is valid for the Sample, Packaging Variant Sample, and Label Variant
Sample object types, and it has two binds:

-   Node for the current object
-   Manager for the STEP manager

The business action has a dependency to \'PLM Food Supplier Record
Library\' with the alias PLMFoodSupplierRecordLibrary.

The main flow of the business action is:

-   Get the suppliers asset folder, object ID (SuppliersAssets).
-   Create an asset in the supplier asset folder with the object type
    Supplier Response Record.
-   Create a reference from the current object to the asset with the
    reference type Supplier Response Record.
-   Generate a supplier bid response HTML using the PLM Food Supplier
    Record Library.
-   Upload the HTML document to the created asset.
