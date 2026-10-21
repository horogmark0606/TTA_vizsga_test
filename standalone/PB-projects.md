# Programming Basics — project cards

> Module 1 of the FullStack course. JavaScript fundamentals, console programs
> first, then HTML / CSS / DOM. Question IDs (`PB-…`) refer to
> `PB-questions.md`.
>
> Status: **draft, mentor review pending.**

---

## Week 1 — Basics

### PB · Calculator (solo, week 1)

**Concepts to understand**
- Terminal input always arrives as a string.
- Converting a string to a number, and recognising when the conversion failed.
- A loop that keeps asking until the input is valid.
- Choosing between several branches (`if` / `else if` or `switch`) based on a value.
- Edge cases that break the maths (division by zero).
- An outer loop that lets the whole program run again.

**Typical pitfalls**
- `"2" + "3"` gives `"23"`: the values were never converted.
- Checking `x === NaN` (always false).
- Validating once instead of repeating until the input is valid.

**Explain-your-own-code prompts**
- "What type does the input have right after you read it? On which line does it become a number?"
- "Type `abc` as the first number. Which line of your code catches it?"
- "How does your program know when to stop?"

**Related questions:** PB-ALG-01, PB-ALG-02, PB-ALG-03, PB-DATA-06, PB-BUILTIN-04, PB-TERM-01, PB-TERM-02

### PB · Become a coder (solo, week 1)

**Concepts to understand**
- `for`, `while` and `for...of`: what each one is good at.
- Building a new string character by character.
- Reading characters by index, and why you can't overwrite a character in place.
- Turning a letter into a number (its position in the alphabet or its character code).
- Range validation of a number entered by the user, repeated until valid.

**Typical pitfalls**
- Trying `word[i] = 'x'`: strings are immutable.
- Off-by-one when taking every second character.
- Mixing strings and numbers when adding.

**Explain-your-own-code prompts**
- "Why did you pick that loop for this step and a different one for the other step?"
- "Why can't you change one letter of a string directly? What did you do instead?"

**Related questions:** PB-ALG-05, PB-BUILTIN-01, PB-LANG-02

### PB · Basics of arrays (solo, week 1)

**Concepts to understand**
- Creating an array, reading items by index, `length`.
- Finding an item and changing it in place.
- Adding to the end, removing an item.
- Looping over an array to print each item.
- A string is also indexable (first character of a name).

**Typical pitfalls**
- The last index is `length - 1`, not `length`.
- Removing an item shifts the indexes of the items after it.

**Explain-your-own-code prompts**
- "How did you find the student whose name you changed? What if two students had the same family name?"
- "What happens to the indexes after you remove someone?"

**Related questions:** PB-DATA-01, PB-DATA-05, PB-BUILTIN-02

### PB · Typewriter backspaces (solo, week 1)

**Concepts to understand**
- Walking through a string character by character.
- Building a result in a new array instead of changing the input.
- Using an array like a stack: add to the end, remove from the end.
- Deciding per character with `if` / `else`.
- Turning the array back into a string for display.

**Typical pitfalls**
- A "backspace" at the very beginning, when there is nothing to remove yet.
- Printing the array instead of the joined string.

**Explain-your-own-code prompts**
- "Walk me through your loop for a short input that contains one special character. What is in your result array after each step?"
- "What happens if the input starts with the special character?"

**Related questions:** PB-ALG-05, PB-BUILTIN-02

### PB · Vacation expenses (solo, week 1)

**Concepts to understand**
- Finding the position of a value in an array.
- Calculating a distance from two indexes.
- Removing a range of items, or building a new array without them.
- Methods that change the original array vs. methods that return a new one.

**Typical pitfalls**
- Not checking what is returned when the value is not found (`-1`).
- Off-by-one: is the end of the range included or not?
- Changing the original array without noticing.

**Explain-your-own-code prompts**
- "Is your original array still the same after your code runs? How do you know?"
- "What would your code do if one of the searched values didn't exist?"

**Related questions:** PB-BUILTIN-02, PB-LANG-02

