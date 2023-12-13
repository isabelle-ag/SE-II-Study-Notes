### Study Notes for Data-driven Software Engineering

#### I. Key Concepts
- **Main Idea 1:** Big data generated in software development can be leveraged for various engineering tasks using data mining techniques.
- **Main Idea 2:** Source code artifacts come in different languages, complexities, and styles, and can be analyzed for code recommendation, clone detection, and completion.
- **Main Idea 3:** Issue reports containing bug and feature requests can be utilized for bug localization and recommending developers to fix issues.

#### II. Definitions
- **Artifact:** A product generated during the software development process.
- **Vector Space Model (VSM):** A mathematical model to represent text documents as vectors of identifiers such as, but not limited to, the term-frequency-inverse-document-frequency (TF-IDF) weights.
- **Code Clone:** Code fragments exhibiting similar semantics or functionality, potentially duplicative or derived from one another.

#### III. Important Details
- **Point 1:** CodeHow is a search engine that leverages API documentation for effective code search.
- **Point 2:** Extended Boolean Model measures the similarity between an extended query and code snippets.
- **Point 3:** Bug localization techniques model the similarity between bug reports and source files, and the bug proneness of files based on their history.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** Abstract Syntax Tree representing the hierarchical structure of source code and its components.
- **Diagram 2:** Vector representation of queries and documents for retrieval in VSM.
- **Diagram 3:** Topic Modeling visualization showcasing the distribution of topics within documents and words within topics.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** TF-IDF formula for word weighting in document representation.
- **Formula/Theorem 2:** Cosine similarity formula for measuring vector similarity in text retrieval systems.
- **Formula/Theorem 3:** Topic modeling equations representing documents as distributions over topics, and topics as distributions over words.

#### VI. Examples
- **Example 1:** Step-by-step process for leveraging source code for code recommendation, such as clone detection.
- **Example 2:** Demonstration of text preprocessing techniques like tokenization, stop-word removal, and stemming on issue reports.
- **Example 3:** Application of similarity modeling for bug localization, using information retrieval techniques and historical data.

#### VII. Summary/Conclusion
- **Recap of Main Points:** The course explores the use of data mining techniques to analyze artifacts from software development, focusing on source code and issue reports, for tasks like code search, bug localization, and recommendation systems.
- **Connections between Concepts:** Techniques such as text retrieval, vector models, machine learning, and topic modeling are interconnected in processing and understanding both natural language and source code.

#### VIII. Additional Resources
- **Textbook Pages:** Not specified.
- **Online Resources:** 
  - GitHub CodeBERT: https://github.com/microsoft/CodeBERT
  - BERT as a service: https://github.com/hanxiao/bert-as-service
  - Example code search tool CodeHow: ASE 2015 publication by Wang et al.

---

Notes: 
Software Engineering IIData-driven Software Engineering
Lecturer: Shaowei Wang

Email: shaowei@cs.umanitoba.ca
Big data of software engineering
2
Large amount of artifacts are generated in the software development process
Increased amount of data available in software archives through large open source projects
Data-driven software engineering
What types of software data are available?
Which software engineering tasks can be assisted?
Which data mining techniques can be used?

3
Artifact: Source Code
4
Artifact: Source Code
Where to find code?
GitHub







How to analyze source code?
Analyze -> automatically parse and understand, model using program analysis tools
5
Artifact: Source Code
Variety in code
Various programming languagesVarious scale: small, medium, large
Various complexities
Various systems (for web, mobile, etc.)
Various programming styles


6
What can we do with source code?

Leveraging source code
Code recommendation
Clone detection
Code completion
…

Applications
CodeHow: Improving code searching  by leveraging API documentation
API recommendation + Source code search
CodeHow: Effective Code Search Based on API Understanding and Extended Boolean Model, Wang, et al, ASE 2015


10
Developers leverage an enormous number of APIs when building systems
Current code search engines mostly treat code as text (text-oriented)
11
Ohloh  code
Current code search engines mostly treat code as text (text-oriented)
12
Ohloh  code

Query: 
read file line by line

