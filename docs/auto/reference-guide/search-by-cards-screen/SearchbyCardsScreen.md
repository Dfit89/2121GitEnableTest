---
description: 'Automotive Solution: The Search by Card Screen uses the
  sync between search cards functionality providing an easy-to-use
  intelligent search interface with an effective results table thereby
  making it possible for the user to narrow down the search result and
  only see the relevant result.'
title: '\[%=Heading.AnyLevel%\]'
---

Search by Card Screen
=====================

The Search by Card Screen uses the sync between search cards
functionality to provide an easy-to-use intelligent search interface.
This makes it possible for the user to narrow down the search result and
only see the relevant result. This screen can be configured to define
the most likely used filter groups for the search in the Web UI. For
example, if the user needs to find a vehicle based on the Name, Make,
Model, Year, or any attribute value, and the search cards are configured
to be available for each of these search criteria in the Search by Card
Screen, then users can refine the list of objects based on one or more
of the available filters.

The top half of the Search by Card Screen offers features related to the
intelligent search interface. The bottom half of the screen is dedicated
to the search results table and its toolbar

The Search by Card Screen topics in online help include:

-   Search by Card Screen Initial Configuration ([here]{.mcFormatColor
    style="color: Blue;"})
-   Using Search by Card Screen Interface ([here]{.mcFormatColor
    style="color: Blue;"})

The topics listed below cover more information on Search by Card
configurations, going beyond the basic setups described in the
introductory material.

-   Using Search by Cards Screen with Data Onboarding Tasks

The Search by Card Screen is highly configurable via the Web UI
Designer, and more than one Search by Card Screen can be created within
each Web UI. Therefore, it is expected that a Web UI administrator will
configure a Search by Card Screen in a manner that best meets their
user\'s needs. For more information on configuring the Search by Card
Screen, see the **Search by Card Initial Configuration** topic[
here]{.mcFormatColor style="color: Blue;"}.

Search by Card Screen Interface Overview
----------------------------------------

The top half of the Search by Card Screen offers features related to the
intelligent search interface. The bottom half of the screen is dedicated
to the search results table and its toolbar. The Search by Card Screen
is composed of the following:

![](../../Resources/Images/Search%20by%20Card%20Screen/11.png)

1.  **Title:** Users can edit the Title in Design mode with any text
    string.
2.  **Card based search panel:** Use cards to narrow down the search
    result and only see relevant nodes. Users can configure the cards to
    use attributes, parent hierarchy, or Name. All of the configured
    cards are synchronized, and the search criteria can be entered into
    the cards in any order, and the available search criteria will
    display in the typeahead dropdown based upon the criteria that have
    been entered within the other cards.
3.  **Saved search tool:** Allows users to save previously selected
    search criteria with custom names, and then quickly populate
    previously saved search criteria by selecting the name of a saved
    search from the saved search dropdown. The tool consists of a saved
    search dropdown field, as well as Save, Rename, and Delete icons.
    For more information about the saved search tool, see the **Saved
    Search Tool** topic within the **Application Manager** section of
    this guide[ here]{.mcFormatColor style="color: Blue;"}.
4.  **Clear All link:** Allows users to clear all search criteria and
    results that are displayed in the results table. The Clear All link
    remains disabled until at least one criterion for one of the search
    cards is populated. When text is typed into a search card, but is
    not yet selected, clicking the link will also remove the text typed
    into the search card. Additionally, a criterion can be cleared one
    at a time by clicking the
    \'[X]{style="color: #0000ff; font-weight: bold;"}\' to the right of
    a value within a search card. Clearing the criteria in either way
    does not update the search results. Once any unnecessary criteria
    are removed, the Search button must be used to update the results
    table.
5.  **Search button:** When clicked, the Search button will use the
    criteria that are provided within the search cards, and then provide
    results matching the search criteria in the results table. The
    Search button remains disabled until at least one search card is
    populated.
6.  **Results table toolbar:** Allows users to configure action buttons,
    such as bulk update or export, relative to the Search by Card
    results table. Action buttons can be configured using the Web UI
    Designer. For more information about action buttons, see the
    **Action Buttons** section of the **Web User Interfaces** guide
    within **STEP Online Help**[ here]{.mcFormatColor
    style="color: Blue;"}.
7.  **Display Mode:** Allows user to change the display modes. The list
    of available display modes can be edited as needed by accessing the
    Search by Cards Node List Properties Child Component Display Modes
    parameter. For more information on the list of available display
    modes, see the **Node List Component** topic within the **Web User
    Interfaces** section of **STEP Online Help**[ here]{.mcFormatColor
    style="color: Blue;"}.

![](../../Resources/Images/Search%20by%20Card%20Screen/10.png)

1.  **Flip table icon:**
    ![](../../Resources/Images/AppMgr/ResultsTable/Flip%20table%20icon.png)
    Allows users to change or flip the orientation of the table.
2.  **Row selection boxes:** Allows for selection of one or more rows
    within the table. Selecting at least one row can change the action
    buttons that display within the toolbar.

![](../../Resources/Images/AppMgr/ResultsTable/Row%20selection%20boxes.png)

1.  **Hyperlinks:** When text within the results table displays as a
    hyperlink, users are able to click the text and a screen specific to
    that text will display.

![](../../Resources/Images/Search%20by%20Card%20Screen/9.png)

11. **Results table:** Displays the list of search results. A Node List
    component is used to display the results of selections made within
    the intelligent search interface. Each column label can be edited as
    needed by accessing the Search by Cards Node List Properties Headers
    parameter.
12. **Edited items panel:** Contains an expand / collapse arrow, Save,
    and Reset buttons. When the panel is expanded and changes are made
    to the results table, the changes are displayed as a list in the
    panel. In the example below, it is easy to see that the
    034-VC36004(2) object has been edited. By default, the \'Use
    Immediate Save\' parameter within the Node List Properties is
    disabled. When enabled, the Save button will not display, and the
    list of edited items will briefly display.

![](../../Resources/Images/Search%20by%20Card%20Screen/8.png)

1.  **Number of items:** List the total number of search result items
    that are listed within the results table.
