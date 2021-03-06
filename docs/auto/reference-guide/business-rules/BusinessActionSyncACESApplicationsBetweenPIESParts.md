---
description: 'Automotive Solution: Describes the Sync ACES Applications
  Between PIES Parts Business Action.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Action: Sync ACES Applications Between PIES Parts
==========================================================

This rule is a business action found under the Automotive menu that will
synchronize all ACES applications between two PIES Items by following a
reference between the parts.

This rule cannot be used to move applications outside of the AutoCare
model (using PIES Item and ACES Application object types) as the
functionality for construction of the application ID and other related
data relies on the standard model.

The rule has a single parameter (Reference Type), which requires
selection of a reference. For the rule to function properly, the
selected reference must be a product reference with the PIES Item object
type (ID=AC\_PIESItem) as both the source and the target, and the rule
must be set with the PIES Item as the valid object type.

The action evaluates all ACES applications that are child to the
selected part on which the rule is being executed, and the applications
on the target(s) of the reference indicated in the business rule
configuration. The records are then synchronized between the parts,
excluding duplicates. For example, assume Part A has 3 records and Part
B has 2 records. One of the records on each part is a match to the
other, meaning that all data for the application is identical, except
the part number. Following the sync, both parts will have 4 records.

When a sync occurs, the applications are copied between the referenced
parts with all data on the original records retained, except the part
number. The part that the application is being applied to is written as
the part number in both the application name and the hash function of
the application ID, as well as within the ACES Replacement Context
metadata value. The brand element of the replacement context is also
updated if the part that the application is being moved to is from
another brand (indicated by the value of the attribute with
ID=AC\_PIES\_ITEMBrandAAIAID on the PIES Item).

ACES supports only a single asset being linked to any application. If
multiple assets are present on an application, all will be linked to the
record being created by the sync, but only one will be accounted for in
the application ID. This could lead to duplicate applications in the
system so it is important to ensure that the standard is adhered to and
only one asset is present for any application.
