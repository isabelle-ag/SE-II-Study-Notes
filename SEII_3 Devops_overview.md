### Study Notes for Comp 4350 Software Engineering II: Lecture 3 - DevOps Overview

#### I. Key Concepts
- **Main Idea 1:** DevOps aims to bridge the gap between software development (Dev) and IT operations (Ops) to improve collaboration, productivity, and the quality of products.
- **Main Idea 2:** DevOps emphasizes continuous integration, continuous delivery, and continuous deployment to enable frequent and reliable release schedules.
- **Main Idea 3:** Cloud services (AWS, Azure, Google Cloud) play a pivotal role in DevOps by providing scalable and cost-effective environments.

#### II. Definitions
- **Version Control:** A system that records changes to files over time so that specific versions can be recalled later.
- **Continuous Integration (CI):** The practice of merging all developers' working copies to a shared mainline several times a day.
- **Infrastructure as Code (IaC):** The process of managing and provisioning computer data centers through machine-readable definition files, rather than physical hardware configuration.

#### III. Important Details
- **Point 1:** DevOps helps in making product deliveries faster and more reliable by facilitating better communication and collaboration between Dev and Ops teams.
- **Point 2:** High-quality code and builds are crucial, with automated testing and deployment processes adopted to ensure reliability and reduce manual error.
- **Point 3:** Cloud services allow scalability and cost-effectiveness, making it easier for organizations to manage peak loads and reduce hardware expenses.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** The DevOps lifecycle, illustrating the continuous loop of Planning, Coding, Building, Testing, Releasing, Deploying, Operating, and Monitoring.
- **Diagram 2:** Blue/green deployment strategy, showing how two identical production environments can help reduce downtime and deployment risks.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** N/A in context of DevOps; this is more applicable in mathematical or scientific contexts rather than software engineering processes.
- **Formula/Theorem 2:** N/A 
- **Formula/Theorem 3:** N/A

#### VI. Examples
- **Example 1:** Setting up a continuous integration pipeline using TravisCI, showing how a change to the code triggers an automated build and testing process.
- **Example 2:** Implementing blue/green deployment to manage and switch between production environments with minimal user disturbance.
- **Example 3:** Using cloud service models (IaaS, PaaS, SaaS) to deploy and scale an application according to the incoming load and traffic.

#### VII. Summary/Conclusion
- **Recap of Main Points:** DevOps is a set of practices that combines software development (Dev) and IT operations (Ops), emphasizing inter-team collaboration, automation in software development processes, and the utilization of cloud services to enable rapid and reliable delivery of software products.
- **Connections between Concepts:** DevOps integrates concepts from Agile development, cloud computing, and IT operations to create a harmonious workflow that benefits both development and operations by improving communication and reducing time-to-market.

#### VIII. Additional Resources
- **Textbook Pages:** Relevant chapters from "Effective DevOps" by Jennifer Davis & Katherine Daniels.
- **Online Resources:** Links for TravisCI documentation and cloud service comparisons, as well as various articles detailing CI/CD practices and Agile methodologies.

---

Notes: 
Dr. Shaowei Wang
Comp 4350Software Engineering IILecture 3
TA available time
Review 
Version control
Code
Dependency
Configuration 
Environment 
Code style
Convention 

DevOps overview

Why DevOps?
What is DevOps?
DevOps Stage
DevOps tools

Agenda
Software Development
6
Design and specification
Testing
Coding
Building
Software Operation
7
Deployment
Operation
Software Operations
8
Definition: The people and management processes associated with IT service management to deliver the right set of services at the right quality and at competitive costs for customers

Duties: 
- Manage hardware
Deploy into production environment
Monitor the execution of production (e.g., error, performance)

Operators

There is a gap between software developers and operators
10
Developers
Operators
Does my system perform well in the field?
What does this error message mean?  It doesn’t work in the production. 
How do I resolve it?
What problem is DevOps trying to solve?
Poor communication between Dev and Ops
Developers have more insights on operations
Operators have more insights on the developers
Slow product delivery 
Devs want to push new features
Ops want to keep the system available/stable
Leads to slower release schedules 
DevOps
Remove the gap between Dev team and Ops team
DevOps is the practice of operations and development engineers participating together in the entire service lifecycle, from design through the development process to production support, to increase organization’s ability to deliver products faster.
What is DevOps?
Goal of DevOps: 
- remove the gap between operation and development
- reduce the time between committing a change to a system and the change being deployed into production environment, while ensuring high quality.
What does high quality mean?
High quality code
Well tested

High quality builds and delivery mechanism
Automation & more testing
No interruption of the existing system
A must when deploying to production 25x per day (etsy.com)

