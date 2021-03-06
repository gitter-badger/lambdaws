# Lambdaws

(todo: add Travis CI)

Lambdaws makes it trivial to build highly scalable, high availability applications. Built on top of AWS Lambda.

## Installation

```npm install lambdaws```

## Usage

```lambdaws.fromPromise``` takes an async function returning a promise and deploys it to AWS Lambda. If you call cloudedFunction it will be runned in the cloud.

```
var lambdaws = require('lambdaws');

var normalAsyncFunction = function() {/* returns promise */};

var cloudedFunction = lambdaws.fromPromise(normalAsyncFunction);

cloudedFunction.then(function(data) { console.log(data); });

```

```lambdaws.fromCallback``` takes a function accepting a callback and deploys it to AWS Lambda. If you call cloudedFunction it will be runned in the cloud.

```
var lambdaws = require('lambdaws');

var normalFunction = function(args, callback) {...};

var cloudedFunction = lambdaws.fromCallback(normalFunction);

cloudedFunction(args, function(data) {
	console.log(data);
});

```

