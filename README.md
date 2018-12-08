# Update Pagination and Dynamic Element Size
--------

## Update the template
1. Clone ins-os-product-selection to `ins-os-training-product-selection`
2. Make sure the template renders after the user reaches the Product Selection step.
```
ng-if="... && bpTree.asIndex == control.rootIndex"
```
3. Under *** CUSTOMIZABLE VARIABLES *** section of JS, update the $scope.usePagination.
```
$scope.usePagination = $scope.bpTree.children[$scope.bpTree.asIndex].children[0].eleArray[0].propSetMap.remoteOptions.usePagination;
```
4. Also, update $scope.pageSize.
```
$scope.pageSize = $scope.bpTree.children[$scope.bpTree.asIndex].children[0].eleArray[0].propSetMap.remoteOptions.pageSize;
```
5. Define the variables on Selectable Items of OmniScript under Remote Options.
pageSize : 3
usePagination : true


