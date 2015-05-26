### JS Questions

#### Explain event delegation

Event delegation allows us to attach a single event listener to a parent element, its children, and any new children. To further explain this, we should understand event propogation.

Event propogation is the idea that there is event bubbling and event capturing. They are the inverse of each other. Event bubbling is when a user performs an event, it will start from the innermost element (deepest child) and bubble its way up and firing that event. Event capturing starts from the outermost element (greatest ancestor) and goes in, firing that event.

As of right now, event bubbling is the default for jQuery so let's start with that. Let's say you had this DOM structure

```html
<body>
  <ul>
    <li></li>
  </ul>
</body>
```

If you wanted to add an `click` event onto the `<li>`, and you clicked the `<li>`, it would fire any `click` events added to the `<li>` on the page, then bubble up to the `<ul>` and then finally to the `<body>`. 

So normally, you may add a `click` event in jQuery by doing 

`$('ul li').on('click', function(e) {
  // Click event 
})` 

which is fine, but what happens if we added more `<li>`'s? Click events are added on page load and if we have a dynamic web application like a To-Do list, it will not know to add the new click events. This is where event delegation comes in. jQuery does this for you by letting you specify the parent element and which children events should be delegated to in case new ones come in like so


`$('ul').on('click', 'li', function(e) {
  // Click event 
})` 

Another huge benefit of event delegation is lets say there were thousands of `<li>`'s in the list above. You would be adding thousands of click handlers to each `<li>`. With event delegation, it focuses only on the parent, drastically decreasing the number of event handlers.

#### Explain how `this` works in JavaScript

#### Explain how prototypal inheritance works

#### What do you think of AMD vs CommonJS?

#### Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
* What needs to be changed to properly make it an IIFE?

#### What's the difference between a variable that is: `null`, `undefined` or `undeclared`?
* How would you go about checking for any of these states?

#### What is a closure, and how/why would you use one?

#### What's a typical use case for anonymous functions?

#### How do you organize your code? (module pattern, classical inheritance?)

#### What's the difference between host objects and native objects?

#### Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?

#### What's the difference between `.call` and `.apply`?

#### Explain `Function.prototype.bind`.

#### When would you use `document.write()`?

#### What's the difference between feature detection, feature inference, and using the UA string?

#### Explain AJAX in as much detail as possible.

#### Explain how JSONP works (and how it's not really AJAX).

#### Have you ever used JavaScript templating?
* If so, what libraries have you used?

#### Explain "hoisting".

#### Describe event bubbling.

#### What's the difference between an "attribute" and a "property"?

#### Why is extending built-in JavaScript objects not a good idea?

#### Difference between document load event and document ready event?

#### What is the difference between `==` and `===`?

#### Explain the same-origin policy with regards to JavaScript.

Make this work:

```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
#### Why is it called a Ternary expression, what does the word "Ternary" indicate?

#### What is `"use strict";`? what are the advantages and disadvantages to using it?

#### Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, `"buzz"` at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`

#### Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?

#### Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?

#### Explain what a single page app is and how to make one SEO-friendly.

#### What is the extent of your experience with Promises and/or their polyfills?

#### What are the pros and cons of using Promises instead of callbacks?

#### What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?

#### What tools and techniques do you use debugging Javascript code?

#### What language constructions do you use for iterating over object properties and array items?
