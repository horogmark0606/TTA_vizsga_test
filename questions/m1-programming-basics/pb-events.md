# pb-events

Module 1 · Programming Basics · workbook section "Event Basics" (PB-EVENT-01 – PB-EVENT-03).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).
Extra care topic: go gradual and concrete.

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

**Practised in:** Events around us, Smol Twitter, Neighbouring countries

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

**Practised in:** Smol Twitter, Favorite products, More on favorite products

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

**Practised in:** Events around us, Bold buttons, Favorite products

**Verify at:** MDN, `Event.target`, `Event.currentTarget`
