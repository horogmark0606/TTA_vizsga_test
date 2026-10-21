# pb-css

Module 1 · Programming Basics · workbook section "Design Basics" (PB-DESIGN-01 – PB-DESIGN-05).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

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

**Practised in:** HTML Animals, CSS hive, A proper site

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

**Practised in:** A proper site

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

**Practised in:** Design Around Us, CSS hive

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

**Practised in:** CSS hive, A proper site

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

**Practised in:** Design Around Us, A proper site, Bold buttons

**Verify at:** MDN, `Element.classList`
