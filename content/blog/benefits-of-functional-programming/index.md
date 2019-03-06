---
title: Benefits of Functional Programming
description: Functional programming and purity is awesome
date: '2017-05-02T16:00:00.000Z'
---

![Brick Laying](./laying_bricks.jpeg)

## You should learn _functional programming_

Exposure to functional ideas and patterns will make you a better developer. Your software will become more intuitive, easier to understand, and typically much more concise. Combining this with functional purity and immutability will also help you write fewer bugs. You’ll end up with software that is easier to understand, with infrequent bugs, and quicker to write.

### You don’t need to write in a functional language

You should learn functional patterns and practices even if your codebase is not actually written in a functional language. Most modern languages treat functions as first class citizens, so although you might not write in a functional language you can take the ideas expressed here and still apply them right away.

## Benefits

### Purity

Functional programming has no side effects. This means if you give a function the same input parameters, it will always give you the same output _no matter what_. A simple example:

```javascript
function add(a, b) {
  return a + b
}
```

The above addition function is simple but it is **pure**. No matter what you give it as parameters you will always get the same result. `add(2,2)` is always going to return 4. Lets contrast this with an **impure** function.

```javascript{3}
function add(a, b) {
  const sum = a + b
  dropProductionDatabase()
  return sum
}
```

This is **impure**. This function changes something that exists outside the scope of the function. We don't want to drop our database every time we call the add function. This is an extreme example but this gets the point across. Large software applications become hard to keep track of and mistakes can happen. Purity can make it a lot easier to keep track of your code and the changes everyone is making.

You can immediately start writing software with this concept in mind. You’ll start to see this will not only introduce fewer bugs into your code, but it can also help improve your general workflow.

### Brevity

A beautiful consequence of writing functionally is it forces you **write programs that are easier to understand**. You’re forced to write _declaratively_ which is typically a lot easier to read and comprehend than _imperatively_ written code.

_Declarative Example:_

```javascript
function square(arr) {
  return arr.map(val => val * val)
}
```

_Imperative Example:_

```javascript
function square(arr) {
  let results = []
  for (let i = 0; i < arr.length; i++) {
    results.push(arr[i] * arr[i])
  }

  return results
}
```

In the examples above we can see some obvious differences in our implementations. We are describing _how_ we should be doing something in the imperative implementation vs. _what_ we should be doing in the declarative one. This is what makes functional programming easier to read and understand.

The declarative `square` function is pretty easy to read. You’re mapping over an array and returning the square of every value. In the imperative example you’re explicitly laying out all the steps. You have to create a new return array, loop through all your values, and push a new value into your array for every value you encounter.

### Abstraction

A developer’s ability to abstract out problems into understandable parts and components is incredibly important. Not only does it allow for creating software quickly but it enables other readers to understand what was written. Future maintainers will be incredibly grateful because you’ll save them time and headaches.

Very powerful patterns also emerge from functional programming, such as <a href="https://en.wikipedia.org/wiki/Higher-order_function" target="_blank">higher-order functions</a>, which allow you to further abstract out your code. Higher-order functions, take a function as input and returns another function as a result. The `map` function is a great example.

### Comprehension

![My code is broken & I don't know why](./i-dont-know-why.jpeg)

Bug hunting is a part of every programmer’s daily life. **Mutations make bugs harder to squash**. Pure functions give you greater confidence in what your code is actually doing and prevent you from worrying about side effects you may otherwise have been unaware of. Because of this, searching for bugs becomes easier and much more straight forward. Due to the declarative style of writing, you’re programs are also shorter, which itself allows for easier comprehension.

<a href="https://redux.js.org/" target="_blank">Redux</a>, is a beautiful functional framework used to build large complicated applications. Redux itself is small. It does not consist of a lot of code — you could sit down and read through it in an afternoon. The creator of Redux even has <a href="https://egghead.io/lessons/react-redux-implementing-store-from-scratch" target="_blank">videos where he builds out the core functionality of Redux</a> in front of you in only a couple of minutes (This blog takes heavy inspiration from him). There is no “magic” in his framework. The Redux framework is simple and pure, and implementation details aren’t hidden from the programmer.

### Happiness, Confidence, & Bugs

A function will always return the same output from a given input with no exceptions. I can’t emphasize enough how powerful this removal of side-effects is for your software.

Purity removes so many bugs that are found in imperative programs. It’s arguable that _most_ bugs in large software applications can be traced back to side-effects.

Functional programming allows developers to write fewer bugs, to write less code, and to have more confidence that their programs are sound and correct. Combined, all of these result in huge improvements to not only your productivity but also your overall happiness.

### Issues

Functional programming uses up a lot of memory and you can end up in scenarios where your program would run slower than if was implemented imperatively.

For example, an imperative implementation of Quicksort is pretty fast and it can be completed in place with little extra memory footprint. However, a functional implementation of this would take up a lot more memory and run somewhat slower. So in the event where performance is vital to your program an imperative solution would be the better option. But, thanks to modern machines this is rarely an issue most people have to deal with anymore.

### Who Cares?

WhatsApp was recently bought by Facebook for **19 billion dollars**. They run all of their software off of Erlang, a functional programming language. Paul Graham’s <a href="http://www.paulgraham.com/avg.html" target="_blank">Beating the Odds</a> essay goes in depth of how the use of a functional programming language helped his startup become more successful than all their competitors. They used a language called **Lisp.**

> Lisp is worth learning for the profound enlightenment experience you will have when you finally get it; that experience will make you a better programmer for the rest of your days, even if you never actually use Lisp itself a lot.

This is meant to be a primer for anyone who may have been interested in functional programming or just wanted more information. There is a completely different and beautiful world out there and I hope this is has motivated you to go out and explore it!
