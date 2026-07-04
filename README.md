
# Module 1: Execution Context, Hoisting & Scope

## Theory Questions
what is javascript?
1. Definition-
JavaScrip is a high-level, interpreted, and single-threaded programming language.
2. Main Purpose-
It is used to create interactive and dynamic web applications.
3. Where It Runs-
Earlier, it was used only in browsers, but now with Node.js, it can also run on the server side.
4. Features-
It supports object-oriented, functional, and event-driven programming.
5. Real Project Usage-
In projects, I have used it for DOM manipulation, API calls, asynchronous programming, and performance optimization.
-High level-easy for humans to read, write, and understand.
-interpreter-code is executed line by line by a program
-single threaded-xecutes one task at a time.
-----------------------------------------------------------------------------------------------
🔥 followup question:
If JavaScript is single-threaded, how does it handle asynchronous tasks?

"JavaScript is single-threaded, which means it executes one task at a time using a single call stack.

However, for asynchronous operations like API calls, timers, and DOM events, JavaScript uses Web APIs provided by the browser or APIs provided by Node.js.

When an async operation starts, JavaScript sends that task to these APIs and continues executing the remaining code without waiting.

Once the async task is completed, its callback is placed into the Callback Queue or Microtask Queue.

The Event Loop continuously checks whether the Call Stack is empty. If it is empty, the Event Loop moves the callback from the queue to the Call Stack for execution.

So, JavaScript remains single-threaded, but with the help of Web APIs and the Event Loop, it can handle asynchronous tasks efficiently without blocking the application.
-------------------------------------------------------------------------------------------------
```
💻 Example
console.log("Start");

setTimeout(() => {
    console.log("Hello");
}, 2000);

console.log("End");
Output
Start
End
Hello

```
🔥 Follow-up Question
Why do Promises execute before setTimeout?

Example:

console.log(1);

setTimeout(() => console.log(2), 0);

Promise.resolve().then(() => console.log(3));

console.log(4);

Output:

1
4
3
2
Reason:
Promise callbacks go to the Microtask Queue.
setTimeout callbacks go to the Callback (Macrotask) Queue.
The Event Loop always executes Microtasks before Macrotasks.
The Event Loop always gives higher priority to the Microtask Queue. It first executes all microtasks and only then processes the macrotasks.  
So, even if setTimeout has a delay of 0 milliseconds, the Promise callback runs first."

-------------------------------------------------------------------------------------
1. What is JavaScript Execution Context?  

"Execution Context is the environment where JavaScript code is executed. It contains all the information needed to run the code, such as variables, functions, and the value of this.

Whenever a JavaScript program starts or a function is called, JavaScript creates a new execution context for it.

Each execution context goes through two phases: the Creation Phase and the Execution Phase.

During the Creation Phase, memory is allocated for variables and functions, and the this keyword is initialized.

During the Execution Phase, the code runs line by line, and values are assigned to variables and functions are executed.

There are mainly two types of execution contexts: Global Execution Context and Function Execution Context."

-------------------------------------------------------------------------------
🔥 Types of Execution Context
1. Global Execution Context (GEC)
Created when the program starts.
Created only once.
this points to window in browsers.
In the Global Execution Context, this points to the window object.
this === window   // true
Example:

var a = 10;

This runs inside the Global Execution Context.

2. Function Execution Context (FEC)
Created whenever a function is called.
Every function call gets its own execution context.

Example:

function test() {
    console.log("Hello");
}

test();

Calling test() creates a new Function Execution Context.

----------------------------------------------------------------------------------------
2. Explain Global Execution Context and Function Execution Context.



3. What happens during the Creation Phase and Execution Phase?
4. What is Hoisting?
5. Difference between `var`, `let`, and `const`?
6. What is Temporal Dead Zone (TDZ)?
7. What is Lexical Scope?
8. Explain Scope Chain.
9. What is Block Scope?
10. What is Function Scope?

## Practical Questions

1. Predict the output:

```javascript
console.log(a);
var a = 10;
```

2.

```javascript
console.log(a);
let a = 10;
```

3.

```javascript
function test() {
    console.log(x);
    var x = 20;
}
test();
```

4.

```javascript
for(var i=0;i<3;i++){
    setTimeout(()=>console.log(i),1000);
}
```

5.

```javascript
for(let i=0;i<3;i++){
    setTimeout(()=>console.log(i),1000);
}
```

---

# Module 2: Closures (VERY IMPORTANT)

## Theory Questions

1. What is a Closure?
2. How does Closure work internally?
3. Real-world use cases of Closures?
4. How is data hiding achieved using Closures?
5. What are advantages and disadvantages of Closures?
6. Can Closures cause memory leaks?

## Practical Questions

1. Counter using Closure

```javascript
function counter(){
    let count=0;

    return function(){
        return ++count;
    }
}
```

2. Create private variables using Closure.

3. Implement Memoization.

4. Fix the `setTimeout` loop problem.

5. Implement Debounce using Closure.

---

# Module 3: this, call, apply, bind

## Theory Questions

1. What is `this` in JavaScript?
2. How does `this` work in Global Scope?
3. How does `this` work inside Object Methods?
4. Arrow function vs Normal Function (`this`)?
5. Difference between `call`, `apply`, and `bind`?
6. When do you use `bind` in real projects?

## Practical Questions

1.

