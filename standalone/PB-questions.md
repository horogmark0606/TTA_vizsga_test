# Programming Basics — interview question rubrics

> Questions come from the module's Tech Interview Workbook (students already
> have them). Rubrics are for the agent only: compare silently, never show
> them, never turn them into a model answer. See the agent instructions.
> Which projects practise each question: `PB-index.md`.
>
> Status: **draft, mentor review pending.**

---

## Data Basics

### PB-DATA-01
**Question:** What are the differences between objects, arrays, and primitives in JavaScript? How are they used in programming?

**A good answer covers**
- primitives: a single, simple value (number, string, boolean, …)
- arrays: an ordered list, accessed by numeric index
- objects: a collection of named properties (key → value)
- arrays and objects are reference types and can hold other values (even each other)
- an example of a typical use for each

**Common misconceptions**
- "Arrays are not objects" (they are a special kind of object)

**Interviewer follow-ups**
- "How would you store a list of students, each with a name and age?"

**Verify at:** MDN, "JavaScript data types and data structures"

### PB-DATA-02
**Question:** How would you access the value of a specific key in an object?

**A good answer covers**
- dot notation: `obj.key`
- bracket notation: `obj["key"]`
- bracket notation is needed when the key is in a variable or isn't a valid identifier
- accessing a missing key gives `undefined`, not an error

**Common misconceptions**
- `obj.keyName` works when `keyName` is a variable holding the key

**Interviewer follow-ups**
- "The key name comes from user input. How do you read it?"

**Verify at:** MDN, "Property accessors"

### PB-DATA-03
**Question:** Explain the concept of key-value pairs in objects and how they differ from indexed elements in arrays.

**A good answer covers**
- object: each value is reached by a meaningful name (key)
- array: each value is reached by its position (index from 0)
- array order matters and is used; object keys describe meaning
- choosing between them depends on whether you look things up by name or by position

**Common misconceptions**
- "Object keys can be any type" (they are strings or symbols)

**Interviewer follow-ups**
- "How would you count how many times each word appears in a text? Which structure?"

**Verify at:** MDN, "Working with objects", "Indexed collections"

### PB-DATA-04
**Question:** Describe a scenario where you would choose to use an object instead of an array, or vice versa, and explain your reasoning.

**A good answer covers**
- a concrete scenario for an object (one thing with named properties, or lookup by key)
- a concrete scenario for an array (many similar items, order, iteration)
- the reasoning, not just the choice
- bonus: array of objects as a combination

**Common misconceptions**
- picking based on habit with no reasoning

**Interviewer follow-ups**
- "Which did you use in one of your projects, and would you choose differently now?"

**Verify at:** MDN, "Working with objects"

### PB-DATA-05
**Question:** How can you retrieve the first and last items of an array?

**A good answer covers**
- first: index `0`
- last: index `length - 1`
- (modern) `at(-1)`
- `pop()` / `shift()` also return them **but remove them** from the array

**Common misconceptions**
- `arr[arr.length]` is the last item

**Interviewer follow-ups**
- "What do you get for an empty array?"

**Verify at:** MDN, `Array.prototype.at()`, `length`

### PB-DATA-06
**Question:** Identify the five most commonly used primitive types in JavaScript, and provide examples demonstrating when and how to use them?

**A good answer covers**
- number, string, boolean, undefined, null (also: bigint, symbol exist)
- an example use case for each
- `typeof` to check the type

**Common misconceptions**
- "Arrays / objects are primitives"
- "`typeof null` is `'null'`" (it is `'object'`, a historical quirk)

**Interviewer follow-ups**
- "What's the difference between `undefined` and `null` in practice?"

**Verify at:** MDN, "Primitive" (Glossary), `typeof`

---

## Algorithm Basics

### PB-ALG-01
**Question:** Provide examples of assignment operators in JavaScript.

**A good answer covers**
- `=`
- compound: `+=`, `-=`, `*=`, `/=`, `%=`
- increment / decrement `++`, `--` (closely related)
- assignment is not comparison

**Common misconceptions**
- confusing `=` with `==` / `===`

**Interviewer follow-ups**
- "What does `x += 1` do when `x` is a string?"

**Verify at:** MDN, "Assignment operators"

### PB-ALG-02
**Question:** Name some of the arithmetic operators in JavaScript.

**A good answer covers**
- `+ - * /`
- `%` (remainder) and a use case (even/odd)
- `**` (exponent)
- `+` also concatenates strings

**Common misconceptions**
- `%` is "percent"