Why companies care?
IBM
“IBM has gone from spending about 58% of its development resources on innovation to about 80%” -> spend more efforts on develop new features

Paddy Power (Ireland):
“The cycle time from a user story's conception to production has decreased from several months to 2 to 5 days.
“Previously, approximately 30% of the workforce was fixing bugs. Now, bugs are so rare that the teams no longer need a bug-tracking system.” -> Auto-testing
Nowadays, a profound shift is taking place and make DevOps happen
Instead of managing their own data centers, many companies are moving to the cloud, taking advantage of services such as Amazon Web Services, Azure, and Google Cloud.
Instead of investing heavily in hardware, many Ops teams are spending all their time working on software, using tools such as Jenkins, Puppet, and Docker for deployment and monitoring. 
As a result, both Dev and Ops spend most of their time working on software, and the distinction between the two teams is blurring.
DevOps stages
Plan
The Plan stage covers everything that happens before the developers start writing code, and it’s where a Product Manager or Project Manager earns their keep.
Requirements and feedback are gathered from stakeholders and customers and used to build a product roadmap to guide future development. 
Tools: 
Jira, Azure DevOps or Asana

Coding
In addition to the standard toolkit of a software developer, the team has a standard set of plugins installed in their development environments to aid the development process, help enforce consistent code-styling and avoid common security flaws and code anti-patterns.
Build
Once a developer has finished a task, they commit their code to a shared code repository. It triggers two processes:
Automated building. An automated process which builds the codebase and runs a series of end-to-end, integration and unit tests to identify any regressions. 
Code review. This manual review is supposed to be quick and lightweight, but it’s effective at identifying issues early.
What is an automated build system?
Modern software organizations rely on an efficient and robust build system!
21￼
Shane
McIntosh
.tex
.java
.java
.dvi
.jar
.pdf
.zip
Build systems describe how sources are
translated into deliverables
22￼
.class
.class
Build systems describe how sources are
translated into deliverables
When you run your tool, it will calculate how to reach the goal you specify by executing tasks in the correct order, running each task that your goal depends on exactly once. 
Build tools
Make
A build automation tool that automatically builds executable programs and libraries from source code in Unix. 
Ant
A Java library used for automating build processes for Java applications as  a replacement for the Make build tool of Unix. The main benefit of Ant is its flexibility. 
XML format
Maven
A build automation tool used primarily for Java projects. Maven can be considered a plugin execution framework, since all work is done by plugins. 
XML format
Gradle
A build automation tool that was built upon the concepts of Ant and Maven.
Written in Groovy or Kotlin

Code review
Testing
Once a build succeeds, it is automatically deployed to a test environment (existing hosting service) for deeper, out-of-band testing. 
Manual test
traditional User Acceptance Testing (UAT) where people use the application as the customer would to highlight any issues or refinements that should be addressed before deploying into production.
Automated tests
Different levels of functional testing
security scanning against the application
performance test
load testing

How deep the test should be?
Where is the first place DevOps kicks in? 
Continuous integration
Continuous integration (CI) is DevOps practice of integrating new code written by developers with a mainline or “master” branch frequently throughout the day, rather than having developers working on independent feature branches for weeks or months at a time, merging their code back to the master branch only when it is completely finished. 
Why: Long periods of time in between merges means that much more has been changed, increasing the likelihood of some of those changes being breaking existing ones, e.g., causing conflict, break existing features.
https://itnext.io/git-concepts-for-newcomers-part-2-git-repository-working-tree-and-staging-area-a2e720bf3528
Continuous integration
Release
Release phase is a milestone in a DevOps pipeline - it’s the point at which we say a build is ready for deployment into the production environment.
Operations team can be confident that breaking issues and regressions are unlikely.
Deploy
Finally, a build is ready for the big time and it is released into production. Now it’s time to run an application on a server or device. 
Cloud service
Organizations tend moving their deployment from on-premises IT infrastructure to cloud service
Cloud service providers
Amazon Web Services (AWS)
Google Cloud Platform
Microsoft Azure
Infrastructure-as-a-Service (IaaS)
Platform-as-a-Service (PaaS)
Software-as-a-Service (SaaS)

Different flexibility 







Benefit of cloud service
Benefit of cloud service
Scalability
you can quickly scale up or down with a few clicks
perfect solution for handling peak loads
Cost-effectiveness
removes hardware expenses
no need to buy, install, configure, and maintain servers, databases, and other components of your runtime environment
What only for what you use
Immediate availability
Cloud solutions are available as soon as you’ve paid for them
Benefit of cloud service
Performance
equip their data centers with high-performance computing infrastructure that guarantees low network latency for your applications.
Security
kept in safe data centers to ensure a top level of security
data is backed up and can easily be recovered. 
https://www.t4.ai/industry/cloud-computing-market-share
Cloud Business Process Services, Cloud Management and Security Services, and Desktop as a Service
Continuous Delivery
Continuous Delivery is an extension of CI since it enables automation to deploy all the code changes to an environment (dev, qa, prod) after the changes have been merged.
Developers can deploy their changes at any time by simply clicking a button or at the completion of CI.

