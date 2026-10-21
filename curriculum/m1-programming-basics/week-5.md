# Programming Basics — DOM rendering (static)

> Project cards for Week 5 — DOM rendering (static). Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
