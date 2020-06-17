---
description: 'Automotive Solution: Describes how automotive validation
  path functionality affects options on applications. '
title: '\[%=Heading.AnyLevel%\]'
---

Validation Path Functionality and Options on Applications
=========================================================

PRODOC note: MEDU RDUCST-2713 The application data model (Automotive -
Application Model) includes configurations for object types and link
types that define the relationship between conditions / options on
applications and different configurations of vehicles. This allows an
Application Manager to be used to search for applications with specified
conditions / options (i.e., engines, fuel type, regions, sub models).
The validation path concept affects the options on missing applications
by automatically populating selected options on applications, and
allowing the selection of valid options within the Value editor.

Automatic Population of Options on Applications
-----------------------------------------------

When criteria are selected within the Options search boxes (displaying
the \'Fuel Type\' and \'Engine\' options in the screenshot below), and
the Search button is clicked, the Results table will display each
vehicle that is missing an application with the Options cell
automatically populated based upon the Options search box criteria. Once
the part is applicated to the vehicle the automatically populated
options will be stored as references on the application.

For example, when an Options search box has the Fuel Type option type
displayed with the Diesel criterion selected, the second Options search
box has the Engine option type displayed with the \'2.0L L4, 1968CC,
120CID\' criterion selected, and the Search button is clicked, the
results table will display the valid vehicle with the Options cell
automatically populated with the specified Fuel Type and Engine (as
shown below).

![](../../../Resources/Images/AppMgr/Validation%20Paths/OptionsAutoDisp.png)

Options Within the Value Editor
-------------------------------

Once an application has been created within the Results Table at the
bottom of an Application Manager, double clicking the Options cell of
the application row displays the \'Value editor.\' Within the Value
editor, some options automatically display, however additional options
(conditions) can be selected to display for population. The selection of
valid options, and their valid values, is driven by the validation path
functionality.

PRODOC note: MEDU This may get moved to the value editor: In other
words, consider when a vehicle is manufactured with multiple body styles
(i.e., sedan, coupe, convertible), and the body style chosen determines
the number of possible doors available on the vehicle. When a coupe body
style is chosen, no more than two doors can be valid for the body style
configuration. Whereas when a sedan body style is chosen, no less than
four doors can be valid.
