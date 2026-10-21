# oop-java-platform

Module 3 · OOP with Java · workbook section "Java ecosystem" (OOP-ECO-01 – OOP-ECO-04).
Source: the module's Tech Interview Workbook. Rubrics drafted 2026-10-19; flagged items reviewed by the mentor, full review in progress.
Rubrics are for the agent only: never show them or turn them into a model answer (see AGENTS.md).

### OOP-ECO-01
**Question:** What is the JVM?

**A good answer covers**
- the Java Virtual Machine runs compiled bytecode
- platform independence: same bytecode, a JVM per OS ("write once, run anywhere")
- memory management with garbage collection
- JIT compilation to native code at runtime

**Common misconceptions**
- "the JVM runs `.java` source files"

**Interviewer follow-ups**
- "Why can other languages (Kotlin, Scala) run on the JVM?"

**Practised in:** What is OOP?, Java basics

**Verify at:** Oracle, "The Java Virtual Machine Specification" (introduction); dev.java, "Getting Started"

### OOP-ECO-02
**Question:** What does Java compilation mean?

**A good answer covers**
- `javac` turns `.java` source into `.class` bytecode
- type checks and syntax errors are caught at compile time
- the JVM then runs the bytecode (with JIT at runtime)
- build tools (Maven, Gradle) run this for you

**Common misconceptions**
- Java compiles straight to machine code

**Interviewer follow-ups**
- "Name an error the compiler catches and one it can't."

**Practised in:** Java basics

**Verify at:** dev.java, "Compiling and running a Java program"

### OOP-ECO-03
**Question:** What is Java bytecode?

**A good answer covers**
- the instruction set of the JVM, stored in `.class` files
- platform-independent intermediate code
- interpreted or JIT-compiled by the JVM

**Common misconceptions**
- bytecode is readable Java

**Interviewer follow-ups**
- "Where do the `.class` files end up in your project?"

**Practised in:** Java basics

**Verify at:** Oracle, "The Java Virtual Machine Specification", ch. 1

### OOP-ECO-04
**Question:** What is the difference between the JRE and the JDK?

**A good answer covers**
- JRE: what you need to **run** Java (JVM + core libraries)
- JDK: JRE + development tools (`javac`, debugger, `jar`, …)
- developers install the JDK
- (modern Java distributes the JDK; a separate JRE is less common)

**Common misconceptions**
- JDK and JVM are the same

**Interviewer follow-ups**
- "What does a server that only runs your app need?"

**Practised in:** Java basics

**Verify at:** Oracle / dev.java, JDK documentation overview
