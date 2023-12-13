### Study Notes for Software Engineering II: Lecture 8 - Review of Testing

#### I. Key Concepts
- **Main Idea 1:** Emphasizes the importance of different levels of testing, including unit, integration, and system testing, and their specific targets and focuses.
- **Main Idea 2:** Highlights regression testing and its objective to ensure existing functionalities remain unaffected by code changes.
- **Main Idea 3:** Discusses methodologies for measuring test coverage, the role of control flow graph, and introduces mutation testing.

#### II. Definitions
- **Development Testing:** Practices that aim to catch bugs during the development phase of the software lifecycle.
- **Unit Testing:** Testing aimed at verifying the correctness of individual units of source code, typically the smallest testable parts of an application.
- **Integration Testing:** Testing focused on interfaces and the interaction between integrated units/components.

#### III. Important Details
- **Point 1:** Regression testing is fundamental to identify early defects by re-running functional and non-functional tests.
- **Point 2:** Test coverage is used to determine the effectiveness of tests in covering various parts of the code.
- **Point 3:** Instrumentation is the process of adding additional code to the program to collect information about its execution (e.g., logging, AspectJ).

#### IV. Diagrams/Visual Aids
- **Diagram 1:** Control flow graph - Visually represents possible paths through a program for understanding and designing test cases.
- **Diagram 2:** Code coverage examples - Visual examples of how test cases could cover statements, branches, or paths within a code segment.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** Statement Coverage - A metric used to calculate the percentage of code executed during testing.
- **Formula/Theorem 2:** Tarantula Technique - A software diagnostics technique that visually maps executed statements to failing or passing test cases.

#### VI. Examples
- **Example 1:** Equivalence class and boundary testing with month numbers to ensure different classes of input are handled correctly.
- **Example 2:** Measuring statement coverage using a simple conditional program block.
- **Example 3:** Using Tarantula technique on given code snippets to identify potentially buggy code.

#### VII. Summary/Conclusion
- **Recap of Main Points:** Understanding the various testing methods, the importance of regression testing, and the techniques for measuring test coverage are key components of effective software testing.
- **Connections between Concepts:** Connections are made between the need for thorough testing at various development stages (unit to system) and methods to analyze the adequacy and efficiency of those tests.

#### VIII. Additional Resources
- **Textbook Pages:** Specific sections in the software engineering textbook related to testing methods and coverage measurement.
- **Online Resources:**
  - JaCoCo Tool Overview: https://www.jacoco.org/jacoco/trunk/coverage/org.jacoco.core/index.html
  - Spectrum-based fault localization: https://www.guru99.com/mutation-testing.html
  - More on Fuzzing: https://www.fuzzingbook.org/
  - Synopsys Fuzzing Guide: https://www.synopsys.com/content/dam/synopsys/sig-assets/whitepapers/what-is-fuzzing.pdf

Materials to further explore the concepts include papers on fuzzing, tutorials on code coverage tools, and methods of mutation testing from beginner to advanced levels.

---

Notes: 
Comp 4350Software Engineering IILecture 8
Dr. Shaowei Wang
Review of testing
Development testing
Unit testing
Target: particular program unit (class/method)
Focuses on testing the functionality of an object or a method
Integrating testing
Target: the combination of units that make up a component
Focuses on the interface (e.g., parameters, message passing) that a component exposes to other components
System testing
Target: the whole system
Focuses on the functional and non-functional requirements (e.g., performance, usability)




Regression testing
A software testing practice that ensures an application still functions as expected after any code changes, updates, or improvements. 

Goal
Make sure the changes in code does not break existing functional and non-functional requirement of the system.
Find defect in early stage.

Who tests the tests?
How can we measure test cases?
Outline
Test coverage
Applications for testing coverage
Mutation testing
7
Measure the test cases
Read P 
Read Q 
IF P+Q > 10 THEN 
	Print “Large” 
ENDIF 
If P > 50 THEN 
	\\ bug is here
	… 
ENDIF
Test suite A
Test case 1 P= 5, Q=10

Test suite B
Test case 1 P =5, Q=10
Test case 2 P =51, Q=4

8
Covering code (white box)
Covering input space (black box)
Two types of coverage in test coverage
9
Covering code (for white box testing)
How much code is covered by test cases?
The testing has to reach a targeted coverage of statements/branches/paths; the objective can be to:
cover all possible statements 
cover all possible branches
cover all possible (99%) paths

