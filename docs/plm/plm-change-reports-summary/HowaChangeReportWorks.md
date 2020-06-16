---
description: 'PLM Solution: Private label food out of the box
  configuration includes a set of example configurations for capturing
  data changes in the Supplier Responses phase and Evaluation of the
  Supplier Responses. '
title: '\[%=Heading.Level1%\]'
---

How a Change Report Works
=========================

Private label food out-of-the-box configuration includes a set of
example configurations for capturing data changes in the Supplier
Responses phase and Evaluation of the Supplier Responses.

Change Reports detect any changes that have been made during
user-defined events only if the change has been defined in the recorder.

PRODOC note: Jan Sorensen says that the following sentence is correct
when it says \'supplier response is sent to a supplier\...\'

When a Supplier Response (Recipe Response, Label Response or Packaging
Response) is sent to a Supplier to request his / her responses for
Ingredients, Parameters, Requirements, and Nutrition Information, the
Supplier Responses are initiated in the Private Label Food Supplier
Response workflow.

On entry to the Initiate state of the Private Label Food Supplier
Response workflow, the PLM Food Supplier Snapshot business rule is
executed, and the following actions will take place:

1.  A Snapshot will be created. e.g., SAM183267-Supplier
    Response-12-07-19 13:51:49.
2.  The supplier will then start working on supplier responses and
    respond with any required information. When finished, they select
    \'Send Response\' and send it back to the customer (Buyer).
3.  Once all Supplier Responses are received, all product specifications
    will be moved to the Evaluate Supplier Responses state of the
    Private Label Food Product Specification.
4.  If the supplier completed all required information, it represents
    data changes so a new snapshot will be taken.
5.  When a customer (buyer) starts reviewing the Supplier Responses,
    changes between the snapshot and the current data are detected, and
    the Change Report notification will be visible and active.
