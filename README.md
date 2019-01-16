# Interview UI Test
--------

## Timeline
You have 48hours from the time you have recieved the email to submit the solution. If you need more time, please send us an email.

## Links

For the UI Test, please make sure you have access to the following links:
1. JSON Data - https://jsonblob.com/api/
2. Wireframes - https://invis.io/9NPZNTFYGJ2#/341059211_1-_Benefit_Configurator

Analyze the JSON clearly to understand the Product JSON structure. 

## Tech Stack

You can use any of the following:
1. Angular
2. React
3. Node JS
4. JavaScript

## JSON Structure

```
{
  "records" : [{
    "productId": "",
    "Name": "",
    ...
    "coverages": {
      "records": [
        {
          "productId" : "",
          "Name": "",
          ...
          "attributeCategories": [
            "records": [{
              "Id": "",
              "Name": "",
              ...
              "productAttributes" : {
                "records": [{
                   "attributeGroupType": "In-Network",
                   "inputType": "dropdown",
                   "userValues": "yes",
                        "values": [
                          {
                            "value": "yes",
                            "disabled": false,
                            "readonly": false,
                            "label": "Yes",
                            "id": "0"
                          },
                          {
                            "value": "no",
                            "disabled": false,
                            "readonly": false,
                            "label": "No",
                            "id": "1"
                          }
                    ],
                    ...
                }]
              }
            }]
          ]
        }
      ]
    }
  }]
}
```

On a very high-level, here is the product json structure:
```
{
  Product: [{
    Coverages : [{
      AttributeCategory : [{
        Attribute : {}
      }]
    }]
  }]
}
```
* Note: The JSON sample data does not match the UI Screen. The JSON has only 1 product in the list.

## UI Layout
The UI Screen shared in the wireframe has 3 layout section.

1. Left Section - Displays the `Product` List.
2. Middle Section - Displays the `Coverages` that belongs to the selected Product.
3. Right Section - Displays the `Attributes` that belongs to the selected Coverage.

## Problem Statement
1. As a user, I need ability to select a `Product`, depending on the product selected, display the `Coverages`. 
For Ex: When PPO Retiree Comprehensive plan from the Product section, the appropiate Coverages that belong to the Product needs to be loaded in Middle section. 

2. On `Coverage` selection, display the `Attributes` that are related to the Coverage.
For Ex : When Acupuncture is selected, Display the attributes that are related to the coverage Accupuncture. 

3. Attribute elements needs to be dynamically rendered on the screen depending on the type of the Attribute.
For Ex : If Attribut type is input, display a input field, if Attribute type is dropdown, display a dropdown field with neccessary values loaded in the dropdown.

4. Group the attributes with In-Network and Out-of-Network.
5. Group the attributes with Attribute Category.
For Ex: Acupuncture Outpatient Institutional, Acupuncture Outpatient Professional

6. On click of toggle next to Attribute Category, hide the Attribute and reset the values.

## Test Submission
Please Share the code using Git/BitBucket URL. Do not send Zip Files of the code.
