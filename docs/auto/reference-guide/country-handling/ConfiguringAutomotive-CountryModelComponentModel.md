---
description: 'Automotive Solution: Describes how to configure the
  \''Automotive - Application Model\'' component model for use with the
  Country Handling solution. Once a STEP system is set up to display the
  \''Automotive - Application Model\'' component model, then the
  \''Automotive - Country Model\'' component model will also display
  within Workbench\> System Setup \> Component Models. '
title: '\[%=Heading.AnyLevel%\]'
---

Configuring Automotive - Country Model Component Model
======================================================

09/11/2018 Sprint Demo SUJAY. includes a typeahead filter for Country
can be within a Country Group, a Save button. Need to be able to see the
countries that are selected within a country group (highlighted?).
Countries are modeled within Country Groups via the Classification files
and the TD\_CountryToCountryGroup Reference Type. Automotive - Country
Model component model. The Automotive - Country Model component model is
available with the Automotive license. SIMO to talk with BEJA about
having more than one Country Model. The classification folders and
references are created upon import of the TD Reference Data importer.
Solution was designed with the TD Reference Data Importer in mind.

Once a STEP system is setup to display the \'Automotive - Application
Model\' component model, then the \'Automotive - Country Model\'
component model will also display within Workbench \> System Setup \>
Component Models.

The component model will need to be manually configured. In the example
below, the standard TecDoc object types, LOV, and Reference Type have
been used to configure the component model values.

![](../../Resources/Images/Country%20Incl%20Excl/1.png)

Click the **Edit** link located below the component parameters to add or
remove values for the parameters. All of the parameters must be properly
populated for the Country Handling solution to function as expected.

The \'Automotive - Country Model\' component model provides the
following required parameters:

-   **Country:** Required parameter used to define the Country and/or
    Country groups to be used within the Country Handling solution. Add
    one or more Country and/or Country groups. In the example above, the
    following values are added: \'Country\' (TD\_Country) and \'Country
    Group\' (TD\_CountryGroup). Though the label is \'Country\' (EU can
    be considered a country, and DK can be considered a country) This
    solution only considers leaf countries. Countries are modeled within
    Country Groups via the Classification files and the \'Country to
    Country Group\' (TD\_CountryToCountryGroup) Reference Type.The
    classification folders and references are created upon import of the
    TD Reference Data importer.

The Country and Country groups classifications must be configured with
the Reference Type configured within the \'Country group link\'
parameter or the solution will not work.

-   **Country LOV link:** Required parameter used to define the one LOV
    list of countries to be used for both the inclusion and exclusion
    attributes. It is important to only use one LOV list as this helps
    to guarantee the same country will not be referenced for both
    inclusion and exclusion attributes. The LOV list should be single
    valued and use LOV Value ID\'s. In the example above, the following
    LOV value is added: \'Country Code (single value)\'
    (TD\_ATTR\_CountryCode). As defined \<\<SOMEWHERE\>\>, some
    configuration needs to be done before this can be populated.

The \'Country Code (single value)\' (TD\_ATTR\_CountryCode) LOV must
contain the country codes of all the countries and/or country groups to
be displayed, and the LOV must be made valid for both the inclusion and
exclusion attributes.

-   **Country group link:** Required parameter used to define the
    countries that should be listed within each Country group. In the
    example above, the following value is added: \'Country to Country
    Group\' (TD\_CountryToCountryGroup).

To apply this concept to more than one Country Handling solution (i.e.,
OWN model), Country LOV Link attribute, Country Object Type, and Country
group link values need to be configured separate from those used for the
TecDoc or AutoCare solutions.

Once the Automotive - Country Model component model is configured, the
\'Application Country Handling Table Header\' and/or \'Country Handling
Value\' components need to be configured. For more information, see the
**Configuring Application Country Handling Table Header**
([here]{.mcFormatColor style="color: Blue;"}), and the **Configuring
Country Handling Value Component** topics[ here]{.mcFormatColor
style="color: Blue;"}.