Continuous Deployment
Continuous Deployment takes the process one step further than continuous delivery.
All changes that pass the verification steps at each stage in the pipeline are released to production. This process is completely automated and only a failed verification step will prevent pushing the changes to production.
CD using docker
Continuous Delivery Pipeline
Continuous delivery pipeline


Development strategy - blue/green deployment
A deployment strategy to reduces downtime and risk by running two identical production environments called Blue (old environment) and Green (new environment).
When the new environment is ready, the hosting service (e.g., Nginx) points all new requests to the new environment. If at any point, an issue is found with the new build, you can simply tell the hosting service to point requests back to the old environment while you come up with a fix.








Operate
Based on the configuration of the hosting service, the environment automatically scales with load to handle peaks and troughs in the number of active users.
The organisation has also built a way for their customers to provide feedback on their service, as well as tooling that helps collect and triage this feedback to help shape the future development of the product. 
Operate
Based on the configuration of the hosting service (AWS), the environment automatically scales with load to handle peaks and troughs in the number of active users.
Monitor
The ‘final’ phase of the DevOps cycle is to monitor the environment. 

It is a process to monitor and identify compliance issues and security risks throughout each phase of DevOps lifecycles.

It helps organizations to track, identify, understand key metrics and also resolve application or infrastructure issues in real-times.
What type of data we can monitor? 




Monitoring data type
53


deploy
operate
test
build
code
plan

release
Dev
Ops



monitor
Logs
Metrics
Traces
Alerts
Types of monitoring
Infrastructure Monitoring
to collect and analyze data from the IT infrastructure and leverage that data to improve the final results.
Application Monitoring
offers runtime metrics of system performance like application uptime, application-performance, application security-monitoring, log-monitoring etc
Network Monitoring
monitor and track everything about the network, like routers, firewalls, servers, switches, and VMs. 
DevOps Practices
Automate Everything.
CI: automatic build, testing
CD: automatic deployment


Develop infrastructure code with the same set of practices as application code
We need “infrastructure as Code” : using IaaS APIs, etc., to automate creation of environments (Docker)
Misconfiguration can derail your application (Puppet)
Reference
Chapter 2 & 4 & 6, Effective DevOps, Jennifer Davis & Katherine Daniels 
https://rubygarage.org/blog/iaas-vs-paas-vs-saas
https://www.indellient.com/blog/whats-the-difference-between-continuous-integration-continuous-delivery-and-continuous-deployment/

DevOps Consequences
Keep teams relatively small
Amazon’s “two pizza rule”: you should be able to feed the team with two pizzas

Advantages: make decisions quickly, less coordination overhead, more coherent units

DevOps Consequences
Team size becomes a major driver of the overall architecture:

Small teams develop small services -> Microservices

Coordination overhead is minimized by channeling most interaction through service interfaces:
Team X provides service A, which is used by teams Y and Z
If changes are needed, they are communicated, implemented, and added to the interface.
Try it out using TravisCI
Set up TravisCI for:
Fork this repository:
https://github.com/shaoweiwang2010/TravisExercise

Go to https://travis-ci.org/ and log in with your github account
In your profile page, enable Travis’s access to the repo of TravisExercise

On your machine clone your repository
git clone REPLACE_THIS_BY_YOUR_REPO_URL
Add a .travis.yml file to your forked repository
specify the language by putting: language: java


Push a change to break the build (in your forked repo) and see if Travis finds it!

You need to show your CI works and have empty tests available in the Sprint 2!

We need automation and tool supports!
Try it out using TravisCI
Read about how to set up Travis CI for your fork here:
https://travis-ci.org/
http://docs.travis-ci.com/user/getting-started/
http://docs.travis-ci.com/user/languages/java/
http://docs.travis-ci.com/user/languages/java/#Projects-Using-Ant
http://docs.travis-ci.com/user/customizing-the-build/
Add a .travis.yml file to your forked repository
Push a build break into your fork to see if Travis finds it!
BONUS: Make your repository based on Maven and use Travis to build and test!
Process 1: Waterfall
Requirements definition
System and software design
Implementation and unit testing
Integration and system testing
Operations and maintenance
Limitations of waterfall
Agile development
Customer feedback
Customer feedback
Customer feedback
Customer feedback
Agile development
https://itnext.io/git-concepts-for-newcomers-part-2-git-repository-working-tree-and-staging-area-a2e720bf3528
