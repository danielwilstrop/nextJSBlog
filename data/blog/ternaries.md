---
title: Ternary Operators in Javascript
date: '2021-05-10'
tags: ['coding', 'javascript', 'ES6']
draft: false
summary: Super simple and condensed method for true/false conditionals
---

## Ternary Operators

Before this amazing bit of syntax was relases with ES6 checking a simple true or false value, and then acting upon it, may have looked a little soemthiung like this.

```js
if (some - condition) {
  //do some cool stuff
} else {
  // do some other cool stuff
}
```

With a ternary operator this can be on one line and look like this.

```js
condition ? doIfTrue : doIfFalse
```

So what exactly is going on here and why is it so great? The readbility of a ternary operator and the ease of one-line code is fantastic. The syntax is _condition_ ? _expression if true_ : _expression if false_ . It really is that simple. If the condition returns as a truthy value the first expression will be executed, if it returns falsy the second condtion will be executed. A working example may look a little like this.

```js
const greeting = (name) => {
  return name ? `Hello ${name}` : 'Hello Stranger'
}

console.log(greeting('Dan'))
// Hello Dan

console.log(greeting())
//Hello Stranger
```

In this function we are checking if the parameter has been passed. If it has it will be a truthy value and returns a perosnalised greeting, if there is no parameter passed it will be _null_, a falsy value and the function will return the 'Hello Stranger' string instead. Simple and effective stuff.

Like an if/else statement a ternary can also be nested within another ternary, this is just as simple and requires adding another conditonal in place of the expression as demonstrated here.

```js
const number = (num) => {
  return num > 10
    ? num > 20
      ? 'Your number is over 20'
      : 'your number is between 10 and 20'
    : 'Your number is less than 10'
}

console.log(number(12))
// 'your number is between 10 and 20'
```

Away from pure javascript a ternary is a really great way of checking state and altering the UI for the user based on that data when using a framwork such as React. For example, if you had a user authentication system and wanted to change the display based on wether the user was logged in you can easily accomplish this with ternary operatiors. The example below checks if the variable _isLoggedIn_ is true and if so dsiplays a 'Log-Out' button, otherwise it would display a 'Log-In' button if placed within the correct place in the JSX code.

```js
{
  isLoggedIn ? <LogOutButton /> : <LogInButton />
}
```

As you can see ternaries are useful, flexible, adaptable, easily readbale and a great addition to javascript in ES6.
