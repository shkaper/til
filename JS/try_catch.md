```javascript
try {
  throw ...
} catch (e) {
  ...
}
```

Q: How do we use the information from the `throw` expression in the `catch` block?

A: The `catch` clause defines a new variable that will receive the exception object. The expression is usually an object literal containing a name property and a message property. Example:
```javascript
try {
	throw new Error("Something happened!");
} catch (e) {
	console.error(e);
}
```
or
```javascript
try {
	throw {name: "Bad stuff", message: "I have no idea what just happened"};
} catch (e) {
	console.error(e.name, e.message);
}
```
