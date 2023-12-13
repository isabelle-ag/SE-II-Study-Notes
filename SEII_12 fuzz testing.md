### Study Notes for Advanced Topic in Fuzz Testing

#### I. Key Concepts
- **Main Idea 1:** Fuzz Testing (Fuzzing) involves automatically generating numerous random inputs to a program, potentially leading to discoveries of bugs, crashes, and bad behavior without a predetermined oracle.
- **Main Idea 2:** The approach to fuzz testing includes constructing invalid, abnormal, or random inputs, running the program with these inputs, and monitoring for bugs and system errors.
- **Main Idea 3:** Applying Fuzz Testing to modern applications like self-driving systems challenges test case generation due to the infinite space problem - the need to create inputs that are likely to trigger bugs.

#### II. Definitions
- **Fuzz Testing:** A software testing technique used to find security vulnerabilities by automatically feeding invalid, unexpected, or random data into the system.
- **Oracles for Fuzz Testing:** A mechanism or set of guidelines used in software testing to determine whether a test has passed or failed.
- **Differential Fuzzing:** A method that provides the same input to a series of similar applications (or different implementations of the same application) and looks for differences in execution to find bugs.

#### III. Important Details
- **Point 1:** Fuzz testing has various approaches like Random, Template-based, and Mutation-based generation of test cases.
- **Point 2:** Template-based test cases are more effective because they can pass parser checks and resemble valid inputs that trigger deeper system behavior.
- **Point 3:** Mutation-based fuzzing involves altering existing inputs slightly, while guided mutation-based fuzzing uses system feedback to refine the mutations.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** A flowchart describing the process of mutation-based fuzzing from seed creation to the evaluator, highlighting the mutation process and selection of candidates.
- **Diagram 2:** Dataflow graphs representing the program's computational paths during fuzz testing, providing insights into API calls and potential bugs.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** FitnessFunction(𝐶) = D + U − R, a function used to evaluate the effectiveness of fuzz test programs based on the depth of execution paths, diversity, and the complexity of API invocations.
- **Formula/Theorem 2:** Bernoulli Bandit Problem Algorithm, a solution to select mutation operators that likely generate valid and unique code snippets during fuzz testing.

#### VI. Examples
- **Example 1:** A step-by-step explanation of how a fuzz test is conducted using random test generation and the typical lack of effectiveness without additional strategies.
- **Example 2:** Illustrations of how template-based and mutation-based fuzz testing can generate more relevant and penetrating test cases.
- **Example 3:** An example of a fitness function application to assess and rank generated test programs' potential in covering more code and detecting bugs.

#### VII. Summary/Conclusion
- **Recap of Main Points:** The study focuses on fuzz testing techniques and their application to automated software testing, emphasizing the importance of generating relevant test cases to trigger bugs.
- **Connections between Concepts:** The noted approaches demonstrate a gradient from random through template-based to mutation-based fuzzing, each building upon the previous to increase efficacy in uncovering software vulnerabilities.

