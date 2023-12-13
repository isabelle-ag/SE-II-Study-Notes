### Study Notes for Comp 4350 - Software Engineering II: Lecture 4

#### I. Key Concepts
- **Main Idea 1:** The rapid release cycle in modern software engineering involves frequent software releases, sometimes multiple times a day.
- **Main Idea 2:** Release pipelines consisting of integration, build, and deployment are crucial for delivering new software content efficiently.
- **Main Idea 3:** DevOps integrates developers and operations engineers in all service lifecycle phases, emphasizing continuous integration for rapid and high-quality product delivery.

#### II. Definitions
- **DevOps:** A set of practices that combine software development (Dev) and IT operations (Ops) aiming to shorten the systems development lifecycle and provide continuous delivery with high software quality.
- **Continuous Integration (CI):** A DevOps practice where developers regularly merge code changes into a central repository after which automated builds and tests are conducted.
- **Build System:** Tools and processes used to automate the conversion of source code files into executable artifacts.

#### III. Important Details
- **Point 1:** Build systems are necessary for translating sources to deliverables and are particularly crucial for large systems which are difficult to build manually.
- **Point 2:** Build tools such as Ant, Maven, Gradle, and PyBuilder automate the build process using defined dependencies and actions.
- **Point 3:** Incremental builds only recompile changed components, which improves efficiency and reduces build time.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** Release pipeline schema illustrating the steps from integration to deployment.
- **Diagram 2:** Dependency graph of build systems depicting how various components are interconnected.
- **Diagram 3:** Visual representation of the `make` command dependency rules and their associated recipes within a Makefile.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** The `make` command processes a Makefile to automate the build process by understanding dependencies and recipes for building an application.
- **Formula/Theorem 2:** Martin Fowler’s practices on CI emphasize the importance of a single source repository, automated builds, quick build correction, and daily commits.

#### VI. Examples
- **Example 1:** Step-by-step guide on setting up a GitHub Actions workflow to automate CI tasks.
- **Example 2:** Creating a Makefile that details build dependencies and recipes for compiling a program with multiple source files.
- **Example 3:** Implementing an Ant build file for Java applications, as demonstrated in the provided GitHub repository.

#### VII. Summary/Conclusion
- **Recap of Main Points:** The lecture emphasized the importance of rapid release cycles, the need for efficient build systems and the role of DevOps and continuous integration in modern software engineering.
- **Connections between Concepts:** There is a clear connection between the implementation of DevOps practices, like continuous integration, and the use of build tools (Ant, Maven, etc.) to automate and streamline the software build and deployment process.

#### VIII. Additional Resources
- **Textbook Pages:** Consult Chapter 3 and 6 of "Continuous Delivery" by Jez Humble and David Farley for further reading.
- **Online Resources:** GitHub Docs for GitHub Actions and workflows, Travis-CI user tutorial, and various repository links provided within the lecture for hands-on learning.

