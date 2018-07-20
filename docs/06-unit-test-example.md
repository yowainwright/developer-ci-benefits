# Unit Testing Example

The example below is a unit test provided purely by the browser!

The function below is written in TypeScript initially. This is done so _hopefully_, a potential failure is clear
_(The function expects a number)_. TypeScript help define a code's interface.
 After writing the code below in TypeScript, a text editor can be configured to quickly communicate to a developer if it is working as expected.

```typescript

const addsOne = (num: number) => num + 1

```

Here's an es6 or es5 version of the same method.
This code (below) is what the TypeScript above will be compiled into.

```javascript

// es 6
const addsOne = (num) => num + 1
// es 5
function addsOne (num) { return num + 1 }

```

Using a browser this method can be unit tested using `console.assert`. Read more about [console.assert](https://developer.mozilla.org/en-US/docs/Web/API/console/assert).

```javascript

const addsOne = (num) => num + 1

const numPlus1 = addsOne(3)

const stringNumPlus1 = addsOne('3')

console.assert(numPlus1, 4)
console.assert(stringNumPlus1, 4)

```

The unit test above catches a problem! If the `num` argument is a string the function fails.

An engineer can now decide how to change, fix or not fix the function.

----

## An for advanced users

`Console.assert` was used to display how unit testing can be done without any libraries.
However, frameworks like [Jest](https://jestjs.io/) are often used to describe how code that will be compiled for production should function. This important to not because tests can run within your editor as you code using [Quokka](https://quokkajs.com/). Quokka can test code as it is written, log code via comment asserts, and communicate code that is tests—or untested.
