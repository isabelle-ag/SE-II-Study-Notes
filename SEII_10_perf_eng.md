### Study Notes for Comp 4350: Software Engineering II - Lecture 10: Software Performance Engineering (SPE)

#### I. Key Concepts
- **Main Idea 1:** Software Performance Engineering (SPE) focuses on ensuring software systems meet performance requirements through the entire Software Development Life Cycle (SDLC).
- **Main Idea 2:** Non-functional requirements such as response time, throughput, and resource utilization are critical for assessing software performance.
- **Main Idea 3:** Performance testing includes various types of tests like stress, endurance, and load testing to measure system behaviors under different conditions.

#### II. Definitions
- **Performance Engineering Life Cycle:** An extension of the SDLC that incorporates performance-related activities such as non-functional requirements gathering, performance testing, and capacity management.
- **Response Time:** The total elapsed time from submitting a request to receiving the response.
- **Throughput:** The number of total completions per unit time, commonly expressed as transactions per second.

#### III. Important Details
- **Point 1:** The technical seminar is evaluated on the usefulness of information and quality of presentation, with peers and instructor sharing the evaluation weight.
- **Point 2:** SPE concerns with various performance indicators and examines the system or its components' efficiency.
- **Point 3:** The performance of systems can have significant financial implications, evidenced by examples such as lost revenue and software-related hardware issues.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** Comparison between SDLC and the Performance Engineering Life Cycle – emphasizing the integration of performance tasks.
- **Diagram 2:** Graphical representation of SPE activities overlaid onto SDLC – showing when performance tasks occur.
- **Diagram 3:** Examples of performance data visualized (e.g., CPU and memory usage) before and after fixes for deadlocks and memory leaks.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** Utilization = Busy Time / Total Time – a measure of how occupied system resources are.
- **Formula/Theorem 2:** (No specific formulas or theorems provided in the text; however, utilization can be considered a formula.)

#### VI. Examples
- **Example 1:** Estimation of workload intensity and mix by analyzing historical data and user actions.
- **Example 2:** Transition probabilities between different user actions to understand system usage patterns.
- **Example 3:** Designing load tests based on realistic load patterns derived from historical data.

#### VII. Summary/Conclusion
- **Recap of Main Points:** SPE integrates performance considerations throughout the SDLC, focused on meeting non-functional requirements and optimizing the system's performance through various testing methodologies.
- **Connections between Concepts:** There's a connection between methodologies in SPE and potential impact on business outcomes, emphasizing the importance of early performance considerations.

#### VIII. Additional Resources
- **Textbook Pages:** (Not provided in the text)
- **Online Resources:** Reference materials include IEEE articles, geeksforgeeks.org sections on software testing, and Practical Performance Analyst webpages.

Notes:
- Administrative details regarding the technical seminar were provided, including evaluation criteria and submission instructions.
- Examples given in the text, such as messaging systems and online gaming servers, show real-world applications of SPE.
- Specific SPE and testing resources from literature were cited, suggesting further reading for in-depth understanding.

---

Notes: 
Comp 4350Software Engineering IILecture 10
Dr. Shaowei Wang
Administrative items
Technical seminar (the week of Oct 31)
The purpose of the seminar is to share knowledge and experience among teams. The topic of the seminar could be technology, design choice, challenges you faced and how you solved them, and lessons have learned, etc. 
The seminar should be 15 mins (~13 minutes for presentation, 2 mins for Q&A ) for each team. 
The presentation will be evaluated in three aspects:
1) usefulness of the seminar
2) quality of the presentation
Each team will be evaluated by other teams and the instructor (the weight is 70% : 30%), in terms of the usefulness of the seminar and presentation quality. 
Schedule could be found in the google sheet
https://docs.google.com/spreadsheets/d/1ewp5bUNU8EbpPAQqRLjMIKLyGNiLejSgUvC55txSoIA/edit#gid=0 
Submit your slides to UMLearn -> Assignments -> Technical seminar
(Ultra) Large-Scale Software Systems

450 million active users> 50 billion messages every day


4 million users2600-3000 req/sec on most weekdays

Software system failures are often due to performance issues rather than functional bugs
4
A page load slowdown of only one second could cost?  
5
$1.6 billion
6
The short-battery-life of the Surface Pro tablet was due to a software performance bug
Outline
Software Performance Engineering (SPE)
Performance testing
Load testing

