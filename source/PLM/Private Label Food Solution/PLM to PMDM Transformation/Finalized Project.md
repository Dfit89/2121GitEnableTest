---
description: 'PLM Solution: A finalized project is where a supplier has
  been awarded, the project will be moved out of the design
  specification hierarchy of active projects, and any objects that are
  not part of the awarded recipe(s) will be deleted.'
title: '\[%=Heading.Level1%\]'
---

Finalized Project
=================

A finalized project is where a supplier has been awarded, the project
will be moved out of the design specification hierarchy of active
projects, and any objects that are not part of the awarded recipe(s)
will be deleted.

**Data Model**

The recipe library will be organized with the following Product object
hierarchy:

  ------------------------------------------------------------------
  Object Type ID             Object Type     Description
                             Name            
  -------------------------- --------------- -----------------------
  PLMFinalizedProjectRoot    Finalized       The root object type
                             Project Root    for the finalized
                                             projects

  PLMFinalizedProjectGroup   Finalized       A self-referenced
                             Project Group   object type to organize
                                             the finalized projects

  PLMDesignSpecification     Design          The PLM project
                             Specification   
  ------------------------------------------------------------------
