# angular-scrollable-table 1.0.1 (added footer)
Yet another table directive for AngularJS.
This one features a fixed header and footer that elegantly handles overly-long column header/footer names.

Other features:

Scroll to row
Sortable header with custom comparator functions
Resizable columns
Installation
```
git clone https://github.com/Snakelight/angular-scrollable-table-1.0.1
```
Usage
```
angular.module('myApp', ['scrollable-table', ...]);
```
Example
```
<scrollable-table watch="visibleProjects">
  <table class="table table-striped table-bordered">
    <thead>
      <tr>
         <th sortable-header col="facility">Facility</th>
         ...
      </tr>
    </thead>
    <tbody>
      <tr ng-repeat="proj in visibleProjects" row-id="{{ proj.facility }}" 
          ng-class="{info: selected == proj.facility}" >
        <td>{{ proj.facility }}</td>
        ...
      </tr>
    </tbody>
    <tfoot>
    <tr>
        <th sortable-header col="facility">Facility</th>
        ...
    </tr>
    </tfoot>
  </table>
</scrollable-table>
```
where the controller contains
```
    $scope.visibleProjects = [{
      facility: "Atlanta",
      code: "C-RD34",
      cost: 540000,
      conditionRating: 52,
      extent: 100,
      planYear: 2014
    }, ...];
    
    $scope.$watch('selected', function(fac) {
       $scope.$broadcast("rowSelected", fac);
    });
})
```
Third-party dependencies:

jQuery
Bootstrap 3 CSS (for styling, optional. See the 'bootstrap2' branch also)
Demo here: https://jsfiddle.net/onot2tuy/

More infomation here: http://blog.boxelderweb.com/2013/12/19/angularjs-fixed-header-scrollable-table/

License: MIT

FAQ
How do I change the height of the table?

See here: https://jsfiddle.net/j4sy8xs7/