7
8
Software Performance Engineering (SPE)
Performance Efficiency (ISO 25010)
9
Software performance
Performance measures the efficiency of the software against the constraints of time and resource allocation.
There are several indicators to capture and evaluate performance.
Response Time: The total elapsed time between submission of a request and receipt of the response.
Processing Rate/Throughput: The total completions per unit time, e.g. Transactions/Sec.
Utilization: The ratio of busy time to total time (how busy or free the resources within a given system are).
Other indicators (e.g., capacity, battery/power consumption)
It is possible to consider the performance of 
entire system (including hardware and software)
part of the system such as a software component.
10
Software Performance Engineering (SPE)
The set of tasks or activities that need to be performed across the Software Development Life Cycle (SDLC) to meet the documented Performance Requirements.
11
SPE: Objectives
Increase revenue by ensuring the system processes all transactions in a timely manner.
Eliminate delayed deployment due to performance issues.
Reduce the increased costs of maintenance due to performance issues during production or ad hoc performance corrections.
Reduce operational overhead to address system problems due to performance issues.
Identify bottlenecks by simulating a prototype.
Increase server capacity.
12
13
Software Development Life Cycle 
Performance Engineering Life Cycle
Functional Requirements Gathering
Architecture & Design
Implementation
System Test & User Acceptance Test
Deploy Into Production
Non-functional Requirements Gathering
Design for High Performance
Unit Performance Test & Code Optimization
Performance Test
Monitoring & Capacity Management








Source: https://tangowhisky37.github.io/PracticalPerformanceAnalyst/pages/
spe_fundamentals/performance_engineering_101/
14
Software Development Life Cycle 
Performance Engineering Life Cycle
Functional Requirements Gathering
Architecture & Design
Implementation
System Test & User Acceptance Test
Deploy Into Production
Non-functional Requirements Gathering
Design for High Performance
Unit Performance Test & Code Optimization
Performance Test
Monitoring & Capacity Management









SPE: Requirements Phase
Review production performance metrics of the current version if available.
Determine non-functional requirements.
So that system performance goals can be set and measured against. 
Identify tools, resources and infrastructure.
Early identification allows budget and time allocation for installation and staff training.
15
16
Software Development Life Cycle 
Performance Engineering Life Cycle
Functional Requirements Gathering
Architecture & Design
Implementation
System Test & User Acceptance Test
Deploy Into Production
Non-functional Requirements Gathering
Design for High Performance
Unit Performance Test & Code Optimization
Performance Test
Monitoring & Capacity Management










SPE: Architecture and Design
Evaluate the alternatives.
Provide input from a performance perspective to the architecture being recommended.
Determine the capacity of the required infrastructure.
By combining the non-functional requirements with the architecture design, determine the underlying infrastructure requirements (e.g., CPU, RAM, GPU). 
Define performance targets for developers.
Define performance targets for the development teams across application components in case any bottleneck happens. 
17
Key considerations for designing software
Optimize algorithms: Choose algorithms that are efficient and optimize them to minimize the amount of processing required.
Use parallel processing: Parallel processing can help improve performance by distributing processing across multiple cores or processors.
Consider scalability: The architecture should be designed with scalability in mind. As the amount of data processed increases, the system should be able to handle the load without a significant decrease in performance.
Use caching and load balancing: Caching can help reduce the amount of processing required by storing frequently accessed data in memory. Load balancing can help distribute the workload across multiple servers to improve performance.




18
19
Software Development Life Cycle 
Performance Engineering Life Cycle
Functional Requirements Gathering
Architecture & Design
Implementation
System Test & User Acceptance Test
Deploy Into Production
Non-functional Requirements Gathering
Design for High Performance
Unit Performance Test & Code Optimization
Performance Test
Monitoring & Capacity Management










SPE: Testing
Create performance tests to simulate the workload model. 
Use the tests to validate the non-functional requirements. 
Identify application bottlenecks. 
Validate the impact of code and configuration changes on application performance. 
Identify performance regressions
20
What is a performance regression?
Old version
New version
Does the new version have worse performance than the old version?

