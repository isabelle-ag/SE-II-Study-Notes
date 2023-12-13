# Study Notes for Comp 4350: Software Engineering II - Lecture 7

## AIOps (Artificial Intelligence for IT Operations)

- **Definition**: AIOps combines big data, machine learning, and visualization to enhance IT operations like deployment and monitoring. It addresses DevOps challenges with AI.

## Monitoring in DevOps

- Critical for quality assurance in IT services.
- Involves logs, metrics, and traces.
- Increasing data volume and complexity require efficient monitoring tools.

## Artificial Intelligence (AI)

- **Definition**: Simulation of human intelligence processes by machines, including learning, reasoning, and self-correction.
- Two approaches: Knowledge-based (e.g., autopilot systems) and machine learning-based (e.g., AlphaGo).

## Machine Learning Techniques

- Common techniques include:
    - Semi-supervised learning
    - Classification (categorical)
    - Regression (numeric)
    - Frequent pattern mining

## Frequent Pattern Mining

- Finding sets of items that frequently occur together.

## Clustering

- Grouping a set of objects into classes of similar objects.

## Anomaly Detection

- Identifying data points, events, or observations that deviate from a dataset's normal behavior.

## Autonomous Configuration of Software Systems

- Manually configuring large-scale systems is costly and error-prone.
- Autonomous configuration aims for self-monitoring, self-configuring, and self-optimizing systems.

## Performance and Workload

- Performance is influenced by a system's configuration and the characteristics of its workload.

## Autonomous Configuration and Its Challenges

- Ensuring minimal footprint, fast response, and understanding the relationship between configuration parameters and performance.
- Avoid exhaustive testing due to feasibility.

## Mining Monitoring Data

- Utilizing logging data right involves parsing, abstracting, and analyzing for diagnostics, anomaly detection, and incident prediction.

## Methodology for Performance Debugging

- Process includes extracting of interest, mining frequent patterns, and clustering for analysis.

## AIOps Research Sub-Areas

- Automated logging, log abstraction, anomaly detection, performance analysis, incident prediction, logging practices, fault diagnostics, system comprehension, autonomous configuration, AIOps infrastructure, generating monitoring code right, using monitoring data right.

## Log Parsing

- First step in log analysis tasks.
- It is the process of converting unstructured log data into a structured data format.

## Case Studies

- Examples include detecting performance bugs in Windows Explorer UI and predicting node failures in cloud platforms.

## Predictive Analytics in AIOps

- Predicting failures in cloud systems using monitoring data to recognize differing patterns between failed and normal nodes.

## Scenario Exercise

- For predicting runtime failures in the next two hours, use Anomaly detection or Incident prediction solutions.

## References

- Includes studies and reports from EMSE, ICSE, JSME, ICSM, TOSEM, and other reputable sources on various topics related to AIOps.

## Observer Effect

- Observation of a system can itself perturb the system, known as the observer effect.

---

---

# Class Notes

---

### Slide 1
Title: Comp 4350 Software Engineering II Lecture 7  
Dr. Shaowei Wang

### Slide 2
Title: Agenda
- What is AIOps
- Motivating example
- Sub-areas of AIOps research

### Slide 3
Title: AIOps (Artificial Intelligence for IT Operations)
- AIOps enhances IT operations (deployment and monitor) through greater insights by combining big data, machine learning, and visualization.
- Addresses DevOps challenges with AI
- From: 2018 Gartner

### Slide 4
Title: Monitoring is critical for ensuring the quality of the delivered services
- deploy
- operate
- test
- build
- code
- plan
- release
- Dev
- Ops
- monitor

### Slide 5
Title: Monitoring is critical for ensuring the quality of the delivered services
- deploy
- operate
- test
- build
- code
- plan
- release
- Dev
- Ops
- monitor
- Logs
- Metrics
- Traces

### Slide 6
Title: Increasing volume and complexity of monitoring data
- Production Environments
- Billions of logs, metrics, and alerts per day
- Human Brain
- Hundreds/thousands of events
- Analysis of big and complex monitoring data poses challenges to software monitoring.

