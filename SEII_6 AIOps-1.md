### Study Notes for Comp 4350 Software Engineering II Lecture 7

#### I. Key Concepts
- **Main Idea 1:** AIOps combines big data, machine learning, and visualization to enhance IT operations for deployment and monitoring, addressing DevOps challenges.
- **Main Idea 2:** Monitoring is vital in maintaining service quality, with increasing data volume and complexity requiring sophisticated analysis.
- **Main Idea 3:** Autonomous configuration of large-scale software systems using AIOps can improve performance and address the constant need for manual reconfiguration due to changing workloads.

#### II. Definitions
- **AIOps:** Artificial Intelligence for IT Operations, enhancing IT functions through insights provided by big data and machine learning.
- **Monitoring Data:** Includes logs, metrics, and traces that are essential for maintaining the system's health.
- **Autonomous Configuration:** The capability of a software system to self-tune its configuration parameters based on artificial intelligence techniques.

#### III. Important Details
- **Point 1:** Billions of logs, metrics, and alerts are generated daily, overwhelming the human ability to analyze without AI assistance.
- **Point 2:** Machine learning approaches in AIOps include semi-supervised learning, classification, regression, frequent pattern mining, clustering, and anomaly detection.
- **Point 3:** The challenges of autonomous configuration are complex system behavior, minimal footprint, and fast response to the changing environment.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** DevOps lifecycle highlighting the central role of monitoring in deployment, operation, and release.
- **Diagram 2:** Visualization of monitoring data types (logs, metrics, traces) and their proliferation in production.
- **Diagram 3:** Workflow diagrams illustrating the process of autonomous system configuration optimization using AIOps.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** Frequent Itemsets and Support in pattern mining, fundamental for data analysis within AIOps.
- **Formula/Theorem 2:** Multi-variate Adaptive Regression Splines (MARS), for performance optimization in autonomous configuration.
- **Formula/Theorem 3:** Methodology for performance debugging through mining of stack traces, including pattern mining and clustering.

#### VI. Examples
- **Example 1:** Autonomous configuration of cache size, fetch.blocksize, and table.pageReserve for performance improvements.
- **Example 2:** Applying machine learning models to performance data to autonomously tune system configurations.
- **Example 3:** Performance debugging using mined stack traces, discovering impactful performance bugs within Windows Explorer.

#### VII. Summary/Conclusion
- **Recap of Main Points:** AIOps is crucial for enhancing IT operations through intelligent data analysis and monitoring, and autonomous configurations can significantly improve system performance. 
- **Connections between Concepts:** There is a strong relation between AIOps and the DevOps lifecycle, with AI providing solutions for pain points in system monitoring and configuration.

#### VIII. Additional Resources
- **Textbook Pages:** Seek relevant chapters that cover artificial intelligence in IT operations, system monitoring and optimization, and machine learning applications in software engineering.
- **Online Resources:** Research papers cited in the lecture, such as those by Li et al., Jiang et al., and other studies on AIOps and its applications.

Notes:
- To effectively use the study notes, cross-reference with the PowerPoint slides and additional readings where necessary for deeper comprehension.
- For practical understanding, you may also consider accessing datasets to apply the concepts and techniques mentioned in the notes, particularly regarding pattern mining and anomaly detection.

---

Notes: 
Comp 4350Software Engineering IILecture 7
Dr. Shaowei Wang
Agenda
What is AIOps
Motivating example
Sub-areas of AIOps research
2
AIOps (Artificial Intelligence for IT Operations)
AIOps enhances IT operations (deployment and monitor) through greater insights by combining big data, machine learning and visualization
 AIOps addresses the DevOps challenges with AI
3
From: 2018 Gartner




Monitoring is critical for ensuring the quality of the delivered services
4


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




Monitoring is critical for ensuring the quality of the delivered services
5


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
Increasing volume and complexity of monitoring data
6
Production Environments
Billions of logs, metrics, and alerts per day
Human Brain
Hundreds/thousands of events
The analysis and utilization of the big and complex monitoring data poses challenges to software monitoring..
What is AI?
The simulation of human intelligence processes by machines, especially computer systems. These processes include learning, reasoning, and self-correction.
7
Knowledge-based approach to AI: hard coded knowledge using logical inference rules (e.g., autopilot systems)

