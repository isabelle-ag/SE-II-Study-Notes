### Study Notes for Comp 4350: Software Engineering II - Lecture 9 (Mutation Testing)

#### I. Key Concepts
- **Main Idea 1:** Mutation Testing introduces small changes to program code (mutants) to assess the effectiveness of test cases.
- **Main Idea 2:** The goal is to ensure that the mutants are detected (killed) by the test cases, indicating that the tests can find small errors.
- **Main Idea 3:** A high mutation score reflects the adequacy of the test suite in detecting bugs.

#### II. Definitions
- **Mutation Testing:** A method to test the quality of software tests by introducing changes and checking if tests detect these changes.
- **Mutants:** Slight variations of the program code to simulate potential bugs.
- **Mutation Score:** A quantitative measure (percentage) of how many mutants are detected by the test suite.

#### III. Important Details
- **Point 1:** Mutation testing does not directly measure how much code is covered, but rather the effectiveness of test cases in bug detection.
- **Point 2:** Mutants should be representative of realistic types of faults that could occur in practice.
- **Point 3:** Equivalent mutants represent syntactic changes that do not affect the program's functionality and thus cannot be detected by any test case.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** Example code with a simple `max()` function and corresponding mutants.
- **Diagram 2:** Mutation test process flowchart, from creating mutants to evaluating the test suite's effectiveness.
- **Diagram 3:** Visualization of mutation score calculation.

#### V. Key Formulas/Theorems
- **Mutation Score Formula:** The percentage of killed mutants (D) over the total number of non-equivalent mutants (N - E).
- **Competent Programmer Assumption:** Presupposes that most software faults by experienced programmers are due to small syntactic errors.
- **Coupling Effect Assumption:** Small changes can have a cascading impact, leading to the manifestation of complex errors.

#### VI. Examples
- **Example 1:** Mutation testing on a `max()` function with input sets to detect bugs.
- **Example 2:** Application of different mutation operators on a `min()` function and detecting the induced bugs.
- **Example 3:** Step-by-step guide for enhancing test suites with mutation testing in an interactive program.

#### VII. Summary/Conclusion
- **Recap of Main Points:** Mutation testing helps in evaluating test case effectiveness by checking their ability to kill mutants, which represent potential faults in the code.
- **Connections between Concepts:** The concept combines software testing technique with fault modeling and code coverage principles.