How to measure the coverage?
1) run test case, collect the execution information, e.g., which statements are executed?
2) program analysis – how many branches/paths in the program in theory?
3) calculate the coverage
Void Main(){
    …
    O.Func1();
    
    O.Func2();
    …
}

Void Main(){
    …
    O.Func1();
    log.info(“O.Func1 is executed”);
    O.Func2();
     log.info(“O.Func2 is executed”);
    …
}


instrumentation
Collecting execution info - instrumentation
Instrument at compile time
e.g., logging, AspectJ 
Instrument or monitor at runtime
Also requires a special VM
E.gVisualVM (hooks into JVM using debug symbols to profile/monitor)
12
2015 (c) C. Le Goues


13


14
https://www.javatpoint.com/spring-aop-aspectj-annotation-example

15
https://stackoverflow.com/questions/48470588/placing-log-information-inside-a-method-using-aspectj-spring
Collecting execution info - instrumentation
Instrument at compile time
e.g., logging, AspectJ 
Instrument or monitor at runtime
Also requires a special VM
E.g, Javassist, VisualVM (hooks into JVM using debug symbols to profile/monitor)
16
2015 (c) C. Le Goues


Java Bytecode Instrumentation 
We know that when we run our Java programs it gets converted to bytecode. 

These are then loaded to JVM using classloaders.

Bytecode instrumentation use Instrumentation APIs (Javassist) to modify the bytecodes of these programs at runtime.

How to measure the coverage?
1) collect the execution information, e.g., which statements/branches are executed?
2) program analysis – how many statements/branches in the program?
3) calculate the coverage
19
Control flow graph
In computer science, a control-flow graph (CFG) is a representation, using graph notation, of all paths that might be traversed through a program during its execution. 
Entry
Exit
Control node: Each branch in the code (such as if and while statements) creates a branch in the graph
Basic block: a straight-line code sequence with no branches in except to the entry and no branches out except at the exit.
https://www.geeksforgeeks.org/software-engineering-control-flow-graph-cfg/
20
Read P 
Read Q 
IF P+Q > 10 THEN 
	Print “Large” 
ENDIF 
If P > 50 THEN 
	Print “P Large” 
ENDIF

21
Read P 
Read Q 
IF P+Q > 10 THEN 
	Print “Large” 
ENDIF 
If P > 50 THEN 
	Print “P Large” 
ENDIF

Cover all possible statements?
 1A-2C-3D-E-4G-5H
Input: P=60, Q=10
22
Read P 
Read Q 
IF P+Q > 10 THEN 
	Print “Large” 
ENDIF 
If P > 50 THEN 
	Print “P Large” 
ENDIF

Cover all possible branches?
 1A-2C-3D-E-4G-5H
1A-2B-E-4F
Input: P=60, Q=10
Input: P=1,Q=1
23
Read P 
Read Q 
IF P+Q > 10 THEN 
	Print “Large” 
ENDIF 
If P > 50 THEN 
	Print “P Large” 
ENDIF

Cover all possible paths?
1A-2B-E-4F
1A-2B-E-4G-5H
1A-2C-3D-E-4G-5H
1A-2C-3D-E-4F
Exercise: generate the test case input to cover all paths?
Input: P=1,Q=1
Input: P=60, Q=-60
Input: P=60, Q=10
Input: P=6; Q=6
Question: How many paths?
...
for (int i = 0; i < n; ++i) {
	if (a.get(i) == b.get(i)) 
		x[i] = x[i] + 100;
	else
		x[i] = x[i]/2;
}
...
The ugly truth about testing:Large number of possible paths
...
for (int i = 0; i < n; ++i) {
	if (a.get(i) == b.get(i)) 
		x[i] = x[i] + 100;
	else
		x[i] = x[i]/2;
}
...
Number of Paths = 2n
If each test takes 10-3 seconds, with n=36, we need more time than has passed since the big bang!
How to measure coverage?
In practice, we measure statement (line) coverage
# of statements (line) being executed/ # total statements


Input: P=60, Q=10
Exercise – calculate the statement coverage


Read P 
Read Q 
IF P+Q > 10 THEN 
	Print “Large”
ELSE
	Print “Small” 
ENDIF 
If P > 50 THEN 
	Print “P Large” 
ENDIF
Input: P=60, Q=10
Print “Small”
Exercise – calculate the statement coverage


Read P 
Read Q 
IF P+Q > 10 THEN 
	Print “Large”