### PB · Phonebook (solo, week 1)

**Concepts to understand**
- Combining strings with variables (concatenation, template literals).
- Checking whether input is a whole number.
- Range conditions with `<`, `<=`, `&&`.
- Splitting a string into parts by position.
- Collecting unique values.
- Counting occurrences without hard-coding the result.
- Checking a pattern by hand, character by character.

**Typical pitfalls**
- Boundary values (exactly 18, exactly 40) landing in the wrong group.
- Counting the invalid items as well.

**Explain-your-own-code prompts**
- "Which group does exactly 40 fall into in your code? Show me the condition."
- "How do you make sure an area code only appears once?"
- "How does your counter work? What data structure holds the counts?"

**Related questions:** PB-ALG-03, PB-ALG-04, PB-DATA-03, PB-BUILTIN-01

### PB · Hangman (team, week 1)

**Concepts to understand**
- Game loop: a loop that keeps running until one of several end conditions (win, lose, quit) becomes true.
- Game state: which values must be remembered between rounds, and which data type fits each one.
- Strings vs. arrays: when to turn one into the other, and why.
- Normalising input for comparison while keeping the original form for display.
- Input validation: deciding what "valid" means before acting on the input.
- Random selection from a list (how an index is produced from `Math.random()`).
- Mapping a number (lives left) to a piece of output (ASCII art), including when the starting number can change.
- Breaking the program into small functions with one job each.

**Typical pitfalls**
- Off-by-one when turning a random number into an array index.
- End condition checked in the wrong place → one extra round, or an infinite loop.
- Comparing letters without normalising case.
- One long function that mixes input, logic and printing.

**Explain-your-own-code prompts**
- "Point to the exact line where your program decides the game is over. What are all the ways to get there?"
- "Walk me through what happens, step by step, when the player types the same letter twice."
- "Which variables hold the state of the game? Why did you choose that type for each?"
- "If lives started at 10 instead of 6, what would you change, and where?"

**Related questions:** PB-ALG-05, PB-DATA-05, PB-FN-01, PB-FN-06, PB-BUILTIN-03, PB-GIT-02

### PB · Text Adventure (team, week 1)

**Concepts to understand**
- Running a JavaScript file with Node.js from the terminal; installing dependencies.
- Why variables exist; `let` vs. `const`; meaningful names.
- The primitive types (number, string, boolean) and when to use each.
- Branching with `if` / `else if` / `else` (maybe `switch`).
- Planning the program flow first (a flowchart), then coding it.
- The order in which the computer executes code.

**Typical pitfalls**
- Deeply nested `if`s that are impossible to follow.
- Using `const` for something that has to change.

**Explain-your-own-code prompts**
- "Show me one path through your story in the flowchart, then the same path in your code."
- "Which player attributes do you store, and what type is each one?"
- "In what order does the computer read your file?"

**Related questions:** PB-DATA-06, PB-LANG-05, PB-TERM-01, PB-TERM-03, PB-TERM-04, PB-GIT-01, PB-GIT-03

---

## Week 2 — Complex data structures

### PB · Hello Functions! (solo, week 2)

**Concepts to understand**
- Declaring a function vs. calling it.
- Parameters (in the definition) vs. arguments (in the call).
- `return` vs. `console.log`: giving a value back vs. printing it.
- A function that calls other functions and combines their results.
- What a function returns when it has no `return`.
- What a parameter is when no argument is passed; default parameters.

**Typical pitfalls**
- Printing inside the function when the caller needs the value.
- Defining the function but never calling it.

**Explain-your-own-code prompts**
- "What's the difference between the function printing the greeting and returning it? Where does that matter in your code?"
- "What gets stored in a variable if the function has no `return`? Why?"

**Related questions:** PB-FN-01, PB-FN-02, PB-FN-03, PB-LANG-04, PB-LANG-06

### PB · Password validator (solo, week 2)

**Concepts to understand**
- Small functions that each check one rule and return a boolean (single responsibility).
- Combining several checks into a list of problems.
- Checking whether a string contains a character from a set.
- A first taste of testing: call a function with a known input and compare with the expected result.
- Boundary values (exactly the minimum length).

