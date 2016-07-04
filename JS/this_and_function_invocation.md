Q: Consider the code:
```javascript
value = 100; //note the absence of 'var'

var obj = {
    value: 3,
    double: function(){
        var helper = function(){
            this.value = this.value * 2;
        }
        helper();
    }
}
obj.double();
console.log(obj.value);
console.log(value);
```
What will be the output of the two `console.log`s and why? How to fix this behaviour without changing the functions' structure?

A: The outputs are `3` and `200` because when a function is invoked with a **function pattern**, the `helper`'s `this` is bound to the global object, not the `this` variable of the outer function `double`. 
To fix this issue, `double` can define a variable and assign it the value of `this`, thus the `helper` function will have access to `this` through that variable:
```javascript
value = 100; //note the absence of 'var'

var obj = {
    value: 3,
    double: function(){
        var that = this;
        var helper = function(){
            that.value = that.value * 2;
        }
        helper();
    }
}
obj.double();
console.log(obj.value); //6
console.log(value); //100
```
