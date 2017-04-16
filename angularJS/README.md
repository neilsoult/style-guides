# angular-style-guide

## module declaration
_Why_: for consisistent declarations across applications, and readability 
```js
// suggested
angular.module('module.name', [
    'ngRoute',
    'module.controller'
])
.config(moduleConfig);

moduleConfig.$inject = ['$routeProvider'];
function moduleConfig ($routeProvider) {
    // configuration logic
}

// avoid
angular.module('app.name')
    .controller('moduleController', function ($scope) {
        // controller logic
    });
```
