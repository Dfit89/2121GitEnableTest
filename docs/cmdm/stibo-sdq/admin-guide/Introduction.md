---
description: 'Stibo SDQ Admin Guide: Stibo SDQ is an easy-to-install
  certified Salesforce app compatible with both the Salesforce Classic
  and Lightning Experience. '
title: '\[%=Heading.AnyLevel%\]'
---

Introduction
============

Stibo Systems Data Quality (Stibo SDQ) is a Salesforce app that allows
Salesforce Administrators to ensure and enhance the quality of their
system data. The app is compatible with both Salesforce Classic and
Lightning Experience.

This guide will enable system administrators to easily setup and
configure Stibo SDQ for Salesforce. Stibo SDQ is designed to be used
with one or more themes interchangeably with flexible configurations.
Each implementation can provide very different results. This guide aims
to describe the different Stibo SDQ configuration settings by theme,
allowing system administrators to easily configure the capabilities as
described within the **Stibo SDQ User Guide** ([here]{.mcFormatColor
style="color: Blue;"}).

API keys and/or credentials for the Stibo SDQ themes are provided by
Stibo Systems by sending an email to StiboSDQ\@stibosystems.com. Once
you have received the necessary API keys and/or credentials, consult the
Areas to Configure section below.

This guide includes an **Appendix** ([here]{.mcFormatColor
style="color: Blue;"}) containing additional background information that
a system administrator may find useful.

Prerequisites
-------------

It is recommended that system administrators read the **Stibo SDQ User
Guide** ([here]{.mcFormatColor style="color: Blue;"}) prior to this
guide.

At least 48 hours prior to installing Stibo SDQ, it is recommended to
email StiboSDQ\@stibosystems.com to obtain the required API keys and/or
credentials for the desired themes.

Areas to Configure
------------------

The following guide is broken down into sections, where each will
configure a part of Stibo SDQ.

1.  Installing apps in Salesforce can be done with a single click from
    the Salesforce App Exchange. There are a few parameters to keep in
    mind while installing the app. For a walk through of these
    installation process, see the **Installing Stibo SDQ** topic in this
    guide [ here]{.mcFormatColor style="color: Blue;"}
2.  After installing the Stibo SDQ app, the various validation themes
    will allow certain validation processes to be enabled. Users may
    enable one theme, two themes, or all three. For more information on
    enabling the Stibo SDQ themes, see the **Enable StiboSDQ Themes**
    topic in this guide [ here]{.mcFormatColor style="color: Blue;"}.
    These sections will also detail how to map data objects from
    Salesforce to Stibo SDQ.

```{=html}
<!-- -->
```
a.  To validate data based on user phone numbers, email addresses,
    and/or physical addresses, see the **Enable the Real-time Contact
    Data Validation Theme** in this guide[ here]{.mcFormatColor
    style="color: Blue;"}.
b.  To connect to the STEP or other MDM platform, see the **Enable the
    Master Data Management Theme** topic in this guide[
    here]{.mcFormatColor style="color: Blue;"}
c.  To take advantage of the Dun & Bradstreet platform for data
    validation, see the **Enable Dun & Bradstreet Theme** topic in this
    guide[ here]{.mcFormatColor style="color: Blue;"}.

```{=html}
<!-- -->
```
3.  To access various pages and perform certain actions in Stibo SDQ, a
    user profile will need to be created or certain permissions need to
    be added to the standard user profile. For information on which
    permissions are needed, see the **Set Up a User Profile** topic in
    this guide to set up the correct permissions for Stibo SDQ[
    here]{.mcFormatColor style="color: Blue;"}.
4.  Stibo SDQ requires some custom fields to be configured to ensure
    that the data objects from Salesforce can pass the data to Stibo
    SDQ. For information on these custom fields, see the **Set Up Custom
    Fields** topic in this guide[ here]{.mcFormatColor
    style="color: Blue;"}.
5.  Salesforce requires customization of buttons to use new
    functionality with the D&B Enrichment Theme. For information on
    setting up the buttons needed for the D&B enrichment theme, see the
    **Button Customization Setup** topic in this guide[
    here]{.mcFormatColor style="color: Blue;"}.
6.  Salesforce will need configurations for triggering asynchronous
    validation. For information on setting up these triggers, see the
    **Async Validation** topic in this guide[ here]{.mcFormatColor
    style="color: Blue;"}.

Contact Us
----------

For more information about Stibo SDQ, or to obtain the required
application keys, email StiboSDQ\@stibosystems.com, otherwise contact
support at StiboSDQSupport\@stibosystems.com.