**Typical pitfalls**
- Testing only the "happy" case.
- One big function that checks everything and is hard to test.

**Explain-your-own-code prompts**
- "Why is each rule in its own function? What would get harder if it were all in one?"
- "Which test checks the boundary? What would happen without it?"

**Related questions:** PB-FN-01, PB-FN-03, PB-BUILTIN-01, PB-DEBUG-01

### PB · Snail mail (solo, week 2)

**Concepts to understand**
- Turning a written list of requirements into an ordered list of checks.
- String methods for searching, splitting and slicing.
- Counting how many times a character appears.
- Order of conditions: the first matching rule decides the message.
- Variables inside a function are not visible outside it.

**Typical pitfalls**
- Checks in the wrong order give the wrong error message.
- Only checking "contains @" and not "exactly one @".

**Explain-your-own-code prompts**
- "Why is this check before that one? What breaks if you swap them?"
- "How does your code count the `@` characters?"

**Related questions:** PB-BUILTIN-01, PB-ALG-04, PB-FN-06

### PB · Student catalog (solo, week 2)

**Concepts to understand**
- Object literals: keys and values of different types.
- An array of objects as a simple "table".
- Dot notation vs. bracket notation; reading a key whose name comes from user input.
- Looping over an object's keys and values.
- Adding a new key to every object in the array.
- A menu loop that repeats until the user quits.

**Typical pitfalls**
- `obj.key` when the key name is in a variable (needs `obj[key]`).
- The menu runs once instead of looping.

**Explain-your-own-code prompts**
- "The user types a key name. Show me how your code reads that key from each object."
- "How do you add a new key to every person? Which loop did you use?"

**Related questions:** PB-DATA-02, PB-DATA-03, PB-DATA-04, PB-ALG-05

### PB · Take me to a nice place (solo, week 2)

**Concepts to understand**
- Data from two sources in different shapes, converted into one common shape.
- A converter function: one object in, one object out.
- Validating data and signalling "invalid" with a special return value (`null`).
- Building a filtered result array from valid items only.
- Formatting output so a human can read it.

**Typical pitfalls**
- Copying the converter and forgetting to adapt one field.
- Accidentally modifying the source object instead of creating a new one.

**Explain-your-own-code prompts**
- "How does an item from source A become the common format? Walk me through one example."
- "Where does an invalid item get dropped?"

**Related questions:** PB-DATA-03, PB-DATA-04, PB-FN-01, PB-LANG-01, PB-LANG-03

### PB · Tic-tac-toe-console (team, week 2)

**Concepts to understand**
- A board as an array of arrays (rows and columns).
- Why each row must be a separate array, and not the same array reused.
- Translating user coordinates (letter + number, starting from 1) into array indexes (starting from 0).
- One function per job: make the board, print it, read a move, check the winner, check for a full board.
- Checking rows, columns and diagonals.
- The game loop and its end conditions.
- Simple AI: a random empty cell first, then rules (win if possible, block if needed).
- Splitting code into modules and using external packages.

**Typical pitfalls**
- Filling the board with the same row array, so changing one cell changes a whole column.
- Off-by-one between what the user types and the array index.

**Explain-your-own-code prompts**
- "How did you create the board? If you change one cell, why doesn't the cell below it change?"
- "Walk me through how `B2` becomes a position in your array."
- "How does your AI decide where to move?"

**Related questions:** PB-LANG-01, PB-LANG-02, PB-FN-01, PB-ALG-05, PB-DEBUG-02, PB-GIT-04

### PB · Billionaire game (team, week 2)

**Concepts to understand**
- Questions and answers stored as an array of objects.
- Picking random items without repeats.
- A `while` loop that runs the game until an end condition.
- Special inputs (commands) handled before normal answers.
- Remembering one-time features (lifelines) with flags.
- Accumulating a score.

**Typical pitfalls**
- The same question comes up twice.
- A lifeline that can be used more than once.