**Interviewer follow-ups**
- "What is `'5' + 3`? And `'5' - 3`? Why?"

**Verify at:** MDN, "Arithmetic operators"

### PB-ALG-03
**Question:** What are the different comparison operators in JavaScript?

**A good answer covers**
- `===` / `!==` strict (no type conversion)
- `==` / `!=` loose (type conversion), and why `===` is preferred
- `<`, `>`, `<=`, `>=`
- comparison returns a boolean

**Common misconceptions**
- `==` and `===` are the same
- objects/arrays are compared by content (they are compared by reference)

**Interviewer follow-ups**
- "What is `0 == ''`? And `0 === ''`?"

**Verify at:** MDN, "Equality comparisons and sameness"

### PB-ALG-04
**Question:** Name a few logical operators used in JavaScript.

**A good answer covers**
- `&&`, `||`, `!`
- what each returns / when it is true
- short-circuiting (the right side may not run)
- bonus: `??`

**Common misconceptions**
- `&&` / `||` always return a boolean (they return one of the operands)

**Interviewer follow-ups**
- "How would you check that a number is between 1 and 9?"

**Verify at:** MDN, "Logical AND (&&)", "Logical OR (||)"

### PB-ALG-05
**Question:** Explain the differences between a `for` loop, `for of` loop, and `for in` loop in JavaScript.

**A good answer covers**
- classic `for`: explicit counter, start / condition / step; full control (skip, go backwards, use the index)
- `for...of`: iterates over the *values* of an iterable (array, string)
- `for...in`: iterates over the *keys* (property names) of an object
- `for...in` on an array gives index strings, so it isn't the usual choice for arrays
- when to choose which one

**Common misconceptions**
- "`for...in` and `for...of` are the same thing"
- "`for...of` works on plain objects"

**Interviewer follow-ups**
- "You need both the index and the value. Which loop, and how?"
- "How would you loop over an object's values?"

**Verify at:** MDN, `for...of`, `for...in`

### PB-ALG-06
**Question:** If you can't use any built-in functions or methods, how would you calculate the average of values in an array?

**A good answer covers**
- a running sum in a loop
- divide by the number of items
- handles the empty array (division by zero → `NaN`)
- can explain it step by step on a small example

**Common misconceptions**
- starting the sum from `undefined` instead of `0`

**Interviewer follow-ups**
- "What does your code return for `[]`? What should it return?"

**Verify at:** (no single source; check by running it)

---

## Function Basics

### PB-FN-01
**Question:** What is a function in JavaScript? Explain its purpose and how it is used in programming.

**A good answer covers**
- a named, reusable block of code
- takes input (parameters), can give back output (`return`)
- reasons: reuse, readability, splitting a problem into parts, testability
- defining vs. calling

**Common misconceptions**
- "a function must return something"

**Interviewer follow-ups**
- "Show me a function from your project. Why is it a function and not inline code?"

**Verify at:** MDN, "Functions" (Guide)

### PB-FN-02
**Question:** Describe the different syntax elements that make up a JavaScript function.

**A good answer covers**
- `function` keyword (or arrow syntax), name
- parameter list in parentheses
- body in curly braces
- `return` statement (optional)

**Common misconceptions**
- the name is required for every function (anonymous functions exist)

**Interviewer follow-ups**
- "Write the same function as a declaration and as an arrow function."

**Verify at:** MDN, "function declaration", "Arrow function expressions"

### PB-FN-03
**Question:** How do you pass arguments to a function? Explain the concept of parameter passing and provide an example.

**A good answer covers**
- parameters in the definition, arguments in the call
- arguments are matched by position
- missing argument → parameter is `undefined`; default parameters
- primitives: the value is copied; objects/arrays: the *reference* is copied, so mutating them inside is visible outside, but reassigning the parameter is not

**Common misconceptions**
- "parameter" and "argument" are the same word

**Interviewer follow-ups**
- "You pass an array to a function that pushes into it. What happens to the original?"

**Verify at:** MDN, "Functions" (Guide), "Default parameters"

### PB-FN-04
**Question:** What is the difference between function expressions and function declarations? Provide examples of each.

**A good answer covers**
- declaration: `function name() {}` as a statement
- expression: a function assigned to a variable (`const f = function () {}` or arrow)
- declarations are hoisted (callable before the line); expressions are not
- when to prefer one or the other

**Common misconceptions**
- "arrow functions are the same as declarations"

**Interviewer follow-ups**
- "Can you call a function before the line it is defined on? It depends — on what?"