Collection of APIs with their online docs
13
Identify 
relevant APIs
Identify relevant APIs to a Query using online API documentation
14
Query: read file line by line
Use a Vector Space Model to measure the similarity between a Query and the API docs
15

Query: 
read file line by line

Extended Query: 
original query + relevant APIs (e.g., File.Readlines())

16
Collection of APIs with their online docs
Identify 
relevant APIs
Code retrieval in API-oriented code search engine
17
void readFileLines(String file){
Var lines = File.ReadLines(file);
Foreach(var line in lines){
	Console.print(line);
}
}

Extended query (EQ)
Code snippet (C)(Method level)

Method body

Extended Boolean Model 
Extended Boolean Model 
Similarity (EQ, C) = 
18
Code retrieval in API-oriented code search engine

Query: 
read file line by line

19
Extended Query: 
original query () + relevant APIs (e.g., File.Readlines())

Collection of APIs with their online docs
Identify 
relevant APIs
int i; 
int sum = 0; 
int product = 1; 
int w = 7; 
String path = “/home/”;
for(i = 1; i < N; ++i) { 
	sum = sum + i + w; 	product = product * i; 
}
File f = new File(path)
f.writeline(sum); 
print(product); 

20
Remove irrelevant code using slicing
int i; 
int sum = 0; 
int product = 1; 
int w = 7; 
String path = “/home/”;
for(i = 1; i < N; ++i) { 
	sum = sum + i + w; 	product = product * i; 
}
File f = new File(path)
f.writeline(sum); 
print(product); 


int i; 
int sum = 0; 
int w = 7; 
String path = “/home/”;
for(i = 1; i < N; ++i) { 
	sum = sum + i + w; 
}
File f = new File(path)
f.writeline(sum); 

21
Remove irrelevant code using slicing

22
Save image as png
Query: read file line by line
Vectorization and similarity calculation
23
Text Preprocessing
Tokenization
Stop-word Removal
Stemming
24
Text: Tokenization
Breaking a document into its constituent tokens or terms
In a textual document, a token is typically a word.

Steps:
Segmenting text into words. Most existing tokenizers signal token boundaries by white spaces. 
Handling Abbreviations
	E.g., Str is abbreviation of String. 
3. Handling Hyphenated Words
	E.g., visual-studio
4. Numerical and special expressions
	E.g., I installed an eclipse 4.3




25
Note: if you consider social media, you might need more text normalization techniques. 
Tokenization Example
"I said, 'what're you? Crazy?’
26
Text: Stop-Word Removal
stop words = extremely common words which would appear to be of little value in helping select documents matching a user need
Examples: a, an, and, are, as, at, be, by, for, from, has, he, in, is, it, its, of, on, that, the, to, was, were, will, with
Stop word elimination used to be standard in older IR systems.
But you need stop words for phrase queries, e.g. “King of Denmark”
Most web search engines index stop words.

Note: better try both, with stop-word, after removal, any improvement? 
Top 1% word?
27
Text: Stemming
Definition of stemming: Crude heuristic process that chops off the ends of words to reduce related words to their root form

E.g., automate, automatic, automation all reduce to automat

Porter’s Algorithm 
Most common algorithm for stemming English
Results suggest that it is at least as good as other stemming options
Used to reduce the variation of words and vobaculary 

28
Should I use stemming?
Depends: stemming can increase effectiveness for some queries and decreases effectiveness for others.
Queries where stemming is likely to help: 
[tartan sweaters], [sightseeing tour san francisco] 
(equivalence classes: {sweater,sweaters}, {tour,tours})
Increase recall
Queries where stemming hurts:
[operational research], [operating system], [operative dentistry]
Lose information

29
 Code Preprocessing
Regard  as NLP
Leveraging static analysis
Parsing
Identifier Extraction
Identifier Split
Identifier Expansion 
30
void readFileLines(String file){
Var lines = File.ReadLines(file);
Foreach(var line in lines){
	Console.print(line);
}
}
Code: Parsing
Creating an abstract syntax tree (AST) of the code.
Identify which ones are variable names, which ones are method calls, etc.
Difficulties:
Multiple languages
Partial code (imcomplete code snippets)
Tools:
ANTLR
Java parser