**Explain-your-own-code prompts**
- "How does your game guarantee a question isn't asked twice?"
- "Where do you remember that a lifeline was used?"

**Related questions:** PB-DATA-03, PB-DATA-04, PB-ALG-04, PB-BUILTIN-03

---

## Week 3 — Algorithms & validation

### PB · Functional calculator (solo, week 3)

**Concepts to understand**
- Planning top-down: decide the functions before writing them.
- A function that keeps asking until it gets a valid value, then returns it.
- Type conversion and invalid input.
- Keeping the calculation itself in a pure function (inputs in, result out).
- Handling an invalid calculation (division by zero).
- A "quit" command that has to work at any prompt.

**Typical pitfalls**
- Input reading and calculation mixed in the same function.
- Quit only works at one of the prompts.

**Explain-your-own-code prompts**
- "Compare this with your week 1 calculator. What changed, and why is it better?"
- "Which of your functions could you test without typing anything? Why?"

**Related questions:** PB-FN-01, PB-FN-03, PB-BUILTIN-04, PB-DEBUG-01

### PB · Wordchain (console) (solo, week 3)

**Concepts to understand**
- The first and last character of a string.
- Case-insensitive comparison.
- Checking that a word contains letters only.
- Telling commands apart from normal input by a prefix.
- Remembering used words and checking for repeats.
- Taking turns between players with a variable.

**Typical pitfalls**
- Repeat check is case-sensitive while the rest of the game isn't.
- A command is accepted as a game word.

**Explain-your-own-code prompts**
- "How does your code decide whether an input is a command or a word?"
- "How do you know a word was used before, even if it was typed with different capitals?"

**Related questions:** PB-BUILTIN-01, PB-DATA-05, PB-ALG-04

### PB · String theory (solo, week 3)

**Concepts to understand**
- Normalising a string first (case, letters only), then checking it.
- Reversing a string.
- Counting letters (an object used as a counter).
- Sorting characters to compare two strings.
- Pure functions that return `true` / `false`.

**Typical pitfalls**
- Forgetting to normalise one of the two strings.
- Mutating input while checking it.

**Explain-your-own-code prompts**
- "Which helper functions do you reuse across the different checkers?"
- "How does your anagram check work? Could you do it a different way?"

**Related questions:** PB-BUILTIN-01, PB-BUILTIN-02, PB-DATA-03

### PB · Boring buses (solo, week 3)

**Concepts to understand**
- Modelling real-world data with objects.
- Converting one data structure into another (list → object, and back).
- Keys generated dynamically (built from a counter).
- Producing the reverse direction from the same data.
- Serialising to JSON and why the result must be valid JSON.
- Nested objects.

**Typical pitfalls**
- Building the reverse route by changing the original.
- Printing a JavaScript object and calling it JSON.

**Explain-your-own-code prompts**
- "How do you create a key name like 'stop 3' in code?"
- "What's the difference between your object and the JSON string you printed?"

**Related questions:** PB-FILE-01, PB-FILE-02, PB-DATA-03, PB-LANG-01

### PB · Memorize numbers (solo, week 3)

**Concepts to understand**
- Separating logic into small building blocks (functions with clear inputs and outputs).
- A function that takes a message, asks the user and returns a number.
- Comparing two arrays position by position.
- Returning a marker value to describe a status.
- Generating a random array of a given length.

**Typical pitfalls**
- Functions that print and return at the same time, so they can't be reused.
- Comparing arrays with `===`.

**Explain-your-own-code prompts**
- "Pick one function and tell me its input, its output and its single job."
- "Why can't you compare two arrays with `===`?"

**Related questions:** PB-FN-01, PB-FN-03, PB-BUILTIN-03, PB-LANG-01

### PB · Battleship.js (console) (team, week 3)

**Concepts to understand**
- A board as a 2D array whose size comes from input.
- Validating coordinate format (letter followed by number).
- Translating coordinates into indexes.
- Two separate game states (player and computer) that must not mix.
- A random computer shot that never repeats.
- Detecting the end of the game.
- Organising a large program into many functions.

