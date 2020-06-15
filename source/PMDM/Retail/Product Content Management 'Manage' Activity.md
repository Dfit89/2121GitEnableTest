---
description: 'Within the Product Content Management module, the
  \''manage\'' activity involves user groups for images, marketing copy,
  and warehouse providing the required data for the buyer\''s approval.'
title: '\[%=Heading.AnyLevel%\]'
---

Product Content Management \'Manage\' Activity
==============================================

![](../../../Resources/Images/PMDM%20for%20Retail/PMDMManage.png)

Two actions are included in the \'manage\' activity:

-   Enrich data for a newly created product in the Product Creation
    Workflow.
-   Collaborate about any subject on a product or a family in the
    Product Collaboration Workflow.

Each action is described below.

Enrich Product Data Action
--------------------------

Within the Product Content Management module, the \'enrich\' action
involves user groups for images, marketing copy, and warehouse providing
the required data for the buyer\'s approval.

The business logic in this action is as follows:

-   STEP checks if the product is classified, and if not, the product is
    assigned to the \'Buyer Group\' for manual classification. This is
    repeated until the product is classified.
-   The **Buyer** reviews the data. If the data is not acceptable, the
    task is reassigned to the previous individual user for additional
    data review.
-   The product is reviewed and enriched by these user groups:

The **Marketing Copy Group** handles the \'Copy Writing\' state and
enriches marketing information.

The **Image Group** handles the \'Digital Assets\' state and uploads
digital assets relevant to the product.

The **Warehouse Group** handles the \'Warehouse Data\' state and
enriches warehouse data information.

-   The **QA Expert** reviews all data and either accepts or rejects the
    product.

 

![](../../../Resources/Images/PMDM%20for%20Retail/manageEnrichmentProcess.png)

### Review and enrichment actions by role

  ---------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ![](../../../Resources/Images/PMDM%20for%20Retail/buyer.png)                 The Buyer reviews a newly-completed product completely before submitting it to the rest of the team.
  ![](../../../Resources/Images/PMDM%20for%20Retail/marketingspecialist.png)   The Marketing Specialist must assign the product to a Web Category and should also provide additional review as necessary.
  ![](../../../Resources/Images/PMDM%20for%20Retail/imagespecialist.png)       The Image Specialist must attach a Primary Product Image, and should also provide additional review as necessary, and clicks the \'Proceed\' button.
  ![](../../../Resources/Images/PMDM%20for%20Retail/warehousespecialist.png)   The Warehouse Specialist has no required actions, as this role can vary per customer. This review can include attribute information for Base Unit Information (the package of the \'each\' dimensions and weight), Country of Origin, Regulatory Information, and Packaging Hierarchy (in this module, Packaging Hierarchy are modeled as a Data Container).
  ![](../../../Resources/Images/PMDM%20for%20Retail/qaexpert.png)              The QA Expert performs the final review and validation, and then approves or rejects the product.
  ---------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Review and enrichment action process

1.  On the homepage in the Product Creation Workflow widget, specialists
    see the number of products ready for review and enrichment based on
    role. In this example, the Marketing Specialist clicks the link to
    display the \'To do\' tab and the tasks in the Copywriting Review
    state.

![](../../../Resources/Images/PMDM%20for%20Retail/enrichWorkflow.png)

1.  On the To Do tab, the specialist reviews the product, focusing on
    the data listed, and clicks the **Assign To Me** button if editing
    is required. In this example, the Marketing Specialist clicks the
    \'Assign to me\' button before providing the data for the
    Copywriting Review task.

![](../../../Resources/Images/PMDM%20for%20Retail/enrichToDoAssign.png)

1.  After each team completes the review and enrichment, the QA Expert
    validates the data quality and takes one of these actions:

-   Accepts the product, which is then automatically approved and
    exported, as defined in the **Product Content Management \'Share\'
    Activity** topic[ here]{.mcFormatColor style="color: Blue;"}.
-   Rejects the product and returns it to the Buyer, Copy Writing,
    Digital Assets, and/or Warehouse group, adding a message for the
    group(s).

![](../../../Resources/Images/PMDM%20for%20Retail/enrichQASpecialist.png)

Collaboration Action
--------------------

PMDM for retail integrates a Collaboration feature based on a workflow.
When browsing a product page, a member of the team can forward the
product to a user group with a message. Collaboration can be used to
raise a question, request action from a team member, etc.

For example, consider the following process to conduct a conversation
between Rachel, the buyer, and Imogen, the image specialist.

1.  Buyer Rachel clicks the Collaboration button.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationButton.png)

1.  Buyer Rachel selects the Image Group as recipient and adds a
    message.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationImgGrpMessage.png)

1.  Image specialist Imogen sees there is a message for the Image Group
    on the homepage Collaboration Workflow widget and clicks the link.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationLink.png)

1.  Image specialist Imogen reviews the latest message in the task list.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationMessage.png)

1.  Image specialist Imogen uses the \'Assigned to me\' header to claim
    the task.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationMessageAssigned.png)

1.  Image specialist Imogen views the conversation thread on the product
    page.

![](../../../Resources/Images/PMDM%20for%20Retail/collaborationConvoThread.png)

1.  Image specialist Imogen can perform the following actions:

-   Continue the conversation by adding a new message and clicking the
    **Collaboration** button.
-   Click the **Release Task** button to remove the current assignment
    so that someone else in the group can work the task.
-   Click the **End Collaboration** button to finish the conversation.
