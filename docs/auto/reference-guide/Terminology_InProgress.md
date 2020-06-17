---
description: 'Automotive Solution: Describes terminology specific to the
  automotive solution'
title: '\[%=Heading.AnyLevel%\]'
---

PMDM for Automotive Terminology
===============================

PRODOC note: MEDU PRODOC- 1296 Assigned to SIMO with notes about data
model inconsistancies and suggestions for improvement.

PRODOC note: MEDU per KRMA - Add a terminology table to align across the
standards. The core solution uses the word \'Assembly\' a lot (e.g., in
component models, Web UI designer, etc). But this is a TecDoc term.
Those using the solution for AutoCare, NAPA, or their own model won\'t
necessarily know what this means. So we need some type of definitions on
all of this just so people know what is being referenced in the UIs and
which terms are equivalent across the models. e.g., Vehicle = Assembly =
Make Model Year. Part = Article = PIES Part. Application = Linkage =
ACES application = Parts Pro. Part Terminology = Part Type = MPCC.
Conditions = Options = Criteria. (Plus a definition of the concept that
each set of related words is about).

PRODOC note: MEDU Much of the TecDoc Term column was gleaned from the
TecDoc Terminology PDF

The table below can be used to align terminology used across the
standards.

+----------+----------+----------+----------+----------+----------+
| STEP     | General  | AutoCare | NAPA     | [TecDoc  | Model    |
| Term     | Des      | Term     | Term     | Term]{s  | Term     |
|          | cription |          |          | tyle="fo |          |
|          |          |          |          | nt-size: |          |
|          |          |          |          |  10pt;"} |          |
+==========+==========+==========+==========+==========+==========+
| Vehicle  | What an  | Base     | NAPA     | Linking  |          |
|          | app      | Vehicle  | Year     | Target   |          |
|          | lication |          |          |          |          |
|          | points   |          |          |          |          |
|          | to.      |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| Part     | [An      | PIES     | NAPA     | Article  |          |
|          | artifact | Item     |  Product |          |          |
|          | that is  |          |          |          |          |
|          | one of   |          |          |          |          |
|          | the      |          |          |          |          |
|          | in       |          |          |          |          |
|          | dividual |          |          |          |          |
|          | parts of |          |          |          |          |
|          | which a  |          |          |          |          |
|          | c        |          |          |          |          |
|          | omposite |          |          |          |          |
|          | entity   |          |          |          |          |
|          | (        |          |          |          |          |
|          | vehicle) |          |          |          |          |
|          | is made  |          |          |          |          |
|          | up;      |          |          |          |          |
|          | es       |          |          |          |          |
|          | pecially |          |          |          |          |
|          | a part   |          |          |          |          |
|          | that can |          |          |          |          |
|          | be       |          |          |          |          |
|          | s        |          |          |          |          |
|          | eparated |          |          |          |          |
|          | from or  |          |          |          |          |
|          | attached |          |          |          |          |
|          | to a     |          |          |          |          |
|          | s        |          |          |          |          |
|          | ystem.]{ |          |          |          |          |
|          | style="f |          |          |          |          |
|          | ont-size |          |          |          |          |
|          | : 9pt;"} |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| Part     | The most | Part     | NAPA     | U        |          |
| Type     | granular | Ter      | MPCC     | niversal |          |
|          | product  | minology | d        | Generic  |          |
|          | classi   | d        | elivered | Article  |          |
|          | fication | elivered | via the  | /        |          |
|          | of a     | via the  | Tra      | Standard |          |
|          | part     | PCdb     | nslation | Generic  |          |
|          | and/or   |          | file.    | Article  |          |
|          | co       |          |          |          |          |
|          | mponents |          |          |          |          |
|          | that are |          |          |          |          |
|          | not      |          |          |          |          |
|          | appli    |          |          |          |          |
|          | cations. |          |          |          |          |
|          | For      |          |          |          |          |
|          | example, |          |          |          |          |
|          | Water    |          |          |          |          |
|          | Pump     |          |          |          |          |
|          | Pulley   |          |          |          |          |
|          | or Tire  |          |          |          |          |
|          | Valve    |          |          |          |          |
|          | Stem     |          |          |          |          |
|          | Rep      |          |          |          |          |
|          | lacement |          |          |          |          |
|          | Tool.    |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| App      | [Defines | ACES     | NAPA     | Linkage  |          |
| lication | part to  | App      | App      |          |          |
|          | vehicle  | lication | lication |          |          |
|          | fitment  |          |          |          |          |
|          | based on |          |          |          |          |
|          | vehicle, |          |          |          |          |
|          | part     |          |          |          |          |
|          | type,    |          |          |          |          |
|          | part     |          |          |          |          |
|          | number,  |          |          |          |          |
|          | and      |          |          |          |          |
|          | ad       |          |          |          |          |
|          | ditional |          |          |          |          |
|          | options  |          |          |          |          |
|          | (e.g.,   |          |          |          |          |
|          | P        |          |          |          |          |
|          | osition, |          |          |          |          |
|          | Q        |          |          |          |          |
|          | uantity, |          |          |          |          |
|          | Number   |          |          |          |          |
|          | of       |          |          |          |          |
|          | d        |          |          |          |          |
|          | oors).]{ |          |          |          |          |
|          | style="f |          |          |          |          |
|          | ont-size |          |          |          |          |
|          | : 9pt;"} |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
|          |          |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| Part     | For      | PCdb     |          |          |          |
| Type     | example, | Ca       |          |          |          |
| Ca       | Water    | tegories |          |          |          |
| tegories | Pump and | and      |          |          |          |
| (        | related  | Subca    |          |          |          |
| Classifi | co       | tegories |          |          |          |
| cations) | mponents |          |          |          |          |
|          | or Tire  |          |          |          |          |
|          | Service  |          |          |          |          |
|          | Tools.   |          |          |          |          |
|          | Logical  |          |          |          |          |
|          | co       |          |          |          |          |
|          | llection |          |          |          |          |
|          | of       |          |          |          |          |
|          | related  |          |          |          |          |
|          | part     |          |          |          |          |
|          | types    |          |          |          |          |
|          | that     |          |          |          |          |
|          | perform  |          |          |          |          |
|          | together |          |          |          |          |
|          | as a     |          |          |          |          |
|          | system.  |          |          |          |          |
|          | For      |          |          |          |          |
|          | example, |          |          |          |          |
|          | Cooling  |          |          |          |          |
|          | System   |          |          |          |          |
|          | or Tools |          |          |          |          |
|          | and      |          |          |          |          |
|          | Eq       |          |          |          |          |
|          | uipment. |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| Part     | Physical | PIES     | \*look   | Article  |          |
| A        | charact  | A        | for      | A        |          |
| ttribute | eristics | ttribute | export   | ttribute |          |
|          | of a     | & PAdb   | plugin   |          |          |
|          | specific | At       | napa     |          |          |
|          | part     | tributes | a        |          |          |
|          | that     |          | ttribute |          |          |
|          | will not |          | export   |          |          |
|          | change,  |          |          |          |          |
|          | re       |          |          |          |          |
|          | gardless |          |          |          |          |
|          | of which |          |          |          |          |
|          | vehicle  |          |          |          |          |
|          | the part |          |          |          |          |
|          | is       |          |          |          |          |
|          | fitted   |          |          |          |          |
|          | to.      |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| Options  | Vehicle  | Defined  | Defined  | Defined  |          |
|          | specif   | within   | within   | within   |          |
|          | ications | VCdb     | Valid    | R        |          |
|          | that can |          | Vehicle  | eference |          |
|          | describe |          | Table    | Data     |          |
|          | details  |          |          |          |          |
|          | or       |          |          |          |          |
|          | va       |          |          |          |          |
|          | riations |          |          |          |          |
|          | of a     |          |          |          |          |
|          | vehicle. |          |          |          |          |
|          | For      |          |          |          |          |
|          | example  |          |          |          |          |
|          | Sub      |          |          |          |          |
|          | Model,   |          |          |          |          |
|          | Engines, |          |          |          |          |
|          | Drive    |          |          |          |          |
|          | types    |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| Co       | Co       | ACES Co  | NAPA     | Linkage  |          |
| nditions | nditions | nditions | Co       | Criteria |          |
|          | are      |          | nditions |          |          |
|          | rest     |          |          |          |          |
|          | rictions |          |          |          |          |
|          | on an    |          |          |          |          |
|          | app      |          |          |          |          |
|          | lication |          |          |          |          |
|          | as to    |          |          |          |          |
|          | when and |          |          |          |          |
|          | how the  |          |          |          |          |
|          | part can |          |          |          |          |
|          | fit the  |          |          |          |          |
|          | vehicle. |          |          |          |          |
|          | Co       |          |          |          |          |
|          | nditions |          |          |          |          |
|          | can      |          |          |          |          |
|          | refer to |          |          |          |          |
|          | the      |          |          |          |          |
|          | vehicles |          |          |          |          |
|          | options. |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| Comments | Used to  | ACES     | NAPA     | Text     |          |
|          | describe | App      | Comment  | Block    |          |
|          | co       | lication |          |          |          |
|          | nditions | Note     |          |          |          |
|          | for      |          |          |          |          |
|          | appl     |          |          |          |          |
|          | ications |          |          |          |          |
|          | that do  |          |          |          |          |
|          | not fit  |          |          |          |          |
|          | pr       |          |          |          |          |
|          | edefined |          |          |          |          |
|          | att      |          |          |          |          |
|          | ributes. |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| Make     | Brand    | Make     | Make     | Manu     |          |
|          | name     |          |          | facturer |          |
|          | under    |          |          | / Brand  |          |
|          | which    |          |          |          |          |
|          | vehicles |          |          |          |          |
|          | are      |          |          |          |          |
|          | sold.    |          |          |          |          |
|          | For      |          |          |          |          |
|          | example, |          |          |          |          |
|          | Acura,   |          |          |          |          |
|          | BMW, and |          |          |          |          |
|          | Honda.   |          |          |          |          |
+----------+----------+----------+----------+----------+----------+
| Model    |          | Model    | Model    | Model    |          |
|          |          |          |          | Series   |          |
+----------+----------+----------+----------+----------+----------+
| PRODOC   | Parts    | Part     | N        |          |          |
| note:    | Lists    | Ter      | APA Part |          |          |
| MEDU Per | are made | minology | Ter      |          |          |
| SIMO     | up of    | List     | minology |          |          |
| Feature  | various  |          | List     |          |          |
| in old   | parts    |          |          |          |          |
| App      | that     |          |          |          |          |
| lication | form an  |          |          |          |          |
| Editor   | integral |          |          |          |          |
| that was | part of  |          |          |          |          |
| not      | the main |          |          |          |          |
| brought  | part.    |          |          |          |          |
| into AM  | Parts    |          |          |          |          |
| This is  | lists    |          |          |          |          |
| in the   | are      |          |          |          |          |
| c        | fixed. A |          |          |          |          |
| omponent | parts    |          |          |          |          |
| model    | list is  |          |          |          |          |
| today.   | always   |          |          |          |          |
|          | in a 1-1 |          |          |          |          |
| Part     | relation |          |          |          |          |
| type     | with the |          |          |          |          |
| list     | main     |          |          |          |          |
|          | part.    |          |          |          |          |
|          | That     |          |          |          |          |
|          | means    |          |          |          |          |
|          | that the |          |          |          |          |
|          | main     |          |          |          |          |
|          | part     |          |          |          |          |
|          | will     |          |          |          |          |
|          | always   |          |          |          |          |
|          | contain  |          |          |          |          |
|          | the same |          |          |          |          |
|          | fixed    |          |          |          |          |
|          | number   |          |          |          |          |
|          | of parts |          |          |          |          |
|          | list     |          |          |          |          |
|          | items.   |          |          |          |          |
+----------+----------+----------+----------+----------+----------+

There are three automotive standards:

PRODOC note: MEDU I think these need to go on the standards intro page..
if there is one\...

-   **AutoCare:** Standardization of part and fitment data pertaining to
    North America. This standard is managed by the AutoCare Association.
    More information about this standard can be found at
    [www.autocare.org](http://www.autocare.org/).
-   **NAPA:** Standardization of part and fitment data pertaining to
    North America. This standard is managed by the Genuine Parts
    Company.
-   **TecDoc:** Standardization of part and fitment data pertaining to
    Europe. This standard is managed by TecAlliance. More information
    about this standard can be found at
    [www.tecalliance.net](https://www.tecalliance.net/).
-   [ACES]{.bold} - Aftermarket Catalog Exchange Standard
-   [Hard Parts]{.bold} - Parts required for your vehicle to operate
    properly (i.e., Spark Plugs, alternators, ball joints, control arms,
    batteries)
-   [Interchanges]{.bold} - Identify application equivalent part from
    competing suppliers
-   [Mapper]{.bold} - process of converting your own data to ACES, NAPA
    Parts Pro, PIES, or some other format, so that it can be easily
    translated by your trading partners
-   [PIES]{.bold} - Product Information Exchange Standard
-   [TecDoc]{.bold} - European Part and Vehicle Standards (owned by
    manufacturers)
