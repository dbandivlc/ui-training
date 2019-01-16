# Interview UI Test
--------

For the UI Test, please make sure you have access to the following links:
1. JSON Data - https://jsonblob.com/api/
2. Wireframes - https://invis.io/9NPZNTFYGJ2#/341059211_1-_Benefit_Configurator

Analyze the JSON clearly to understand the Product JSON structure. 

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
