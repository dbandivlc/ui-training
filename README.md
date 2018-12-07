# Navigation
--------

OmniScript runs by default on a OmniScriptUniversalPage, but if we need to overwrite the out of the box functionality, here are the following steps.

## Creating VisualForce Page
1. Create a new version of OS from TrainingUIFlow and update the name to `TrainingUIUXFlow` and subtype to `UIUXFlow`.
2. Click on `How to launch activated script` button.
3. Under `Embedded` section, select `Newport` and copy the script below.
4. Goto `SetUp`, in the Quick Find search for `Visualforce pages`. Create a `New` Visualforce page.
5. Set the Label and Name as `TrainingUIFlow` and Enable Lightning Experience.
6. Insert the previously copied script from Step 3 into the Visualforce page.
7. Click on Save.


## Linking VF Page to OmniScript
1. In the OmniScript, under Script Configuration, go to Visualforce Pages section.
2. Click on `Add New Visuaforce Page For Preview`
3. Name : TrainingUIUXFlow, Label : c__TrainingUIUXFlow?&layout=newport
4. Go to Preview of OmniScript, on the dropdown select the last option TrainingUIUXFlow.


## Get `Path` Component from NewPort
1. Run NewPort Design System on you local `npm start`
For more info : https://github.com/vlocityinc/newport-design-system
2. Select `Path` from Component List.
3. Copy the HTML by clicking on the code icon on bottom right of the panel.
4. Create a Visualforce component and name it as `TrainingStepChart`.
5. Add `<c:TrainingStepChart />` under the script tag after initializing AngularJS in Visualforce page.

Go back to your OmniScript and hit the preview tab, select TrainingUIUXFlow page from dropdown, you will be having a new UI Navigation.
