# Programming Basics — Complex data structures

> Project cards for Week 2 — Complex data structures. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
