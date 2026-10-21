# web-oop-js

Module 2 · Web Frameworks · workbook section "Object Oriented JavaScript" (WEB-OOJS-01 – WEB-OOJS-07).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### WEB-OOJS-01
**Question:** What is the difference between the class syntax and the constructor function syntax?

**A good answer covers**
- both create objects that share methods via the prototype
- `class` is mostly syntax over constructor functions + prototypes
- classes: must be called with `new`, not hoisted the same way, body in strict mode
- clearer syntax for inheritance (`extends`, `super`)

**Common misconceptions**
- JS classes work like Java classes (they're prototype-based)

**Interviewer follow-ups**
- "Where are the methods stored in both cases?"

**Practised in:** (no project; theory only)

**Verify at:** MDN, "Classes", "Inheritance and the prototype chain"

### WEB-OOJS-02
**Question:** What does the `new` keyword do?

**A good answer covers**
- creates a new empty object
- links it to the constructor's prototype
- runs the constructor with `this` = the new object
- returns the object (unless the constructor returns another object)

**Common misconceptions**
- (none typical; check all steps)

**Interviewer follow-ups**
- "What happens if you call a constructor function without `new`?"

**Practised in:** (no project; theory only)

**Verify at:** MDN, `new`

### WEB-OOJS-03
**Question:** What does a `constructor` method do in class syntax? When it is executed?

**A good answer covers**
- initialises a new instance (sets fields from arguments)
- runs once, automatically, on `new ClassName(…)`
- one per class; in a subclass, `super()` must be called before using `this`

**Common misconceptions**
- the constructor must be called manually

**Interviewer follow-ups**
- "What happens in a subclass constructor if you forget `super()`?"

**Practised in:** (no project; theory only)

**Verify at:** MDN, `constructor`

### WEB-OOJS-04
**Question:** What are the class methods of a class syntax?

**A good answer covers**
- functions defined in the class body
- shared by all instances (on the prototype)
- called on an instance; `this` is that instance
- `static` methods belong to the class itself

**Common misconceptions**
- each instance gets its own copy of every method

**Interviewer follow-ups**
- "When would you make a method `static`?"

**Practised in:** (no project; theory only)

**Verify at:** MDN, "Classes"

### WEB-OOJS-05
**Question:** What are the fields of a class syntax?

**A good answer covers**
- properties declared in the class body (public fields)
- each instance gets its own value
- private fields with `#`
- static fields

**Common misconceptions**
- fields are shared between instances like methods

**Interviewer follow-ups**
- "What does `#` in front of a field name mean?"

**Practised in:** (no project; theory only)

**Verify at:** MDN, "Public class fields", "Private properties"

### WEB-OOJS-06
**Question:** What is inheritance in the context of Javascript objects?

**A good answer covers**
- an object can use properties / methods of another through the prototype chain
- lookup goes up the chain until found or `null`
- with classes: `extends` sets up the chain
- reuse and specialisation

**Common misconceptions**
- properties are copied into the child

**Interviewer follow-ups**
- "What does the prototype chain look like for an array?"

**Practised in:** (no project; theory only)

**Verify at:** MDN, "Inheritance and the prototype chain"

### WEB-OOJS-07
**Question:** What does the `extends` keyword do?

**A good answer covers**
- creates a subclass of another class
- the subclass inherits the parent's methods
- `super(...)` calls the parent constructor; `super.method()` the parent method
- methods can be overridden

**Common misconceptions**
- a class can extend several classes

**Interviewer follow-ups**
- "How do you call the parent's version of an overridden method?"

**Practised in:** (no project; theory only)

**Verify at:** MDN, `extends`, `super`