### Slide 7
Title: What is AI?
- Simulation of human intelligence processes by machines, especially computer systems.
- Includes learning, reasoning, and self-correction.

### Slide 8
Title: Common machine learning techniques
- Semi-supervised
- A small amount of labeled data with a large amount of unlabeled data.

### Slide 9
Title: Classification (categorical)

### Slide 10
Title: Regression (numeric)

### Slide 11
Title: Frequent pattern (itemset) mining
- Goal: finding sets of items frequently occurring together

### Slide 12
Title: Definition: Frequent Itemsets
Body:
- Itemset: a set of items
- E.g., acm={a, c, m}
- (absolute) Support of itemsets
- Sup(acm)=3
- Given min_sup = 3, acm is a frequent pattern
- Frequent pattern mining: find all frequent patterns in a database
- Transaction database

### Slide 13
Title: Clustering: the process of grouping a set of objects into classes of similar objects

### Slide 14
Title: Anomaly detection
- Identifies data points, events, or observations that deviate from a dataset's normal behavior.

### Slide 15
Title: Beyond Ops: Making monitoring code right
- Monitoring code made right
- Monitoring data used right
- Monitoring code
- Monitoring data

### Slide 16
Title: Motivating Example
Body: Autonomous configuration of large-scale software systems

### Slide 17
Title: Manually configuring large-scale software systems is costly & error-prone
- Software system
- Workload
- Performance
- Configuration
- Unsatisfied perf.?
- Workloads are constantly evolving, requiring constant human intervention for optimal performance

### Slide 18
Title: Parameters of Database system
Body: 
- Cache.size
- Fetch.blocksize
- Table.pageReserve
- ...

### Slide 19
Title: Characteristics of Workload
Body:
- Number of user requests
- Query type (insert, fetch)
- Size of each fetch
- Frequency of queries on each table
- ...

### Slide 20
Title: Optimization goal
Body:
- Minimize the latency of queries on average
- Use minimal memory

### Slide 21
Title: Using an AIOps solution to autonomously tune system configurations
- Software system
- Self-monitoring
- Self-configuring
- Self-optimizing
- Optimized parameter values
- Logs
- Performance measures
- Metrics
- [Li et al. 2018]

### Slide 22
Title: Challenges in autonomous configuration of large-scale software systems
- Complex system behavior
- Minimal footprint
- Fast response to environment
- [Li et al. 2018]

### Slide 23-24
Title: Challenges in autonomous configuration of large-scale software systems
- Complex system behavior
- Minimal footprint
- Fast response to environment
- [Li et al. 2018]

### Slide 25
Title: Understanding the relationship between config. parameters and performance metrics
- Asking domain experts
- Perf. related parameters
- Perf. data
- Impact of parameters?
- Running tests
- [Li et al. 2018]

### Slide 26
Title: Blue force approach
Body:
- Exhaustively run different combinations of parameter values.
- Too many combinations become infeasible.
- Multivariate Adaptive Regression Splines (MARS)
- [Li et al. 2018]

### Slide 27
Title: Understanding the relationship between config. parameters and performance metrics
- Perf. related parameters
- Perf. data
- Perf. critical parameters
- Running tests
- Only a few candidate parameters significantly impact system performance.
- Multivariate Adaptive Regression Splines (MARS)
- [Li et al. 2018]

### Slide 28-29
Title: Challenges in autonomous configuration of large-scale software systems
- Complex system behavior
- Minimal footprint
- Fast response to environment
- [Li et al. 2018]

### Slide 30
Title: How to capture KPI for different settings of parameters
Body:
- Simulating the behavior of different parameter settings and recording them.
- Slow but accurate
- Historical data: pairs <parameters, KPIs>
- Fast but less accurate

### Slide 31
Title: Machine learning-based
Body:
- Use accumulating data to train ML models for auto-tuning parameters.
- Pairs <characteristics of current workload, settings of parameter>

### Slide 32-33
Title: Challenges in autonomous configuration of large-scale software systems
- Complex system behavior
- Minimal footprint
- Fast response to environment
- [Li et al. 2018]

