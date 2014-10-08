---
author: rogeriolino
comments: true
date: 2013-12-12 13:57:12+00:00
layout: post
slug: angular-js-inplace-editing
title: 'Angular.js: Inplace editing'
wordpress_id: 811
categories:
- Angular.js
- HTML5
- Javascript
- Quickpost
- Tutorial
tags:
- angularjs
- demo
- inplace
- Javascript
- tutorial
---

**HTML**

    
```html    
<div class="container" ng-app="todo">
    <div ng-controller="todoCtrl">
        <form ng-submit="add()">
            <input type="text" class="form-control" placeholder="New task..." ng-model="newTodo">
            <button class="btn btn-primary">Add</button>
        </form>
        <ul>
            <li ng-repeat="todo in todos">
                <span ng-click="editing = true" ng-hide="editing">{{todo.text}}</span>
                <span ng-show="editing">
                    <input type="text" class="form-control" ng-model="todo.text" ng-blur="editing = false" ng-required>
                    <a data-ng-click="editing = false" class="glyphicon glyphicon-ok"></a>
                </span>
            </li>
        </ul>
    </div>
</div>
```


**Javascript**


```js  
var app = angular.module('todo', []);

app.controller('todoCtrl', function($scope) {

    $scope.todos = [
        {text: "First task"}
    ];

    $scope.add = function() {
        if ($scope.newTodo && $scope.newTodo != '') {
            $scope.todos.push({
                text: $scope.newTodo
            });
            $scope.newTodo = '';
        }
    }

});
```


[JSFiddle demo](http://jsfiddle.net/rogeriolino/DTF2f/)
