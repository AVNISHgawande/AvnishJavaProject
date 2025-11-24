# Campus Course & Records Manager (CCRM)

A comprehensive Java console application for managing students, courses, enrollments, and grades in an educational institution.

---

## Features

* Student Management (add, list, update, deactivate)
* Course Management (add, list, update, deactivate, search)
* Enrollment Management (enroll, unenroll with business rules)
* Grade Management (record marks, compute GPA)
* File Operations (import/export CSV, backup with NIO.2)
* Transcript Generation
* Backup and Recovery

---

## Evolution of Java

* **1995**: Java 1.0 released by Sun Microsystems
* **1997**: Java 1.1 with JDBC, RMI, and reflection
* **2000**: Java 1.3 with HotSpot JVM
* **2004**: Java 5 with generics, annotations, autoboxing
* **2014**: Java 8 with lambdas, streams, new date/time API
* **2017**: Java 9 with module system
* **2018**: Java 11 as LTS version
* **2021**: Java 17 as current LTS version
* **2023**: Java 21 with virtual threads

---

## Java Platforms Comparison

| Platform | Full Name | Purpose | Key Features |
| :--- | :--- | :--- | :--- |
| Java SE | Standard Edition | Desktop and server applications | Core Java libraries, JVM, development tools |
| Java EE | Enterprise Edition | Enterprise applications | Servlets, JSP, EJB, JMS (now Jakarta EE) |
| Java ME | Micro Edition | Mobile and embedded devices | Limited libraries for constrained environments |

---

## Java Architecture

* **JDK (Java Development Kit)**: Development environment including compiler, debugger, and other tools
* **JRE (Java Runtime Environment)**: Runtime environment for executing Java applications
* **JVM (Java Virtual Machine)**: Executes Java bytecode, provides platform independence

The JDK contains the JRE, which contains the JVM. Developers use the JDK to create applications, which run on the JRE using the JVM.

---

## Installation on Windows

1.  Download JDK from Oracle's website
2.  Run the installer and follow the instructions
3.  Set `JAVA_HOME` environment variable to JDK installation path
4.  Add `%JAVA_HOME%\bin` to `PATH` environment variable
5.  Verify installation with `java -version` in command prompt

---

## Eclipse IDE Setup

1.  Download Eclipse IDE for Java Developers
2.  Extract to a folder and run `eclipse.exe`
3.  Create a new Java project
4.  Configure JDK in project properties
5.  Create packages and classes as needed

---

## How to Run

1.  **Clone the repository.**
2.  **Navigate to the project directory:**
    `cd MYINSTITUTEPROJECT`
3.  **Compile:**
    `javac -d bin src/com/myinstitute/cli/*.java src/com/myinstitute/core/*.java src/com/myinstitute/data/*.java src/com/myinstitute/exceptions/*.java src/com/myinstitute/records/*.java src/com/myinstitute/services/*.java src/com/myinstitute/utils/*.java`
4.  **Run:**
    `java -cp bin com.myinstitute.cli.Main`

---

## Mapping Table: Syllabus Topics to Code

This table maps the project's requirements from the syllabus to the specific files where they are implemented.

| Syllabus Topic | File/Class/Method |
| :--- | :--- |
| **Encapsulation** | `Learner.java`, `Module.java` (private fields with getters/setters) |
| **Inheritance** | `Entity.java` (parent class for other entities) |
| **Abstraction** | `Entity.java` (abstract class with abstract methods) |
| **Polymorphism** | `Entity` class references to `Learner` and `Module` objects |
| **Singleton Design Pattern** | `AppCore.java` |
| **Builder Design Pattern** | `Learner.java` (nested Builder class) |
| **Custom Exceptions** | `MaxUnitLimitExceededException.java`, `DuplicateRegistrationException.java` |
| **Streams API** | `AcademicReportGenerator.java`, `LearnerService.java` (use of `stream()` and `filter()`) |
| **NIO.2 File I/O** | `FileHandler.java` |
| **Date/Time API** | `Registration.java` (uses `LocalDate`) |
| **Enums** | `Module.java` (`Semester`), `Assessment.java` (`Grade`) |
| **Recursion** | `FileHandler.java` (recursive method for backup size) |
| **Interfaces** | `Persistable`, `Searchable` |
| **Lambdas** | `LearnerService.java` (`stream().map()`) |

---

## Usage and Sample Data

* **Import data:** Use the menu option to import `learners.csv` and `modules.csv` from the `test-data` folder.
* **Export data:** Use the menu option to export current data to the `data` folder.
* **Backup data:** Use the backup command to create a timestamped folder with a copy of your exported data.

### Notes on Assertions

Assertions are used in the code to check for invariants, such as ensuring non-null IDs or correct credit bounds. To enable assertions when running the application, use the `-ea` flag.

**Example:**
`java -ea -cp bin com.myinstitute.cli.Main`