# oop-sql-statements

Module 3 · OOP with Java · workbook section "Databases" (OOP-DB-11 – OOP-DB-16).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### OOP-DB-11
**Question:** Which SQL statement is used to create tables? Describe the syntax briefly.

**A good answer covers**
- `CREATE TABLE name (column type constraints, …)`
- primary key, not null, defaults, foreign keys
- example

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "How do you add a column to an existing table?"

**Practised in:** Book DB, Bookshelf API

**Verify at:** PostgreSQL docs, `CREATE TABLE`

### OOP-DB-12
**Question:** Which SQL statement can be used to insert values? Describe the syntax briefly.

**A good answer covers**
- `INSERT INTO table (cols) VALUES (…)`
- several rows at once
- generated IDs (`RETURNING id` in PostgreSQL)
- `INSERT … SELECT`

**Common misconceptions**
- column list can always be omitted safely

**Interviewer follow-ups**
- "How do you get the generated ID back in Java?"

**Practised in:** Book DB

**Verify at:** PostgreSQL docs, `INSERT`

### OOP-DB-13
**Question:** Which SQL statement can be used to update values? Describe the syntax briefly.

**A good answer covers**
- `UPDATE table SET col = value, … WHERE condition`
- without `WHERE` every row changes
- can use expressions and subqueries

**Common misconceptions**
- forgetting the `WHERE` clause is harmless

**Interviewer follow-ups**
- "How do you protect yourself from an accidental full-table update?"

**Practised in:** Book DB

**Verify at:** PostgreSQL docs, `UPDATE`

### OOP-DB-14
**Question:** Which SQL statement can be used to delete rows?. Describe the syntax briefly.

**A good answer covers**
- `DELETE FROM table WHERE condition`
- without `WHERE` all rows go
- foreign keys may block or cascade
- vs. `TRUNCATE` / `DROP TABLE`

**Common misconceptions**
- `DELETE` removes the table

**Interviewer follow-ups**
- "What's the difference between `DELETE`, `TRUNCATE` and `DROP`?"

**Practised in:** Book DB

**Verify at:** PostgreSQL docs, `DELETE`

### OOP-DB-15
**Question:** Which SQL statement can be used to create queries?. Describe the syntax briefly.

**A good answer covers**
- `SELECT cols FROM table WHERE … GROUP BY … HAVING … ORDER BY … LIMIT …`
- logical order of evaluation differs from written order (FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY)
- aggregates, aliases, `DISTINCT`

**Common misconceptions**
- using a column alias in `WHERE`

**Interviewer follow-ups**
- "Why can't you use a `SELECT` alias in the `WHERE` clause?"

**Practised in:** Introduction to SQL, Northwind Traders – Natural SELECTion, Northwind Traders - GROUP your data, DVD Rental, Codecoolers everywhere!!!

**Verify at:** PostgreSQL docs, `SELECT`

### OOP-DB-16
**Question:** How can you join tables together in SQL? When should you do it?

**A good answer covers**
- `JOIN … ON` a matching condition (usually FK = PK)
- `INNER` (only matches), `LEFT` / `RIGHT` (keep unmatched from one side), `FULL`
- when the data you need is spread over related tables
- a missing condition causes a cross product

**Common misconceptions**
- `INNER JOIN` keeps rows without a match

**Interviewer follow-ups**
- "Find customers who never placed an order. Which join?"

**Practised in:** Northwind Traders - JOIN Tribbiani, Northwind Traders - GROUP your data, DVD Rental, Codecoolers everywhere!!!

**Verify at:** PostgreSQL docs, "Joins Between Tables"
