---
description: 'Automotive Solution: Automotive Solution: PMDM for
  Automotive 10.0 - 7.0.28 Release Notes'
title: 'PMDM for Automotive 10.0 - 7.0.28 Release Notes'
---

PMDM for Automotive 10.0 - 7.0.28 Release Notes {#pmdm-for-automotive-10.0---7.0.28-release-notes .MPN}
===============================================

Release Date: May 22, 2019 {#release-date-may-22-2019 style="text-align: center;"}
--------------------------

 

There is no new functionality or bugfixes included with this release.
The 10.0 - 7.0.28 installation recipe makes the automotive component
compatible with the released core code for STEP 10.0.

New Features {#new-features .MPNNewFeatures}
------------

Internal Note: RDCUST- 4155Added support to access \'Onboarding mapping
navigator\' component in the new Global Navigation Panel

The released core code for STEP 10.0 has superseded the existing Stack
Panel component by a new component called Global Navigation Panel.
Earlier, the Mapper Configuration setup entity was allowed to be
configured within the Stack Panel component for access within the Web
UI. Now, the Mapper Configuration setup entity can be accessed through
the Global Navigation Panel too.

For users, this means that the Stack Panel component is not completely
removed (deleted) yet. However, as the alternate component is now
announced, it is very important for customers to make sure they are
using the Global Navigation Panel component for accessing the Mapper
Configuration setup entity after this upgrade. Details on how to
configure the Global Navigation Panel is outlined in the Global
Navigation Panel topic in the Web User Interfaces / Web UI Getting
Started documentation of the STEP Online Help ([here]{.mcFormatColor
style="color: Blue;"}). And for information on adding the \'Onboarding
mapping navigator\' component in the Global Navigation Panel, see the
Onboarding Mappings Details Screen topic of the Automotive Reference
Guide[ here]{.mcFormatColor style="color: Blue;"}.

 

Patch recipe {#patch-recipe .MPNDownload}
------------

The Automotive add-on can be installed with the following recipe:

[to:automotive/7.0/automotive-7.0.28.]{.commandfont}[spr]{.commandfont
createdate="2018-10-04T09:05:58.3700255-04:00" creator="medu"
initials="MEDU"
comment="update the Patch Recipe and Compatibility topic too"
editor="medu" editdate="2018-10-10T15:52:58.2899872-04:00"}

The above recipe is compatible with the following STEP 10.0 baseline
recipe:

[to:step/platform/step-10.0.spr]{.commandfont}

Once an Automotive add-on is installed to a base STEP system, the base
system cannot be upgraded without upgrading the Automotive add-on at the
same time. Additionally, when upgrading any base STEP system that has
any Automotive add-on installed, both install recipes must be prepared
at the same time.

For assistance in applying the patch to systems with extensions or
additional add-on components, contact Stibo Systems Technical Services.
