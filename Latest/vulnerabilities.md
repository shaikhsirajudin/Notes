1) What is OWASP? 

OWASP stands for Open Web Application Security Project. It is an organization which supports secure software development. 

2) Mention what flaw arises from session tokens having poor randomness across a range of values? 

Session hijacking arises from session tokens having poor randomness across a range of values. 

3) Mention what happens when an application takes user inserted data and sends it to a web browser without proper validation and escaping? 

Cross site scripting happens when an application takes user inserted data and sends it to a web browser without proper validation and escaping. 


4) Mention what threat can be avoided by having unique usernames produced with a high degree of entropy? 

Authorization Bypass can be avoided by having unique usernames generated with a high degree of entropy. 

5) Explain what is OWASP WebGoat and WebScarab? 

• WebGoat: Its an educational tool for learning related to application security, a baseline to test security tools against known issues. 
It’s a J2EE web application organized in “Security Lessons” based on tomcat and JDK 1.5. 
• WebScarab: It’s a framework for analysing HTTP/HTTPS traffic. It does various functions like fragment analysis, observer the traffic between the server and browser, manual intercept, session ID analysis, identifying new URLs within each page viewed • 

6) List Top 10 OWASP Vulnerabilities 
• OWASP top 10 security flaws include 
• Injection • Cross site scripting 
• Broken Authentication and Session Management 
• Insecure cryptographic storage 
• Failure to restrict 
• Insecure communications 
• Malicious file execution 
• Insecure direct object reference 
• Failure to restrict url access 
• Information leakage and improper error handling

7) Explain what threat arises from not flagging HTTP cookies with tokens as secure? 

Access Control Violation threat arises from not flagging HTTP cookies with tokens as secure.

8) Name the attack technique that implement a user’s session credential or session ID to an explicit value? 

Dictionary attack can force a user’s session credential or session ID to an explicit value 

9) Explain what does OWASP Application Security Verification Standard (ASVS) project includes? 

OWASP application security verification standard project includes 
• Use as a metric: It provides application owners and application developers with a yardstick with which to analyze the degree of trust that can be placed in their web applications 
• Use as a guidance: It provides information to security control developers as to what to build into security controls in order to meet the application security requirements 
• Use during procurement: It provides a basis for specifying application security verification requirements in contracts 

10) List out the controls to test during the assessment? 

• Information gathering 
• Configuration and Deploy management testing 
• Identify Management testing 
• Authenticate Testing 
• Authorization Testing 
• Session Management Testing 
• Data Validation Testing 
• Error Handling 
• Cryptography 
• Business logic testing 
• Client side testing 

11) Explain what the passive mode is or phase I of testing security in OWASP? 
The passive mode or phase I of security testing includes understanding the application’s logic and gathering information using appropriate tools. 
At the end of this phase, the tester should understand all the gates or access points of the application. 

12) Mention what is the threat you are exposed to if you do not verify authorization of user for direct references to restricted resources? 

You are exposed to threat for insecure direct object references, if you do not verify authorization of user for direct references to limited or restricted resources. 

13) Explain what is OWASP ESAPI? 

OWASP ESAPI (Enterprise Security API) is an open source web application security control library that enables developers to build or write lower risk applications.

14) Mention what is the basic design of OWASP ESAPI? 

The basic design of OWASP ESAPI includes 
• A set of security control interfaces 
• For each security control there is a reference implementation 
• For each security control, there are option for the implementation for your own organization 

15) How to select tool can be based on the following parameters: 

• Integration with IDE
 • Licensed or Open Source 
• Types of vulnerabilities it can detect (OWASP Top 10 / Seven Deadly Sins of Quality) OWASP is nothing, but Open Web Application Security Project community dedicated for web application security and t the op 10 flaws are given below: 

1. Injection - Flaws like SQL Injection allowing attacker to steal information through queries. 

2. Broken Authentication & Session Management - Improper implementation of authentication /authorization which allows attacker to compromise on passwords, keys or session tokens. 

3. Cross-Site scripting ( XSS) - Flaw that allows untrusted data and send it to web browser without proper validation. This allows attacker to execute scripts in victim’s browser. 

4. Insecure direct object references - File/Database or directory object references in code without any proper access validation then it will allow attacker to manipulate and get unauthorized data. 

5. Security Misconfiguration - Secure settings can’t be default which is insecure and have to be defined for web server, application, database server. 

6. Sensitive Data Exposure - Sensitive data like credit card & customer profile information when used has to be encrypted and kept secure otherwise attacker will easily manipulate to steal the data. 

7. Missing Function Level Access Control - Application has to be verify function level access when it s accessed by UI and has to be configured. Otherwise attacker will forge request in order to access it.

8. Cross Site Request Forgery - Forces logged on victim’s browser to send forged HTTP request to another vulnerable website. 

