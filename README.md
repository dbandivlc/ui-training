# Exercise 3 - Update Product Attribute Template
--------

## Update the Template Reference from OmniScript
1. Clone ins-coverages-os-template and rename it to `ins-coverages-os-training-template`.
2. The ins-coverages-os-training-template is actually referencing to another template which is defined in your OmniScript, under Script Configuration, update the ins-os-attribute-component to `ins-os-attribute-training-component`.
3. Clone the ins-os-attribute-component to `ins-os-attribute-training-component`.
4. This template renders the attributes that are defined for the Product. Find the component that renders `radio` and update the template to support Color and Wheels Image on the UI.
5. On change, we need to update the Car Image, hence update the `ng-click` on the input to include `updateCarImage(value.value);`
6. Define `updateCarImage` in JS part of parent template : `ins-coverages-os-training-template`
```
$scope.updateCarImage = function(color){
  $scope.carColor = color;
}
```
7. Use $scope.carColor to render the image from Static Resource.
```
<img src="../resource/TrainingImages/imgs/{{bpTree.response.searchCars['searchCar-Block'].searchCar}}_{{carColor}}.jpeg"/>
```
