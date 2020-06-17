---
description: 'Automotive Solution: Describes the Move ACES Applications
  for PIES Part Business Action.'
title: '\[%=Heading.AnyLevel%\]'
---

Business Action: Move ACES Applications for PIES Part
=====================================================

This rule is a business action found under the Automotive menu that will
move all ACES applications from one PIES Item to another by following a
reference between the parts. The rule has a single parameter (Reference
Type), which requires selection of a reference. For the rule to function
properly, the selected reference must be a product reference with the
PIES Item object type (ID=AC\_PIESItem) as both the source and the
target, and the rule must be set with the PIES Item as the valid object
type.

The action evaluates all ACES applications that are child to the
selected part on which the rule is being executed and moves the child
applications from the current object to the target(s) of the reference
identified in the rule. If the PIES Item has no reference of this type,
no action is taken and the existing applications will remain in place.
If the PIES Item has one or multiple targets of the reference, the
applications will be duplicated to all targets and removed from the
source object.

When a move occurs, the application is moved with all data on the
original record retained, except the part number. The part that the
application is being moved to is applied as the part number in both the
application name and the hash function of the application ID, as well as
within the ACES Replacement Context metadata value. The brand element of
the replacement context is also updated if the part that the application
is being moved to is from another brand (indicated by the value of the
attribute with ID=AC\_PIES\_ITEMBrandAAIAID on the PIES Item).

ACES supports only a single asset being linked to any application. If
multiple assets are present on an application, all will be linked to the
moved record, but only one will be accounted for in the application ID.
This could lead to duplicate applications in the system so it is
important to ensure that the standard is adhered to and only one asset
is present for any application.

Note that this rule cannot be used to move applications outside of the
AutoCare model (using PIES Item and ACES Application object types) as
the functionality for construction of the application ID and other
related data relies on the standard model.
