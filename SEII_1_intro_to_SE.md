### Study Notes for Comp 4350: Software Engineering II, Lecture 1

#### I. Key Concepts
- **Main Idea 1:** Introduction to the course, instructor, and the educational focus on data mining, machine learning, and other software engineering methodologies.
- **Main Idea 2:** Essentials of course communication details, office hours, and course format which includes lectures, Q&A, and regular updates on UMLearn.
- **Main Idea 3:** Detailed explanation of the course project, its requirements, and evaluation method, emphasizing the hands-on experience of DevOps and software quality assurance.

#### II. Definitions
- **DevOps:** A set of practices that combines software development and IT operations to shorten the development life cycle and provide continuous delivery with high software quality.
- **Software Quality Assurance (SQA):** Consists of a means of monitoring the software engineering processes and methods used to ensure quality.

#### III. Important Details
- **Point 1:** Course communication primarily through UMLearn and direct email with Dr. Shaowei Wang; course materials and announcements will be posted on UMLearn.
- **Point 2:** Project-driven course structure—students will form teams to develop a web application incorporating DevOps tools and meet specified requirements.
- **Point 3:** A detailed breakdown of project tracking and evaluations—submission of project proposals, progress tracking through sprints, seminars for technique sharing, and final project presentation and deliverables.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** N/A for this session.
- **Diagram 2:** N/A for this session.
- **Diagram 3:** N/A for this session.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** N/A for this session.
- **Formula/Theorem 2:** N/A for this session.
- **Formula/Theorem 3:** N/A for this session.

#### VI. Examples
- **Example 1:** Team project evaluation based on individual contributions—illustrative distribution of marks depending on members' percentage of contribution.
- **Example 2:** Usage of GitHub for version control, code review, and discussion tracking in project management.
- **Example 3:** Applying agile methodologies like Scrum to software engineering projects for iterative and incremental development.

#### VII. Summary/Conclusion
- **Recap of Main Points:** Introduction to the course, the significance of data analytics, machine learning in SE, course communication methods, project focus, and evaluation criteria have been outlined.
- **Connections between Concepts:** The course integrates principles of SQA, DevOps, and agile methodologies to emphasize the importance of systematic, rigorous, and measurable software development.

#### VIII. Additional Resources
- **Textbook Pages:** Check UMLearn for uploaded recommended textbooks under Content->Recommended text books.
- **Online Resources:** Visit https://sites.google.com/view/mambalab for instructor resources and engage in team collaboration through the specified Google Docs sheet for team information.

Notes:
- Doctor Shaowei Wang specializes in data mining and software engineering.
- Key topics include DevOps principles, software security, and advanced testing techniques.
- The final exam contributes to 40% and the project to 60% of the course evaluation.
- The project demands practical demonstration of learned skills and includes multiple assessments.
- Use of generative AI tools is allowed for assignments but needs proper documentation and referencing.

---

Notes: 
Comp 4350Software Engineering IILecture 1
Dr. Shaowei Wang
Research into data mining and software engineering
Machine learning for software engineering (e.g., API recommendation, code completion)
data analytics on software artifacts (e.g., Stack Overflow, GitHub, AppStore)
auto debugging (e.g., bug localization, fault localization)
Software security
Contact
shaowei.wang@umanitoba.ca
https://sites.google.com/view/mambalab
2
About me (Shaowei Wang)
About the course
3
Course website
On UMLearn 
Check regularly for announcements and updates
Lectures
60 mins lecture + 15mins Q&A
All slides will be posted on UMLearn after class
4
Contact & Office Hours
Dr. Shaowei Wang
Tuesday 9am-11am, EITC-E2-408
TAs:
Xu Yang <yangx4@myumanitoba.ca>Office hour: TBD
Shayan Daneshvar <daneshvs@myumanitoba.ca>Office hour: TBD
Cody Wallbridge <wallbric@myumanitoba.ca>Office hour: TBD




What are we doing here?
What are we doing here?
Cover topics:
DevOps
Configuration management 
Continuous integration
Continuous deployment
AI for DevOps
Architecture
microservice
Software quality assurance
Advanced testing
Mutation testing
Load testing
Performance testing
…
Security analysis
Refactoring 
Research in software engineering 
Machine learning for software engineering
Data-driven software engineering
…

6
Recommend Books
Uploaded on UMLearm (Content->Recommended text books)
7





How will the course be evaluated?
9
Final exam: 40%
Project: 60%
Overall evaluation scheme




What is the project about?
11
Project topic

A team of 4 or 5 students in the course to build a software system 
Web application with front and back ends
At least have the same number of core functional features as team size
Meet the following non-functional requirement i.e., can response 20 users with a total of 200 requests per minute concurrently.
Your TA is your customer
You can use any programming language, framework, and tech stack.

Goal of project
Through the project 
Obtain hand-on experience/skills of DevOps (tools like GitHub Action and Docker)
Obtain hand-on experience/skills of software quality assurance (e.g., load testing and security analysis)

Create a cool project
Team project (a total of 60%):
Project proposal + presentation (5%)
Progress tracking (20%, 4 sprints, each sprint 5%)
Technique sharing seminar (5%)
Final project presentation (10%)
Final project deliverable (20%)
Peer evaluation
13
How will project be tracked and evaluated?
Each team will submit a project proposal, which includes (template found on UMLearn)
project summary
core features
Technique or framework
user stories for core features 
Present their proposed project in the class (10 mins) 