#### VIII. Additional Resources
- **Textbook Pages:** Further reading on mutation testing concepts and techniques may be available in specific software engineering textbooks.
- **Online Resources:** 
  - [TechTarget Mutation Testing Definition](https://www.techtarget.com/searchitoperations/definition/mutation-testing)
  - [Guru99 Mutation Testing Guide](https://www.guru99.com/mutation-testing.html)

---

Notes: 
Comp 4350Software Engineering IILecture 9
Dr. Shaowei Wang
Outline
Test coverage
Applications for testing coverage
Faulty localization
Mutation testing

An Example of Using Tarantula
3
Only running on 1/5 of the pass cases.
Running on all the pass cases.
Outline
Test coverage
Applications for testing coverage
Faulty localization
Mutation testing

5
Mutation testing
Measuring Test Cases
What we have learned so far?
Quantitatively measure how much code is covered by test cases?
Do the coverage metrics directly measure the effectiveness of test cases (where your test case could detect bug)?
No. 
Test Case Effectiveness
Detecting bug is the most effective way to measure test case.
Test suite A can detect more bugs than test suite B.
Given one bug, some test cases in suite A fail, but all test cases in suite B pass.
The best test suite can detect every bug; whenever a bug is introduced, at least one test case will fail.
7
What if we manually inject bugs and let the test cases to detect?
8
Mutation testing
Mutation testing
Artificially inject bugs by modifying (mutating) some statements in the code, so we have many different versions of the code. Each version has a bug.
Check if the test cases can find the bugs, i.e., some test cases fail and some do NOT fail.
9

int max(int x, int y){
int Max;
if (x > y)
	Max = x;
else
	Max = y;
return Max;
}
Input sets:
{x=3, y=2;}  => return 3 => cannot detect bug
 {x=3, y=2; x=2, y=3} => always return 2, detect the bug

int max(int x, int y){
int Max;
if (x > y)
	Max = x;
else
	Max = x;   // mutant
return Max;
}
Steps in Mutation Testing
Input: an original program and a target test suits
Step 1: Modify statements in the original program and create a number of variates (i.e., mutants).
E.g., “z = y + x” is modified to “z = y - x”
“if (x >= y)” is modified to “if (x > y)”, and vice versa.
Step 2: Test cases are run through the each generated mutant.
Step 3: Compare the results of the original and the mutant.
Step 4:  
=>The mutant is killed if different results are found (i.e., dead mutant). The test suite is good as it detects the change (i.e., injected defect).  
=> The mutant is alive if the results are the same: the test suite is NOT effective.
11
Mutation Testing
For the automated generation of mutants, we use mutation operators, i.e., predefined program modification rules (corresponding to a fault model)

one mutant = one syntactic change introduced at a time
Simple Example – mutation operations
int min(int a, int b) {
   int minVal = a;
   if (b < a) {
      minVal = b;
   }
   return minVal;
}
      Original code:  			            Mutants:
Specifying Mutation Operators
Ideally, we would like the mutation operators to be representative of (and generate) all realistic types of faults that could occur in practice

Mutation operators change with programming languages, design and specification paradigms (much overlap though)

In general, the number of mutation operators is large as they are supposed to capture all possible syntactic variations in a program

Example of Mutation Operators
Statement deletion
Statement duplication
Statement insertion
Replacement of Boolean expressions with true or false
Replacement of arithmetic operations with others (e.g., + with *, - with /)
Replacement of conditional expressions (e.g., > with ≥, == with ≤)
Negation of conditional expressions
Replacement of variables (must be type compatible)
Replacement of constant with variable or vice versa
Replacement of array reference with constant or variable or vice versa
Replace increments with decrements or vice versa
Replace constructor calls with null
Replacement of return statement
For a compete list supported by the Pitest tool: see http://pitest.org/quickstart/mutators/
Example of Mutation Operators
Specific to object-oriented programming languages:
Replacing a type with a compatible subtype (inheritance)
Changing the access modifier of an attribute or method
Changing the instance creation expression (inheritance)
Changing the order of parameters in the definition of a method
Changing the order of parameters in a call
Removing an overloading method
Reducing the number of parameters
Removing an overriding method
Mujava
Class level mutation 
Method level mutation









17

https://cs.gmu.edu/~offutt/mujava/
Type of mutation testing
Statement mutation
developer cut and pastes a part of a code of which the outcome may be a removal of some lines
Value mutation
values of primary parameters are modified
Decision mutation
Control statement are to be changed
Mutation coverage

Mutation Score = 100 * D / N 
D: Dead mutants (killed mutants)
N: Number of mutants
A set of test cases is mutation adequate if its mutation score is 100%.

Number of mutants tends to be large, even for small programs.

If not all mutants are killed, enhance your test suit.
Why some mutants still remain live?
Why some mutant still remain live?
The test set is inadequate to kill the mutant (the test set does not cover the modified spots). For this case, the test data need to be  re-examined, possibly augmented (increase test set) to kill the live mutant



int max(int x, int y){
int Max;
if (x > y)
	Max = x;
else
	Max = y;
return Max;
}
Input sets:
{x=3, y=2;}  => return 3 => cannot detect bug, because the mutated statement is not executed.

int max(int x, int y){
int Max;
if (x > y)
	Max = x;
else
	Max = x;   // mutant
return Max;
}
Why some mutant still remain live?
The test set is inadequate to kill the mutant (the test set does not cover the modified spots). For this case, the test data need to be  re-examined, possibly augmented (increase test set) to kill the live mutant

It is equivalent to the original program (functionally identical though syntactically different – equivalent mutant)


Example – Equivalent mutants 
int min(int a, int b) {
   int minVal = a;
   if (b < a) {
      minVal = b;
   }
   return minVal;
}
      Original code:  			            Mutants:
Mutation coverage

Mutation Score = 100 * D / (N - E) 
D: Dead mutants (killed mutants)
N: Number of mutants
E: Number of equivalent mutants
However, detecting equivalent mutants is challenging.
Use constraints to Detect Equivalent Mutants 
Example – Equivalent mutants 
int min(int a, int b) {
   int minVal = a;
   if (b < a) {
      minVal = b;
   }
   return minVal;
}
      Original code:  			            Mutants:
Mutation coverage

Mutation Score = 100 * D / (N - E) 
D: Dead mutants (killed mutants)
N: Number of mutants
E: Number of equivalent mutants
However, detecting equivalent mutants is challenging.
Use constraints to Detect Equivalent Mutants 
Avoid generating equivalent mutants
Example – Equivalent mutants 
int min(int a, int b) {
	…
   int x = y +x;
	…
	x = 0; /*re-initialize */
	…
	return x;
}
      Original code:  			            Mutants:
Assumptions for mutation testing
What about more complex errors, involving several statements?

Competent programmer assumption:most software faults introduced by experienced programmers are due to small syntactic errors
Coupling effect assumption:simple changes can lead to complex errors
Different Mutants
Equivalent mutant: always produces the same output as the original program

Stillborn mutant: syntactically incorrect, killed by compiler




Example - Stillborn mutant
int min(int a, int b) {
   int minVal = a;
   if (b < a) {
      minVal = b;
   }
   return minVal;
}
      Original code:  			            Mutants:
Return type of failOnZero() is String
Different Mutants
Equivalent mutant: always produces the same output as the original program

Stillborn mutant: syntactically incorrect, killed by compiler

Trivial mutant: killed by almost any test case (i.e., covered by every test case)




Example - Trivial mutant
public int getMin ( int [] numbers ) { 
	int min = numbers [0]; 
	for ( int i =1; i < numbers.length; ++ i ) { 
		if (numbers[i] < min) {  
			min = numbers [ i ]; 
		} 
	} 
	return min ;
}
      Original code:  			            Mutants:
A=[1,2,3,4,5] fail
B=[1,1,3,56,0] fail
What is the condition for a test case to trigger a mutant?
Reachability: reach the fault seeded (mutated code) during execution 
E.g., one branch is not covered
Infection: Cause the program state to be incorrect 
 E.g., equivalent mutant
Propagation Cause the program output to be incorrect
E.g., the incorrect state is re-initialized






1. int min(int A, int B)
2. { // original
  int minVal;
  minVal = A; 
  if (B < A) {
6.     minVal = B;
7.   }
8.   return minVal;
9. }

1. int min(int A, int B)
2. { // mutant
  int minVal;
4.1  minVal = B; 
  if (B < A) {
4.     minVal = B;
  }
  return minVal;
7. }
Replace one varirable 
with another
Reachability: unavoidable
Propagation: wrong minVal needs to return to the caller; that is we cannot execute the body of the if statement, so need B >= A
Infection: need B != A
Test case => B>A
Example –use mutation testing to enhance test cases
The program prompts the user for a positive number in the range of 1 to 20 and then for a string of that length. The program then prompts for a character and returns the position in the string at which the character was first found or a message indicating that the character was not present in the string. 
The user has the option to search for more characters. 

FindPos(x, a, c){
//a is the given string, x is the length of a, c is the target character
	…
	if (x > 20 || x<1)
		print(“input integer between 1 and 20”)
found := FALSE;
i := 1;
x = sizeof(a)
while(not(found) and (i  x)) do
begin
	if a[i] = c then
		found := TRUE
	else
		i := i + 1
end
	…
}
Test Cases
x is the length of the string
a is the string
c is the character we are looking for
Response indicates whether we want to continue the search
   Original code:







Mutant 1
Re-run original test data set
Failure: “character a appears at position 1” != n

Mutant 1  is killed.
FindPos(x, a, c){
	…
		if (x > 20 || x<1)
		print(“input integer between 1 and 20”)
found := FALSE;
i := 1;
x = sizeof(a)
while(not(found) and (i  x)) do
begin
	if a[i] = c then
		found := TRUE
	else
		i := i + 1
end
	…
}
Mutant 2
Running our original test data set fails to reveal the fault
Mutant is not killed  test cases are not adequate
Need to increase our string length and search for a character further along it. 
   Original code:







FindPos(x, a, c){
	…
		if (x > 20 || x<1)
		print(“input integer between 1 and 20”)
found := FALSE;
i := 1;
x = sizeof(a)
while(not(found) and (i  x)) do
begin
	if a[i] = c then
		found := TRUE
	else
		i := i + 1
end
	…
}
FindPos(x, a, c){
	…
		if (x > 20 || x<1)
		print(“input integer between 1 and 20”)
found := FALSE;
i := 1;
x = sizeof(a)
while(not(found) and (i  x)) do
begin
	if a[i] = c then
		found := TRUE
	else
		i := i + 1
end
	…
}
Mutant 2
Running our original test data set fails to reveal the fault
   Original code:







Failure: “Character v does not occur in string” 

Mutant is killed  test cases are adequate

FindPos(x, a, c){
	…
		if (x > 20 || x<1)
		print(“input integer between 1 and 20”)
found := FALSE;
i := 1;
x = sizeof(a)
while(not(found) and (i  x)) do
begin
	if a[i] = c then
		found := TRUE
	else
		i := i + 1
end
	…
}
Mutant 3
Again, our test data fails to kill the mutant
Need to augment the test data to search for a character in the middle of the string.
   Original code:

Failure: “Character v does not occur in string” 
FindPos(x, a, c){
	…
		if (x > 20 || x<1)
		print(“input integer between 1 and 20”)
found := FALSE;
i := 1;
x = sizeof(a)
while(not(found) and (i  x)) do
begin
	if a[i] = c then
		found := TRUE
	else
		i := i + 1
end
	…
}
Mutation Testing: summary
Measures the quality of test cases

Provides the tester with a clear target (mutants to kill)

Computationally intensive, a possibly very large number of mutants is generated
It is not appliable for black box testing

Refenrece 
https://www.techtarget.com/searchitoperations/definition/mutation-testing#:~:text=Mutation%20testing%2C%20also%20known%20as,cause%20errors%20in%20the%20program.
https://www.guru99.com/mutation-testing.html

