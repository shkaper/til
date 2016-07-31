Q: How to invoke a method of an object on another object that neither has this method nor shares the first object's prototype?

A: One simple way is to use the `apply` method. 
For example, to iterate over the `arguments` object of a function we cannot use the `Array.prototype.forEach()` method out of the box (since `arguments` is not an instance of _Array_ but is rather an _Array-like object_) but it becomes an easy task with the use of `apply`:
```javascript
var printByLine = function(){
  Array.prototype.forEach.apply(arguments,[function(item){
      console.log(item);
  }]);
}
printByLine("1", "two", 3); 
//1
//two
//3
```
This method is called the **Apply Invocation Pattern**. The `apply` method takes two parameters. The first is the value that should be bound to `this`. The second is an array of parameters.
`apply()` can be replaced with `call()` in this case like that:
```javascript
...
Array.prototype.forEach.call(arguments,function(item){
 ...
})
...
```
The difference is that `apply()` passes an _array_ of arguments into the called method, while `call()` needs the arguments to be specified _explicitly_.
