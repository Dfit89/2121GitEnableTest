Sample STEP Publisher Publication Setup
=======================================

This documentation section details a model setup for a STEP Publisher
publication that mounts products using data in two Contexts (English and
German), a table, pagination rules, running page headers, and asset
references.

This setup is used for a basic drag and drop publication.

Described in this topic are the underlying data model used, the
publication data model, the attributes and their inheritance, the tables
and their inheritance, pagination rules and their inheritance.

This is achieved through setups in InDesign on a publication and product
template, styles within the publication template (paragraph and rule
line), frame settings on the product template,

Running page headers use InDesign variables to pull the content onto the
page dynamically. Page variables are InDesign functionality, not STEP,
but they are useful when working alongside STEP attributes to pull
dynamic content onto the page using STEP Publisher functionality in
conjunction with dynamic features that are native to InDesign.

Pagination Rules
----------------

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/PaginationRulesAB.png)

The attribute Product Template is a description attribute valid on the
Print Product object, and is based on an LOV. The first rule is looking
for the attribute value of Template Type A, the second rule is looking
for the LOV value of Template Type B (20). Either are valid options, but
this is shown to illustrate two different options for pagination rules,
looking for an attribute value and looking for an LOV value. (What is
the difference again, really? Is this too confusing?)

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/PaginationRulesAtt.png)

Template Type A:

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/TempTypeA.png)

Temp Type B:

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/TempTypeB.png)

Sample Table Setup with Recommended Practices for Header Rows
-------------------------------------------------------------

PRODOC note \-- there\'s another topic about recommended practices for
table headers, I suggest that this go there instead

Running Headers for Publication Templates
-----------------------------------------

This avoids the issue of possibly having to use a separate product
template to mount at the top of the page just to pull in page titles
that corresponds with the \'level\' of products being mounted into a
particular publication section.

### Setup in STEP

For the \'Print Product\' object type, four title attributes are valid:
Title Level 1 (Print\_TitleLevel1), Title Level 2 (Print\_TitleLevel2),
Title Level 3 (Print\_TitleLevel3), and Title Level 4
(Print\_TitleLevel4). These are calculated attributes that pull the
values of the upper-level product categories, e.g., Level 1 =
Electronics, Level 2 = Audio Accessories, and so forth.

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/TitleLevelAtts.png)

The formula used for the Title Level 3 (Print\_TitleLevel3) is as
follows. It is designed to return the value of the attribute Display
Name (Print\_DisplayName) that exists on the Print Projects Level 3
object type under which the current product exists (i.e., of which it is
a child).

    {

``` {space="preserve"}
     L3:=filter(
```

``` {space="preserve"}
         path(),
```

``` {space="preserve"}
         'exact(stepobjecttype(), "Print Products Level 3")'
```

``` {space="preserve"}
     )
```

    }

    iterate(

``` {space="preserve"}
     L3,
```

``` {space="preserve"}
      "value('Print_DisplayName')"
```

``` {space="preserve"}
)
```

In this example, the value of Display Name (Print\_DisplayName) is
Headphones.

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/PrintDisplayName_English.png)

A Description attribute is used instead of the STEP Name because the
attribute is inheritable and translatable. The STEP Name may not always
be translated, and the STEP Name may be altered by users for various
reasons that make it unusable for a stable value to be pulled, e.g., to
sort products, users may add exclamation points to the beginning of the
product names to put them at the top of a hierarchy (e.g.,
!Electronics).

 

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/PrintDisplayName_German.png)

###  

### Product Template Setup

The tag for the running header is placed into a tiny, \'invisible\'
frame on the product template, which cannot be seen on the mounted page.
This frame is to hold the attribute value tag, which will be mounted
onto the publication template, but will also be invisible. (The frame
could also be hidden behind another frame, for example.) The text is
there, but it is white (color \'None\') so it cannot be seen.

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/RunningHeadProdTempFrame.png)

To see what the attribute is, the following screenshot is zoomed in at
1600% and the font changed to black to see that there are two attributes
in the frame, Print\_TitleLevel3 and Print\_TitleLevel4:

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/RunningHeadProdTempZOOM.png)

The paragraph styles used within this frame are

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/RunningHeadProdTempStyle1.png)

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/RunningHeadProdTempStyle2.png)

### Publication Template Setup

In the topmost corners of the master pages of the Publication template,
running headers are set up as InDesign variables.

![](../../../Resources/Images/Solution%20Enablement/PMDM/Print/RunningHeadPubTemp.png)

 

 

 