ELSE
	Print “Small” 
ENDIF 
If P > 50 THEN 
	Print “P Large” 
ENDIF
Input: P=60, Q=10
Print “Small”
Code coverage tools (for Java)
30
12/10/2023
Tutorials on Code Coverage Tools For Java
JaCoCo  –  free code coverage tool (current version of Cassandra, etc.)

Coverage.py  – Coverage.py is a tool for measuring code coverage of Python programs.

Cobertura  – not actively maintained any more, used in earlier version of Cassandra  

Emma – not actively maintained any more, and don’t support the current Java version

etc.
Know about JaCoCo - Features
31
12/10/2023
Tutorials on Code Coverage Tools For Java
Free code coverage tool for Java, developed as a replacement for EMMA

Coverage analysis of branches, lines, methods, and cyclomatic complexity

Several report formats (HTML, XML, CSV)

Integration with Various Tools (Ant Tasks, Maven plug-in, Gradle)





https://www.jacoco.org/jacoco/trunk/coverage/org.jacoco.core/index.html
Coverage.py
Overhead for instrumentation
Affect performance
We will cover two types of coverage
35
Covering code (white box)
Covering input space (black box)
Covering input space (for black-box testing)
Input domain for testing is infinite. 
E.g., real number in [1,1000]
Testing is fundamentally about choosing finite sets of values (i.e., a representative set of inputs) from the input domain.


36
Unit testing strategies
Equivalence classes:
Identify groups of inputs that have common characteristics (should be processed the same way)
Such groups are called equivalence classes. 
A tester needs only to run one test per equivalence class


38
Examples of equivalence classes
Valid input is a month number (1-12)
Equivalence classes are: [-∞..0], [1..12], [13.. ∞]

Valid input is one of ten strings representing a type of fuel
Equivalence classes are
10 classes, one for each string
A class representing all other strings
Don’t forget Null/empty

File upload with different size (up to 1G):
Equivalence classes are
Small file uploads (less than 1MB).
Medium-sized file uploads (1MB to 100MB).
Large file uploads (100MB to 1G).
Over size (> 1G)


Rule of thumb

Boundary testing: This involves testing input values that are close to the minimum or maximum values that the system can handle. This can help you find errors or unexpected behavior near the boundaries of the input range.
Negative testing: This involves providing input that is known to be incorrect or outside the expected range, and testing that the system behaves appropriately, such as by rejecting the input or providing a useful error message. 
Input validation testing: This involves testing the input validation logic in your system to ensure that it properly rejects invalid input and handles input errors. (e.g., password formatting error)

Application
Application based on code coverage:
Spectrum-based fault localization
40
Fault Localization
Problem: Given a set of test cases, one or several test cases fail, where are the buggy lines?
41

System
Test suite



where are the bugs?
Fault Localization
Problem: Given a set of test cases, one or several test cases fail, where are the buggy lines?
42
Test cases
int mid (x, y, z) {
}
Coverage-based Fault localization
Intuition: Statements that are primarily executed by failed test cases are more likely to be faulty than those that are primarily executed by passed test cases 
Solution: Ranking based on suspiciousness (Tarantula)
43
S: statement
number of failing test cases is executed by s
number of  passing test cases is executed by s
An Example of Using Tarantula
44
Only running on 1/5 of the pass cases.
Running on all the pass cases.
45
Other ranking formulars
cef indicates the number of failing test cases (f) is executed by  a program entity (c), cnf is the number of failing test cases is not executed (n) by a program entity 
Totalfail = cef  +  cnf 
cep is the number of passing test cases (p) is executed by a program entity and cnp represents the number of passing test case is not executed by a program entity
Total pass = cep + cnp
Exercise
46
cef indicates the number of failing test cases (f) is executed by  a program entity (c), cnf is the number of failing test cases is not executed (n) by a program entity, cep is the number of passing test cases (p) is executed by a program entity
Exercise
47
cef indicates the number of failing test cases (f) is executed by  a program entity (c), cnf is the number of failing test cases is not executed (n) by a program entity, cep is the number of passing test cases (p) is executed by a program entity

Materials
https://www.synopsys.com/content/dam/synopsys/sig-assets/whitepapers/what-is-fuzzing.pdf
https://www.fuzzingbook.org/
https://www.guru99.com/mutation-testing.html
https://www.softwaretestinghelp.com/what-is-mutation-testing/

48