**Typical pitfalls**
- Player and computer boards accidentally sharing the same arrays.
- Coordinate validation that accepts out-of-range values.

**Explain-your-own-code prompts**
- "How do you keep the two boards separate?"
- "How does the computer avoid shooting the same cell twice?"
- "Which function would you debug first if a hit wasn't registered? Why?"

**Related questions:** PB-LANG-01, PB-FN-01, PB-BUILTIN-03, PB-DEBUG-01, PB-DEBUG-02, PB-DEBUG-03

---

## Week 4 — Higher-order functions

### PB · Greeting styles (solo, week 4)

**Concepts to understand**
- Functions are values: they can be stored and passed around.
- A higher-order function: takes a function as a parameter.
- Anonymous functions and arrow functions.
- Passing a function (`fn`) vs. passing its result (`fn()`).

**Typical pitfalls**
- Calling the function while passing it.

**Explain-your-own-code prompts**
- "What's the difference between passing `shout` and passing `shout('Ann')`?"
- "Rewrite one of your functions as an arrow function. What changed?"

**Related questions:** PB-FN-04, PB-FN-05

### PB · Functional trio (solo, week 4)

**Concepts to understand**
- How `map`, `filter` and `reduce` work inside: a loop that calls the callback for each item.
- What the callback receives and what it must return in each case.
- Returning a new array instead of changing the input.
- The accumulator and its starting value in `reduce`.
- Testing with different callbacks.

**Typical pitfalls**
- Forgetting the starting value of the accumulator.
- Pushing the original item instead of the callback's result (map) or the item itself (filter).

**Explain-your-own-code prompts**
- "Explain your `reduce` with a small array. What is the accumulator after each step?"
- "Who calls the callback: you or your function?"

**Related questions:** PB-FN-05, PB-BUILTIN-02, PB-BUILTIN-05, PB-LANG-02, PB-ALG-06

### PB · Expense manager (solo, week 4)

**Concepts to understand**
- Using the built-in `map`, `filter`, `reduce` on an array of objects.
- Choosing which one fits: transform, select, or combine into one value.
- Template literals to build output strings.
- Writing tests for functions.

**Typical pitfalls**
- Using `map` when nothing should be transformed (or `forEach` when a result is needed).
- `reduce` without a starting value on an empty array.

**Explain-your-own-code prompts**
- "Why is this one a `filter` and not a `map`?"
- "What happens to your total when the list is empty?"

**Related questions:** PB-BUILTIN-02, PB-BUILTIN-05, PB-FN-05

### PB · Secure ERP (team, week 4)

**Concepts to understand**
- Create / read / update / delete on arrays **without** changing the original (immutability).
- Chaining array methods: first select the records, then transform or total them.
- Grouping and aggregating with `reduce` into an object.
- Splitting a program into modules and connecting them with a shared menu.
- Dates as values to compare.

**Typical pitfalls**
- Modifying the object inside the array when "updating" (the original changes too).
- Group-by accumulator not initialised for a new key.

**Explain-your-own-code prompts**
- "How can you show that your update doesn't change the original array?"
- "Walk me through your group-by with three records."
- "How do the modules talk to each other?"

**Related questions:** PB-LANG-01, PB-LANG-02, PB-BUILTIN-02, PB-FN-05, PB-DATA-04

---

## Week 5 — DOM rendering (static)

### PB · HTML Animals (solo, week 5)

**Concepts to understand**
- The basic structure of an HTML document.
- Semantic elements (header, nav, main, footer, section…) and why they matter.
- Linking pages with relative paths.
- Images, tables, lists.

**Typical pitfalls**
- Using `div` for everything.
- Broken links from wrong relative paths.

**Explain-your-own-code prompts**
- "Why did you choose this element here instead of a `div`?"
- "How does the browser find the other page from your link?"

**Related questions:** PB-VIEW-01, PB-DESIGN-01

### PB · View around us (solo, week 5)

**Concepts to understand**
- The same element written in HTML vs. created with JavaScript.
- Creating an element, setting its text, inserting it at a chosen place.
- Creating many elements from an array.

