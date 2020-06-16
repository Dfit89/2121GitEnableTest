---
description: 'PLM Solution: This topic describes the JSON schema and its
  structure.'
title: '\[%=Heading.Level1%\]'
---

JSON Schema
===========

The JSON schema has the following structure:

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-ConditionalTABLE.png)

JSAON Schema in table above:

    var text = {

    "PLMDefiningAttribute": {

    "mandatory": false,

    "readonly": false,

    "conditionalMandatory": true,

    "flexAttribute" : true,

    "rules": [

    {

    "attribute": "attributeID",

    "values": [

    {

    "context": "Context1",

    "value": "Y"

    }

    ]

    }

    ]

    };

    return JSON.stringify(text);

Any number of rules can be defined for an attribute. The rules will be
evaluated from the top down, and stop evaluating when a rule is
evaluated to true, displaying the conditional attribute in the MRE
dialog.

If any of the attributes for a rule have not been added as a PLM
Attribute Value child component to the PLM Edit Reference Action, the
rule will be ignored and skipped, and a warning will be logged to the
system log file.

Example 1: Condition Rules -- Business Function

In this example, the \'Additional Comments\' attribute is shown in the
\'Answer Requirement\' dialog when the dependent attribute \'Meets
Requirements?\' has a value equal to **No**.

The \'Additional Comments\' attribute has been configured as a
Conditional Mandatory attribute.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-ConditionalBRTable2.png)

Business function in table above:

    var text = {

    "PLMDefiningAttribute": {

    "mandatory": false,

    "readonly": false,

    "conditionalMandatory": true,

    "flexAttribute" : true,

    "rules": [

    {

    "attribute": "PLMMeetsRequirement",

    "values": [

    {

    "context": "Context1",

    "value": "Y"

    }

    ]

    }

    ]

    },

    "PLMAdditionalSupplierComments": {

    "mandatory": false,

    "readonly": false,

    "conditionalMandatory": false,

    "rules": [

    {

    "attribute": "PLMMeetsRequirement",

    "values": [

    {

    "context": "Context1",

    "value": "N"

    }

    ]

    }

    ]

    },

    "PLMRequirementDescription": {

    "mandatory": false,

    "readonly": true,

    "conditionalMandatory": false

    },

    "PLMHelpText": {

    "mandatory": false,

    "readonly": true,

    "conditionalMandatory": false

    }

    };

    return JSON.stringify(text);

Example 2: Condition Rules -- Business Function

In this example, the \'Additional Comments\' attribute is shown in the
Answer Requirement dialog when the dependent attribute \'Meets
Requirements?\' has a value equal to **No**.

The \'Additional Comments\' attribute has been configured as a
Conditional Mandatory attribute. The Save button will not be enable
until the \'Additional Comments\' attribute is populated.

![](../../../../Resources/Images/Solution%20Enablement/PLM/Conditional-MReTABLE4.png)

**Business function in table above**:

    var text = {

    "PLMDefiningAttribute": {

    "mandatory": false,

    "readonly": false,

    "conditionalMandatory": true,

    "flexAttribute" : true,

    "rules": [

    {

    "attribute": "PLMMeetsRequirement",

    "values": [

    {

    "context": "Context1",

    "value": "Y"

    }

    ]

    }

    ]

    },

    "PLMAdditionalSupplierComments": {

    "mandatory": true,

    "readonly": false,

    "conditionalMandatory": false,

    "rules": [

    {

    "attribute": "PLMMeetsRequirement",

    "values": [

    {

    "context": "Context1",

    "value": "N"

    }

    ]

    }

    ]

    },

    "PLMRequirementDescription": {

    "mandatory": false,

    "readonly": true,

    "conditionalMandatory": false

    },

    "PLMHelpText": {

    "mandatory": false,

    "readonly": true,

    "conditionalMandatory": false

    }

    };

    return JSON.stringify(text);

Example 3: Condition Rules -- Business Function

In this example, the \'Additional Comments\' attribute is shown always
in the Answer Requirement dialog when the dependent attribute \'Meets
Requirements?\' has a value equal to **No**.

The \'Additional Comments\' attribute become a Mandatory attribute, and
the Save button will not be enabled until \'Additional Comments\' field
is populated.

![](../../../../Resources/Images/Solution%20Enablement/PLM/MRE-ConditionalTable5.png)

Only attributes that are valid on the Requirement reference and/or
Parameter reference should be configured in the component list. If they
are not valid, they will not be displayed and will not have any values.

Business function in table above:

    var text = {

    "PLMDefiningAttribute": {

    "mandatory": false,

    "readonly": false,

    "conditionalMandatory": true,

    "flexAttribute" : true,

    "rules": [      {

    "attribute": "PLMMeetsRequirement",

    "values": [

    {

    "context": "Context1",

    "value": "Y"

    }

    ]

    }

    ]

    },

    "PLMAdditionalSupplierComments": {

    "mandatory": false,

    "readonly": false,

    "conditionalMandatory": true,

    "rules": [

    {

    "attribute": "PLMMeetsRequirement",

    "values": [

    {

    "context": "Context1",

    "value": "N"

    }

    ]

    }

    ]

    },

    "PLMRequirementDescription": {

    "mandatory": false,

    "readonly": true,

    "conditionalMandatory": false

    },

    "PLMHelpText": {

    "mandatory": false,

    "readonly": true,

    "conditionalMandatory": false

    }

    };

    return JSON.stringify(text);
