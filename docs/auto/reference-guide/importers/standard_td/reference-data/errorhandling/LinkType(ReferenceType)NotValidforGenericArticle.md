---
description: 'Automotive Solution: Describes an error that can occur
  when importing a TecDoc Reference Data file by listing an overview of
  the error, error message template, error message example, where the
  error messages can be viewed, and how best to address the error.'
title: Link Type (Reference Type) Not Valid for Generic Article
---

Link Type (Reference Type) Not Valid for Generic Article
========================================================

PRODOC note: MEDU RDCUST- 3067 I have requested that this error be
handled with code. BEJA and NIFE identify this as a TD data error. I
have instructions in this ticket to document it for users to work
around. I need to do this to complete the topic.

Overview

Overview {#overview conditions="Primary.Web"}
--------

This type of error occurs when a Generic Article exists within the
Universal Assembly Group but the link type (Reference Type) in the
import file is supposed to be for a Standard Generic Article. Thus, the
Reference Type (Standard GA to Search Tree) is valid for a Standard
Generic Article instead of a Universal Generic Article.

Conversely, this error can occur when a Generic Article exists in the
Standard Assembly Group but the link type (Reference Type) in the import
file is supposed to be for a Universal Generic Article. Thus, the
Reference Type (Universal GA to Search Tree) is valid for a Universal
Generic Article instead of a Standard Generic Article.

When a user views the error message, this is apparent because the
message template states: The link type \<\'Reference ID\'\> is not valid
for \'classification \'TD\_GENART\_\<GenArtNr\>.''

When viewing the example error message below, it is clear that the
Reference Type that is not valid is the Reference ID
\'TD\_StandardGAToSearchTree(PC)' for the Universal Generic Article
\'classification \'TD\_GENART\_06911.\''

Error Message Template

Error Message Template {#error-message-template conditions="Primary.Web"}
----------------------

Error in this import 06\_Search\_Tree.xml setting completed with errors
- Error: The link type \<\'Reference ID\'\> is not valid for
\'classification \'TD\_GENART\_\<GenArtNr\>.\"

Error Message Example

Error Message Example {#error-message-example conditions="Primary.Web"}
---------------------

Error in this import \[import file name\] setting completed with errors
- Error: The link type \[Reference Type ID\] is not valid for
classification \[Classification ID\].'

Viewing the Error Message

Viewing the Error Message {#viewing-the-error-message conditions="Primary.Web"}
-------------------------

![](../../../../../Resources/Images/Importers/Errors/1.png)

Explanation

Explanation {#explanation conditions="Primary.Web"}
-----------

Because this error pertains to a Generic Article, and all Generic
Articles are listed within the TecDoc Reference Data file Data Table
320, it is important to understand data table 320.

For this explanation the following example data from Data Table 320 is
used. The Delta Keys that pertain to this error type are displayed with
red text.

![](../../../../../Resources/Images/Importers/Errors/4.png)

Understanding Data Table 320

The following important Delta Keys are within this table:

**GenArtNr:** Five digit number representing a Generic Article (GA)
number. Stored in STEP as a \'Universal Assembly GA\' Object Type using
the following prefix: \'TD\_GENART\_.\'

In the example below, GenArtNr 06911 is displayed in Workbench as the
\'Universal Assembly GA\' Object Type, Adjustment Tool Set, valve timing
(TD\_GENART\_06911).

![](../../../../../Resources/Images/Importers/Errors/5.png)

**BgNr:** Four digit number representing an Assembly Group where the
GenArtNr is stored.

In the example below, BgNr 0160 is displayed in Workbench as the
\'Universal Assembly Group\' Object Type, Special Tools, universal
(TD\_ASMGRP\_0160).

![](../../../../../Resources/Images/Importers/Errors/6.png)

**OK-Universal:** One digit number defining if the Reference Type should
be either Universal Assembly Group or Standard Universal Assembly Group.

-   A value of '1' defines the Reference Type as Universal GA to search
    tree.
-   A value of '0' defines the Reference Type as Standard GA to search
    tree.

In the example data from Data Table 320, the \'OK-Universal\' value is
\'1.\' Thus, it is expected that upon import of this data file the
GenArtNr 06911 will reference the BgNr 0160.

![](../../../../../Resources/Images/Importers/Errors/4.png)

This example data would result in:

-   Creating Generic Article Number \'06911\' in STEP as
    \'TD\_GENART\_06911\' beneath the Universal Assembly Group
    (TD\_ASMGRP\_0160). And the OK-Universal number '1' indicates that
    the link type / Reference Type is Standard GA to search tree. As the
    link type is not valid between the Generic Article (as this is under
    Universal assembly group and not the Standard assembly group) and
    the search tree, it displays an error.

If the appropriate values defining the Reference types are not present,
STEP may not accurately determine the classification reference between
the generic article and the search tree.

In this case, STEP will continue importing the process (Stops the
process if \'Continue on Error\' parameter is disabled on the Import
state) and report an error to the

Resolution

Resolution {#resolution conditions="Primary.Web"}
----------

To resolve this, manually edit the \'OK-Universal\' number in Data Table
320 to value \'0\' and import again. This will change the reference type
to \'Standard GA to Search Tree\'.

PRODOC note: BOND raised a query to SIMO. awaiting response\...
