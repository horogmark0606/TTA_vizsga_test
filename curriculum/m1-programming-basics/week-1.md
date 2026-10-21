# Programming Basics — Basics

> Project cards for Week 1 — Basics. Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
