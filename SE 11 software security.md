### Study Notes for Comp 4350: Software Engineering II - Lecture 12: Software Security

#### I. Key Concepts
- **Main Idea 1:** Software security is vital throughout a system's development and deployment stages. It forms part of the quality parameters in software and should cater to authorization levels.
- **Main Idea 2:** Security issues, such as vulnerabilities and data breaches, are prevalent and can have significant consequences.
- **Main Idea 3:** Security can be assured through various practices such as Static Analysis, Security Tests, and fostering Self-protective software.

#### II. Definitions
- **Software Security Assurance (SSA):** Measures to ensure software is free from vulnerabilities and unintended malicious actions.
- **Vulnerability:** A weakness in the software that can be exploited to cause harm.
- **Penetration Test (PT):** An authorized simulated attack on a system to discover vulnerabilities.

#### III. Important Details
- **Point 1:** Security must be ensured at various levels within a system; failing to secure one level can compromise higher levels.
- **Point 2:** Identifying security defects early is less expensive and critical for the robustness of software.
- **Point 3:** Common vulnerabilities include SQL injection and Cross-Site Scripting (XSS), with mitigation steps available such as parameterized queries.

#### IV. Diagrams/Visual Aids
- **Diagram 1:** Link to Google Sheets for seminar schedules – provides visualization of seminar planning and logistics.
- **Diagram 2:** Control Flow Graph - depicts dependencies between instructions and code blocks for vulnerability identification.
- **Diagram 3:** SQL injection code examples – illustrate how vulnerabilities occur and how to prevent them.

#### V. Key Formulas/Theorems
- **Formula/Theorem 1:** Parametrized queries - a method to secure databases against SQL injections.
- **Formula/Theorem 2:** HTML entity escaping - a means of converting characters to prevent XSS attacks.
- **Formula/Theorem 3:** Access control strategies - to prevent unauthorized object references and ensure system integrity.

#### VI. Examples
- **Example 1:** Secure Java Prepared Statement Example – showing how to use parametrized queries to prevent SQL injection.
- **Example 2:** HTML Escaping – illustrating how escaping can safeguard against XSS.
- **Example 3:** Penetration Test Scenario – detailing the steps of a PT and how vulnerabilities are exploited and reported.

#### VII. Summary/Conclusion
- **Recap of Main Points:** Emphasizes the prevalence of software security issues, importance of incorporating security into all software development phases, and the methods to prevent and mitigate security vulnerabilities.
- **Connections between Concepts:** There's a direct correlation between early detection of vulnerabilities, mitigation efforts, and overall system security integrity.

#### VIII. Additional Resources
- **Textbook Pages:** Not specified within the provided text.
- **Online Resources:** 
    - GitHub vulnerability scanner thread: https://community.spiceworks.com/topic/2122662-github-vulnerability-scanner-reveals-4-million-security-flaws-in-code
    - OWASP Foundation: https://owasp.org
    - Acunetix on XSS: https://www.acunetix.com/websitesecurity/cross-site-scripting/
    - Software Secured's Code Review Checklist: https://www.softwaresecured.com/secure-code-review-checklist/
    - Tool links for static analysis and security checks: 
       - Cppcheck: https://cppcheck.sourceforge.io/
       - Facebook infer: https://fbinfer.com/
       - Sonarcloud: https://sonarcloud.io/

---

Notes: 
Comp 4350Software Engineering IILecture 12
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
Agenda
Software Security
Static Analysis
Security Tests

3
Security issues are very prevalent in online code repositories
4
? security flaws in public repos.

4 million
From  https://community.spiceworks.com/topic/2122662-github-vulnerability-scanner-reveals-4-million-security-flaws-in-code
5
The first announced breach, reported in September 2016, had occurred sometime in late 2014, and affected over 500 million Yahoo! user accounts.[2] 

A separate data breach, occurring earlier around August 2013, was reported in December 2016. Yahoo! affirmed in October 2017 that all 3 billion of its user accounts were impacted.[4] 

