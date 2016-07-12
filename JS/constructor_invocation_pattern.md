Q: Given an original function: 
```javascript
var Foo = function (string) {
    console.log('hi');
    this.status = string;
};
Foo.prototype.get_status = function ( ) {
    return this.status;
};
```
How to create a new object so that:

1) `this` will be bound to that new object?

2) 'hi' will be logged?

What pattern of function invocation was used?

A: The __construction invocation pattern__ can be used here. `Foo()` is a constructor, and when we use the `new` prefix, a new object with a hidden link to the value of the original function’s prototype member will be created. This will also run the constructor's code.
```javascript
var bar = new Foo("fooing"); //hi
console.log(bar.get_status()); //fooing
```