**Verify at:** MDN, "function expression", "Hoisting" (Glossary)

### PB-FN-05
**Question:** Explain what a callback function is in JavaScript.

**A good answer covers**
- a function passed as an argument to another function
- the receiving function decides *when* (and whether) to call it
- functions are values in JS, which is what makes this possible
- at least one concrete example (`forEach` / `map` / `filter`, event listener, `setTimeout`)

**Common misconceptions**
- "Callbacks are always asynchronous" (`map` calls it synchronously)
- writing `fn()` instead of `fn` when passing it

**Interviewer follow-ups**
- "What's the difference between passing `sayHi` and passing `sayHi()`?"
- "Write a function that takes a callback and calls it twice."

**Verify at:** MDN Glossary, "Callback function"

### PB-FN-06
**Question:** What is the scope of variables in JavaScript functions? Explain the difference between local and global variables.

**A good answer covers**
- scope = where a variable is visible
- local (function / block) vs. global
- `let` / `const` are block-scoped
- inner functions can see outer variables, not the other way around
- why many globals cause problems

**Common misconceptions**
- a variable declared inside an `if` with `let` is visible after the `if`

**Interviewer follow-ups**
- "Two functions both declare `count`. Do they affect each other?"

**Verify at:** MDN, "Scope" (Glossary)

---

## Built-in Features

### PB-BUILTIN-01
**Question:** What are some commonly used built-in functions or methods in JavaScript for working with strings? Provide examples and explain their usage.

**A good answer covers**
- at least 4–5 methods with purpose (e.g. `toLowerCase`, `includes`, `indexOf`, `slice`, `split`, `trim`, `replace`, `startsWith`)
- string methods return a new string; the original never changes
- an example from their own code

**Common misconceptions**
- `str.toUpperCase()` changes `str`

**Interviewer follow-ups**
- "How would you check whether a word is a palindrome?"

**Verify at:** MDN, "String"

### PB-BUILTIN-02
**Question:** Name at least five built-in functions or methods in JavaScript for manipulating arrays. Describe how each function/method works and provide an example for each.

**A good answer covers**
- at least five, with purpose (e.g. `push`, `pop`, `slice`, `splice`, `indexOf`, `includes`, `map`, `filter`, `reduce`, `find`, `sort`)
- which ones change the array (`push`, `pop`, `splice`, `sort`) and which return something new (`slice`, `map`, `filter`)
- an example for each

**Common misconceptions**
- `slice` and `splice` do the same thing
- `map` changes the original array

**Interviewer follow-ups**
- "Which of these change the original array?"

**Verify at:** MDN, "Array"

### PB-BUILTIN-03
**Question:** How can you use built-in functions or methods in JavaScript to perform mathematical operations? Give examples of commonly used functions or methods for mathematical calculations.

**A good answer covers**
- the `Math` object
- e.g. `Math.round`, `floor`, `ceil`, `max`, `min`, `abs`, `pow`, `sqrt`
- `Math.random()` and how to get a random integer in a range

**Common misconceptions**
- `Math.random()` can return 1

**Interviewer follow-ups**
- "Give me a random index for an array of length 5."

**Verify at:** MDN, "Math"

### PB-BUILTIN-04
**Question:** What are some built-in functions or methods in JavaScript for manipulating numbers? Describe their functionality and give examples of how they can be used.

**A good answer covers**
- converting: `Number()`, `parseInt`, `parseFloat`
- checking: `Number.isNaN`, `Number.isInteger`
- formatting: `toFixed`
- difference between `Number('12px')` and `parseInt('12px')`

**Common misconceptions**
- `toFixed` returns a number (it returns a string)

**Interviewer follow-ups**
- "How do you check that user input is a valid whole number?"

**Verify at:** MDN, "Number"

### PB-BUILTIN-05
**Question:** Discuss the differences between `for` loops and the `forEach` method in JavaScript.

**A good answer covers**
- `forEach` is an array method that takes a callback
- `for` gives control over start, step, and stopping early
- `break` / early `return` don't stop `forEach`
- readability trade-off

**Common misconceptions**
- `forEach` returns a new array

**Interviewer follow-ups**
- "You want to stop at the first negative number. Which do you use?"

**Verify at:** MDN, `Array.prototype.forEach()`

---

## File Basics

### PB-FILE-01
**Question:** What distinguishes JavaScript data structures from JSON data structures?

