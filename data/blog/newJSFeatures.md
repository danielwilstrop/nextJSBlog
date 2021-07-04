---
title: Modern JS Features
date: '2021-06-15'
tags: ['javascript', 'coding', 'Tips']
draft: false
summary: A quick guide to some of the newwer JS syntax and operators
---

### Modern JS Features

# Spread Operator ( ... )

The spread operator works by merging arrays, and more recently objects, together or apart to simplify this common necessity.

For an an array the example below shows us how we can use **...** to spread the contents of one array and join it to another.

```js
const arr1 = [1, 2, 3]
const arr2 = [4, 5, 6]

const spreadArray = [...arr1, ...arr2]

console.log(spreadArray)
//  [1, 2, 3, 4, 5, 6 ]
```

We could also use this same feature to add another item to an array like in the below example.

```js
const arr1 = [1, 2, 3]
const value = 4

const spreadArray = [...arr1, value]

console.log(spreadArray)
//  [1, 2, 3, 4 ]
```

The spread operator also works, since ES2018, with objects which opens up many posibilities with your code. We can use the same princples as above to add a key/value to objects as below.

```js
const obj = {
  x: 1,
  y: 2,
  z: 3,
}

const obj2 = {
  a: 4,
}

const spreadObj = { ...obj, ...obj2 }

console.log(spreadObj)
//{ x: 1, y: 2, z: 3, a: 4 }
```

The most useful feature of this operator is destruturing a value from an object such as demonstrated below.

```js
const obj = {
  x: 1,
  y: 2,
  z: 3,
}

const { x, ...b } = obj

console.log(x)
// 1

console.log(b)
// { y:2, z:3 }
```

# The flat method

By using **.flat()** we can 'flatten' arrays to remove any nested arrays within then, which previously could only be done iwht third party libraries, .concat(), or custom functions involving loops.

```js
const array = [1, 2, [3, 4, 5], 6, [7, 8], [9, 10]]
const flattened = array.flat()

console.log(flattened)
//[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

# The Finally Method

The new **.finally()** method allows us to perform an action after an returning a promise regardless of the outcome of the promise. In normal circumstances we would, for example, call a fetch request and process it if successful by chaining **.then()** statements. At the end of these blocks we would use a **.catch()** to catch and process any errors should the promise be unresolved. Only one of these blocks would be called. With the new **.finally()** method we can chain this to the end of our async functions and the code will automaticlaly be run regardless of wether of not the promise resolves or rejects.

```js
fetch('www.madeup.com')
  .then((res) => res.json())
  .catch((error) => console.log(error))
  .finally(() => console.log('This code will always run'))

// Will console log 'This code will always run' regardless of the promsie status
```

# Optional Chaining

Optional chaining quite simply, is remarkable. It was introduced in ES2019 and it allows you to check the properties of objects and data exist and if so you can use them, if not the code wont fail it will simply move on. These checks could be done previously with lists os && statements but the readability of optional chanining makes this much much simpler. When accessing data using the **dot operator .** we can add a **?** before the dot which will check first is the propery exists. The below example shows the same process restructured using this handy new feature.

```js
// Old Method
let userInfo = undefined
if (user && user.name && user.name.access && user.name.access[1]) {
  userInfo = user.name.access[1]
}

//Optional Chaining
const userInfo = user?.name?.access?.access[1]
```

# Double Bangs !!

The last method on the list isnt new but its a useful trick to know if you need to return a true boolean value. JS treats the following as falsy values...

- 0 / -0
- 0n
- '' - _empty string_
- null
- undefined
- NaN = _not a number_
- false

Sometimes you need a boolean vlaue that is either true or false when your project may return undefined to start with, this can happen with state management in React (for example).

We know that the **!** operator returns the opposite of its input. For example `!false = true`

By manipulating this we can also use the **!** operator to return true from any of the above falsy list as so `!undefined = true`

Now we know this, what would happen if we were to add another **!** creating a **!! _double-bang_**?

We are now saying we want the opposite of the opposite as so `!!true = true`

By doing this with a flasy value we can convert that to a boolean of **true** and then immediately ask for the opposite, thus converting a flasy value into the true boolean **false**

```js
!null = true
!!null = false

!false = true
!!false = false
```
