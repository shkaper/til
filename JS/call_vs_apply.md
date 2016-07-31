Q: What's the difference between `call()` and `apply()`?

A: The difference is that `apply()` passes an _array_ of arguments into the called method, while `call()` needs the arguments to be specified _explicitly_: 
```js
var argsArray = [arg1, arg2];
Obj.method.apply(context, argsArray);
``` 
vs 
```js
Obj.method.call(context, arg1, arg2);
```