### Slide 34
Title: Separating the autonomous configuration capabilities from the original system
- Software system
- Self-monitoring
- Self-configuring
- Self-optimizing
- Optimized parameter values
- Remote control
- Logs
- Performance measures
- Metrics
- [Li et al. 2018]

### Slide 35-36
Title: Autonomous configuration significantly improves system performance
- Low workload, KPI is optimal
- High workload, KPI drops
- Autonomous configuration
- [Li et al. 2018]

### Slide 37-40
Title: Sub-areas of AIOps research
- Automated logging
- Log abstraction
- Anomaly detection
- Performance analysis
- Incident prediction
- Logging practices
- Fault diagnostics
- System comprehension
- Autonomous configuration
- AIOps infrastructures
- Generating Monitoring code right
- Using Monitoring data right

### Slide 41
Title: Log parsing is the first step for many log analysis tasks
- Fault diagnostics
- Anomaly detection
- System comprehension
- Parsing splits unstructured log data into structured format.

### Slide 42-43
Title: Log parsing is the first step for many log analysis tasks
- Fault diagnostics
- Anomaly detection
- System comprehension

### Slide 44
Title: Why we need this? Reduce the size
- [Jiang et al. 08]

### Slide 45
Title: How many types of “errors” are there? – prioritize work based on frequency
Body:
- Enterprise application generates 1.6 million log lines in 8 hours; 23,000 lines contain “fail” or “failure”
- Total 319 execution events; 16 contain “fail” or “failure”
- [Jiang et al. 08]

### Slide 46
Title: Sub-topics of AIOps research
- Automated logging
- Log abstraction
- Anomaly detection
- Performance analysis
- Incident prediction
- Logging practices
- Fault diagnostics
- System comprehension
- Autonomous configuration
- AIOps infrastructures
- Generating Monitoring code right
- Using Monitoring data right

### Slide 47
Title: Fault diagnostics
- Identify the root leading to the fault and its location

### Slide 48-49
Title: Performance Debugging in the Large via Mining Millions of Stack Traces - Microsoft
- Performance bugs slow down the system
- Windows collects millions of execution traces
- Call stack analysis for system slowdown
- [ResearchGate Link]

### Slide 50-51
Title: Using clustering to reduce the size
- Group related execution trace patterns for large-scale performance debugging
- Select representative patterns from each cluster

### Slide 52-53
Title: Methodology
- Extract area of interest
- Extract frequent sequential patterns
- Cluster patterns based on similarity measure
- Hierarchical clustering
- [Alignment of patterns]

### Slide 54
Define cost of alignment (edit cost) and get optimal alignment.

### Slide 55
Title: Experiment
- Finding hidden performance bugs on Windows Explorer UI
- Input: 921 trace streams, 140 million call stacks
- Output: 1,215 pattern clusters
- Detection of 12 highly impactful performance bugs
- [Li et al. 2018]

### Slide 56-60
Title: Sub-topics of AIOps research
- Automated logging
- Log abstraction
- Anomaly detection
- Performance analysis
- Incident prediction
- Logging practices
- Fault diagnostics
- System comprehension
- Autonomous configuration
- AIOps infrastructures
- Generating Monitoring code right
- Using Monitoring data right
- Case study on Dell DVD Store
- 99.99% reduction in viewed log lines with a precision of 56-100%

### Slide 61-64
Title: Predicting Node Failures in an Ultra-large-scale Cloud Computing Platform
- Early monitoring data shows differences between failed nodes and normal nodes.
- [Li et al. 19]
- AUC: 0.92

### Slide 65-66
Title: Exercise: select the AIOps solutions for given scenarios
- Given existing monitoring data, determine runtime failure in the next two hours.
- A. Fault diagnostics
- B. Anomaly detection
- C. Incident prediction

### Slide 67-69
Title: References
- Various papers on AIOps topics

### Slide 70-73
Title: Comparing system performance with a baseline derived from previous runs
- Distribution, Evolution, Step-wise Performance Diagnosis
- [Jiang et al. 09]

### Slide 74
Title: When you observe a system, you are perturbing it. No free lunch
- Observer effect applies to monitoring software systems