9. Using Components with known vulnerabilities - Applications using components with known vulnerabilities[Always run with full privileges] may undermine application defenses and enable a range of possible attacks and impacts. 
10. Unvalidated Redirects & Forwards - Without proper validation, attackers can redirect victims to phishing or malware sites, or use forwards to access unauthorized pages. 

Seven deadly sins of Quality 
1. Duplicated code 
2. Coding standards 
3. Unit tests 
4. Complex code 
5. Potential bugs 
6. Comments 
7. Design and architecture Some of the static code analysis tools for .NET are the following: 

Code Security Tools 
• Fortify 
• Veracode 
• Microsoft CAT.NET 
• Coverity 

Security Analyser Code Quality Tools 
• Resharper 
• NDepend 
• SonarQube 
• Microsoft FxCop 
• Parasoft 


16)  What is Penetration Testing and how is it useful? 

Penetration Testing is also called Pen Testing and is a kind of cyber attack on a
web application or a system which can be of good or bad intent. In terms of bad intent, it is a kind of cyber attack on a system to steal some kind of secure, confidential and sensitive information. In terms of good intent, it is a kind of checking the strengths and weaknesses of a system to vulnerabilities and external attacks and the strength of security levels it can handle. 

17)  What are the advantages of Penetration Testing? 

This is the common Penetration Testing Interview Questions asked in an interview. The advantages of performing Penetration Testing on a System are 
1. It will help in detecting the security threats and vulnerabilities of a system or web application. 
2. It will help in monitoring the necessary standards to evade some. 
3. It is helpful in reducing the downtime of the application in case of diverting large amounts of traffic to the network by penetrating into the application.
4. It protects the organizations confidential and secured information and maintains the brand image or value. 
5. It is important in securing the application to avoid huge financial losses. 
6. Focuses more on business continuity. 7. Maintains trust among the customers. 

18) What are the different stages of Penetration Testing? 


There are different stages of performing penetration testing on a target system or web application such as Planning and reconnaissance, Scanning, Gaining access, Maintaining access, Analysis and configuration: Popular Course in this category 
1. Planning and Reconnaissance: In this stage analysis and testing the goals to carry out are performed and the information is gathered. 
2. Scanning: In this stage, any kind of scanning tool is used to test the responsiveness of a target system in the case of intruder penetration.
3. Gaining Access: In this stage, penetration or intruder attack will be executed and web applications are attacked to disclose the possible vulnerabilities of the system. 
4. Maintaining Access: In this, stage the gained access will be maintained carefully to identify the vulnerabilities and weakness of the system. 
5. Analysis and Configuration: In this stage, the results obtained from the maintained access will be used to configure Web Application Firewall settings also. Let us move to the next 
# Penetration Testing Interview Questions. 


1)  What are the needs of Scrum? 


The below is the list of few requirements of Scrum but are not exhausted : 
1. It requires User Stories to describe the requirement and track the completion status of the assigned user story to the team member whereas Use Case is the older concept. 
2. A name is required is it describes a sentence as a single line overview to give the simple explanation of the User Story.
3. A description is required as it gives a high-level explanation of the requirement to be met by the assignee. 
4. Documents or attachments are also required to know about the story. For eg. In the case of any change in User Interface Screen Layout, that can be easily known only by having a look at the Wire Frame or Prototype of the Screen model. This can be attached to the board using the attachment option. 

2) What are the different Penetration Testing methods? 

The different penetration testing methods are External Testing, Internal Testing, Blind Testing, Double-Blind Testing, and Targeted Testing. External Testing is a form of testing on the internet sites those are publicly visible and email applications and DNS servers etc., Internal Testing is a kind of testing which will penetrate into the internal applications of the system through a form of phishing or internal attacks. Blind Testing is a form of penetrating into the application based on its name in the form of a real-time possibility. Double Blind Testing is a form of testing where even the name of the
application is also unknown and even the security professional will be having any idea in executing on a particular target and Targeted Testing is a form of performing testing from both the security professional and tester together in the form of targeting on each other. 

3) What is Cross Site Scripting (XSS)? 

Cross Site Scripting is a type of attack in the form of injections into a web application or system. In this case, different types of malicious scripts are injected into a weak system to acquire confidential information or hack the system without the knowledge of the administrator of the system. 

4) What is Intruder Detection? 
Intruder Detection mechanism will help in detecting the possible attacks those happened by scanning the existing files in the form of records in the file system of the application. This will help the organization to detect the attacks early on their system applications. 

5) What is SQL injection? 

SQL injection is a form of attack in which the attacker injects data into an application which will result in executing the queries to retrieve the sensitive information from the database that results in the data breach. 

6) What is SSL/TLS? 

This is the popular Penetration Testing Interview Questions asked in an interview. It is Secure Socket Layer / Transport Layer Security which are standard security protocols to establish encryption between a web server and a web browser.