**Typical pitfalls**
- Creating the element but never inserting it into the page.
- Inserting at the wrong position.

**Explain-your-own-code prompts**
- "What exists on the page after `createElement` but before you insert it?"
- "How did you choose where the new element goes?"

**Related questions:** PB-VIEW-01, PB-VIEW-02

### PB · What a tree (solo, week 5)

**Concepts to understand**
- The DOM as a tree of nested elements.
- Getting a reference to an element and keeping it in a variable.
- Building nested structures (heading inside a container).
- Fixing or reshaping data before rendering it.

**Typical pitfalls**
- Selecting an element before it exists.
- Appending everything to the same parent, so the nesting is flat.

**Explain-your-own-code prompts**
- "Draw the tree your code produces. Which element is the parent of which?"
- "Where did you fix the data: before rendering or during? Why?"

**Related questions:** PB-VIEW-01, PB-VIEW-02

### PB · Product list (solo, week 5)

**Concepts to understand**
- Rendering an array of objects into the page.
- Nested loops for nested data (items and their sub-items).
- Choosing which properties to display.
- Keeping data (JavaScript) and view (DOM) apart.

**Typical pitfalls**
- Sub-items inserted in the wrong place (all at the end).

**Explain-your-own-code prompts**
- "How do the sub-items end up right after their own parent item?"
- "Where is the data and where is the view in your code?"

**Related questions:** PB-VIEW-02, PB-DATA-03

### PB · More on product list (solo, week 5)

**Concepts to understand**
- Sorting with a compare function; `sort` changes the original array.
- Filtering before rendering.
- Grouping items by a property.
- Formatting numbers for display (e.g. seconds → minutes:seconds, padding with zero).

**Typical pitfalls**
- Sorting numbers without a compare function.
- Sorting the original data and breaking another part of the page.

**Explain-your-own-code prompts**
- "What does your compare function return, and what does that tell `sort`?"
- "Does your sorting change the original array?"

**Related questions:** PB-BUILTIN-02, PB-BUILTIN-04, PB-LANG-02

### PB · Design Around Us (solo, week 5)

**Concepts to understand**
- CSS selectors: element, class, id, descendant.
- Adding a class from JavaScript.
- The box model: content, padding, border, margin.
- Units: px, %, viewport units.

**Typical pitfalls**
- A selector that is too broad or too specific.
- Width that doesn't include padding and border (box-sizing).

**Explain-your-own-code prompts**
- "Which elements does this selector match? Why exactly those?"
- "How wide is this element really, once padding and border are added?"

**Related questions:** PB-DESIGN-03, PB-DESIGN-05

### PB · CSS hive (solo, week 5)

**Concepts to understand**
- Sizing, colours, borders.
- Typography properties.
- Backgrounds: images and gradients.
- Animations: keyframes and the animation property.
- How `display` changes layout.

**Typical pitfalls**
- Animation defined but not applied to any element.

**Explain-your-own-code prompts**
- "Explain one animation: what are its keyframes, and what triggers it?"
- "Why does this element sit next to that one instead of below it?"

**Related questions:** PB-DESIGN-01, PB-DESIGN-03, PB-DESIGN-04

### PB · A proper site (solo, week 5)

**Concepts to understand**
- Restyling an existing project without breaking its behaviour.
- Choosing a colour palette and fonts on purpose.
- Interaction feedback: transitions and animations that help the user.
- Asking others for usability feedback.

**Typical pitfalls**
- CSS changes that break the JavaScript (e.g. renamed classes the code depends on).

**Explain-your-own-code prompts**
- "Why these colours and fonts? Where did the idea come from?"
- "Which animation helps the user, and how?"

**Related questions:** PB-DESIGN-01, PB-DESIGN-02, PB-DESIGN-04, PB-DESIGN-05

### PB · Movie DB site (team, week 5)

**Concepts to understand**
- Cleaning up data: removing duplicates, giving each item a unique ID.
- Linking data by ID instead of by name.
- Several HTML pages using shared JavaScript.
- Reading URL query parameters and rendering based on them.
- Filtering, grouping and sorting before rendering.