**A good answer covers**
- JSON is a text format; a JS object is a value in memory
- JSON rules: double-quoted keys and strings, no functions, no `undefined`, no comments
- `JSON.stringify` / `JSON.parse` convert between them

**Common misconceptions**
- "JSON is a JavaScript object"

**Interviewer follow-ups**
- "What happens to a function property when you stringify an object?"

**Verify at:** MDN, "JSON"

### PB-FILE-02
**Question:** How would you create a JavaScript data structure from the data in a JSON file?

**A good answer covers**
- read the file content as text
- `JSON.parse` turns the text into a JS value
- (Node) reading a file, or importing / requiring JSON
- invalid JSON throws an error

**Common misconceptions**
- reading the file already gives an object

**Interviewer follow-ups**
- "What happens if the file contains a trailing comma?"

**Verify at:** MDN, `JSON.parse()`; Node.js docs, `fs.readFileSync`

---

## View Basics

### PB-VIEW-01
**Question:** Explain the difference between JavaScript object data structure and DOM data structure.

**A good answer covers**
- a JS object is your own data in memory
- the DOM is the browser's tree representation of the page
- DOM nodes are objects too, but changing them changes what is shown
- typical flow: data (JS) → render → DOM

**Common misconceptions**
- "the DOM is the HTML file"

**Interviewer follow-ups**
- "Where did you keep your data in a DOM project: in JS or in the page?"

**Verify at:** MDN, "Introduction to the DOM"

### PB-VIEW-02
**Question:** What are the necessary steps to change the content of an HTML element using JavaScript?

**A good answer covers**
- select the element (`querySelector`, `getElementById`)
- change it (`textContent`, `innerHTML`, attributes, class)
- or create a new element and insert it (`createElement`, `append`)
- risk of `innerHTML` with user input

**Common misconceptions**
- `textContent` and `innerHTML` are interchangeable

**Interviewer follow-ups**
- "Why might `innerHTML` with user input be dangerous?"

**Verify at:** MDN, `Document.querySelector()`, `Node.textContent`

---

## Event Basics

### PB-EVENT-01
**Question:** Define an event listener in JavaScript.

**A good answer covers**
- a function that runs when a given event happens on an element
- `addEventListener(type, handler)`
- the handler receives an event object
- the function is passed, not called

**Common misconceptions**
- `addEventListener('click', handle())`

**Interviewer follow-ups**
- "Who calls your handler function, and when?"

**Verify at:** MDN, `EventTarget.addEventListener()`

### PB-EVENT-02
**Question:** Outline the steps involved in changing the content of an HTML element when it is clicked.

**A good answer covers**
- select the element
- attach a click listener
- inside the handler, change the content
- (optionally) update the data first, then re-render

**Common misconceptions**
- (none typical; check the order of steps)

**Interviewer follow-ups**
- "Do it for 100 elements. Still 100 listeners?"

**Verify at:** MDN, "Introduction to events"

### PB-EVENT-03
**Question:** Inside a `click` event listener, how can you access the element that was clicked?

**A good answer covers**
- `event.target`: the element actually clicked
- `event.currentTarget`: the element the listener is on
- when they differ (click on a child element)
- use in event delegation

**Common misconceptions**
- `target` and `currentTarget` are always the same

**Interviewer follow-ups**
- "The button contains an icon and the user clicks the icon. What is `target`?"

**Verify at:** MDN, `Event.target`, `Event.currentTarget`

---

## Design Basics

### PB-DESIGN-01
**Question:** What are the differences between `display: block`, `display: inline`, and `display: inline-block` in CSS? When would you use each display property, and how do they affect the layout and behavior of elements?

**A good answer covers**
- block: new line, takes full width, width/height apply
- inline: flows in text, width/height don't apply
- inline-block: flows inline but width/height apply
- an example element for each and a use case

**Common misconceptions**
- setting `width` on a `span` works as on a `div`

**Interviewer follow-ups**
- "How would you put three boxes side by side?"

**Verify at:** MDN, `display`

### PB-DESIGN-02
**Question:** Explain the distinctions between `position: relative` and `position: absolute` CSS properties.

**A good answer covers**
- relative: offset from its normal place, keeps its space
- absolute: removed from the flow, positioned to the nearest positioned ancestor
- the common pattern: relative parent + absolute child

**Common misconceptions**
- absolute is always relative to the page

**Interviewer follow-ups**
- "How do you put a badge in the top-right corner of a card?"

**Verify at:** MDN, `position`

### PB-DESIGN-03
**Question:** What is the box model? Name the CSS properties associated with it.

