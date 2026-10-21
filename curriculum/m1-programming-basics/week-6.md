# Programming Basics — DOM interaction (dynamic)

> Project cards for Week 6 — DOM interaction (dynamic). Concept level only: no project descriptions,
> tasks or solutions. Question IDs point to topics in `questions/index.yaml`.
> Status: drafted 2026-10-19; mentor review in progress.

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
