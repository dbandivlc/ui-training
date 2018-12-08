# Vlocity UI Training
--------

For the Vlocity UI Training, please make sure you have the following.
1. Install Node JS - https://nodejs.org/en/download/
2. Install Git - https://git-scm.com/downloads
3. Install Vlocity Build (Do not clone) - https://github.com/vlocityinc/vlocity_build
4. Clone the Newport Design System - https://github.com/vlocityinc/newport-design-system

## Install Dependencies for Training
1. Download the datapack `TrainingUIFlow` and push it to Salesforce org using Vlocity Build.
2. Upload `TrainingImages` into Salesforce Static Resource.

## Cheatsheet
1. Referencing a Static Resource in Visualforce Markup
https://developer.salesforce.com/docs/atlas.en-us.pages.meta/pages/pages_resources_reference.htm

2. Define a controller and access the dataJSON
```
vlocity.cardframework.registerModule.controller('trainingUIUXFlowCarSelectController', ['$scope', function($scope) {
    console.info($scope.bpTree.response);
}]);
```

3. Invoke a DataRaptor from Angular JS.
```
$scope.bpService.GenericInvoke(className, classMethod, angular.toJson(inputMap), angular.toJson(options)).then(function(result){
    $scope.allCars = JSON.parse(result).OBDRresp.selectCar;
});
```
