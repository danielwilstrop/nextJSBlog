---
title: Javascript Array Methods
date: '2021-04-11'
tags: ['javascript', 'array', 'coding']
draft: false
summary: Simple built in array methods in javascript
---

One of the first concepts I fully grasped on my coding journey with javascript was arrays and their ease of use, the posibilities with such a basic dataset are endless and I am going to go through a few of the most common built in methods to help speed up and simplify writing code. Its worth noting in the code that the parameter provided to each of these methods could eb any name of your choosing. I have used _num_ in the majority of these examples as I am working with numbers and it provided good readabiltiy to the code.

# .filter()

The **filter** method returns a new array with all the values that pass the specified callback function with value of true.

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const less5 = numbers.filter((num) => num < 5)
console.log(less5)
// [1, 2, 3, 4, 5]
```

# .map()

The **map** method again provie a new array after performing the specified callback function on each item in the array.

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const mappedNumbers = numbers.map((num) => {
  num + 10
})
console.log(mappedNumbers)
// [11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
```

# .forEach()

The **forEach** method performs the specified callback function on each item of the array. This differs from **.map()** as it mutates the original array in place, where as **.map()** returns a brand new array

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
numbers.forEach((num) => {
  console.log(num)
})
// 1
// 2
// 3
// 4 ... etc
```

# .every()

The **every** method checks thast every item in the array passes the specified callback function with a value of true. It will only return a value of _true_ or _false_.

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const allOverZero = numbers.every((num) => num > 0)
console.log(allOverZero)
// true

const allOverOne = numbers.every((num) => num > 1)
console.log(allOverZero)
// false
```

# .includes()

**Every** very simple method that returns either _true_ or _false_ if the array contians the value specified.

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const includesFive = numbers.includes(5)
console.log(includesFive)
//true
```

# .sort()

The **sort** method can arrange the contents of the array into a descending or ascending order based on the funtion provided. Plese also note my example code uses a ternary operator, another piece of ES6 syntax you can read about [Here.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)

```js
const messy = ['e', 'c', 'a', 'b', 'd']
const sorted = messy.sort((a, b) => (a > b ? -1 : 1))
console.log(sorted)
// ['a', 'b', 'c', 'd', 'e']

const descend = messy.sort((a, b) => (a > b ? 1 : -1))
console.log(descend)
// ['e', 'd', 'c', 'b', 'a']
```

# .reduce()

The most complex methoid, with many difering use cases dependign what is passed as the callback but in our example it applies a function against an accumulator to reduce the array to single value (the sum of the array).

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const sum = numbers.reduce((total, current) => {
  total + current
})
console.log(sum)
// 55
```

# .slice()

The **slice** method returns a new array with the values of the original array from the specified start and end indexes you provide. It inlcudes the indexes you have provided.

```js
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
const sliced = numbers.slice(1, 5)
console.log(sliced)
// ['2', '3', '4', '5', '6']
```

There are more methods too of course to be covered in a later article but these are the real 'bread and butter' of javascript arrya methods to make code cleaner, quicker to develop and more readable.
