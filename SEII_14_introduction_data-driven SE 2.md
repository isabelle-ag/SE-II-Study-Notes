### Study Notes for Data-driven Software Engineering II

#### I. Key Concepts
- **Main Idea 1:** Data-driven techniques in Software Engineering (SE) involve mining various sources such as source code, logs, and issues to enhance development processes.
- **Main Idea 2:** Bug localization techniques help find bugs in large codebases using model-based approaches.
- **Main Idea 3:** Source code from platforms like Stack Overflow (SO) is frequently reused in software projects, but it requires careful vetting for quality and licensing issues.

#### II. Definitions
- **Bug Localization:** The process of identifying the parts of the source code that are responsible for a reported bug.
- **Vector Space Model (VSM):** A mathematical model to represent text documents as vectors of identifiers, used in information retrieval.
- **Cosine Similarity:** A metric used to determine how similar two documents are irrespective of their size.

#### III. Important Details
- **Point 1:** Deadlines for Sprint 4 and the final project deliverable are Dec 1st and Dec 15th, respectively.
- **Point 2:** Final examination covers Lectures 1-12, excluding data-driven SE, and is scheduled for Dec 13th.
- **Point 3:** The exam is open book, but online searching and generative AI are prohibited.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** Vectors representing documents/terms in VSM - illustrates the conversion of text to a numerical form that’s computationally tractable.
- **Diagram 2:** Workflow for bug localization techniques, including mining strategies and modeling - shows the process of bug prediction and localization.
- **Diagram 3:** Example of the Vector representation for bug localization (Vector_q, Vector_f1, etc.) - visual representation of how document similarity is computed.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** The cosine similarity formula - used to determine the similarity between two vectors, indicating how closely related two documents are within the VSM.
- **Formula/Theorem 2:** Tf-idf (term frequency–inverse document frequency) - a numerical statistic intended to reflect how important a word is to a document in a corpus.

#### VI. Examples
- **Example 1:** Demonstrating how cosine similarity is calculated between document vectors.
- **Example 2:** Applying tf-idf to determine the weight of terms in documents concerning the entire dataset.
- **Example 3:** Illustrative example of code reuse from Stack Overflow in project development and the related modification requirements.

#### VII. Summary/Conclusion
- **Recap of Main Points:** Data-driven approaches aid bug localization, and the reuse of code from repositories like Stack Overflow is common but requires validation.
- **Connections between Concepts:** Data mining techniques from Stack Overflow can inform automated bug localization methods.

