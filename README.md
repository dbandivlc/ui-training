# Vlocity UI Training
--------

For the Vlocity UI Training, please make sure you have the following.
1. Install Node JS - https://nodejs.org/en/download/
2. Install Git - https://git-scm.com/downloads
3. Install Vlocity Build (Do not clone) - https://github.com/vlocityinc/vlocity_build
4. Clone the Newport Design System - https://github.com/vlocityinc/newport-design-system

## Install Dependencies for Training
1. Download the datapack `Training` and push it to Salesforce org using Vlocity Build.
2. Upload `TrainingImages` into Salesforce Static Resource.

## Cheatsheet
1. OOTB Templates list
https://vlocity.atlassian.net/wiki/spaces/OMNI/pages/47054862/OmniScript+OOTB+Templates

2. Referencing a Static Resource in Visualforce Markup
https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_resources_reference.htm

3. Define a controller and access the dataJSON
```
vlocity.cardframework.registerModule.controller('trainingUIUXFlowCarSelectController', ['$scope', function($scope) {
    console.info($scope.bpTree.response);
}]);
```

4. Invoke DataRaptor from Vlocity Templates.
```
var className = 'vlocity_ins.DefaultDROmniScriptIntegration';
var classMethod = 'invokeOutboundDR';  
var inputMap = {"DRParams":{"Key":$scope.bpTree.response.JSONPath},"Bundle":"DRName"};
var options = '{}';
$scope.bpService.GenericInvoke(className, classMethod, angular.toJson(inputMap), options).then(function(result){
    //result from DataRaptor
});
```

5. Invoke Integration Procedure from Vlocity Templates.
```
var className = 'vlocity_ins.IntegrationProcedureService';
var classMethod = '<Type>_<SubType>';  //Type and Subtype of Integration Procedure
var inputMap = {}; // Input Data
var options = '{}';
dataService.doGenericInvoke(className, classMethod, angular.toJson(inputMap), options).then(function(result){
    //result from Integration Procedure
});
```
