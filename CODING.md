### Coding Questions

#### Question: What is the value of `foo`?

```javascript
var foo = 10 + '20';
```

Answer: foo would be "1020" as a string. Even though 10 is a number, JavaScript knows to cocatenate '20' as a string to 10.

#### Question: How would you make this work?

```javascript
add(2, 5); // 7
add(2)(5); // 7
```

Answer: 
```javascript
function add(a, b) {
  if (b) {
    return a + b;
  } else {
    return function(b) {
      return a + b;
    }
  }
}
```

Things to think about:
 
* Do we need to handle different parameter types? What if users pass Strings? 
* Is it possible to make this scalable? How would we make the function accept an infinite number of parameters? 

#### Question: What value is returned from the following statement?

```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

Answer:
goh angasala m'i


`split("") => ["i", "'", "m", " ", "a", " ", "l", "a", "s", "a", "g", "n", "a", " ", "h", "o", "g"] `
`reverse() => ["g", "o", "h", " ", "a", "n", "g", "a", "s", "a", "l", " ", "a", " ", "m", "'", "i"]`
`join("") => "goh angasala m'i"`

#### Question: What is the value of `window.foo`?

```javascript
( window.foo || ( window.foo = "bar" ) );
```

Answer:
It depends if window.foo is a truthy value prior to running this line. If it is a truthy value, it will be what window.foo was originally assigned and will not change. Otherwise, it will run the latter and assign window.foo as the string "bar".

There are a few things that are considered "false" in JavaScript including undefined, null, 0, NaN, false, etc.

#### Question: What is the outcome of the two alerts below?

```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```
Answer:
It's important to understand closures in this question. The first alert is wrapped in a closure and so the variable bar is only scoped within that anonymous function. Variable foo on the other hand is defined globally so the anonymous function has access to it. The first alert will print "Hello World" and the second alert will fail with a ReferenceError saying it cannot find the variable bar because it thinks it was never defined.

#### Question: What is the value of `foo.length`?

```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

Answer:
It depends when foo.length is called. If we are talking about the very end, it will result in 2 because two values have been pushed into the array foo. 

#### Question: What is the value of `foo.x`?

```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

Answer:
foo.x will be undefined and foo will be assigned its new value `{n: 2}`. In JavaScript, chaining variable assignments without commas in between will run each thing line-by-line. `foo.x = foo = {n: 2}` is the same as doing

```javascript
foo.x;
foo = {n: 2};
```
Because foo has been defined, any missing or non-existing properties called will simply return undefined.