#### VIII. Additional Resources
- **Textbook Pages:** To be provided based on the course's assigned textbook.
- **Online Resources:** 
  - [Final Exam Schedule](https://umanitoba.ca/registrar/final-exams/final-exam-schedule)
  - [Stack Exchange Data Dump](https://meta.stackexchange.com/questions/134495/academic-papers-using-stack-exchange-data)
  - WordNet: [https://wordnet.princeton.edu/](https://wordnet.princeton.edu/)

Note: This is a basic structure of the study notes based on provided text. Specific details such as textbook pages or direct quotes from the lecture to be used as "Examples" will need to be added based on the student's class materials.

---

Notes: 
Software Engineering IIData-driven Software Engineering -2
Lecturer: Shaowei Wang

Email: shaowei@cs.umanitoba.ca
Administrative item
Sprint 4's deadline is postponed to Dec 1st  (Friday) 
Final project deliverable is due on Dec 15th
Final exam
Schedule: Dec 13, 6 pm. https://umanitoba.ca/registrar/final-exams/final-exam-schedule
Scope: Lecture 1 - 12 (including fuzz testing, excluding data-driven SE).
Question type: multi-choice + problem-solving. 
Examination format: In-person. You will be able to download a digital copy of the test (word file) from UMlearn and submit it to UMLearn. 
Guideline: The exam is open book. You are allowed to access class notes, textbooks, and slides. However, no search online and the use of generative AI (e.g., ChatGPT) is not allowed. 


3
Source Code
Issue Report
Question Answering Pairs: Stack Overflow
Pull Requests
Traces/Logs
What to mine?
Mobile apps marketplace
……
Leveraging source code
Code recommendation
Code completion
…

Applications
5
Source Code
Issue Report
Question Answering Pairs: Stack Overflow
Pull Requests
Traces/Logs
What to mine?
Mobile apps marketplace
……
Artifact: Issue Reports
People report bugs and feature requests that they encounter in the field
Information possibly in issue reports:
Description of the issue
Steps to reproduce the issue
Severity level (priority?)
Parts of the system affected by the issue
Failure traces
6
Artifact: Issue Reports
Various kinds of issue repositories
GitHub
Jira
Bugzilla
Etc.
7
Applications
Bug localization – given a bug report, identify the bugs in the source code.

8
Bug localization: Introduction
Program is often large with thousands of files.
Given a bug report, how to locate files responsible for the bug? 
A (semi) automated solution is needed.
9
Bug Localization: Technique
Model the similarity of bug reports and files/methods
Model the bug proneness of files
Number of bugs in a file (based on its history)
Model the similarity of previous bug reports
10
Wang S, Lo D. Version history, similar report, and structure: Putting them together for improved bug localization. In Proceedings of the 22nd International Conference on Program Comprehension 2014 Jun 2 (pp. 53-63).
Model the similarity of bug reports and files
Information retrieval techniques to calculate the similarity between reports and files
Vector space model – tfidf weighting

11
12
Vector_q [1,0.4, 0.2,…]
Vector_f1 [0.2,0.4, 0.6,…]
Vector_f2 [0.2,0.4, 0.6,…]
Vector_f2 [0.2,0.4, 0.6,…]
Text pre-processing
Pre-processing code
13
Vector_q [1,0.4, 0.2,…]
Vector_f1 [0.2,0.4, 0.6,…]
Vector_f2 [0.2,0.4, 0.6,…]
Vector_f2 [0.2,0.4, 0.6,…]
Text pre-processing
similarity
Pre-processing code
VSM: Retrieval
Represent documents and queries as vectors
Compute the similarity between the vectors
Cosine similarity is normally used:






Return top-k most similar documents
qi is the tf-idf weight of term i in the query
di is the tf-idf weight of term i in the document
14
15
Weighting on different components
log
Stack trace
Model the similarity of bug reports and files
Information retrieval techniques to calculate the similarity between reports and files
Frequency based
Word counts
Term frequency – inverse document frequency weighting

Machine learning model-based
Word2vector
Doc2vector
BERT

16
Bug Localization: Technique
Model the similarity of bug reports and files/methods
Model the bug proneness of files
Number of bugs in a file (based on its history)
Model the similarity of previous bug reports
17
Model the bug proneness of files
Observation: a file that occurs a bug recently is more likely to happen bugs again.
Similar bugs usually happen in burst and not in isolation. 
18
Predicting Faults from Cached History, by Kim et al.  
Capture frequency and time of a file being committed
19
Time window
Commits in k days
Target file
number of days that has elapsed between a commit c and the input bug report.
Bug Localization: Technique
Model the similarity of bug reports and files/methods
Model the bug proneness of files
Number of bugs in a file (based on its history)
Model the similarity of previous bug reports
20
Model the similarity of previous bug reports
Observation: similar bugs are likely to happen in similar files

21
Check out bug report before submitting a new bug report, to avoid duplicate.

22



23
Model the similarity of previous bug reports
Hybrid technique
Other applications 
Recommend developer to fix bugs
Predict the severity of bugs
Etc.


Recommend developer to fix bugs: Introduction
26
Leverage activities profile
Ownership, review, resolve in the bug track system
Leverage expertise
Topic model
27
Recommend developer to fix bugs: Technique
Find similar bug reports
28
The fixer of the similar bugs
Reviewer of the similar bugs
Leverage activities profile
Review, commit, ownership, resolve in the bug track system
Leverage expertise
Topic model
29
Recommend developer to fix bugs: Technique
Topic Modeling: Black-Box View
Model a document as a probability distribution of topics
A topic is a probability distribution of words
30
Most simple and common :LDA
Usage of Topic Modeling
Dimensionality reduction: words -> topics
Help with data exploration.
Able to link a document and a query
Do not have share any words
Share related words of the same topics

31
32
comments
Fixed bugs
Developed project/component/files
Tags
Leverage expertise
Model expertise of developers using topic model
VD_comment[t1,t2,… tk], VD_development[t1,t2,… tk]
Model the required expertise of a bug report using topic model
VB[t1,t2,… tk]
Match developers and bug reports based on their expertise
Topic matching
Calculate similarity
33
34
Source Code
Issue Report
Question Answering Pairs: Stack Overflow
Pull Requests
Traces/Logs
What to mine?
Mobile apps marketplace
……
Various types of data on Stack Overflow
Text description
Code snippets
votes
Tags
Mining & leveraging big SE crowd knowledge data
Mining big SE crowd knowledge data

https://meta.stackexchange.com/questions/134495/academic-papers-using-stack-exchange-data






Zhang T, Gao C, Ma L, Lyu M, Kim M. An empirical study of common challenges in developing deep learning applications. In2019 IEEE 30th International Symposium on Software Reliability Engineering (ISSRE) 2019 Oct 28 (pp. 104-115). IEEE.
How do developers utilize source code from Stack Overflow?
Empirical Software Engineering Journal(EMSE) 2018
Yuhao Wu et al. 

function generateID() {
return "avalon" + 
Math.random().toString(36).substring(2, 15) + 
Math.random().toString(36).substring(2, 15)
}
Developers reuse source code from S.O. posts
Source code in a GitHub project
41
An answer on Stack Overflow
How we can know a code snippet was reused from SO
Structure of this study
Part I: Exploratory Study
Part II: Survey
43

How do developers reuse source code?
How do you think S.O. can be improved?

Responses

Part I: Exploratory study
searchcode.com
“stack　overflow”
4,878 source files
Filter
289 files
Analyze code reuse
RQ1: modification frequency and reason
RQ2: origin of code reuse
44
Only 21% of the code are copied exactly
45
32% of the reused source code snippets requires additional modification (C2+C3)
Reimplement based on the idea presented in the answers




21%
10%
22%
13%
35%
43%
26%
1%
30%
Developers adopt answers based on different needs: simplicity, correctness, efficiency, etc.

An advanced tagging system might be helpful
26% of the source code was reused from non-accepted answers
46

Part II: Large-scale survey on 400+ participants
47

Experience
Type of project participated
...
Difficulties in reusing source code
Opinions on OSS licenses
...
Usefulness of proposed advanced tagging system
Any other suggestions
...
Demography (7)
Barriers (10)
Suggestions (2)
Survey Questions
Most suggestions are on code quality
48
35%
24%
13%
12%
10%
7%
Suggestions: improving code quality 
(35% of all categories)
Integrated validator
(42.2%)
Outdated code
(29.7%)
Answer quality
(17.2%)
Code review
(10.9%)
“An inbuilt environment for as many languages/ environments as possible.”
“Make date important in marking outdated code, and deprecate those snippets via the community”
“Better support for answers that are good, but out of date.”
“In-browser code review and commenting similar to that provided by commercial code review tools.”
49
Beyer, S., Macho, C., Di Penta, M. and Pinzger, M., 2020. What kind of questions do developers ask on Stack Overflow? A comparison of automated approaches to classify posts into question categories. Empirical Software Engineering, 25(3), pp.2258-2301.
Yang, X.L., Lo, D., Xia, X., Wan, Z.Y. and Sun, J.L., 2016. What security questions do developers ask? a large-scale study of stack overflow posts. Journal of Computer Science and Technology, 31(5), pp.910-924.
Ahmed, S. and Bagherzadeh, M., 2018, October. What do concurrency developers ask about? a large-scale study using stack overflow. In Proceedings of the 12th ACM/IEEE International Symposium on Empirical Software Engineering and Measurement (pp. 1-10).
Islam, M.J., Nguyen, H.A., Pan, R. and Rajan, H., 2019. What do developers ask about ml libraries? a large-scale study using stack overflow. arXiv preprint arXiv:1906.11940.
Barua, A., Thomas, S.W. and Hassan, A.E., 2014. What are developers talking about? an analysis of topics and trends in stack overflow. Empirical Software Engineering, 19(3), pp.619-654.
Understanding the challenges and problems that developers face
Mining & leveraging big SE crowd knowledge data
Mining big SE crowd knowledge data

Leveraging big SE crowd knowledge data

https://meta.stackexchange.com/questions/134495/academic-papers-using-stack-exchange-data
We have different morphological forms (abbreviations, synonyms and misspellings)

We need a thesaurus to contain software-specific terms and commonly-used morphological forms
We have existing general thesaurus for morphological forms
Wordnet (https://wordnet.princeton.edu/)

Same word in SE and in other domain may have different meaning
Apple  -> cell phone;   Apple -> fruit;

Domain specific knowledge is important!
We need a thesaurus to contain software-specific terms and commonly-used morphological forms
Why we care about this?
Identify various morphological forms of the same concept may also mitigate data sparsity problems when applying NLP techniques for various applications -> reduce the vocabulary size
Information retrieval 
Data mining


Leverage Stack Overflow to train a  model to identify the relational regularities 
 SEthesaurus: WordNet in Software Engineering IEEE TRANSACTIONS ON SOFTWARE ENGINEERING (TSE) 2015. Xiang Chen, Chunyang Chen, Dun Zhang, and Zhenchang Xing
Underling intuition is that words with similar meaning would appear in the similar context.
	-> E.g., Javascript, JS, and JavaScript are used in the similar context

Overview of the approach
Data collection
Software specific corpus
	->Stack Overflow 
	->15,930,617 questions and 24,676,333 		answers
Domain agnostic corpus
	->Wikipedia
	->8,556,773 articles

Overview of the approach
Pre-processing
Text cleaning
remove HTML tags
remove long code snippets but keep short code snippets (e.g., method name)
remove all references 
Tokenization
software-specific tokenizer, which keeps integrity of code-like tokens (e.g., numpy.ndarray.argmin())
Phrase Detection 
Up to four grams
e.g., operating system (OS), breadth first search (BFS)
“Distributed representations of words and phrases and their compositionality” by Mikolov et al. Proceedings of Advances in neural information processing systems, 2013



Overview of the approach
Building software-specific vocabulary
Identify software-specific terms by contrasting the frequency of a term in the software-specific corpus compared with its frequency in the general corpus




Pd(t) and Pg(t) are the probability of t in domain specific corpus and general corpus
Threshold: 10 

Overview of the approach
Vector Embedding: Word Similarity
A simple assumption:
Similar words occur in similar contexts. They are exchangable.
e.g., we can remove/discard the word from the string.



This definition supports unsupervised learning: cluster or embed words according to their contexts.  

 
How embedding works?
Idea: representing a word by means of its neighbors
63
Learning term semantics
Learn work embedding
Two approaches
Continuous skip-gram model 
FastText model
Using the cleaned SO data


Overview of the approach
Extracting semantically related terms
Use cosine similarity to calculate the similarity of two words.
Take top 40 words from   Continuous skip-gram model and FastText model, and union them as the final candidates


Overview of the approach
Discriminating synonyms
One observation: morphological-synonyms among semantically related terms can be usually transformed from one term to another by performing a small number of string edits ([tf idf, tfidf], [windows-service, windowsservices], [angular, angularjs])
Use Levenshtein distance (i.e., Damerau-Levenshtein (DL)) to measure the string edit distance
Measure single-character edits (such as insertions, deletions, substitutions, and transpositions)


Threshold 1/3
Discriminating abbreviations
Determine if a word w as an abbreviation of the term t using following heuristics-based lexical rules:
The characters of the term w must be in the same order as they appear in the term t, such as (pypi, python pacage index), (amq, activemq);
The length of the term w must be shorter than that of the term t;
If there are digits in the term w, there must be the same digits in the term t, e.g., vs2010 is regarded as an abbreviation of visual studio 2010, but vs is not regarded as an abbreviation of visual studio 2010;
The term w should not be the abbreviation of only some words in a multi-word phrase. For example, cmd is regarded as the abbreviation of command, but not as the abbreviation of command line


Overview of the approach


Coverage