21
22
Mozilla takes performance regression seriously! 
23
Software Development Life Cycle 
Performance Engineering Life Cycle
Functional Requirements Gathering
Architecture & Design
Implementation
System Test & User Acceptance Test
Deploy Into Production
Non-functional Requirements Gathering
Design for High Performance
Unit Performance Test & Code Optimization
Performance Test
Monitoring & Capacity Management









SPE: Monitoring & Capacity Management
Perform performance monitoring to continuously assess software performance, and to identify when the system is reaching its capacity. 
Perform capacity management to provide the required infrastructure capacity to sustain growth in business workloads. 
Provide production workload data to support the development of the next version. 
24
How the form it as a pattern mining problem?
25
Transaction data
If a callstack pattern is observed from many trace streams that cost large amount of CPU, it is suspicious to be a highly impactful performance bug
Benefits of SPE
Defining a clear set of non-functional requirements ensures successful development.
The constant and early focus on system performance during all phases of development prevents late and costly changes in the future.
By successfully delivering a functional and performing system as required, the customer will receive full value.
26
Performance Testing
27
Performance Testing
All the tests and methodologies to measure, verify and validate the performance of the system.
It is part of SPE.
Its objectives include:
Demonstrate system compliance with performance criteria.
Measure and identify the components that cause the system to not perform well.
28
Testing: Types of tests
Stress testing: Tests the limits of the system's capacity (beyond max load).
Endurance testing: Tests the system under the expected load for a long time.
Spike testing: Tests the reaction of the system by suddenly increasing or decreasing the load generated by a very large number of users
Capacity testing: Tests the system to find the maximum capacity.
Configuration testing: Test the effect of various configuration or configuration changes to the system.
Load testing: Tests the performance of the system under the expected load. 
A number of users who perform a specified number of requests during a given period of time.

29
Stress testing
Stress testing emphasizes on robustness, availability and error handling under a heavy load rather than on what is correct behavior under normal situations.

Particularly important for critical software but is used for all types of software.

30
Characteristics of stress testing
Stress testing analyzes the behavior of the system after a failure.
Stress testing makes sure that the system recovers after failure.
It ensures to display appropriate error message when the system is under stress.
Metrics: Time to failure, error rates, behavior under failure conditions, and recovery time
31
Testing: Types of tests
Stress testing: Tests the limits of the system's capacity (beyond max load).
Endurance testing: Tests the system under the expected load for a long time.
Spike testing: Tests the reaction of the system by suddenly increasing or decreasing the load generated by a very large number of users
Capacity testing: Tests the system to find the maximum capacity.
Configuration testing: Test the effect of various configuration or configuration changes to the system.
Load testing: Tests the performance of the system under the expected load. 
A number of users who perform a specified number of requests during a given period of time.

32
Endurance testing
Endurance Testing is performed to observe whether an application can resist the processing load it is expected to have to endure for a long period (months or a year).
Endurance testing includes the testing of the operating system and the computer hardware up to or above their maximum loads for a long period of time.
33
Endurance testing
It helps in identification of performance problems occurs when system is used for a long period of time.
Memory consumption is considered to determine potential failures

Metrics: Memory consumption, response time consistency, error rates over extended periods, resource leaks.
34
Looking for known patterns:Deadlocks and memory leak




Performance data under steady load
[Avritzer et al., 2012]
CPU
Memory






Deadlocks and memory leak: before and after fix




Before fix
After fix
[Avritzer et al., 2012]
Testing: Types of tests
Stress testing: Tests the limits of the system's capacity (beyond max load).
Endurance testing: Tests the system under the expected load for a long time.
Spike testing: Tests the reaction of the system by suddenly increasing or decreasing the load generated by a very large number of users
Capacity testing: Tests the system to find the maximum capacity.
Configuration testing: Test the effect of various configuration or configuration changes to the system.
Load testing: Tests the performance of the system under the specific load. 
A number of users who perform a specified number of requests during a given period of time.

37
Load Testing 
Objective: To determine how the system behaves under expected load scenarios. It checks the system's performance by applying the anticipated load in terms of users or tasks it can handle within defined performance criteria (e.g., 1000 requests/second).

