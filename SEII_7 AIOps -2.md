### Study Notes for Comp 4350: Software Engineering II - Lecture 8: AIOps (Artificial Intelligence for IT Operations)

#### I. Key Concepts
- **Main Idea 1:** AIOps enhances IT operations by leveraging big data, machine learning, and visualization to provide greater insights.
- **Main Idea 2:** AIOps tackles DevOps challenges using AI to improve various sub-topics like automated logging and anomaly detection.
- **Main Idea 3:** The lecture includes a hands-on tutorial for anomaly detection using system logs within the context of AIOps.

#### II. Definitions
- **AIOps:** The application of artificial intelligence to enhance IT operations.
- **Anomaly Detection:** The identification of unexpected items or events in data sets, which differ to an extent from the norm.
- **Clustering:** A process in machine learning where a set of objects is divided into groups of similar items.

#### III. Important Details
- **Point 1:** AIOps is capable of addressing complex IT operational challenges such as system comprehension and fault diagnostics.
- **Point 2:** The hands-on anomaly detection tutorial by He et al. focuses on log collection, parsing, feature extraction, and detection.
- **Point 3:** AIOps uses common machine learning techniques like classification, clustering, and dimension reduction for data analysis.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** Flowchart of the anomaly detection process - highlights the steps from log collection to detection.
- **Diagram 2:** Example of GitHub repo link for AIOps data - provides practical resources for learning.
- **Diagram 3:** Visualization of clustering output - enhances understanding of how clustering segregates data.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** Euclidean distance formula - used in defining similarity between data points for clustering.
- **Formula/Theorem 2:** Principle Component Analysis (PCA) - a technique for reducing dimensionality while preserving variance.
- **Formula/Theorem 3:** Permutation feature importance - determines the significance of features in model performance.

#### VI. Examples
- **Example 1:** Step-by-step anomaly detection in system logs - illustrates how actual data gets processed for identifying anomalies.
- **Example 2:** Clustering with the k-means algorithm - provides a process walkthrough for grouping data points.
- **Example 3:** Use of Random Forest classification - shows how this model aggregates decisions from individual trees.

#### VII. Summary/Conclusion
- **Recap of Main Points:** The lecture covered the importance of AIOps in modern IT operations and showcased tools and methods for implementing AIOps, especially focusing on anomaly detection.
- **Connections between Concepts:** There is a connection between the big data and AI methodologies employed in AIOps and the broader goals of DevOps, specifically in automating and improving IT operational tasks.