**Typical pitfalls**
- Duplicates because names differ only in spacing or case.
- No handling of a missing or unknown ID in the URL.

**Explain-your-own-code prompts**
- "How does the movie page know which movie to show?"
- "How did you remove the duplicates? What counts as 'the same person'?"

**Related questions:** PB-VIEW-02, PB-DATA-04, PB-BUILTIN-02

---

## Week 6 — DOM interaction (dynamic)

### PB · Events around us (solo, week 6)

**Concepts to understand**
- Attaching a listener to an element.
- The event object and what it contains.
- Which element triggered the event (`target`) vs. where the listener is (`currentTarget`).
- The path of an event through the DOM.
- Different event types (click, input).

**Typical pitfalls**
- Calling the handler instead of passing it to `addEventListener`.

**Explain-your-own-code prompts**
- "Where does the event object come from? Who passes it to your function?"
- "Click the text inside a button. What is `target`, and what is `currentTarget`?"

**Related questions:** PB-EVENT-01, PB-EVENT-03, PB-FN-05

### PB · Smol Twitter (solo, week 6)

**Concepts to understand**
- UI state (logged in / logged out) that decides what is shown.
- Reading the value of an input field.
- Creating a new element for each post.
- Putting the newest item first.
- Clearing input after use.

**Typical pitfalls**
- State tracked only in the DOM, which makes logic hard to follow.

**Explain-your-own-code prompts**
- "How does your page know whether someone is logged in?"
- "How do you put the newest post on top?"

**Related questions:** PB-EVENT-01, PB-EVENT-02, PB-VIEW-02

### PB · Bold buttons (solo, week 6)

**Concepts to understand**
- Creating elements in a loop.
- One listener per element vs. one listener on the parent (event delegation).
- Finding out what kind of element was clicked.
- Adding and removing a class; only one element highlighted at a time.

**Typical pitfalls**
- The previous active element keeps its class.

**Explain-your-own-code prompts**
- "How many listeners does your page have? Could it work with one?"
- "How do you remove the highlight class from the element that had it before?"

**Related questions:** PB-EVENT-03, PB-DESIGN-05

### PB · Favorite products (solo, week 6)

**Concepts to understand**
- Adding a button to each rendered item.
- Connecting a clicked button to the data item it belongs to.
- Storing favourites in a data structure, not just in the page.
- Updating the button's look after the click.

**Typical pitfalls**
- Every button refers to the last item (e.g. a `var` loop variable captured by the handlers).

**Explain-your-own-code prompts**
- "When a button is clicked, how does your code know which item it belongs to?"
- "Where are the favourites stored?"

**Related questions:** PB-EVENT-02, PB-EVENT-03, PB-VIEW-01

### PB · More on favorite products (solo, week 6)

**Concepts to understand**
- Re-rendering a list from data (not reading data back from the page).
- Emptying a container before rendering again.
- Swapping one control for another.
- Resetting the view to the full list.

**Typical pitfalls**
- Items doubled because the container wasn't cleared.

**Explain-your-own-code prompts**
- "When you filter, where does the list come from: the page or your data?"
- "What happens to the old elements when you render again?"

**Related questions:** PB-VIEW-02, PB-EVENT-02, PB-BUILTIN-02

### PB · Neighbouring countries (team, week 6)

**Concepts to understand**
- Working with complex nested data (objects referring to each other by code).
- Looking up an item by a key.
- Finding the "biggest" item by a property.
- Filling a drop-down from data and reacting to its change.
- Navigation history: moving back and forward with an index; disabling a button at the ends.
- Reading nested data by a key chosen at runtime (translations).

**Typical pitfalls**
- Previous / next breaks after selecting a new country from the list.
- Assuming every country has neighbours.

**Explain-your-own-code prompts**
- "How do you get from a country to its neighbours' full data?"
- "How does your history work? What is stored, and what does the index point to?"

**Related questions:** PB-DATA-03, PB-BUILTIN-02, PB-EVENT-01, PB-VIEW-02