References:
- Continuous Delivery, Jez Humble and David Farley
- [SAPUB Article on Build Systems](http://article.sapub.org/10.5923.j.ac.20201001.02.html)
- [GitHub Docs - Events that Trigger Workflows](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows)
- [GitHub Actions Quickstart](https://docs.github.com/en/actions/quickstart)
- [Building and Testing Java with Ant](https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-java-with-ant)
- [Travis-CI User Tutorial](https://docs.travis-ci.com/user/tutorial/)

---

Notes: 
Comp 4350Software Engineering IILecture 4
Dr. Shaowei Wang
The rapid release cycle of modern software systems
Often release several times
in one day!
2￼
Release pipelines:
How organizations deliver new content
3
   1. Integration
   2. Build 
   3. Deployment
3￼
DevOps is the practice of operations and development engineers participating together in the entire service lifecycle, from design through the development process to production support, to increase organization’s ability to deliver products faster, while ensure high quality
DevOps
Continuous integration
Continuous integration is a DevOps software development practice where developers frequently merge their code changes into a central repository, after which automated builds and tests are run on the branch.
Continuous Integration (CI)
6￼
Continuous integration benefits
Improve developer productivity

Find and address bugs quickly

Deliver updates faster
7
Continuous Integration (CI)
8￼

What is a build system?
Modern software organizations rely on an efficient and robust build system!
9￼
.tex
.java
.java
.dvi
.jar
.pdf
.zip
Build systems describe how sources are
translated into deliverables automatically. 
10￼
.class
.class
Why we need a build system?

gcc -c random.c
gcc -c input.c
gcc -c main.c
11

gcc -c random.c
gcc -c input.c
gcc -c main.c
gcc random.o \
input.o \
main.o \
-o program
12

gcc -c random.c
gcc -c input.c
gcc -c main.c
gcc random.o \
input.o \
main.o \
-o program
13

gcc -c random.c
gcc -c input.c
gcc -c main.c
gcc random.o \
input.o \
main.o \
-o program
14

gcc -c random.c
gcc -c input.c
gcc -c main.c
gcc random.o \
input.o \
main.o \
-o program
15
It’s extreme hard to build large system manually

16
Jetty dependency tree
Linux 2.4
Linux 2.6
Build dependency graph

18
How can I re/build the system?
Build tools
Ant
A Java library used for automating build processes for Java applications as  a replacement for the Make build tool of Unix. The main benefit of Ant is its flexibility. 
XML format
Maven
A build automation tool used primarily for Java projects. Maven can be considered a plugin execution framework, since all work is done by plugins. 
XML format
Gradle
A build automation tool that was built upon the concepts of Ant and Maven.
Written in Groovy or Kotlin
PyBuilder
A build automation tool 
Written in python
How does build system work?
Define the dependency

Define the action
20
make to the rescue
Step 1 - Expressing dependencies
Step 2 -
Writing
recipes


gcc main.o \
-o program
21






Step 1 - Expressing dependencies
program : random.o input.o main.o
22






Step 1 - Expressing dependencies
program : random.o input.o main.o
23






Step 1 - Expressing dependencies
program : random.o input.o main.o
24






program : random.o input.o main.o
<tab>gcc -o program random.o input.o main.o
Step 2 -
Writing recipes
25





program : random.o input.o main.o
<tab>gcc -o program random.o input.o main.o
random.o : random.c
<tab>gcc -c random.c
input.o : input.c
<tab>gcc -c input.c
main.o : main.c
<tab>gcc -c main.c
Step 2 -
Writing recipes
26
make command reads the makefile
$ make
gcc -c random.c
gcc -c input.c
gcc -c main.c
gcc -o program random.o input.o main.o
$ 
27

gcc -c random.c
gcc -c input.c
gcc -c main.c
gcc random.o \
input.o \
main.o \
-o program
28
Continuous integration
Continuous integration is a DevOps software development practice where developers frequently merge their code changes into a central repository, after which automated builds and tests are run on the branch.
make Incremental Builds!
$ vim random.c
...
$ make
gcc -c random.c
gcc -o program random.o input.o main.o
$

How does incremental build work? 
31
First of all – build the dependency graph
32
program : random.o input.o main.o
<tab>gcc -o program random.o input.o main.o
random.o : random.c
<tab>gcc -c random.c
input.o : input.c
<tab>gcc -c input.c
main.o : main.c
<tab>gcc -c main.c

program : random.o input.o main.o
<tab>gcc -o program random.o input.o main.o
random.o : random.c
<tab>gcc -c random.c
input.o : input.c
<tab>gcc -c input.c
main.o : main.c
<tab>gcc -c main.c






Only random.c is modified
34
Random.o is older than random.c =>receipt is executed
Input.o is newer than input.c => nothing happens
main.o is newer than main.c => nothing happens
promgramis older than random.o =>receipt is executed
Ant build file
35
https://github.com/shaoweiwang2010/SE_course_JunitTest_Demo/blob/master/build.xml
36
How clients do interact with build system? 
37
Build systems have a
variety of clients
38
Build system interactions:
Quality Assurance Personnel
QA and Builds:
Builds should be configured to perform most tests automatically

QA teams hook automated tests into the build system

Since normal builds need to provide a fast feedback loop, only quick tests run in a typical builds

Slower tests can be relegated to special build targets that are executed less often

39
https://github.com/shaoweiwang2010/SE_course_JunitTest_Demo/blob/master/build.xml
40
Build systems have a
variety of clients

41
Build system interactions:
Static analysis
Static analysis and builds:
Static analysis can be triggered with the build command (e.g., Google’s ErrorProne)


Scan the source code or byte code for common bugs like resource leaks and dead code
42
Build system interactions:
Code review environments
Code review and builds:
Modern code review tools like Gerrit execute builds to provide early feedback for reviewers
Check out https://codereview.qt-project.org/#/c/140545/
Sanity bot’s feedback is from the build system
43
Build system interactions:
Nightly builds
Builds are sometimes on a schedule:

QA teams can pick up version that is going to be released to do thorough testing on the new features and validate the bug fixes during night
44
Build system interactions:
The problem with nightly builds
Night builds are too infrequent:
As the amount of change per day has grown, nightly builds have become difficult

Consider the case when a nightly build does not complete cleanly
If hundreds of developers have committed changes, it’s hard to tell who caused the problem!
Imagine you broke the build, but you wrote the code yesterday! Hard to recall!
45
Build system interactions:
The problem with nightly builds
Night builds are too infrequent:
As the amount of change per day has grown, nightly builds have become difficult

Consider the case when a nightly build does not complete cleanly
If hundreds of developers have committed changes, it’s hard to tell who caused the problem!
Imagine you broke the build, but you wrote the code yesterday! Hard to recall!
Martin Fowler’s practice on CI

Maintain a Single Source Repository.
Make it Easy for Anyone to Get the Latest Executable
Everyone can see what's happening

Automate the Build
Keep the Build Fast
Fix Broken Builds Immediately
Everyone Commits To the Mainline Every Day

Every Commit Should Build the Mainline on an Integration Machine
Test in a Clone of the Production Environment
Make Your Build Self-Testing
47
Continuous integration tools
On-premises:
Jenkins
CruiseControl
Buildbot

Cloud-based:
GitHub Action
TravisCI
CloudBees
CircleCI
On-premises VS Could-based
48
Github Actions
49
GitHub Actions workflow






GitHub Actions workflow to be triggered when an event occurs in your repository, (pull request being opened or an issue being created). 
Your workflow contains one or more jobs which can run in sequential order or in parallel. 
Each job will run inside its own virtual machine runner, or inside a container, and has one or more steps that either run a script that you define or run an action, which is a reusable extension that can simplify your workflow.
50
Event

51
https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows
Action
52
Set up GtiHub Action for a GitHub project
Tutorial (https://docs.github.com/en/actions/quickstart)
Github repo  https://github.com/shaoweiwang2010/SEII_GithubAction_Demo	
















54
name: GitHub Actions Demo
on: [push]
jobs:
  Explore-GitHub-Actions:
    runs-on: ubuntu-latest
    steps:
      - run: echo "🎉 The job was automatically triggered by a ${{ github.event_name }} event."
      - run: echo "🐧 This job is now running on a ${{ runner.os }} server hosted by GitHub!"
      - run: echo "🔎 The name of your branch is ${{ github.ref }} and your repository is ${{ github.repository }}."
      - name: Check out repository code
        uses: actions/checkout@v2
      - run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
      - run: echo "🖥️ The workflow is now ready to test your code on the runner."
      - name: List files in the repository
        run: |
          ls ${{ github.workspace }}
      - run: echo "🍏 This job's status is ${{ job.status }}."

55
You need to show your CI works and have tests available in the Sprint 2!
Build with Ant
56
https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-java-with-ant

57
Reference
Chapter 3 and 6, Continuous Delivery, Jez Humble and David Farley 
http://article.sapub.org/10.5923.j.ac.20201001.02.html

https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows

58
Set up TravisCI for a GitHub project
Set up TravisCI for (https://docs.travis-ci.com/user/tutorial/):
Fork this repository:
https://github.com/shaoweiwang2010/SE_course_TravisExercise

Go to https://travis-ci.org/ and log in with your github account
In your profile page, enable Travis’s access to the repo of TravisExercise

On your machine clone your repository
git clone REPLACE_THIS_BY_YOUR_REPO_URL
Add a .travis.yml file to your forked repository
specify the language by putting: language: java

Push a change to break the build (in your forked repo) and see if Travis finds it!

You need to show your CI works and have empty tests available in the Sprint 2!