Machine learning-based approach to AI: automatically learned rules from data (e.g., AlphaGo)
Common machine learning techniques
Semi-supervised
8
A small amount of labeled data with a large amount of unlabeled data. 
Classification (categorical)
9
Regression (numeric)
10
Frequent pattern (itemset) mining
11
Goal: finding sets of items frequently occurring together
12
Definition: Frequent Itemsets
Itemset: a set of items
E.g., acm={a, c, m}
(absolute) Support of itemsets
Sup(acm)=3
Given min_sup = 3, acm is a frequent pattern
Frequent pattern mining: find all frequent patterns in a database
Transaction database
12
Clustering: the process of grouping a set of objects into classes of similar objects


















































13
Anomaly detection
14
Anomaly detection (aka outlier analysis) is a step in data mining that identifies data points, events, and/or observations that deviate from a dataset's normal behavior. 
Beyond Ops: Making monitoring code right
15
Monitoring code made right
Monitoring data used right
Monitoring code
Monitoring data
Motivating Example
Autonomous configuration of large-scale software systems
16
Manually configuring large-scale software systems is costly & error-prone
Workload
Performance
Configuration
17

Unsatisfied perf. ?
Workloads are constantly evolving, requiring constant human intervention to ensure optimal performance
Parameters of Database system
Cache.size 
Some performance improvement may be seen by increasing the size of the cache, which reduces I/O. For best results, the cache size should be a prime number. Increasing the size may give improved performance at the expense of memory usage.
Fetch.blocksize
By knowing the number of rows of data you need to retrieve or fetch from the database, you can configure this parameter, using PointBase Server only, to minimize network traffic and improve performance. This can also be set via a JDBC statement for individual statements.
Table.pageReserve
By configuring this parameter you can reserve space in each table to improve the performance of the system every time it performs an UPDATE. This parameter specifies how much space should be reserved while inserting rows into a table. If the table is not updated, then you can set this value to 0.
…

18
Characteristics of Workload
Number of user requests
Query type (insert, fetch)
Size of each fetch
Frequency of queries on each table
…

19
Optimization goal
Minimize the latency of queries on average
Use minimal memory 
20
Using an AIOps solution to autonomously tune system configurations
Self-monitoring
Self-configuring

Self-optimizing
Optimized parameter values

Logs
21
Performance measures
Metrics
[Li et al. 2018]
Challenges in autonomous configuration of large-scale software systems
22
Complex system
behavior
Minimal footprint
Fast response to environment
[Li et al. 2018]
Challenges in autonomous configuration of large-scale software systems
23
Complex system
behavior
Minimal footprint
Fast response to environment

[Li et al. 2018]
Challenges in autonomous configuration of large-scale software systems
24
Complex system
behavior
Minimal footprint
Fast response to environment

[Li et al. 2018]
Understanding the relationship between config. parameters and performance metrics
Asking domain experts
25
Perf. related parameters
Perf. data
Impact of parameters?
Running tests
[Li et al. 2018]
Blue force approach
One way to fully understand the effect of the configuration parameters on system performance is to exhaustively run different combinations of the parameter values.
However, too many combination to test 
5 parameters, and each parameter has 10 settings, we have 10^5 combination! 
Infeasible! Each combination requires several hours to run.
What if coming with hundreds of parameters?
26
Understanding the relationship between config. parameters and performance metrics
Asking domain experts
27
Perf. related parameters
Perf. data
Perf. critical parameters
Running tests
Only a few out of many candidate parameters significantly impact system performance and reduce the search space.
Multivariate Adaptive Regression
Splines (MARS)
[Li et al. 2018]
Challenges in autonomous configuration of large-scale software systems
28
Complex system
behavior
Minimal footprint
Fast response to environment


[Li et al. 2018]
Real-time monitoring of system behavior using readily-existing logs and metrics data
29
Log & metric streams
Real-time perf. measures
Logs
Perf. opt.
Metrics
[Li et al. 2018]
How to capture KPI for different setting of parameters
Simulating the behavior of different setting of parameters and record them
Slow but accurate

Historical data
E.g., pairs <parameters, KPIs>
Fast but not very accurate



30
Machine learning-based
As time going, we will get more and more data!

Such data could be used to training machine learning models to auto-tune the parameters.
Pairs <characteristics of current workload, settings of parameter>


31
Challenges in autonomous configuration of large-scale software systems
32
Complex system
behavior
Minimal footprint
Fast response to environment

