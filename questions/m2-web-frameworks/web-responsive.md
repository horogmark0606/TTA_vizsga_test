# web-responsive

Module 2 · Web Frameworks · workbook section "Responsive Design" (WEB-RESP-01 – WEB-RESP-08).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### WEB-RESP-01
**Question:** What does responsive design do? Why is it important?

**A good answer covers**
- the layout adapts to screen size and device
- one codebase for mobile, tablet, desktop
- usability and accessibility; most traffic is mobile
- SEO / user expectations

**Common misconceptions**
- "responsive = a separate mobile site"

**Interviewer follow-ups**
- "What did you change in your project for small screens?"

**Practised in:** My social media, My Little Gallery, Weather in the Capitals, Yet Another Online Shop

**Verify at:** MDN, "Responsive design"

### WEB-RESP-02
**Question:** What is a mobile-first approach?

**A good answer covers**
- write the base styles for small screens first
- add `min-width` media queries for larger screens
- forces focus on the essential content
- smaller screens don't download / override desktop styles

**Common misconceptions**
- "mobile-first means only mobile"

**Interviewer follow-ups**
- "Mobile-first: `min-width` or `max-width` media queries? Why?"

**Practised in:** (no project; theory only)

**Verify at:** MDN, "Responsive design"

### WEB-RESP-03
**Question:** How can you test the website's appearance on different screen sizes in the browser?

**A good answer covers**
- DevTools device / responsive mode
- preset devices and custom sizes
- resizing the window
- testing on a real device too

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "What can DevTools device mode *not* tell you?"

**Practised in:** My Little Gallery

**Verify at:** Chrome DevTools docs, "Simulate mobile devices with device mode"

### WEB-RESP-04
**Question:** Can you give some techniques that help to fulfill the responsive design criteria?

**A good answer covers**
- fluid / relative units (%, rem, vw)
- Flexbox and Grid
- media queries
- responsive images (`max-width: 100%`, `srcset`)
- the viewport meta tag
- CSS frameworks' grid systems

**Common misconceptions**
- media queries alone are enough

**Interviewer follow-ups**
- "What does the viewport meta tag do, and what happens without it?"

**Practised in:** My social media, My Little Gallery, Freestyle Firebase Project, Part 1

**Verify at:** MDN, "Responsive design"

### WEB-RESP-05
**Question:** What do media queries do? How do they work?

**A good answer covers**
- apply CSS only when a condition is true (width, orientation, …)
- `@media (min-width: 768px) { … }`
- breakpoints
- later rules override earlier ones when they match

**Common misconceptions**
- media queries change the HTML

**Interviewer follow-ups**
- "Two media queries both match. Which rule wins?"

**Practised in:** My Little Gallery, Weather in the Capitals

**Verify at:** MDN, "Using media queries"

### WEB-RESP-06
**Question:** How would you define the Flexbox layout?

**A good answer covers**
- a one-dimensional layout model (row **or** column)
- `display: flex` on the container
- main axis / cross axis; `justify-content` vs. `align-items`
- items can grow, shrink and wrap

**Common misconceptions**
- Flexbox is two-dimensional (that's Grid)

**Interviewer follow-ups**
- "How do you centre something horizontally and vertically?"

**Practised in:** My social media

**Verify at:** MDN, "Basic concepts of flexbox"

### WEB-RESP-07
**Question:** How can you debug the Flexbox layout in the browser?

**A good answer covers**
- DevTools: the flex badge / overlay on the container
- inspect computed sizes, the box model, gaps
- toggle properties live
- temporary outlines / borders

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "An item won't shrink. What do you check?"

**Practised in:** My social media

**Verify at:** Chrome DevTools docs, "Inspect and debug CSS flexbox"

### WEB-RESP-08
**Question:** What is the difference between the Flexbox container and the Flexbox item?

**A good answer covers**
- container: the element with `display: flex`; controls direction, wrapping, alignment, gap
- items: its **direct** children; control their own grow / shrink / basis / order / `align-self`
- an element can be both an item and a container

**Common misconceptions**
- grandchildren are flex items too

**Interviewer follow-ups**
- "Where do you put `flex-grow`: on the container or the item?"

**Practised in:** My social media

**Verify at:** MDN, "Basic concepts of flexbox"
