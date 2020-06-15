---
description: 'PLM Solution: A library recipe is an object that is
  generated from the awarded supplier recipe and stored in a library so
  that users can view the recipe. '
title: '\[%=Heading.Level1%\]'
---

Recipe Library
==============

A library recipe is an object that is generated from the awarded
supplier recipe and stored in a library so that users can view the
recipe. The library recipe is also linked to the PMDM product in case
additional information about the recipe needs to be reviewed.

Data Model

The recipe library is organized with the following Product object
hierarchy:

+----------------------+----------------------+----------------------+
| Object Type ID       | Object Type Name     | Description          |
+======================+======================+======================+
| PLMRecipeLibraryRoot | Recipe Library Root  | The root object type |
|                      |                      | for the recipe       |
|                      |                      | library              |
+----------------------+----------------------+----------------------+
| P                    | Recipe Library Group | A self-referenced    |
| LMRecipeLibraryGroup |                      | object type to       |
|                      |                      | organize the library |
|                      |                      | recipes              |
+----------------------+----------------------+----------------------+
| PLMLibraryRecipe     | Library Recipe       | The library recipe   |
+----------------------+----------------------+----------------------+

A library recipe has three data containers for storing nutrition values,
nutrition daily values, and all other information from the supplier
recipe.

+---+---+----------------------+
| D | D | Description          |
| a | a |                      |
| t | t |                      |
| a | a |                      |
| C | C |                      |
| o | o |                      |
| n | n |                      |
| t | t |                      |
| a | a |                      |
| i | i |                      |
| n | n |                      |
| e | e |                      |
| r | r |                      |
| I | N |                      |
| D | a |                      |
|   | m |                      |
|   | e |                      |
+===+===+======================+
| P | L | Data container for   |
| L | i | storing attribute    |
| M | b | values from the      |
| L | r | supplier recipe      |
| i | a |                      |
| b | r |                      |
| r | y |                      |
| a | R |                      |
| r | e |                      |
| y | c |                      |
| R | i |                      |
| e | p |                      |
| c | e |                      |
| i | V |                      |
| p | a |                      |
| e | l |                      |
| V | u |                      |
| a | e |                      |
| l | s |                      |
| u |   |                      |
| e |   |                      |
| s |   |                      |
+---+---+----------------------+
| P | L | Data container for   |
| L | i | the recipe's         |
| M | b | nutritional values   |
| L | r |                      |
| i | a |                      |
| b | r |                      |
| r | y |                      |
| a | R |                      |
| r | e |                      |
| y | c |                      |
| R | i |                      |
| e | p |                      |
| c | e |                      |
| i | N |                      |
| p | u |                      |
| e | t |                      |
| N | r |                      |
| u | i |                      |
| t | t |                      |
| r | i |                      |
| i | o |                      |
| t | n |                      |
| i | V |                      |
| o | a |                      |
| n | l |                      |
| V | u |                      |
| a | e |                      |
| l | s |                      |
| u |   |                      |
| e |   |                      |
| s |   |                      |
+---+---+----------------------+
| P | L | Data container for   |
| L | i | the recipe           |
| M | b | nutritional daily    |
| L | r | values               |
| i | a |                      |
| b | r |                      |
| r | y |                      |
| a | R |                      |
| r | e |                      |
| y | c |                      |
| R | i |                      |
| e | p |                      |
| c | e |                      |
| i | N |                      |
| p | u |                      |
| e | t |                      |
| N | r |                      |
| u | i |                      |
| t | t |                      |
| r | i |                      |
| i | o |                      |
| t | n |                      |
| i | D |                      |
| o | V |                      |
| n | V |                      |
| D | a |                      |
| V | l |                      |
| V | u |                      |
| a | e |                      |
| l | s |                      |
| u |   |                      |
| e |   |                      |
| s |   |                      |
+---+---+----------------------+

All attributes for the library recipes are located in the attribute
group Library Recipe Values (PLMLibraryRecipeValues).

+----------------------+----------------------+----------------------+
| Attribute ID         | Attribute Name       | Description          |
+======================+======================+======================+
| PLMLibr              | Library Recipe       | Storing the STEP ID  |
| aryRecipeAttributeID | Attribute ID         | for the source       |
|                      |                      | attribute            |
+----------------------+----------------------+----------------------+
| PLMLibrar            | Library Recipe       | Storing the STEP     |
| yRecipeAttributeName | Attribute Name       | name for the source  |
|                      |                      | attribute            |
+----------------------+----------------------+----------------------+
| PLMLibrary           | Library Recipe       | Storing the value    |
| RecipeAttributeValue | Attribute Value      |                      |
+----------------------+----------------------+----------------------+