[Li et al. 2018]
Minimize the change of exiting system and the overhead of the system 
Adding new features to an existing needs to perform significant code changes and may affect the overall design of the system, which may cause additional bugs, development overheads, and maintenance problems.
33
Separating the autonomous configuration capabilities from the original system
Self-monitoring
Self-configuring

Self-optimizing
Optimized parameter values
Remote control

Logs
34
Performance measures
Metrics
[Li et al. 2018]
Autonomous configuration significantly improves system performance
35
Low workload, KPI is optimal
High workload, KPI drops
(KPI)
Autonomous configuration
[Li et al. 2018]
Autonomous configuration significantly improves system performance
36
KPI is always optimal


Adapting quickly to the changing workloads 
(KPI)
Autonomous configuration
[Li et al. 2018]
Sub-areas of AIOps research

37
38
Generating & leveraging monitoring data
39
Generating Monitoring code right
Using Monitoring data right
Monitoring code
Monitoring data
Sub-topics of AIOps research
40
Automated logging
Log   abstraction
Anomaly detection
Performance analysis
Incident prediction
Logging practices
Fault diagnostics
System comprehension

Generating Monitoring code right

Using Monitoring data right
Autonomous configuration
AIOps infrastructures
Sub-topics of AIOps research
41
Automated logging
Log   abstraction
Anomaly detection
Performance analysis
Incident prediction
Logging practices
Fault diagnostics
System comprehension


Autonomous configuration
AIOps infrastructures
Generating Monitoring code right
Using Monitoring data right
Log parsing is the first step for many log analysis tasks
42



Parsing is the process of splitting unstructured log data into structured data format.
Log parsing is the first step for many log analysis tasks
43


User checkout for accountID(Tom), item=100
User checkout for accountID(Jenny), item=100
Item shipped for accountID(Tom), item=100
User checkout for accountID(John), item=100





Why we need this? Reduce the size
[Jiang et al. 08]
44
How many types of “errors”are there? – prioritize work based on frequency
One enterprise application from BlackBerry generates 1.6 million log lines (in 8 hours) and 23,000 lines contain “fail” or “failure”
Total 319 execution events, among them 16 contains “fail” or “failure”




[Jiang et al. 08]
45
Sub-topics of AIOps research
46
Automated logging
Log   abstraction
Anomaly detection
Performance analysis
Incident prediction
Logging practices
Fault diagnostics
System comprehension


Autonomous configuration
AIOps infrastructures
Generating Monitoring code right
Using Monitoring data right
Fault diagnostics
Identify the root leading to the fault and its location

47
Performance Debugging in the Large via Mining Millions of Stack Traces - Microsoft
Performance bugs leads to unbearably slow system
To debug performance issues, Windows has the facility to collect millions of execution traces (data is available)
Call stack - … InitComponents, GetHashCode, GetShortPathName, MmAccessFault …

Which calls slow down the system?

48
https://www.researchgate.net/publication/241632979_Performance_debugging_in_the_large_via_mining_millions_of_stack_traces
How to form it as a pattern mining problem?
49
Transaction data
If a callstack pattern is observed from many trace streams that cost large amount of CPU, it is suspicious to be a highly impactful performance bug
Using clustering to reduce the size
Proposed solution:
Group related execution trace patterns together to enable performance debugging in large scale
Select the representative pattern from each cluster to investigate

50


























Using clustering to reduce the size
Proposed solution:
Group related execution trace patterns together to enable performance debugging in large scale
Select the representative pattern from each cluster to investigate

51




























Methodology
Phase 1: Extract area of interest
Focus on events
CPU consumption (if running)
Waiting time (if waiting)
Use developer's domain knowledge to localize this area of interest (e.g., the waiting time > threshold)
Phase 2: Extract frequent sequential patterns 
Phase 3: Cluster the patterns together (why? They want to consider slightly different patterns)
52
Methodology
Hierarchical clustering is performed
Key: similarity measure
Similarity measure:
Alignment of two patterns
Computation of similarity
53
54
Define cost of alignment (edit cost) and get optimal alignment.






Experiment
Finding hidden performance bugs on Windows Explorer UI
Input: 921 trace streams (A trace stream records a stream of system level events to capture the program execution behaviors during a time period of bad performance)
140 million call stacks
Output: 1,215 pattern clusters
Pattern mining and clustering time: 10 hours
Developer manually investigate the clusters (top-400)
Eight hours -> detect 12 highly impactful performance bugs

