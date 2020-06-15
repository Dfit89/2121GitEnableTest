---
description: 'PLM Solution: Each object in the Suppliers hierarchy is
  listed below, along with the purpose of the object type.'
title: '\[%=Heading.Level1%\]'
---

Suppliers
=========

Each object in the Suppliers hierarchy is listed below, along with the
purpose of the object type.

PRODOC note: The following note is necessary according to Chris Talmant.

The following supplier configurations are necessary for the Private
Label Food demo to work properly. If the target system already has
suppliers configured with different IDs in the global system set up,
existing supplier set ups can be used; however, business rules used for
the demo should be modified for the alternate set up.

+----------------------+---------------------+----------------------+
| Object Type Name     | Object Type ID      | Purpose              |
+======================+=====================+======================+
| Suppliers Group Root | SupplierGroupRoot   | Root node of the     |
|                      |                     | hierarchy.           |
+----------------------+---------------------+----------------------+
| Suppliers Root       | SuppliersRoot       | The root node for    |
|                      |                     | each supplier; each  |
|                      |                     | supplier is assigned |
|                      |                     | one root. Privileges |
|                      |                     | for the associated   |
|                      |                     | supplier user group  |
|                      |                     | are tied to this     |
|                      |                     | node.                |
+----------------------+---------------------+----------------------+
| Suppliers Assets     | SuppliersAssets     | Organizational       |
|                      |                     | folder to hold all   |
|                      |                     | assets for the       |
|                      |                     | supplier; all assets |
|                      |                     | uploaded via the     |
|                      |                     | Supplier Web UI are  |
|                      |                     | linked using the     |
|                      |                     | SupplierAsset        |
|                      |                     | reference.           |
+----------------------+---------------------+----------------------+
| Suppliers Batches    | SuppliersBatches    | Organizational       |
|                      |                     | folder to hold all   |
|                      |                     | batches for the      |
|                      |                     | supplier; default    |
|                      |                     | object created with  |
|                      |                     | each new supplier,   |
|                      |                     | but not utilized for |
|                      |                     | the implementation.  |
+----------------------+---------------------+----------------------+
| Suppliers Products   | SuppliersProducts   | Organizational       |
|                      |                     | folder to hold all   |
|                      |                     | supplier items for   |
|                      |                     | the supplier; all    |
|                      |                     | supplier items       |
|                      |                     | uploaded via the     |
|                      |                     | Supplier Web UI are  |
|                      |                     | linked using the     |
|                      |                     | SupplierLink         |
|                      |                     | reference.           |
+----------------------+---------------------+----------------------+
| Suppliers Contacts   | PLMSupplierContacts | Use to collect       |
|                      |                     | supplier contact     |
|                      |                     | information.         |
|                      |                     |                      |
|                      |                     | Not used in PLM      |
|                      |                     | Private Label        |
|                      |                     | Solution.            |
+----------------------+---------------------+----------------------+