Both breaches are considered the largest discovered in the history of the Internet.
Old, unpatched vulnerabilities.
A vulnerability can be identified and described, but developers do not correct it immediately.
Human errors
Those include bugs, weak passwords, private data sharing.
Malware
They cause minor problems but in large quantities and with a lot of variability.
Insider abuse
The most dangerous vulnerabilities and what require internal security measures.
Physical theft
Personal devices that must be physically protected too.
6
Where are data breach coming from?
Software Security As Quality
7

Security is the quality that controls the ability of the system to ensure that users or other systems can access its data according to their level of authorization. 
8
Software security as quality
Security can be guaranteed at several levels of the system.
It is not enough to guarantee security just at a few levels.
If there are vulnerabilities at lower levels, higher levels are vulnerable too.
9
Security levels
Like all qualities, security must be ensured in all phases of development.
The sooner a defect is identified, the least expensive its correction.
Security must be verified for:
Our software
External software (libraries) that we use in our software.
In fact, the SSA is protecting the software against known vulnerabilities and against unintended malicious actions.
10
Software Security Assurance (SSA)

Vulnerabilities
11

Software security vulnerabilities
A vulnerability is a hole or a weakness in the application, which can be a design flaw or an implementation bug, that allows an attacker to cause harm to the stakeholders of an application.
Vulnerability becomes a problem if it becomes the point of an attack or an "exploit".
Vulnerabilities and exploits can result in lost money, private data, or life!
The system can be protected by identifying vulnerabilities through static analysis, penetration testing or code reviews.
12
SQL injection
Cross Site Script (XSS)
Unsecured object references
Bad security configuration
Unsecure cryptographic storage
13
Common Vulnerabilities
OWASP Foundation: https://owasp.org
SQL injection
An SQL injection is a technique that attackers apply to insert SQL query into input fields to then be processed by the underlying SQL database.
14
15