Project proposal + presentation
15
Progress tracking
The entire project is due in 4 sprints.
Each sprint is 2-4 weeks.
From the 2nd sprint, each sprint needs concrete tasks finished, e.g., features implemented, testing, or bugs fixed, CI/CD pipeline implemented.

16
17
Evaluation of each sprint

Let your TA try out your software and get feedback of the software from TA (customer). 

From sprint 2, at the end of each spring, you should have a working system and detailed instruction for installation for TAs to evaluate.

Each team will be responsible for holding a seminar in the middle of the term. These presentation and discussion sessions will be used to share your learning with other teams, e.g., techniques, frameworks
Technique sharing seminar
19
Final project presentation
Introduce your project
Live demo  
core features
Techniques aspect
Lessons learnt from the project
…
We will invite all other teams to evaluate


20
Final deliverable
Documentation:
Requirements specification (user stories)
Design (e.g., class diagram)
User manual
Testing report
Security scanning report
…
Source code:
Product code
Test cases
CI/CD scripts
Docker image
…
*Found more in release template (UMLearn -> Content -> Course project)
Peer evaluation
Your individual project mark will be assigned by starting with project mark and then weighting it based on your contribution to the work of the team as reported by your fellow team members.

The contribution from team members M1 to M4 are 30%,30%,20%,20%, the project mark is 50. The final project grade for M1 to M4 are 50*30/25 = 60, 60,  50*20/25 = 40, 40 

22
Using GitHub
Manage everything on GitHub.
Other than the code and necessary docs, all the discussion or meeting minutes need to be recorded on GitHub. 
Discussion offline or on other platform needs to be documented on GitHub.
Code review is needed.
Someone else in your team need to read your code before committing after passing test cases.
Everything needs to be referenced.
Use GitHub to track issues.
23
Managing your project
Version control everything on GitHub.
Automate everything with Devops pipeline



24
First thing to do!
Build the team. 
Team leader needs to be confirmed in the first week.
If you do not have a team, leave comments in the google doc. 

Please fill your team information here 
https://docs.google.com/spreadsheets/d/1ewp5bUNU8EbpPAQqRLjMIKLyGNiLejSgUvC55txSoIA/edit?usp=sharing 



Final test (40%)
There will be a final test that will cover course material from class. 
Open book.
The time and location will be announced by the Student Records Office. 
What do I need to succeed?
Take the test seriously
Participate class 
This course is NOT just for programming! Learn and follow the software development and delivery process
Work as a team.
Be fair and supportive to your team members
26

Late submission. Students (student groups) can turn in their assignments and laboratory deliverables up to 2 calendar dates late. The penalty for lateness is that, for being late by each calendar date, a 10% of the actually obtained grade will be deducted.
Re-grading. Students (student groups) have up to 7 days from the time the graded assignment/test or laboratory deliverable is available to request a re-grading, if there is a disagreement with a grade. Weekends and holidays count when calculating re-grading request days. No re-grading will be done after this period. Re-grading requests shall be made to the instructor directly. 
Generative Artificial Intelligence (genAI):  Students may not use artificial intelligence tools for taking tests. However, Students may use artificial intelligence tools, including generative AI, in this course as learning aids or to gather information from across sources and assimilating it for understanding. If genAI was used, students must submit, as an appendix with their assignments, any content produced by an artificial intelligence tool, and the prompt used to generate the content. 
E.g., generate code using ChatGPT, put the setting of ChatGPT, and prompt in the comments.
27

Policy
Introduction to Software Engineering

Software is everywhere!
29


Generative AI
Write code
Write story/poem
Explain concept

How many lines of code?
More than 100 Million lines of code!
No natural limits to the potentialof software, .e.g, lack of physical constraints, software systems can quickly become extremely big and complex. 
Make it difficult to understand, and expensive to change. 
What is this?
“Software Crisis” 
Projects running over-budget
Projects running over-time
Software was very inefficient
Software was of low quality
Software often did not meet requirements
Projects were unmanageable and the code was difficult to maintain
Software was never delivered
Therefore, Software Engineering is engineering principles to build software systematically, rigorously, measurably, on time, on budget, and within specification.
Software engineering

All aspects of software production
Not just technical process of development, also project management and the development of tools, methods etc. to support software production.

Main software engineering activities
Specification
Development
Evolution
Validation
Software Process Phases
There are many different software processes, but they all share the same basic elements.  

The difference is in how these elements are organized.
real-time software in an aircraft has to be completely specified (i.e., Specification) before development (i.e., Development) begins - waterfall 
mobile apps, which require short release circle,  the specification and the program are usually developed together – agile 

Overview of Scrum
45
Scrum is an agile method that focuses on managing iterative development that 

Software engineering fundamentals (I)
Some fundamental principles apply to all types of software system, irrespective of the development techniques used:

Systems should be developed using a managed and understood development process. Of course, different processes are used for different types of software.

Reliability (e.g., time of running without bugs) and performance (e.g., query response time) are important for all types of system. 
Rapid update of Mobile apps
https://testlio.com/blog/how-often-should-you-update-your-mobile-app/
How to reduce the risk of introducing new bugs when making changes to the software?



Software quality assurance
Actions
