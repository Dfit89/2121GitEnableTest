---
description: 'Customer MDM Solution: A getSimilarObject use case for
  finding loyalty members after one of the members has married.'
title: '\[%=Heading.AnyLevel%\]'
---

Use Cases - getSimilarObjects Preventing Duplicates
===================================================

Catherine Yu signed up in-store for an ACME loyalty account to take
advantage of an in-store promotion. Catherine is engaged and living in
Texas. She is across the country from her fiancé who is in Michigan.
Catherine signed up for the loyalty program using her maiden name, her
Texas address, and her lifelong cell phone number.

After she\'s married, Catherine changed her name and moved to Michigan
with her new husband. She goes shopping online and forgets she had
signed up for the loyalty program and attempts to sign up again.
Catherine uses her new last name, her Michigan address, and her lifelong
cell phone number to sign up.

Without the exact same data, it is impossible for the CRM to find
Catherine\'s loyalty account and previous purchases.

Catherine creates a duplicate loyalty account. Flyers and promotions are
now being sent to two addresses. ACME missed cross sell and upsell
opportunities because disjointed records make it impossible to identify
Catherine\'s purchase history.

Current Duplicate Search

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/AsIsCatherine.png)

With the current system landscape, Catherine is unable to see that a
loyalty account exists under her maiden name. ACME has a disjointed view
of who Catherine is and the products she's purchased.

To-Be Duplicate Search

![](../../../../../Resources/Images/Solution%20Enablement/CMDM/To-Be%20Catherine.png)

The CMDM system can identify Catherine's existing loyalty account for
other systems through the getSimilarObjects call. Catherine can identify
and update her existing loyalty account preventing a duplicate loyalty
account from being created.