This says select all customers where they're username is blank ('') or 1=1, which is a boolean, equating to true. Then it uses -- to comment out the rest of the query. So this will just print out all the customer table
Generated vulnerable code from ChatGPT
16
Results from ChatGPT (https://chat.openai.com/) on 2/12/2023
SQL injection. UserId = “105 OR 1=1”, returns ALL rows  in the “users” table.
SQL injection prevention techniques
With user input channels being the main vector for such attacks, the best approach is controlling and vetting user input to watch for attack patterns. 
Parametrized queries

17
Parametrized queries
Parameterized queries are a means of pre-compiling an SQL statement so that you can then supply the placeholders for parameters in order for the statement to be executed. This method makes it possible for the database to recognize the code and distinguish it from input data.

18
Safe Java Prepared Statement Example:
19
// This should REALLY be validated too
String custname = request.getParameter("customerName");
String password = request.getParameter(“password");

// Perform input validation to detect attacks
String query = "SELECT account_balance FROM user_data WHERE user_name = ?  and password  = ?";
PreparedStatement pstmt = connection.prepareStatement( query );

pstmt.setString( 1, custname);
pstmt.setString( 2, password);

ResultSet results = pstmt.executeQuery( );
The following code example uses a PreparedStatement, Java's implementation of a parameterized query, to execute the same database query. 
Database knows exactly what this query will do, and only then will it insert the username and passwords merely as values. So in this case it would look for a username of "Nobody OR 1=1'--" and a blank password, which should come up false. 


20
Cross-site Scripting (XSS) is a client-side code injection attack. The attacker aims to execute malicious scripts in a web browser of the victim by injecting malicious code in a legitimate web page or web application.
The web page or web application becomes a vehicle to deliver the malicious script to the user’s browser. Vulnerable vehicles that are commonly used for Cross-site Scripting attacks are forums, message boards, and web pages that allow comments.
A web page or web application is vulnerable to XSS if it uses unsanitized user input in the output that it generates. This user input must then be parsed by the victim’s browser. 
21
Cross site scripting (XSS)
https://www.acunetix.com/websitesecurity/cross-site-scripting/
Stored XSS
22
To run malicious JavaScript code in a victim’s browser, an attacker must first find a way to inject malicious code (payload) into a web page that the victim visits.
After that, the victim must visit the web page with the malicious code. If the attack is directed at particular victims, the attacker can use social engineering and/or phishing to send a malicious URL to the victim.

23
Malicious code:
<script>doSomethingEvil();</script>  
submit a comment that contains a malicious code
Victim: 
Stealing Cookies Using XSS
Cross-site Scripting Attack Vectors

24


25


26
How to Prevent XSS
To keep yourself safe from XSS, you must sanitize your input. 
Your application code should never output data received as input directly to the browser without checking it for malicious code.
27
28
Escaping HTML
This means converting characters like <, >, &, ", and ' into their HTML entity equivalents. E.g., ‘<‘ converts to ‘&lt’ 

29
<!DOCTYPE html>
<html>
<head>
    <title>Secure Comment Page</title>
</head>
<body>
    <h1>Comments</h1>
    <div>
        <?php
        $userComment = "<script>alert('This is a malicious script!')</script>";
        echo htmlentities($userComment, ENT_QUOTES, 'UTF-8'); // This is secure!
        ?>
    </div>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
    <title>Vulnerable Comment Page</title>
</head>
<body>
    <h1>Comments</h1>
    <div>
        <?php
        $userComment = "<script>alert('This is a malicious script!')</script>";
        echo $userComment; // This is vulnerable!
        ?>
    </div>
</body>
</html>

Unsecured object references
Unsecured object references occur when an application uses an identifier to access an object without verifying that the user has the proper permissions to access that object. 
30
Approach
Use proper access controls: 
Validate user input: Validate user input to ensure that the user is only able to access objects that they are authorized to access. This can be done through input validation, such as checking that a user is only able to access objects that they have permission to access.
Implement session management: Implement session management to ensure that users are authenticated and authorized to access specific objects. This can be achieved through techniques such as session timeouts, session revocation, and other security mechanisms.


31


32
33
Vulnerability chronology 
Security tests
34
Security testing is the process to ensure that mechanisms established to ensure security are not defective.
The success of security tests does not imply the absence of security defects.
Security testing controls security requirements.
Confidentiality, integrity, authentication, authorization, availability, responsibility, non-repudiation.
There are several steps to ensure security and several types of testing to implement security assurance.
35
Security tests
Vulnerability scanning: Find vulnerabilities in the software according to known rules or templates. 
Security Audit: Perform reviews and inspections of code and operating systems.
Penetration tests: Simulate a malicious attack and identify the degree of sensitivity of the vulnerabilities.
36
ST types
Vulnerability Scanner – static analysis
37
Code scanning before deployment and execution to find vulnerabilities (and other bugs).
Identifying vulnerabilities in the early stages of development is ideal.
Techniques :
Data flow analysis: The collection of dynamic information in a static way; how the data is processed by the instructions (e.g., stack overflow).
Control Flow Graph: An abstract representation of the software that shows dependencies between instructions and code blocks (e.g., memory leakage).
38
Static analysis

39
Rule-based
Based on pre-defined rule developed by experts

Apply the rule on the source code/bytecode to identify anti-patterns
40
private void processFile(string fName){
BufferReader fil = new BufferReader(new FileReader(fName));String line;if(line = fil.ReadLine()) != null){
	processLine(line);
	fil.Close();
}else{
      …}
}
Machine learning-based
41
42
Wang W, Nguyen TN, Wang S, Li Y, Zhang J, Yadavally A. DeepVD: Toward Class-Separation Features for Neural Network Vulnerability Detection. In2023 IEEE/ACM 45th International Conference on Software Engineering (ICSE) 2023 May 14 (pp. 2249-2261). IEEE.

43

Avantages
It is possible to run multiple software and it can be repeated tactically.
It facilitates DevOps methods (CI / CD).
For vulnerabilities that are easy to detect automatically, it is very useful.
Disadvantages
Several types of vulnerabilities are not easy to detect automatically.
An increased number of false positives.
Configuration problems, which are not included in the code, are not detected.
Hard to confirm that a security problem is really a vulnerability.
Compiling problems and resolving dependencies prevent code analysis.
44
Static analysis
Language and technology of the analyzed software.
Types of vulnerabilities detected by the tool.
Can it resolve dependencies automatically?
Does it require source files or binary files?
Can it be integrated with IDEs?
Is it accurate?
Is it easy to install / configure / use?
45
Static analysis - criteria for selecting tools

46
Vulnerabilities scanner
Cppcheck
https://cppcheck.sourceforge.io/
Facebook infer – defect bugs

47
https://fbinfer.com/
Sonarcloud - Enhance Your Workflow with Continuous Code Quality & Code Security

48
https://sonarcloud.io/
Vulnerability scanning: Find vulnerabilities in the software according to known rules or templates. 
Security Audit: Perform reviews and inspections of code and operating systems.
Penetration tests: Simulate a malicious attack and identify the degree of sensitivity of the vulnerabilities.
49
ST types
The review is the process of auditing the code to verify that:
Security checks are in place.
They work as expected.
They are called in the appropriate places of the code.
"The review can be performed by combining automatic tools and manual efforts by professionals and experts.
50
Code security review
Reviewers must be familiar with the code, the context, the audience, the importance.
Checklist:
Data validation
Authentication
Session Management
Authorization
Cryptography
Managements of the faults
Logging
Security configuration
Network Architecture
Example of a checklist:
https://www.softwaresecured.com/secure-code-review-checklist/

51
Review: Preparation
Vulnerability scanning: Find vulnerabilities in the software according to known rules or templates. 
Security Audit: Perform reviews and inspections of code and operating systems.
Penetration tests: Simulate a malicious attack and identify the degree of sensitivity of the vulnerabilities.
52
ST types
PT is a simulated and authorized attack to reveal possible exploits and their severity due to vulnerabilities.
The tests can reveal the vulnerabilities but also the power of the system to defend itself.
The tests can be performed in the form of a "black box" or in the form of a "white box".
PTs are part of security audits.
They can be performed internally by the organization or by external authorities or experts.
53
Penetration tests (PT)
Using ZAP for Penetration testing
54
Establish the threat model.
Like use cases and test cases, the threat model specifies the attack scenarios and vulnerability points of the software. This will facilitate testing and security reviews.
Combine automatic tools with manual efforts.
Automatic tools detect vulnerabilities easily and quickly, reducing management costs and concerns to ensure security.
Manual reviews can reduce the false results of automatic tools and increase the accuracy of detection methods.
Understand the approach of developers.
Do not assess the level of risk.
The purpose of the review is to detect the "what" and the "where".
Take a global approach, do not focus on code details.
Review follow up .
The role of the reviewers is not to perform the penetration tests.
55
Review: Best practices
PT reports examples
Offensive Security
MegaCorp One
56
The initial discovery revealed a misconfigured DNS server that gave access to a list of hosts.
One of these hosts contained an interface of an administrative server protected by a password.
The attacker was able to find the password with a brute force attack.
The administrative interface has been vulnerable to remote code injections.
The attacker got access to the operating system.
An attack on a Java applet gave access to all machines used by administrators.
The attack managed to compromise the entire system.
57
Scenario
Vulnerability: "Username and password weak or default (eg admin-admin). "
Risk: High
Vulnerability: "Password reused. "
Risk: High
Vulnerability: "Shared local administrator password (multiple hosts had the same passwords). "
Risk: High
Vulnerability: "Patch management (multiple hosts have not been updated). "
Risk: High
Vulnerability: "DNS zone transfer (DNS server incorrectly configured). "
Risk: Low
Vulnerability: "Apache file by default. "
Risk: Low
58
Results - Reports
Tutorial for Penetration Tests

59
The S & T process follows the development process (SDLC = Software Development Life Cycle)
Early testing is vital for the security and reliability of the software.
The sooner we identify the problems, the less the risk.
Reviews and formal inspections are even more important and reliable.
A rigorous ST process is also important for building trust with customers.
60
Security testing process (ST)
Positive (Functional) Requirements: These describe the appropriate functionality of the system.
Eg the application must hide all private data that will be displayed.
Negative (risk-oriented) requirements: These describe what the application should not do.
Eg the application must not allow modification of the data without authority.
Abuse Cases: Like use cases, they describe scenarios of unplanned or malicious use and describe how the application should react.
Threat models are used to derive negative requirements and they can take the role of an attacker during a case of abuse.
61
Derive and elicit security requirements
Software security faces some challenges:
Engineers focus more on protecting the periphery (network, host) than the software itself.
Almost every effort to ensure security is concentrated during development and just before deployment, and the software remains unprotected while running (except its periphery).
Static and penetration testing is controlled, but the use (or missuse) of the software is not always expected.
To combat these challenges, researchers have suggested that software defends itself.
As in the case of performance, where we have self-adaptive systems, which can adapt their infrastructure to better manage their performance, in case of security, we have self-protective systems.
Generally, we talk about the self-protection of the application during its execution (Runtime Application Self-Protection (RASP)).
Methods of self-protection at the architectural level have also been proposed (Architecture Based Self-Protection (ABSP).
62
Self-protective software
RASP is implemented by inserting instructions into the application code to monitor and protect it.
As in the case of instrumented profiling.
Alternatively, one can develop an external system that is attached to the application.
Based on the MAPE architecture, this system monitor the application and its environment, it is able to recognize malicious activities and finally protect the application by blocking the attack.
63
Self-protection
Advantages
RASP has increased accuracy.
The analyzed information is alive and real.
Sometimes attacks are repeated, so once detected, one can detect all future attacks of the same nature.
RASP not only detects vulnerabilities or attacks, but can also block them.
It can stop the execution of instructions that can modify the database (SQL injection).
It can block an IP address that has tried a lot of requests (DoS attack).
RASP can defend the application against various attacks.
RASP can defend the application against both external and internal threats.
Disadvantages
RASP can affect the performance of the application that it protects.
Additional analysis may delay response.
Protective actions can warn the attacker.
The attacker knows that he is detected and he can modify his attack strategy.
RASP is as good as the expertise and experience of security professionals.
64
Self-protection : Advantages and disadvantages
Recognition
The activity acquires important information for the target system. The information will improve the attack.
Scanning
Using automatic tools, the attacker gains more information. For example, we can find which ports are open or which input fields are vulnerable.
Get access
Exploit identified vulnerabilities to attack the system or increase the level of authorization.
Maintain access
Activities to be able to stay in the system and get as much information as possible.
Cover the tracks
For the attack to succeed, the attacker must erase all traces that the software has been compromised.
Climbing
After a resource (a machine or a component of the software) is compromised, the attacker can continue the attack to the other resources with the information obtained by the first step of the attack.
65
PT: Phases
Description: The URL contains a direct reference to the unobstructed ID of an object. An attacker can change the reference and obtain access to other objects.
Example: http://www.vulnerablesite.com/userid=123 modified to  http://www.vulnerablesite.com/userid=124


66
Insecure direct object references
Description: The application allows the direct passage of roles or privileges in the URL. In addition, the application does not control the privileges passed by the URL.
Example : http://www.vulnerablesite.com/user/getaccounts modified to http://www.vulnerablesite.com/admin/getaccounts 
67
Failure to restrict URL access
Before the development:
Define the SDLC
Revise policies and standards
Develop metrics and metrics criteria and ensure traceability
Design:
Review security requirements
Revise the design and architecture
Create and revise UML and threat models
Development
Code Reviews and Inspections
Static analysis
Deployment
Penetration tests
Configuration Management Testing
Maintenance and operations
Operational Management Reviews
Periodic control of the health of the system
Change check

68
OWASP Testing Framework
