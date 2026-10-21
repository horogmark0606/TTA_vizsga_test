# oop-sql-concepts

Module 3 · OOP with Java · workbook section "Databases" (OOP-DB-01 – OOP-DB-10).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### OOP-DB-01
**Question:** What are relational databases? What are their advantages and disadvantages?

**A good answer covers**
- data in tables with rows and columns; relations through keys
- SQL, schema, constraints
- advantages: consistency, ACID transactions, powerful queries / joins
- disadvantages: rigid schema, harder horizontal scaling, object–relational mismatch

**Common misconceptions**
- "relational" refers to the relationships between tables (it refers to relations = tables)

**Interviewer follow-ups**
- "When would you pick a NoSQL database instead?"

**Practised in:** Book DB

**Verify at:** PostgreSQL docs, "Tutorial: Concepts"

### OOP-DB-02
**Question:** How do you associate entities to each other in a relational database model?

**A good answer covers**
- foreign keys referencing primary keys
- one-to-many: FK on the "many" side
- many-to-many: a join table with two FKs
- one-to-one: unique FK

**Common misconceptions**
- storing lists of IDs in one column

**Interviewer follow-ups**
- "Model questions and tags. How many tables?"

**Practised in:** Northwind Traders - JOIN Tribbiani, AskMate OOP

**Verify at:** PostgreSQL docs, "Foreign Keys"

### OOP-DB-03
**Question:** What are tables in a relational database?

**A good answer covers**
- a named set of rows with the same columns
- each column has a name and a data type
- rows are records; usually identified by a primary key
- constraints define valid data

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "What does one row in your table represent?"

**Practised in:** Introduction to SQL, Northwind Traders – Natural SELECTion

**Verify at:** PostgreSQL docs, "Table Basics"

### OOP-DB-04
**Question:** What is a _primary key_?

**A good answer covers**
- a column (or columns) uniquely identifying each row
- unique and not null
- one per table
- natural vs. surrogate (generated ID) keys

**Common misconceptions**
- a primary key must be a single integer column

**Interviewer follow-ups**
- "Why are email addresses a risky primary key?"

**Practised in:** Book DB

**Verify at:** PostgreSQL docs, "Constraints" (Primary Keys)

### OOP-DB-05
**Question:** What is a _foreign key_?

**A good answer covers**
- a column referencing the primary key of another (or the same) table
- enforces referential integrity
- defines relationships
- `ON DELETE` behaviour (restrict, cascade, set null)

**Common misconceptions**
- a foreign key must be unique

**Interviewer follow-ups**
- "What happens when you delete a row others refer to?"

**Practised in:** Book DB, Northwind Traders - JOIN Tribbiani

**Verify at:** PostgreSQL docs, "Constraints" (Foreign Keys)

### OOP-DB-06
**Question:** What does the SQL abbreviation stand for?

**A good answer covers**
- Structured Query Language
- declarative: you say *what*, the database decides *how*

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "What does 'declarative' mean here?"

**Practised in:** Introduction to SQL

**Verify at:** PostgreSQL docs, "The SQL Language"

### OOP-DB-07
**Question:** What are some of the SQL database providers that you’ve heard of?

**A good answer covers**
- PostgreSQL, MySQL / MariaDB, SQLite, Microsoft SQL Server, Oracle
- open-source vs. commercial
- managed cloud versions (e.g. AWS RDS)

**Common misconceptions**
- (none typical)

**Interviewer follow-ups**
- "Why might a small app use SQLite?"

**Practised in:** (no project; theory only)

**Verify at:** (vendor sites)

### OOP-DB-08
**Question:** What are SQL data types? Are there any differences in data types between different SQL databases?

**A good answer covers**
- each column has a type: integer types, decimal / numeric, text (`VARCHAR`, `TEXT`), boolean, date / time, …
- the standard defines common types; vendors differ (e.g. PostgreSQL `SERIAL`, `JSONB`, MySQL `TINYINT`)
- choosing types affects storage, validation and comparisons

**Common misconceptions**
- all SQL databases have the same types

**Interviewer follow-ups**
- "Why use `NUMERIC` instead of `FLOAT` for money?"

**Practised in:** Northwind Traders – Natural SELECTion, DVD Rental

**Verify at:** PostgreSQL docs, "Data Types"

### OOP-DB-09
**Question:** What are _constraints_ in SQL?

**A good answer covers**
- rules on columns / tables that the database enforces
- `NOT NULL`, `UNIQUE`, `PRIMARY KEY`, `FOREIGN KEY`, `CHECK`, `DEFAULT`
- protect data integrity regardless of the application

**Common misconceptions**
- validation in Java is enough

**Interviewer follow-ups**
- "Write a constraint that keeps prices non-negative."

**Practised in:** Book DB

**Verify at:** PostgreSQL docs, "Constraints"

### OOP-DB-10
**Question:** How can we program different SQL databases in Java?

**A good answer covers**
- JDBC: a standard API; each database provides a driver
- `Connection`, `PreparedStatement`, `ResultSet`
- higher levels: Spring JDBC (`JdbcTemplate`), JPA / Hibernate
- switching databases mostly means switching the driver and URL (SQL dialects may differ)

**Common misconceptions**
- each database needs a completely different Java API

**Interviewer follow-ups**
- "Why `PreparedStatement` rather than `Statement`?"

**Practised in:** Book DB

**Verify at:** Oracle, "JDBC Basics" tutorial
