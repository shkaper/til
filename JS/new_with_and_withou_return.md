Q: What will be logged with the below code and why?
```javascript
var Func = function(){
    this.foo = "asd";
    return {
        foo: "zxc"
    }
}
var bar = new Func();
console.log(bar.foo);
```

A: This will log "zxc". If the function was invoked with the `new` prefix and the return value is not an object, then `this` (the new object) is returned instead.
