# Unit Testing Example

The example below is a unit test provided purely by the browser!

The function below is written in TypeScript. This is done so _hopefully_, a potential failure is clear
_(The function expects a number)_.

```typescript

const addsOne = (num: number) => num + 1

```

Here's an es6 or es5 version of the same method.

```javascript

// es 6
const addsOne = (num) => num + 1
// es 5
function addsOne (num) { return num + 1 }

```

Using a browser this method can be unit tested using `console.assert`.

```javascript

const addsOne = (num) => num + 1

const numPlus1 = addsOne(3)

const stringNumPlus1 = addsOne('3')

console.assert(numPlus1, 4)
console.assert(stringNumPlus1, 4)

```

The unit test above catches a problem! If the `num` argument is a string our function fails.

An engineer can now decide how to change, fix or not fix the function.