Metrics: Response time, throughput, transaction rates, and server resource utilization under anticipated load conditions.
38
Question: you have online gaming server,  you would like to validate server stability and performance in a long period of time (over a couple weeks) understand a stable number of players. What tests will you use? 
39
Load Testing 
Mimics multiple users repeatedly performing the same tasks 
Take hours or even days
Produces GB/TB of data that must be analyzed 
Test Design
Test Execution
Test Analysis
How can we design loads?
41
Designing load Tests
Test report
Loading Test Data
Testing Load
Load Testing Objectives
Executing Load Tests
Analyzing Data
Designing Realistic Loads
Design loads, which resemble the expected usage once the system is operational in the field.
Characterizing an Aggregate Workload
Workload Mix (ratio of different types of requests)
browsing (30%), purchasing (10%) and searching (60%)
Workload Intensity
Rate of requests (e.g., 100  requests/sec) 
Designing Realistic Loads
Aggregate Workload
An E-Commerce System
Use-Case
How can we get the workload mix (ratio) of user action?
45
Estimate using historical data

web access logs for the past few months
192.168.0.1 - [22/Apr/2014:00:32:25 -0400] "GET /dsbrowse.jsp?browsetype=title&browse_category=&browse_actor=&browse_title=HOLY%20AUTUMN&limit_num=8&customerid=41 HTTP/1.1" 200 4073 10

192.168.0.1 - [22/Apr/2014:00:32:25 -0400] "GET /dspurchase.jsp?confirmpurchase=yes&customerid=5961&item=646&quan=3&item=2551&quan=1&item=45&quan=3&item=9700&quan=2&item=1566&quan=3&item=4509&quan=3&item=5940&quan=2 HTTP/1.1" 200 3049 177

192.168.0.1 - [22/Apr/2014:00:32:25 -0400] "GET /dspurchase.jsp?confirmpurchase=yes&customerid=41&item=4544&quan=1&item=6970&quan=3&item=5237&quan=2&item=650&quan=1&item=2449&quan=1 HTTP/1.1" 200 2515 113
For customer 41: browse -> purchase
Estimate using historical data
Estimate the probability/intensity based on logging
User 1: log -> search -> purchase
User 2: log -> browse -> browse -> purchase
User 3: log -> search -> browse -> purchase
…

48
log -> search (40/100)
Log-> browse (60/100)
Search->browse (3/60)
Search 0-> purchase (57/60)
…


Login

Search

Purchase

Browse
…
…
0.4
0.6
0.8
0.15
0.05
0.05
0.95
Estimate using historical data
For new project
Set equivalent load for each action
Refine the load as you get some historical data
50
Aggregate Workload - Workload Intensity
Steady Load
Ease of measurement
Memory leaks?

Step-wise Load
Same workload mix
Different workload intensity
User increase in step-wise?
[Bondi, CMG 2007]
[Hayes, CMG 2000]
https://support.smartbear.com/loadcomplete/docs/testing-with/configuring/load-test-editor/ramp-up.html

