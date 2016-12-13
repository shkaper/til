Q: What's the difference between 
```js
import { A } from './A'
``` 
and 
```js
import A from './A'
```
?

A: The former is a __named import__, the latter is a __default import__.

Named import only works if `./A` contains a named export called `A`:
```js
export const A = 'something'
```

Default import only works if `./A` contains a default export:
```js
export default 'something'
```
