---
description: 'Stibo SDQ User Guide: The DUNS Lookup action button is
  used to enrich an account with a DUNS Number, and optionally add other
  Dun &amp; Bradstreet data to the account. The DUNS Lookup action
  button (shown below) can be accessed by clicking the action button
  dropdown arrow when viewing an account in Salesforce Lightning
  Experience. '
title: '\[%=Heading.AnyLevel%\]'
---

DUNS Lookup Action Button
=========================

The DUNS Lookup action button is used to enrich an account with a
DUNS Number, and optionally add other Dun & Bradstreet data to the
account. The DUNS Lookup action button (shown below) can be accessed by
clicking the action button dropdown arrow when viewing an account
in Salesforce Lightning Experience.

When using Salesforce Classic, the dropdown is not used to access the
action buttons.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/DUNSLookupButton.png)

For more information on displaying the DUNS Lookup action button, see
the **D&B Buttons** setup section of the **Stibo SDQ Admin Guide**.

When a user clicks the DUNS Lookup action button, Stibo SDQ performs a
lookup against the D&B database. If the operation successfully
completes, then the user will be prompted with one of the following
messages:

-   Your request cannot be fulfilled for the given criteria.
-   No candidates resulted for the given input criteria.
-   Select from a list of potential matches.

Your Request Cannot be Fulfilled for the Given Criteria

If the account detail information already in Salesforce is deemed
insufficient when run against the D&B database, an error will display as
shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/DUNSLookupButtonResultIfParametersNotFilled.png)

When given this message, users can:

-   click the \'**X**\' to close the error message and remain on the
    page.
-   click the **Cancel** button to return to the account details page.
-   click the **Change Search Criteria** button to go to the Refine
    Lookup Search page.

No Candidates Resulted for the Given Input Criteria

If the account detail information already in Salesforce is not matched
to any other accounts in the D&B Database, then an error will display
(as shown below).

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/DUNSLookupResultIfNoMatch.png)

When given this message, users can:

-   click the \'**X**\' to close the error message, and remain on the
    page.
-   click the **Cancel** button to return to the account details page.
-   click the **Change Search Criteria** button to be directed to the
    Refine Lookup Search page.

Select From a List of Potential Matches

If the account detail information already in Salesforce potentially
matches other accounts in the D&B Database, then those potential matches
will display within a list from which a user may select.

For example, when an account name field is populated with the text
\'Stibo,\' clicking the DUNS Lookup action button prompts a list of
potential matches to display (as shown below).

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/DUNSLookupButtonResult.png)

If the provided search criteria results in only one potential match,
that record is auto-selected.

When presented with a list of potential matches, users can:

-   click the **Cancel** button to return to the account details page.
-   click the **Change Search Criteria** button to go to the \'DUNS
    Lookup Refine Lookup Search Page.\'
-   select a DUNS Number from the list to go to a \'DUNS Lookup Survival
    Page.\'

Refine Lookup Search Page
-------------------------

When a DUNS Lookup Action results in a list of potential matches, the
user may choose to refine the search to produce more relevant results by
clicking the \'Change Search Criteria\' button. This takes the user to
the Refine Lookup Search page (shown below).

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/Refine%20Lookup%20Search%20Page.png)

In this screen, users can see the criteria used to produce the search
results on the previous screen. Users are given the option to change or
refine the criteria when the list of search results is too long.

Optionally, users can:

-   click the **Cancel** button to return to the account details page.
-   make necessary changes to adjust the search criteria used when
    looking up a DUNS number.
-   click the **Search** button to continue.

DUNS Lookup Survival Page
-------------------------

The DUNS Lookup Survival page allows users to determine which data
should \'survive\' the DUNS Lookup operation.

Once the DUNS Lookup Action Button is used to display a list of
potential matches, and a DUNS Number is clicked, the DUNS Lookup
Survival page will display as shown below.

![](../../../../../Resources/Images/CMDM/User%20Guide/Dun&BradstreetEnrichment/DUNS%20Lookup%20MP1.png)

Optionally users can:

-   select a radio button on a given row for either the
    \'CURRENT VALUE\' or \'D&B VALUE\' columns to determine the survival
    value. The survival value for the row will display within the last
    column, the \'RESULT VALUE\' column.
-   click the **Cancel** button to cancel the operation and return to
    the Account details page.
-   click the **Save** button to update the Account with selected data.