#### VIII. Additional Resources
- **Textbook Pages:** Not specified.
- **Online Resources:** GitHub repository (https://github.com/shaoweiwang2010/SEII-AIOps_data), Loghub, Azure VM traces, Google cluster traces, Alibaba cluster traces.

#### IX. References
- **[1]** Li et al. "Predicting Node Failures in an Ultra-large-scale Cloud Computing Platform: an AIOps Solution." TOSEM ‘20.
- **[2]** He et al., "Experience Report: System Log Analysis for Anomaly Detection." ISSRE ‘16.
- **[3]** Various authors provided insight on machine learning models, data types, and specific techniques pertinent to AIOps.

(Note: Sections are organized based on the provided information, but actual content for study notes would depend on the fuller text and content of the lecture and readings.)

---

Notes: 
Comp 4350Software Engineering IILecture 8
Dr. Shaowei Wang
AIOps (Artificial Intelligence for IT Operations)
AIOps enhances IT operations through greater insights by combining big data, machine learning and visualization
 AIOps addresses the DevOps challenges with AI
2
From: 2018 Gartner
Sub-topics of AIOps research
3
Automated logging
Log   abstraction
Anomaly detection
Performance analysis
Incident prediction
Logging practices
Fault diagnostics
System comprehension

Monitoring code made right

Monitoring data used right
Autonomous configuration
AIOps infrastructures
Agenda
Hand-on tutorial for anomaly detection
Practices of using machine learning techniques
4
Hand-on tutorial for Anomaly Detection

5
Hands-on tutorial: Analyzing System Logs for Anomaly Detection
6
He et al., Experience Report: System Log Analysis for Anomaly Detection. ISSRE ‘16.
Log Collection
Log Parsing
Feature Extraction
Anomaly Detection
Hadoop distributed file system(DFS)
Hands-on tutorial: Analyzing System Logs for Anomaly Detection
7
He et al., Experience Report: System Log Analysis for Anomaly Detection. ISSRE ‘16.
Log Collection
Log Parsing
Feature Extraction
Anomaly Detection
Goal: Detect anomaly behavior on each block
Hands-on tutorial: Analyzing System Logs for Anomaly Detection
8
He et al., Experience Report: System Log Analysis for Anomaly Detection. ISSRE ‘16.
Log Collection
Log Parsing
Feature Extraction
Anomaly Detection
GitHub repo: 
https://github.com/shaoweiwang2010/SEII-AIOps_data

Hands-on tutorial: follow-up tasks 
Using correlation analysis to reduce the feature dimension before fitting the model 
Using PCA analysis to reduce the feature dimension before fitting the model
Mining frequent patterns in the logs and summarize the frequent normal and abnormal patterns 
Clustering  log sequences based on the counts of each log event in a sequence
Classify the anomaly of each log line using a bag of words and treat log level as an ordinal variable
9
Common machine learning techniques
Classification
Clustering 
Dimension reduction

Two steps process - classification
11
Training and Testing sets, Model construction, Model Evaluation
->classifying future or unknown objects
      Evaluation metrics: Accuracy, Precision, Recall, F-measure, AUC, MAP, etc. 
Model Application
12
From: A. E. Hassan and T. Xie: Mining Software Engineering Data
Different types of data in supervised learning
13
Data Types
Categorical
Numerical
Nominal
Binary
Ordinal
Continuous
Discrete
True, False
English, French, Spanish
Beginner, intermediate, advanced
1.76 m, 
65.0 kg
60-70 kg,
70-80 kg
Encoding categorical data into numerical data
14
Data Types
Categorical
Numerical
Nominal
Binary
Ordinal
Continuous
Discrete

Ordinal data 
Li et al., Which log level should developers choose for a new logging statement? EMSE ‘17.
Handling different types of data in supervised learning
First of all, consider the right models
Some models cannot handle categorical data directly (e.g., linear regression model)
Some models can handle categorical response variables but not categorical explanatory variables (e.g., logistic regression model)
Some models can handle both categorical response variables and categorical explanatory variables (e.g., decision tree-based models, random forest)
Some models provide special handling for certain data types (e.g., ordinal regression model for ordinal data)
16
Commonly used classification models
Random forest
construct a forest of decision trees, and get the final prediction based on the votes of each decision tree.


Commonly used classification models

Logistic regression
Commonly used classification models
Support vector machine
Map the data points into a space, so that the margin between two classes is maximized. 

Starting from the simple one first
Logistic regression, which is explainable 
understanding indicator is the most important one to predict a failure of cloud node
Random forest
Achieve robust performance
Common machine learning techniques
Classification
Clustering 
Dimension reduction

Two types of clustering
22
Hierarchical clustering
Partitional clustering
22
1. Decide on a value for k (number of clusters).	
2. Initialize the k cluster centers (randomly, if necessary).	
3. Decide the class memberships of the N objects by assigning them to the nearest cluster center.	
4. Re-estimate the k cluster centers, by assuming the memberships found above are correct.	
5. If none of the N objects changed membership in the last iteration, exit. Otherwise goto 3.	
Algorithm k-means
The K-Means Clustering Method 
24



K=2
Arbitrarily partition the objects into K clusters
Compute the cluster means
Update the cluster means
Reassign

Reassign
Similarity is widely used in various machine learning techniques.
Clustering: the process of grouping a set of objects into classes of similar objects


















































26
Anomaly detection
27
But, what is similarity?
28
The quality or state of being similar; likeness; resemblance; as, a similarity of features. 
Webster's Dictionary
Feature engineering
30
Define cost of alignment (edit cost) and get optimal alignment.






Similarity measures
How to determine similarity between data points
using various distance metrics
Let x = (x1,…,xn) and y = (y1,…yn) be n-dimensional vectors of data points of objects g1 and g2
Euclidean distance









31
Cosine similarity 
Similarity measures
Correlation distance



33
Jaccard Similarity
Common machine learning techniques
Classification
Clustering 
Dimension reduction

Perf regression analysis usually needs to examine hundreds of perf metrics
Perf metrics
CPU
Memory
Response time
…
Logs
Warnings
Errors
Exceptions
…
+
=
Heavy tasks for performance engineers
36
Blue force approach
One way to fully understand the effect of the configuration parameters (more than 100) on system performance is to exhaustively run different combinations of the parameter values.
However, too many combination to test 
5 parameters, and each parameter has 10 settings, we have 10^5 combination! 
Infeasible! Each combination requires several hours to run.
What if coming with hundreds of parameters?
37
Dealing with high dimensionality
38
Understanding the relationship between config. parameters and performance metrics
Asking domain experts
39
Perf. related parameters
Perf. data
Perf. critical parameters
Running tests
Only a few out of many candidate parameters significantly impact system performance and reduce the search space.
Multivariate Adaptive Regression
Splines (MARS)
[Li et al. 2018]
Feature importance
How much contribution of a feature (e.g., Cache.size,Fetch.blocksize) makes to the prediction power of a model (e.g., average query response time)
More contribution of a feature makes, more important it is

40
Permutation feature importance
After evaluating the performance of your model, you permute the values of a feature of interest and reevaluate model performance. 
If more performance drops due to the permutation, more importance it is; otherwise, less importance
It is a model-agnostic approach

41
Dimension reduction – Principle Component Analysis (PCA)
PCA transforms a set of correlated variables into a reduced set of uncorrelated variables (principle components, or PC)
Each PC is a linear combination of the original variables
A smaller number of PCs can explain the variance of the original variables
42
Dimension reduction –  correlation analysis
Y = a1*X1 + a2 * X2 + a3 * X3

If X1 = b2 * X2 + b3 * X3, we can remove X1, and since we can use X2 and X3 to represent X1.
Dimension reduction – correlation analysis
44

Other dimension reduction techniques

t-Distributed Stochastic Neighbor Embedding (t-SNE): 
A prize-winning technique for dimensionality reduction that is particularly well suited for the visualization of high-dimensional datasets
Idea is simple: models each high-dimensional object by a two- or three-dimensional point in such a way that similar objects are modeled by nearby points and dissimilar objects are modeled by distant points with high probability.


45
Exercise: select the most appropriate techniques for different scenarios
Your monitoring data recorded user behaviors (e.g., browsing items, purchasing items, etc.) in an E-commerce system. You want to find the patterns of user behaviors (e.g.., browsing item A following purchasing item B). Which technique will you use?
Classification
Clustering
Frequent Pattern Mining
Dimension Reduction



46
Tools and Datasets

47
Available tools
Industrial solutions:
Application Performance Management (APM) Tools: e.g., AppDynamics, New Relic, Dynatrace, and Pinpoint (open source)
Log Management Tools: e.g., Splunk, ELK Stack (open source), Loggly, and Graylog
Academic tools:
LogPAI (https://github.com/logpai) : log parsers, anomaly detection, where to log
48
Public Datasets
Loghub (https://github.com/logpai/loghub): a collection of system logs generated by different systems
Azure VM traces (https://github.com/Azure/AzurePublicDataset): two representative traces of the virtual machine (VM) workload of Microsoft Azure collected in 2017 and 2019.
Google cluster traces (https://github.com/google/cluster-data/blob/master/ClusterData2011_2.md)
Alibaba cluster traces (https://github.com/alibaba/clusterdata/wiki/About-Alibaba-cluster-and-why-we-open-the-data)
49
Reference
Li, Yangguang, et al. "Predicting Node Failures in an Ultra-large-scale Cloud Computing Platform: an AIOps Solution." TOSEM ‘20.
Lin et al., Predicting Node Failure in Cloud Service Systems. FSE ‘18. 
Zhu et a., Learning to log: helping developers make informed logging decisions. ICSE ‘15. 
El-Sayed et al. "Learning from failure across multiple clusters: A trace-driven approach to understanding, predicting, and mitigating job terminations." ICDCS ‘17.
Botezatu et al. "Predicting disk replacement towards reliable data centers." SIGKDD ‘16.
Xu, Wei, et al. "Detecting large-scale system problems by mining console logs." SOSP ‘09.
50
