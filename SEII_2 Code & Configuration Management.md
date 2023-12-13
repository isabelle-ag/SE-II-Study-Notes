### Study Notes for Comp 4350: Software Engineering II - Version Control and Coding Practice

#### I. Key Concepts
- **Main Idea 1:** Software systems require constant updating, leading to multiple working versions and the necessity of version control.
- **Main Idea 2:** Version control systems help manage changes to software code and maintain a complete history for traceability, branching, and merging.
- **Main Idea 3:** Software Configuration Items (SCIs) such as code, design documents, dependencies, and environment must be properly managed for effective version control.

#### II. Definitions
- **Version Control:** The practice of tracking and managing changes to software code.
- **Codeline:** A sequence of versions of source code, with later versions derived from earlier ones.
- **Baseline:** A specific definition of a system that specifies the versions of components and other configuration details.

#### III. Important Details
- **Point 1:** Multi-version systems require that different versions of a system be maintained and managed at various stages of development.
- **Point 2:** Change history in version control enables root cause analysis of bugs and supports tracking of changes made to the software.
- **Point 3:** Software configuration can be complex, affecting the flexibility of the software and potentially complicating system behavior and testing.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** Tree Evolution Model of Version Control – Shows how software versions evolve and replace previous versions.
- **Diagram 2:** Dependencies Graph – Visualizes the relationships between software package dependencies.
- **Diagram 3:** Docker File Syntax – Provides instructions for building a Docker container, illustrating the configuration of an environment.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** Semantic Versioning – Explains the meaning and importance of software version numbers (MAJOR.MINOR.PATCH).
- **Formula/Theorem 2:** Delta Storage Management – Describes how versions are stored as differences between versions to save space.
- **Formula/Theorem 3:** Git Compression – Discusses Git's approach of using compression instead of deltas, enabling faster file retrieval.

#### VI. Examples
- **Example 1:** Creating a baseline – Steps to define a system version with specified component versions and configurations.
- **Example 2:** Utilizing branching and merging – Practical example of how individual development streams are managed in version control.
- **Example 3:** Applying configuration changes – Demonstrating how to modify MySQL configuration parameters at runtime for flexibility.

#### VII. Summary/Conclusion
- **Recap of Main Points:** Emphasizes the importance of version control in software development and the strategies to manage SCIs efficiently.
- **Connections between Concepts:** Connects the concepts of version control and coding practices to the broader context of software engineering and the importance of understandability in code.

#### VIII. Additional Resources
- **Textbook Pages:** Ian Sommerville, Software Engineering, 10th Edition, Chapter 25 (Configuration Management).
- **Online Resources:** 
  - Semantic Versioning Best Practices: https://blog.codeship.com/best-practices-when-versioning-a-release/
  - Google's C++ Style Guide: https://google.github.io/styleguide/

### Administrative Details
- Instructor: Dr. Shaowei Wang
- Slide 1 uploaded; Build team as soon as possible
- Seminar activities included group introductions and sharing version control experiences.

---

Notes: 
Comp 4350Software Engineering II
Dr. Shaowei Wang
Administrative item
Slides 1 was uploaded
Build team as soon as possible

2
Agenda
Version control
Coding practice

3
Software systems are constantly changing
New versions are created to handle software changes

Each version may have to be maintained and managed
4
Multi-version systems
For large systems, there is never just one ‘working’ version of a system. 
There are always several versions of the system at different stages of development. 
Different versions of the system may be in use
5



Multi-version system development
6
Development system 
Versions of printer firmware products - a tree evolution model
7

In the tree evolution model, one or more new software configuration versions will replace former software configuration version. 


Even the same component needs different configuration to be maintained and tracked.
Version control
Version control, also known as source control, is the practice of tracking and managing changes to software code.
Version control systems are software tools that help software teams manage changes to source code over time.
8
Design documents
Software code
Data files including files of test cases and test scripts
Software development tools 
9
Software item (SCI)


10


11
Deployment code, build code
Dataset for  machina-learning systems.
Why version control?
A complete long-term change history of every file
having the complete history enables going back to previous versions to help in root cause analysis for bugs
Branching and merging
individuals working on their own can benefit from the ability to work on independent streams of changes.
Traceability
trace each change made to the software and connect it to project management and bug tracking
12
Help traceability in software project