Realistic load tests are based on (historical) field workloads, but field workloads change over time
Keep updating the realistic load tests
How can we design loads?
53
Designing load Tests
Test report
Loading Test Data
Testing Load
Load Testing Objectives
Executing Load Tests
Analyzing Data
Designing Fault-Inducing Loads
Design loads, which are likely to cause functional or non-functional problems under load. 
Identify potential load sensitive modules and regions for load sensitive faults  (e.g., memory leaks and incorrect dynamic memory allocation
Annotating the Control Flow Graph of malloc() / free() calls and their sizes
Write test cases which exercise the code regions with high LSI values

[Yang el al., ISSTA 1996]
Performance Test Process
55
Designing Performance Tests
Performance Test report
Performance Test Data
Testing Load
Performance Test Objectives
Executing Performance Tests
Analyzing Performance Data
Live-user Based Test Execution
Coordinated live-user testing
Users are selected based on different testing criteria (e.g., locations, browser types, etc.)
Reflects realistic user behavior
Obtain real user feedbacks on acceptable performance and functional correctness

Hard to scale (e.g., limited testing time)
Limited test complexity due to manual coordination
Driver-based Test Execution
Easy to automate
Scale to large number of requests

Hard to track some system behavior (e.g., audio quality or image display)
No real user feedback
Use existing tools to coordinate the testing
Test monitoring and data collection
Test Monitoring and Data Collection
Metrics and Logs
Test Monitoring Tools

Task Manager
JConsole
CA Willy
App Dynamics
pidstat
Performance Test Process
60
Designing Performance Tests
Performance Test report
Performance Test Data
Testing Load
Performance Test Objectives
Executing Performance Tests
Analyzing Performance Data
Sample Counters
Sample Execution Logs




Version 1
Version 2


Threshold from a prior version
Threshold from requirement
Verifying Against Threshold Values
Detecting Known Problems Using Patterns
Patterns in the memory utilizations
Memory leak detection

Patterns in the logs
Error keywords

Looking for known patterns:Deadlocks and memory leak




Performance data under steady load
[Avritzer et al., 2012]
CPU
Memory






Looking for keywords in logs
Building performance models
Machine learning
(Black box) model



Anomaly




Predict using machine learning models
Reference
Jiang ZM. Load testing large-scale software systems. In2015 IEEE/ACM 37th IEEE International Conference on Software Engineering 2015 May 16 (Vol. 2, pp. 955-956). IEEE.
Jiang ZM, Hassan AE. A survey on load testing of large-scale software systems. IEEE Transactions on Software Engineering. 2015 Jun 15;41(11):1091-118.
https://www.geeksforgeeks.org/software-testing-endurance-testing/
https://www.geeksforgeeks.org/stress-testing-software-testing/
https://www.geeksforgeeks.org/difference-between-load-testing-and-stress-testing/?ref=lbp



69
70
Software performance metrics
Measurements: Basic concepts
Objectives: 
Evaluate compliance with performance targets.
Provide input data for SPE models, to verify and validate models.
Monitor performance during the software lifecycle.
Static and dynamic measurements
Static: No need to run the system.
Dynamic: The system must be running during the measurement.
Performance measures are quite dynamic. 
Internal and external measurements
Internal: Code to detect events and record performance data must be inserted into the system code.
External: The software that measures is independent of the software that is measured.
71
Measurements: Process
Understand the objective of the measurement (questions and hypothesis).
Identify the data needed to answer these questions, collection tools and measurement techniques.
Identify experimental variables and controls.
Define the test cases: workload, software component and environment for each test.
Run the tests and collect the data.
Analyze, interpret, present the results.
72
Measurements: Example - Exercise
You need to develop a system that needs a sorting functionality. You have to choose between an existing solution or to develop the functionality from scratch.

Define the plan of measurements to evaluate the two options.
73
Measurements: Sorting Component
Objective: To use a standard sorting algorithm or to develop a personalized algorithm.
Data collection:
Measure the resource requirements (CPU, disk, memory) for each algorithm.
Use a system to record events.
Evaluate the measurement overload on the performance of the measured system.
Experimental variables:
Number of items
Item size
Order of original data
The sorting algorithm
Test cases:
List length: 36, random ordered numbers
List length: 2000, random ordered numbers 
List length: 8400, random ordered numbers 
Run the tests: Run each test cases several times.
74
Measurements: Data Type
Workload data: number, rate and query patterns
Data characteristics: number and size of data, frequency of queries for data
Execution characteristics:
Path characteristics: number of executions for each important path, number of repetitions of loops, probability of execution of conditional paths.
Software resource usage: number of requests for each software resource, average execution time.
Processing overload: the time of processing resources (CPU, disk, memory) required by software resources.
System usage:
Response time
Throughput
Use of processing resources: processing time + waiting time
Resource utilization: percentage of busy time
Resource queue length: number of tasks waiting to be served.
75
Measurements: Bias
Measurement bias is hard to avoid and unpredictable. 
Example 1: How come the same application today runs faster compared with yesterday?
Example 2: Why the response time is very different when running the same binary under different user accounts?
Example 3: Why the code optimization only works on my computer?




[Mytkowicz et al., ASPLOS 2010]
Repeated measurement
Randomize experiment setup
Measurements: Challenges
System disturbance
When the measurement system affects the performance of the system being measured.
Timing of measurements
Consider the operating system clock, sampling interval
Reproducible results
The system is not isolated and other operations affect monitoring and performance.
Workload generation
77
Challenges of SPE
By promoting time to market and budget constraints, the importance of SPE in the software lifecycle is reduced.
Performance is perceived by users.
Developers know the features but they cannot perceive the performance.
Quality experts know performance, but they don't know features.
One recommended solution to bridge the gap is automation.
Eliminate the need for qualified people for manual construction of methods and models for performance.
Reduce time and effort for performance validation.
78