55
Sub-topics of AIOps research
56
Automated logging
Log   abstraction
Anomaly detection
Performance analysis
Incident prediction
Logging practices
Fault diagnostics
System comprehension


Autonomous configuration
AIOps infrastructures
Generating Monitoring code right
Using Monitoring data right
Anomaly detection
Anomaly detection (aka outlier analysis) is a step in data mining that identifies data points, events, and/or observations that deviate from a dataset's normal behavior. 
57
Automated Functional Analysis
(E2, E3) are always together:
(acquire_lock, release_lock)
(open_inbox, close_inbox) 
If we see (E2, E6) this might be a problem

E1
E2

E3

E4

E1
E2

E3

E4

E1
E2

E3

E4

E1
E2

E6

E4

[Jiang et al. 08]
Case study on Dell DVD Store
[Jiang et al. 08]

99.99% reduction in viewed log lines
with a precision of 56-100%
Sub-topics of AIOps research
60
Automated logging
Log   abstraction
Anomaly detection
Performance analysis
Incident prediction
Logging practices
Fault diagnostics
System comprehension


Autonomous configuration
AIOps infrastructures
Generating Monitoring code right
Using Monitoring data right
Prediction the failure nodes on cloud
61
Early monitoring data shows different distributions between failed nodes and normal nodes in a large-scale cloud
62
The distributions of the alerts in failed vs. normal nodes
[Li et al. 19]
Predicting Node Failures in an Ultra-large-scale Cloud Computing Platform
63

[Li et al. 19]
Predicting Node Failures in an Ultra-large-scale Cloud Computing Platform
64

[Li et al. 19]
Predicting Node Failures in an Ultra-large-scale Cloud Computing Platform
65
[Li et al. 19]
AUC: 0.92
Exercise: select the AIOps solutions for given scenarios
Given the existing monitoring data of a large-scale software system, you want to determine whether there will be a  runtime failure in the next two hours.  Which type of AIOps solution will you use?
A. Fault diagnostics
B. Anomaly detection
C. Incident prediction

66
67
References
Automated logging: Li et al. Studying Software Logging Using Topic Models. [EMSE 2018]
Logging practices: Chen et al. Characterizing and Detecting Anti-patterns in the Logging Code. [ICSE 2017]
Autonomous configuration: Li et al. Adopting autonomic computing capabilities in existing large-scale systems: an industrial experience report. [ICSE-SEIP 2018]
Log abstraction: Jiang et al. An automated approach for abstracting execution logs to execution events. [JSME 2008]
Fault diagnostics: Syer et al. Leveraging performance counters and execution logs to diagnose memory-related performance issues. [ICSM 2013]
Anomaly detection: Jiang et al. Automatic identification of load testing problems. [ICSM 2008]
Performance analysis: Jiang et al. Automated Performance Analysis of Load Tests. [ICSM 2009]
Incident prediction:  Li et al. Predicting Node Failures in an Ultra-large-scale in Cloud Computing Platform: an AIOps Solution. [TOSEM 2020]
System comprehension: Shang et al. Assisting Developers of Big Data Analytics Applications When Deploying on Hadoop Clouds. [ICSE 2013]
Tune system configurations: Lu et al. Speedup your analytics: Automatic parameter tuning for databases and big data systems. Proceedings of the VLDB Endowment. 2019 Aug 26.
68
Sub-topics of AIOps research
69
Automated logging
Log  abstraction
Anomaly detection
Performance analysis
Incident prediction
Logging practices
Fault diagnostics
System comprehension


Autonomous configuration
AIOps infrastructures
Monitoring code made right
Monitoring data used right
Comparing system performance with a baseline derived from previous runs

[Jiang et al. 09]
Performance Analysis Report - Visual Comparison
Distribution
Evolution
[Jiang et al. 09]
Comparing system performance with a baseline derived from previous runs

[Jiang et al. 09]
Performance Analysis Report - Step-wise Performance Diagnosis
77% precision (low false positive rate)
[Jiang et al. 09]
When you observe a system, you are perturbing it. No free lunch 
Observer effect
Eg measuring the tire pressure lets out some of the air

Observer effect applies to the monitoring of software systems 
Eg performance overhead 
74