13
Version control
Code
Dependencies
Software configuration
Environment
14
Code
code management is the process of keeping track of different versions of software code. 


15
Codelines and baselines
code management can be thought of as the process of managing codelines and baselines
16
Codelines and baselines
A codeline is a sequence of versions of  source code with later versions in the sequence derived from earlier versions. 
Codelines normally apply to components of systems so that there are different versions of each component.
17
Codelines and baselines
A baseline is a definition of a specific system. 
The baseline therefore specifies the component versions that are included in the system plus a specification of the libraries used, configuration files, etc. 
18
baselines representing different versions of a system
Codelines and baselines 
19
Versions of printer firmware products - a tree evolution model
20

In the tree evolution model, one or more new software configuration versions will replace former software configuration version. 

baseline
codeline
Version control
Code
Dependencies
Software configuration
Environment
21
Dependencies graph for browserify in NPM
22
https://npm.anvaka.com/#/view/2d/browserify


23
Manage external libraries
Keep locally
Pros: Get started on a project faster. It also means you always have the ability to reproduce your build
Cons: Get repo bigger and check out longer
Download from internet
Pros: The repository gets smaller and check out faster
Cons: Easy to break (get removed from the online repo), safety

Build local external libraries repo in company
In the case of Maven, you should create a repository for your organization containing approved versions of libraries to use 
24


25
Version control
Code
Dependencies
Software configuration
Environment
26
Software configuration management
Configuration information can be used to change the behavior of software at build time, deploy time, and run time, which provides flexibility to software. 

Suggest to treat the configuration of your system in the same way you treat your code: Make it subject to proper management and testing.
27
MySQL configuration parameters

28
Change log level during runtime in Spring Boot
29
Flexibility usually comes at a cost!
Make the requirements of system very complicated
Make the system behavior more complicated and harder to test
…
30
Type of configuration
Configuration information can be injected into your application at several points in your build, deploy, test, and release process.
Your build scripts can pull configuration in and incorporate it into your binaries at build time (e.g., executable is based on configuration). 
Your deployment scripts or installers can fetch the necessary information or ask the user for it and pass it to your application at deployment time as part of the installation process (e.g., end-user application). 
Your application itself can fetch configuration at startup time or run time.
31
Version control
Code
Dependencies
Software configuration
Environment
32
Environment
33
Software 
Hardware 
Infrastructure 

34
Types of environment configuration
The various operating systems in your environment (versions,patch levels, and configuration settings). 
The additional software packages that need to be installed on each environment to support your application, including their versions and configuration.
Any external services that your application depends upon, including their versions and configuration.
Any data or other state that is present in them (for example, production databases).
The networking topology required for your application to work
35
Key principle - make their creation a fully automated process. 
Reduce risk - It removes the problem of having random pieces of infrastructure around whose configuration is only understood by somebody who has left the organization and cannot be reached. When such things stop working, you can usually assume a significant downtime. This is a large and unnecessary risk. 
Replicability - It is essential to be able to create copies of production environments for testing/deployment purposes. In terms of software configuration, testing environments should be exact replicas of the production ones, so configuration problems can be found early. 
36

37
# syntax=docker/dockerfile:1

FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
Version control systems
Version control systems (VCS) identify, store and control access to the different versions of components. There are two types of modern version control system 
Centralized systems
There is a single master repository that maintains all versions of the software components that are being developed.
Subversion is an example of a centralized VC system.
Distributed systems
Multiple versions of the component repository exist at the same time. 
Git is an example of a distributed VC system. 
38
Key features of version control systems
Version and release identification 
Managed versions of a component are assigned unique identifiers
Change history recording 
Tagging components with keywords describing the changes made; then use these tags to select the components to be included in a baseline.
Support for independent development 
Ensures that changes made to a component by different developers do not interfere
Project support
Support the development of several projects which share components
Storage management
Use efficient storage mechanisms (e.g., storing delta, compression)
39
Benefits of distributed version control
It allows for off-line working so that developers can commit changes if they do not have a network connection. 
It provides a backup mechanism for the repository. 
If the repository is corrupted, work can continue and the project repository can be restored from local copies. 
Project support is the default way of working. 
Developers can compile and test the entire system on their local machines and test the changes that they have made. 
40
Open source development
Distributed version control is essential for open source development.
 Several people may be working simultaneously on the same system without any central coordination. 