**A good answer covers**
- content, padding, border, margin (inside → out)
- `width`, `height`, `padding`, `border`, `margin`
- `box-sizing: border-box` vs. `content-box`

**Common misconceptions**
- padding and margin are the same thing

**Interviewer follow-ups**
- "A 200px wide box gets 20px padding. How wide is it now?"

**Verify at:** MDN, "The box model"

### PB-DESIGN-04
**Question:** Identify the CSS properties that affect font and text appearance.

**A good answer covers**
- `font-family`, `font-size`, `font-weight`, `font-style`
- `color`, `line-height`, `letter-spacing`, `text-align`, `text-decoration`, `text-transform`
- units for font size (px, rem, em)

**Common misconceptions**
- (none typical; check breadth)

**Interviewer follow-ups**
- "Why use `rem` instead of `px` for font size?"

**Verify at:** MDN, "Fundamental text and font styling"

### PB-DESIGN-05
**Question:** List the steps for adding or removing a class name from an HTML element.

**A good answer covers**
- select the element
- `classList.add`, `classList.remove`, `classList.toggle`
- (older way) `className`, and why it can overwrite other classes
- the CSS rule for that class does the visual change

**Common misconceptions**
- `className = 'selected'` adds a class (it replaces all of them)

**Interviewer follow-ups**
- "How do you make only one item active at a time?"

**Verify at:** MDN, `Element.classList`

---

## JavaScript — Language Specialties

### PB-LANG-01
**Question:** Elaborate on the differences between value and reference data types in JavaScript, specifically in relation to objects and primitives.

**A good answer covers**
- primitives are copied by value
- objects/arrays: the variable holds a reference; copying the variable copies the reference
- two variables can point to the same object, so a change is visible through both
- `===` on objects compares references
- how to make a (shallow) copy

**Common misconceptions**
- `const b = a` copies an array

**Interviewer follow-ups**
- "Why did changing one row of your board change other rows?"

**Verify at:** MDN, "JavaScript data types and data structures"

### PB-LANG-02
**Question:** Discuss the concept of mutability and immutability in objects, arrays, and primitives, and explain why it is important to understand when working with data structures in JavaScript.

**A good answer covers**
- primitives are immutable (operations make new values)
- objects/arrays are mutable by default
- methods that mutate vs. return new
- `const` does not make an object immutable
- why it matters: hidden side effects, bugs in shared data

**Common misconceptions**
- `const arr = []` means the array can't change

**Interviewer follow-ups**
- "How do you update one item in an array without changing the original?"

**Verify at:** MDN, "Mutable" (Glossary), `const`

### PB-LANG-03
**Question:** Is `null` considered an object or a primitive in JavaScript?

**A good answer covers**
- `null` is a primitive
- `typeof null === 'object'` is a historical bug
- `null` = intentionally "no value"

**Common misconceptions**
- "`null` is an object because `typeof` says so"

**Interviewer follow-ups**
- "How do you check whether a value is `null`?"

**Verify at:** MDN, `null`, `typeof`

### PB-LANG-04
**Question:** What does `undefined` represent in JavaScript?

**A good answer covers**
- a value that hasn't been assigned
- where it shows up: unassigned variable, missing property, missing argument, function without `return`
- difference from `null` (intentional absence)

**Common misconceptions**
- `undefined` and "not declared" are the same (accessing an undeclared variable throws)

**Interviewer follow-ups**
- "What does a function without `return` give back?"

**Verify at:** MDN, `undefined`

### PB-LANG-05
**Question:** When would you use `var`, `let`, and `const` in JavaScript?

**A good answer covers**
- `const` by default; `let` when the variable will be reassigned
- `var`: function-scoped, hoisted, avoided in modern code
- `let` / `const` are block-scoped
- `const` prevents reassignment, not mutation

**Common misconceptions**
- `const` objects can't be changed

**Interviewer follow-ups**
- "Why does your code use `let` here and `const` there?"

**Verify at:** MDN, `let`, `const`, `var`

### PB-LANG-06
**Question:** Explain the concept of hoisting in JavaScript.

**A good answer covers**
- declarations are processed before the code runs
- function declarations can be called before they appear
- `var` is hoisted with `undefined`
- `let` / `const` are hoisted but not usable before the line (temporal dead zone)

**Common misconceptions**
- "the code is physically moved to the top"

**Interviewer follow-ups**
- "What happens if you use a `let` variable one line before declaring it?"