31
Code: Identifier Extraction
Extract the names of identifiers in the code.
Method names
Variable names
Parameter names
Class names
Extract the comments in the code
`
32
Code: Identifier Split
Break identifier names into tokens.
printLine => print line 
System.out.println => system out println
Many identifier names are in camel casing (printLine) or underscore (print_line).
When no Camel Case convention or other separator is used, e.g., fixbug, we need rules/patterns to auto split identifier. 

Why do we need to break identifier names?
Reduce vocabulary and increase recall
Do all identifiers need to be broken?
No always
33
Code: Identifier Expansion
Mapping soft-words to their corresponding domain concepts.
It is helpful for programming languages (e.g., C and C++) that favor the use of short identifiers. 
34
Ref.An Empirical Study of Abbreviations and Expansions in Software Artifacts
representation
Document Representation
Bag-of-Word Model
Term Frequency (TF)
Word2vec
BERT

35
Bag-of-words document representation
Word weighting
In the bag-of-words representation each word is represented as a separate variable having numeric weight (importance)
The most popular weighting schema is normalized word frequency TFIDF:



Tf(w) – term frequency (number of word occurrences in a document)
Df(w) – document frequency (number of documents containing the word)
N – number of all documents
TfIdf(w) – relative importance of the word in the document

The word is more important if it appears 
several times in a target document

The word is more important if it appears in less documents
Bag of Words Consideration
We consider a document as a multi-set of its constituent words (or terms).
We do not consider the order of words in a document.
John is quicker than Mary, and 
Mary is quicker than John 
are represented the same way.


38
Vector Embedding: Word Similarity
Word embeddings depend on a notion of word similarity. 

A very useful definition is paradigmatic similarity:
Similar words occur in similar contexts. They are exchangable.
e.g., we can remove/discard the word from the string.

This definition supports unsupervised learning: cluster or embed words according to their contexts.  

 
How to “transfer” or “share” knowledge between words?
Idea: representing a word by means of its neighbors
39
Word2vec: Local contexts
Word2vec uses words a few positions away from each center word. 

“It was a bright cold day in April, and the clocks were striking”
Center word: red
Context words: blue

Embedding: word2vec

40
word2vec
2 basic neural network models:
Continuous Bag of Word (CBOW): use a window of word to predict the middle word
Skip-gram: use a word to predict the surrounding ones in window. 
41
Faster, good for frequent words
Represents well even rare words
Word2vec: Local contexts
Local contexts capture much more information about relations and properties :


42
BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding
43
https://github.com/hanxiao/bert-as-service
BERT can generate different word embeddings for a word that captures the context of a word 
CodeBERT
CodeBERT learns general-purpose representations that support downstream NL-PL applications such as natural language code search, code documentation generation
It is trained with Transformer-based neural architecture
Use comment-code pair for training
44
CodeBERT: A Pre-Trained Model for Programming and Natural Languages, Feng  et al. EMNLP 2020
45
https://github.com/microsoft/CodeBERT
Leveraging source code
Code recommendation
Clone detection
Code completion
…

Applications
Code clone
Code clone refers to the code fragments with similar/same semantics (function)
E.g., If a bug is identified in one segment of code, all the similar segments need to be checked for the same bug.
Clone types
Type-1: code fragments that are accurate copies of  each other, excluding whitespaces, blank lines, and comments. 
Type-2: structurally identical code fragments that may differ in the names of variables, literals and functions.
Type-3: syntactically similar code fragments that, may include changes like added or removed statements.
Type-4: clones are code fragments with a different syntax, but similar semantics.




Code snippet 1
Vectorization and similarity calculation
49
Code snippet 2
Use CodeBERT
Use CodeBERT
Leveraging source code
Code recommendation
Code clone
Code completion
…

Applications 
Code completion
https://www.tabnine.com/
N-gram language models



Determine the ith word based on previous n words. 

Statistic language model
Code completion with statistical language models. Raychev V, Vechev M, Yahav E. In Proceedings of the 35th ACM SIGPLAN Conference on Programming Language Design and Implementation 2014.
N-gram language models






Statistic language model
Statistic language model
Limitation of traditional language models
Performance improves with keeping around higher n-grams counts (e.g., 4,5,6,7) and doing smoothing.
There are a lot of n-grams
“using one machine with 140GB Ram for 2.5 days we built an unpruned model on 126 billion tokens”

55
 Transformer-based language model
The model is trained with a simple objective: predict the next word, given all of the previous words within some text. 
GPT; GPT2; Xcode
Code and paper (https://openai.com/blog/better-language-models/)



Deep learning models
Self-attention – capture the relationship of different words

https://jalammar.github.io/illustrated-transformer/
References & Acknowledgements
Many slides and images of this course are taken or adapted from:
Dr. David Lo and Dr. Lingxiao Jiang’s Software Mining Course 
Dr. Jiawei Han’s Pattern Discovery in Data Mining Course
Dr. Emily Fox and Carlos Guestrin’s Clustering and Retrieval Course
The research papers mentioned in the slides.



Artifact: Issue Reports
People report bugs and feature requests that they encounter in the field
Information inside issue reports:
Description of the issue
Steps to reproduce the issue
Severity level (priority?)
Parts of the system affected by the issue
Failure traces
59
Artifact: Issue Reports
Various kinds of issue repositories
GitHub
Jira
Bugzilla
Etc.
60
Applications
Bug localization
61
Bug localization: Introduction
Program is often large with thousands of files.
Given a bug report, how to locate files responsible for the bug? 
A (semi) automated solution is needed.
62
Bug Localization: Technique
Model the similarity of bug reports and files/methods
Model the bug proneness of files
Number of bugs in a file (based on its history)
Model the similarity of previous bug reports
63
Model the similarity of bug reports and files
Information retrieval techniques to calculate the similarity between reports and files
Vector space model – tfidf weighting

64
65
Vector_q [1,0.4, 0.2,…]
Vector_f1 [0.2,0.4, 0.6,…]
Vector_f2 [0.2,0.4, 0.6,…]
Vector_f2 [0.2,0.4, 0.6,…]
Text pre-processing
Pre-processing code
66
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
67
68
Weighting on different components
log
Stack trace
Model the similarity of bug reports and files
Information retrieval techniques to calculate the similarity between reports and files
Vector space model – tfidf weighting
Word2vector
Doc2vector

69
Bug Localization: Technique
Model the similarity of bug reports and files/methods
Model the bug proneness of files
Number of bugs in a file (based on its history)
Model the similarity of previous bug reports
70
Model the bug proneness of files
Observation: a file that occurs a bug recently is more likely to happen bugs again.
Similar bugs usually happen in burst and not in isolation. 
71
Predicting Faults from Cached History, by Kim et al.  
72
Capture frequency and time of a file being committed
73
Time window
Commits in k days
Target file
number of days that has elapsed between a commit c and the input bug report.
Bug Localization: Technique
Model the similarity of bug reports and files/methods
Model the bug proneness of files
Number of bugs in a file (based on its history)
Model the similarity of previous bug reports
74
Model the similarity of previous bug reports
Observation: similar bugs are likely to happen in similar files
75

76

77
Model the similarity of previous bug reports
Outline 
Bug localization
Prediction related studies for software bugs
Recommend developer to fix issues
Predict the severity of bugs
Etc.
78
Recommend developer to fix issues: Introduction
79
Leverage activities profile
Review, commit, ownership, resolve in the bug track system
Leverage expertise
Topic model
80
Recommend developer to fix issues: Technique
Find similar issues reports
81
Fixer of the similar issues
Reviewer of the similar issues
Leverage activities profile
Review, commit, ownership, resolve in the bug track system
Leverage expertise
Topic model
82
Recommend developer to fix bugs: Technique
Topic Modeling
Model a group of words as a topic.
Mostly used to explore large scale of text.
Sample papers:

83
Topic Modeling: Black-Box View
Model a document as a probability distribution of topics
A topic is a probability distribution of words
84
Most simple and common :LDA
Usage of Topic Modeling
Dimensionality reduction: words -> topics
Help with data exploration.
Able to link a document and a query
Do not have share any words
Share related words of the same topics

85
86
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
Calculate similarity
87