#### VIII. Additional Resources
- **Textbook Pages:** Not specified.
- **Online Resources:** 
  - Fuzzing Book Website: [FuzzingBook.org](https://www.fuzzingbook.org/)
  - GitLab Documentation on Coverage Fuzzing: [GitLab Coverage Fuzzing](https://docs.gitlab.com/ee/user/application_security/coverage_fuzzing/)
  - Research on using LLM for Fuzzy Testing: [Large Language Models are Zero-Shot Fuzzers (PDF)](https://arxiv.org/pdf/2212.14834.pdf)

**Notes:** The study notes have been adapted for an advanced class on fuzz testing taught by instructor Shaowei Wang. Administrative details include the final presentation being scheduled on Nov 30, Dec 5, and Dec 7 and involve a brief recap, demo, and discussion of the development process as part of project evaluation by peer teams and the instructor with a 7:3 weightage. Additional details about the project presentation can be found in the linked Google Spreadsheet and under the Final project presentation section on the Assignments page.

---

Notes: 
Advanced topicFuzzy testing
Instructor: Shaowei Wang
Administrative item
Final presentation will be on Nov 30 (Thursday), Dec 5 (Tuesday), and Dec 7 (Thursday)
See schedule in google spreadsheet https://docs.google.com/spreadsheets/d/1ewp5bUNU8EbpPAQqRLjMIKLyGNiLejSgUvC55txSoIA/edit#gid=0 
Each team will give a ~20 minutes presentation to introduce their project to the class, plus 2 minutes Q&A.
Quick recap of the project (~1-2 minutes)
Demo of the project (~8-10 minutes)
Discussion of the development process (~7-8 minutes).
We will invite all other teams to evaluate the project and rank them. 
The weight between students and instructor is 7:3.
More details @Assignments ->Final project presentation 

Outline
Fuzz testing
Research in fuzz testing
Fuzz Testing (Fuzzing)
Generates lots of random inputs automatically (including invalid/abnormal) to a program to discover bad behavior such as crashes (without oracle)

4
Fuzz Testing (Fuzzing)
Approach
Construct random/invalid/abnormal inputs 
Run programs using random/invalid/abnormal inputs
Monitor system behavior and Identify bugs 
Errors found: 
Array indices out of bounds, not checking null pointers, …
5
Applying fuzz testing to …
Recent: Testing self-driving system


6
Fuzz images
For any piece of software, the set of invalid inputs is unbounded
Test cases generator must be clever enough to craft test cases that are most likely to trigger bugs in the target software
7
Fuzzing is an infinite space problem
How to generate the test cases?
Generator-based:
Random
Template-based
Mutation-based
8
Randomly generate test case
Random fuzzing is usually ineffective because the test cases are nothing like valid input.
For the most part, the test cases fail to penetrate into the target code
E.g., login function, e.g., notmecome, wrongcode!124

9
Random
10
A template  generator creates test cases based on template and introduces anomalies into valid inputs to create test cases
grammar-based or protocol-base 
In general, template test cases are much more effective than random test cases because they are mostly pass program parser checks.
11
Template-based
We use specific grammar to define the templates
A grammar consists of a start symbol and a set of expansion rules (or simply rules) which indicate how the start symbol (and other symbols) can be expanded. 
https://www.fuzzingbook.org/html/Grammars.html
As an example, consider the following grammar, denoting a sequence of two digits, eventually yielding value between 00 and 99.
We use specific grammar to define the templates
13
https://www.fuzzingbook.org/html/Grammars.html
How to generate the test cases?
Generator-based:
Random
Template-based
Mutation-based
14
Mutation-based
Introducing small changes to existing inputs that may still keep the input valid, yet exercise new behavior. 
https://www.fuzzingbook.org/html/MutationFuzzer.html
Mutation: Insertion, deletion, and replacement
Guided Mutation-based
Leverage target system feedback to refine the mutation operation.
Seed (initial candidates)
mutation
Mutated candidates
Target system
Selected candidates
Evaluator (time/coverage) 
Types of failure
Crashes
Endless loops
Resource leaks or shortage
…

17
Oracles for fuzz testing
https://www.fuzzingbook.org/
https://docs.gitlab.com/ee/user/application_security/coverage_fuzzing/
Research on using LLM for fuzzy testing
Large Language Models are Zero-Shot Fuzzers: Fuzzing Deep-Learning Libraries via Large Language Models, by Zhang et al.

Goal: Generate a large amount of test code containing a set of target APIs 
For instance, our target library is tensorflow, the approach uses the LLM to generate a large number code containing APIS in tensorflow, for finding bugs in tensorflow

https://arxiv.org/pdf/2212.14834.pdf
LLM-based fuzzy generation
Key insight is that 
modern LLMs can include numerous code snippets using various DL libraries in their training corpora (e.g., there are >400,000 TensorFlow/PyTorch projects on GitHub, which is an important training source for modern LLMs)
allowing them to implicitly learn both Python syntax/semantics and intricate types/constraints of DL APIs to directly generate/mutate valid DL programs for fuzzing DL libraries.

Generate code for tensor operation



Overview of the approach

Starting from a seed program generated by LLM


Overview of the approach

Perform mutation operation to generate more program for testing
The masked out (<SPAN>) regions in the code, then feed into the InCoder model to infill the masked regions with sampling.

Argument: replace mutation operator which replaces the API call arguments with the span token
Prefix and suffix mutation operators: choose a code segment (spanning one or multiple lines) before or after the target API invocation to insert the span token. 
Method: replaces a randomly chosen library API method name with a span token.
Mutation Operator Selection – how? 
We have multiple mutation operations (argument, prefix/suffix, method)
The assumption is that the mutation operator that works well (e.g., generating more bug triggering mutants) can be different for different DL APIs. 

Objective: generating program from seed code snippets using mutation that that are valid and different from historical generations.
Mutation Operator Selection – how? 
Question: we do not have any prior knowledge which mutation can achieve the objective. How can we identify mutation operators that help generate more valid and unique code snippet?
We need to estimate the probability of an operators resulting in a more valid and unique code snippets during the fuzzing.


We formulate the question as Bernoulli bandit problem.

Bernoulli bandit problem

Algorithm


Overview of the approach

Fitness function
Design a fitness function and score to rank each generated program.
The intuition behind the fitness calculation is to give higher scores to the generated mutation programs with
deeper execution path
more diverse computation graph
more complicated API invocations

Depth of dataflow graph
Dataflow graph with each edge representing data dependencies between two operations. 
The depth of the dataflow graph (D) is defined as the maximum number of edges in any path of the graph
Number of API calls
We count the number of unique library API calls (U) that exist within each code snippets. 
Since LLM tends to generate many code snippets where code line(s) are repeated, we also count and penalize the number of library APIs that are repeatedly called with the same inputs (R).

FitnessFunction(𝐶) = D + U − R
Oracle
Execute the generated code snippets on CPU and GPU, record all the variables including the intermediate ones, and detect potential bugs. 
Wrong-Computation: Difference in computed values can indicate a potential semantic bug in different backend implementations of a library API or interactions between different APIs.
Crash: During program execution, we also detect unexpected crashes, e.g. segmentation faults, aborts, INTERNAL_ASSERT_FAILED errors. Such crashes indicate failures to check or handle invalid inputs or corner cases, and can lead to security risks.


Differential fuzzing
Differential testing,[1] also known as differential fuzzing, is a popular software testing technique that attempts to detect bugs, by providing the same input to a series of similar applications (or to different implementations of the same application), and observing differences in their execution
Coverage 
The effectiveness of operation selection algorithm

Bugs detected


Summary
Generator-based:
Random
Template-based
Mutation-based
Research on fuzzy testing