**Verify at:** MDN, "Hoisting" (Glossary)

---

## Git

### PB-GIT-01
**Question:** Discuss the advantages of using a version control system.

**A good answer covers**
- history: what changed, when, why
- go back to an earlier state
- work in parallel (branches) and combine work
- collaboration and backup

**Common misconceptions**
- "Git is only for teams"

**Interviewer follow-ups**
- "How did your team use it on a team project?"

**Verify at:** Pro Git book, ch. 1 (git-scm.com/book)

### PB-GIT-02
**Question:** Clarify the differences between Git and GitHub.

**A good answer covers**
- Git: the version control tool, runs locally
- GitHub: a hosting service for Git repositories plus collaboration features (PRs, issues)
- Git works without GitHub; alternatives exist (GitLab, Bitbucket)

**Common misconceptions**
- "Git and GitHub are the same"

**Interviewer follow-ups**
- "Can you commit without internet?"

**Verify at:** Pro Git book, ch. 1 and ch. 6

### PB-GIT-03
**Question:** What is the purpose of remote repositories in Git?

**A good answer covers**
- a shared copy of the repository on another machine / server
- `push` sends commits, `pull` / `fetch` gets them
- collaboration and backup
- `origin` as the default name

**Common misconceptions**
- commit and push are the same thing

**Interviewer follow-ups**
- "What's the difference between `fetch` and `pull`?"

**Verify at:** Pro Git book, "Working with Remotes"

### PB-GIT-04
**Question:** When does a merge conflict occur in Git?

**A good answer covers**
- two branches change the same lines (or one deletes a file the other edits)
- Git can't decide automatically
- resolved by hand: edit, `add`, commit
- how to reduce them (small commits, pull often, communicate)

**Common misconceptions**
- "any two changes to the same file conflict"

**Interviewer follow-ups**
- "Tell me about a conflict you had. How did you resolve it?"

**Verify at:** Pro Git book, "Basic Branching and Merging"

---

## Terminal

### PB-TERM-01
**Question:** How would you execute a JavaScript file in the terminal?

**A good answer covers**
- `node file.js`
- must be in the right folder (or give the path)
- Node.js must be installed

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "You get 'Cannot find module'. What do you check first?"

**Verify at:** Node.js docs, "Introduction to Node.js"

### PB-TERM-02
**Question:** What is the keyboard shortcut to stop a running process in the terminal?

**A good answer covers**
- `Ctrl + C`

**Common misconceptions**
- `Ctrl + Z` (suspends, doesn't stop)

**Interviewer follow-ups**
- "Your program is stuck in an infinite loop. What do you do?"

**Verify at:** (any terminal guide)

### PB-TERM-03
**Question:** How can you retrieve the previous command executed in the terminal?

**A good answer covers**
- up arrow
- bonus: `history`, `Ctrl + R` search

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- (none needed)

**Verify at:** (any terminal guide)

### PB-TERM-04
**Question:** How do you navigate to the parent directory of the current directory in the terminal?

**A good answer covers**
- `cd ..`
- `..` means the parent, `.` the current
- `pwd` to check where you are

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "How do you go up two levels?"

**Verify at:** (any terminal guide)

---

## Debugging

### PB-DEBUG-01
**Question:** What techniques can you use while debugging a program?

**A good answer covers**
- read the error message and the line number
- `console.log` of values at key points
- the debugger: breakpoints, stepping, watching variables
- reproduce the problem with a small input; change one thing at a time
- explaining the code to someone (rubber duck)

**Common misconceptions**
- "debugging = adding random changes until it works"

**Interviewer follow-ups**
- "Tell me about a bug you found. How did you find it?"

**Verify at:** VS Code docs, "Debugging"

### PB-DEBUG-02
**Question:** What does step over, step into and step out mean while using the debugger?

**A good answer covers**
- step over: run the current line, don't go inside the called function
- step into: go inside the called function
- step out: finish the current function and return to the caller

**Common misconceptions**
- step over skips the line without running it

**Interviewer follow-ups**
- "When would you step into instead of over?"

**Verify at:** VS Code docs, "Debugging"

### PB-DEBUG-03
**Question:** How can you start to debug a program from a certain line using the debugger?

**A good answer covers**
- set a breakpoint on that line
- start the program in debug mode
- execution pauses at the breakpoint; then inspect / step
- bonus: conditional breakpoints, `debugger` statement

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "The bug only happens on the 50th loop iteration. How do you get there fast?"

**Verify at:** VS Code docs, "Debugging"