```javascript
const user={
    name:"John",
    show(){
        console.log(this.name);
    }
}
```

2.

```javascript
function greet(city){
    console.log(this.name,city);
}
```

Implement using:

* call
* apply
* bind

3. Polyfill for bind.

---

# Module 4: Prototypes & Inheritance

## Theory Questions

1. What is Prototype?
2. Difference between `prototype` and `__proto__`?
3. Explain Prototype Chain.
4. How does inheritance work in JavaScript?
5. Class vs Prototype-based inheritance?

## Practical Questions

1.

```javascript
function Person(name){
    this.name=name;
}

Person.prototype.greet=function(){
    console.log(this.name);
}
```

Explain internal working.

2. Create inheritance manually.

---

# Module 5: Promises

## Theory Questions

1. What is Promise?
2. Promise states?
3. Why were Promises introduced?
4. Promise Chaining?
5. Error handling in Promises?
6. Promise vs Callback?
7. Promise vs Async/Await?

## Practical Questions

1. Create your own Promise.

2.

```javascript
Promise.resolve(10)
.then(x=>x+10)
.then(console.log)
```

3.

```javascript
Promise.all()
Promise.race()
Promise.any()
Promise.allSettled()
```

Implement examples.

4. Polyfill for Promise.all (important for product companies).

---

# Module 6: Async/Await & Event Loop (MOST IMPORTANT)

## Theory Questions

1. What is Event Loop?
2. Explain Call Stack.
3. What is Callback Queue?
4. What is Microtask Queue?
5. Why do Promises execute before `setTimeout`?
6. How does Async/Await work internally?
7. Is Async/Await blocking or non-blocking?

## Practical Questions

1.

```javascript
console.log("1");

setTimeout(()=>{
    console.log("2");
});

Promise.resolve().then(()=>{
    console.log("3");
});

console.log("4");
```

2.

```javascript
async function test(){
    console.log(1);

    await Promise.resolve();

    console.log(2);
}
```

3. Fetch multiple APIs:

* Sequential execution
* Parallel execution

---

# Module 7: Debounce & Throttle

## Theory Questions

1. What is Debounce?
2. Why do we use Debounce?
3. Real-world use cases?
4. What is Throttle?
5. Difference between Debounce and Throttle?

## Practical Questions

1. Implement Debounce.

2. Implement Throttle.

3. Search input optimization.

---

# Module 8: ES6+ Features

## Theory Questions

1. Destructuring
2. Rest Operator
3. Spread Operator
4. Optional Chaining
5. Nullish Coalescing
6. Template Literals
7. Arrow Functions
8. Modules (`import/export`)

## Practical Questions

1. Merge arrays using spread.

2. Clone objects.

3. Nested destructuring.

4. Implement custom modules.

---

# Module 9: Arrays (VERY IMPORTANT)

## Theory Questions

1. Difference between `map` and `forEach`?
2. Filter vs Find?
3. Reduce internal working?
4. Some vs Every?
5. Flat vs FlatMap?

## Practical Questions

Implement manually:

1. Polyfill for map
2. Polyfill for filter
3. Polyfill for reduce
4. Group By problem
5. Remove duplicates
6. Flatten nested arrays

---

# Module 10: Objects

## Theory Questions

1. Deep Copy vs Shallow Copy
2. Object.assign vs Spread
3. Object.freeze vs seal
4. Enumerability
5. Object.keys, values, entries

## Practical Questions

1. Deep Clone object.

2.

```javascript
JSON.parse(JSON.stringify(obj))
```

limitations?

3. Flatten nested objects.

---

# Module 11: Browser & DOM

## Theory Questions

1. Event Bubbling
2. Event Capturing
3. Event Delegation
4. LocalStorage vs SessionStorage
5. Cookies vs LocalStorage
6. Reflow vs Repaint
7. Critical Rendering Path

## Practical Questions

1. Event delegation example.

2. Dynamic table creation.

3. Infinite scrolling.

---

# Module 12: Performance Optimization

## Theory Questions

1. Memory Leaks in JavaScript
2. Garbage Collection
3. Debounce vs Throttle
4. Lazy Loading
5. Code Splitting
6. Web Workers

---

# Module 13: Security

## Theory Questions

1. What is CORS?
2. What is XSS?
3. What is CSRF?
4. Same-Origin Policy?
5. Content Security Policy?

---

# Module 14: Advanced JavaScript (Product Companies)

## Theory Questions

1. Currying
2. Memoization
3. Pure Functions
4. Higher Order Functions
5. Functional Programming
6. Generators
7. Iterators
8. Symbol
9. WeakMap vs Map
10. WeakSet vs Set

## Practical Questions

1. Implement Curry Function.

2. Implement Memoization.

3. Implement Once Function.

4. Implement Pipe Function.

5. Implement Compose Function.

---

# Most Important Topics (Must Master Before Interview)

If you have only 30 days, focus on these first:

1. Hoisting
2. Scope & Closures
3. `this`
4. Call/Apply/Bind
5. Prototypes
6. Promises
7. Async/Await
8. Event Loop
9. Debounce & Throttle
10. Array Methods
11. Deep vs Shallow Copy
12. Event Delegation
13. CORS
14. Memory Leaks
15. ES6 Features

Master these properly, and you'll be well prepared for most **service-based and product-based company interviews** for a 4+ years JavaScript role.