Developers also maintain a public server repository to which they push new versions of components that they have changed. 
It is then up to the open-source system ‘manager’ to decide when to pull these changes into the definitive system. 
41
Storage management
Disk space was expensive decades ago and it was important to minimize the disk space used by the different copies of components. 

Instead of keeping a complete copy of each version, some VCS systems stores a list of differences (deltas) between one version and another. 
By applying these to a master version (usually the most recent version), a target version can be recreated. 
One of the problems of the delta-based approach is that it can take a long time to apply all of the deltas

42
Storage management using deltas 
43
Rebuilding Version V1.3 to V1.1, it has to rebuilt V1.2 by applying D3, and then rebuild V1.1 by applying D2.
Storage management in Git
Git uses an alternative, faster approach. 
Git does not use deltas but applies a standard compression algorithm to stored files and their associated meta-information for speed. 
Retrieving a file simply involves decompressing it, with no need to apply a chain of operations.
44
https://stackoverflow.com/questions/43359590/git-internals-how-does-git-store-small-differences-between-revisions
Tips 
Keep Absolutely Everything in Version Control 
Check In Regularly to Trunk
Use Meaningful Commit Messages
Keep reasonable size of each push 
45
Semantic versioning of software releases
46

What do the numbers mean?
Semantic versioning of software releases
47
48
Best practices for versioning a release – https://blog.codeship.com/best-practices-when-versioning-a-release/
Good example
Bad example
Activity1: Introduce to each other
Group in a four/five people surrounding you
5-10 minutes
Introduce yourself a bit
Share your experience of version control, e.g., challenges, tips 
Agenda
Version control
Coding practice


50
Understandability:What to keep in mind?
Code is read by humans!
Code describes what a computer should do
Yet, it is still mainly read by people
As such, it should be written with people in mind
What does this code do?
#include <stdio.h>
#define C(a) ((a)*(a)*(a))
int main(){int x,y;for(y=9;y>-6;y--){for(x=-8;x<9;x++)
putchar(C(x*x+y*y-25)<25*x*x*y*y*y?"LOVE"[(x+10)%4]:'-');
putchar('\n');}
return 0;}




How can we write
understandable
code?
Tips
Use meaningful identifier names!
Add comments that complement the code!
Classifying Code Comments in Java Open-Source Software Systems
https://ieeexplore.ieee.org/abstract/document/7962372
Classifying Code Comments in Java Open-Source Software Systems
https://ieeexplore.ieee.org/abstract/document/7962372
Classifying Code Comments in Java Open-Source Software Systems
https://ieeexplore.ieee.org/abstract/document/7962372
Classifying Code Comments in Java Open-Source Software Systems
https://ieeexplore.ieee.org/abstract/document/7962372
Research on automated comment generating
https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8778714

61
Code 1 
Code 2
Code 3
Comment1
Comment 2
Comment 3
New code
Codebase
Research on automated comment generating
https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8778714
Sequence to Sequence Model
Sequence-to-sequence model (Seq2Seq) is models that convert sequences from one domain (e.g. sentences in English) to sequences in another domain (e.g. the same sentences translated to French).


DEEP NEURAL NETWORKS BASED COMMENT GENERATION ALGORITHMS
"the cat sat on the mat" -> [Seq2Seq model] -> "le chat etait assis sur le tapis" 

64
https://xin-xia.github.io/publication/icpc182.pdf
Pair programming with AI

65

Coding conventions are a set of guidelines for a specific programming language that recommend programming style, practices, and methods for each aspect of a program written in that language.
Understandability tip #3:

https://google.github.io/styleguide/
https://mechatronics.me.wisc.edu/labresources/DataSheets/NASA-GSFC_C_Programming_Styles-94-003.pdf

References
Jez Humble and David Farley,  Continuous Delivery, Chapter 2 (Configuration Management) 
Ian Sommerville, Software Engineering, 10th Edition, Chapter 25 (Configuration Management)
69
Versions of an accounting software package - a linear evolution model
70


In the linear evolution model, only one new software configuration version will replace the former “old” software configuration version. 
Configuration management
71
The CM process is widely used by other domains, such as weapon systems, military vehicles, civil engineering and other industrial engineering segments such as roads, bridges, canals, dams, and buildings.
