# Programming Basics — Algorithms & validation

> Project cards for Week 3 — Algorithms & validation. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
