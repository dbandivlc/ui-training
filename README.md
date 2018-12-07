# Exercise 2 - Apply UI/UX Design
--------

## Get Products Dynamically on Search
In the OmniScript provided, the user needs to explicitly click on `Search` button, we need to invoke the DataRaptor and get products without hitting the Search button.

1. Deactivate getCars DataRaptor.
2. Clone the template used for Step and rename it as `omniNewport-vlcTrainingStep`.
3. Add the Javascript in the JS part of the template
```
vlocity.cardframework.registerModule.controller('trainingUIUXFlowStepController', ['$scope', function($scope) {
    $scope.allCars = [];
    $scope.$watch('bpTree.response.searchCars["searchCar-Block"].CarBrandId', function(newVal) {
        if(typeof newVal != 'undefined' && newVal != null){
            var className = 'vlocity_ins.DefaultDROmniScriptIntegration';
            var classMethod = 'invokeOutboundDR';  
            var inputMap = {"DRParams":{"Key":$scope.bpTree.response.searchCars['searchCar-Block'].searchCar},"Bundle":"GetAllCars"};
            $scope.bpService.GenericInvoke(className, classMethod, angular.toJson(inputMap), '{}').then(function(result){
                //$scope.allCars = **CODE - Extract data from result**
            });
        }
    });
}]);
```
4. Link the controller into the HTML part of the template
```
 ng-controller="trainingUIUXFlowStepController"
```
5. Clone the template used for Selectable Item and rename it as `omniNewport-vlcTrainingSelectableItem`.
6. Link the controller into the HTML part of the template and update `ng-repeat`
```
 ng-controller="trainingUIUXFlowCarSelectController"
 ng-repeat='item in allCars'
```
7. Update the OOTB capability of selecting the product by adding `ng-change='onTrainingSelectItem(item)'` on input checkbox.
8. Add the Javascript in the JS part of the template
```
vlocity.cardframework.registerModule.controller('trainingUIUXFlowCarSelectController', ['$scope', function($scope) {
    $scope.onTrainingSelectItem = function(selectedCar){
        $scope.bpTree.response.searchCars.selectCar= [{
            id : ['**CODE - Find the key from to map to id**'],
            'Product Name' : ['**CODE - Find the key from to map to id**']
        }]
    }
}]);
```

To verify the functionality is working, go back to the preview of OmniScript, Search for Brand Name, you should see the Selectable Items getting populated. Select one of the product from the selectable items, the data should be passed into the dataJSON.
