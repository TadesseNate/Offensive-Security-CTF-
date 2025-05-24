# Offensive-Security-CTF-


Rekall Corporation
Penetration Test Report



________________
Confidentiality Statement

This document contains confidential and privileged information from Rekall Inc. (henceforth known as Rekall). The information contained in this document is confidential and may constitute inside or non-public information under international, federal, or state laws. Unauthorized forwarding, printing, copying, distribution, or use of such information is strictly prohibited and may be unlawful. If you are not the intended recipient, be aware that any disclosure, copying, or distribution of this document or its parts is prohibited.






________________
Table of Contents


Confidentiality Statement        2

Contact Information        4

Document History        4

Introduction        5

Assessment Objective        5

Penetration Testing Methodology        6

Reconnaissance        6

Identification of Vulnerabilities and Services        6

Vulnerability Exploitation        6

Reporting        6

Scope        7

Executive Summary of Findings        8

Grading Methodology        8

Summary of Strengths        9

Summary of Weaknesses        9

Executive Summary Narrative        10

Summary Vulnerability Overview        13

Vulnerability Findings        14












________________
Contact Information


  Company Name
  WillyWonkaSecurity LLC

	Contact Name
	Oompa Loompa
 
	Contact Title
	Security Analyst
 
Document History
Version
	Date
	Author(s)
	Comments
	001
	08/11/2024
	Oompa Loompa
	N/A
	

________________
Introduction


In accordance with Rekall policies, our organization conducts external and internal penetration tests of its networks and systems throughout the year. The purpose of this engagement was to assess the networks’ and systems’ security and identify potential security flaws by utilizing industry-accepted testing methodology and best practices.


For the testing, we focused on the following:


* Attempting to determine what system-level vulnerabilities could be discovered and exploited with no prior knowledge of the environment or notification to administrators.
* Attempting to exploit vulnerabilities found and access confidential information that may be stored on systems.
* Documenting and reporting on all findings.


All tests took into consideration the actual business processes implemented by the systems and their potential threats; therefore, the results of this assessment reflect a realistic picture of the actual exposure levels to online hackers. This document contains the results of that assessment.


Assessment Objective


The primary goal of this assessment was to provide an analysis of security flaws present in Rekall’s web applications, networks, and systems. This assessment was conducted to identify exploitable vulnerabilities and provide actionable recommendations on how to remediate the vulnerabilities to provide a greater level of security for the environment.


We used our proven vulnerability testing methodology to assess all relevant web applications, networks, and systems in scope. 


Rekall has outlined the following objectives:


Table 1: Defined Objectives
Objective
	Find and exfiltrate any sensitive information within the domain.
	Escalate privileges.
	Compromise several machines.
	

________________
Penetration Testing Methodology


Reconnaissance
 
We begin assessments by checking for any passive (open source) data that may assist the assessors with their tasks. If internal, the assessment team will perform active recon using tools such as Nmap and Bloodhound.


Identification of Vulnerabilities and Services


We use custom, private, and public tools such as Metasploit, hashcat, and Nmap to gain perspective of the network security from a hacker’s point of view. These methods provide Rekall with an understanding of the risks that threaten its information, and also the strengths and weaknesses of the current controls protecting those systems. The results were achieved by mapping the network architecture, identifying hosts and services, enumerating network and system-level vulnerabilities, attempting to discover unexpected hosts within the environment, and eliminating false positives that might have arisen from scanning. 


Vulnerability Exploitation


Our normal process is to both manually test each identified vulnerability and use automated tools to exploit these issues. Exploitation of a vulnerability is defined as any action we perform that gives us unauthorized access to the system or the sensitive data. 


Reporting


Once exploitation is completed and the assessors have completed their objectives, or have done everything possible within the allotted time, the assessment team writes the report, which is the final deliverable to the customer.


________________
Scope


Prior to any assessment activities, Rekall and the assessment team will identify targeted systems with a defined range or list of network IP addresses. The assessment team will work directly with the Rekall POC to determine which network ranges are in-scope for the scheduled assessment. 


It is Rekall’s responsibility to ensure that IP addresses identified as in-scope are actually controlled by Rekall and are hosted in Rekall-owned facilities (i.e., are not hosted by an external organization). In-scope and excluded IP addresses and ranges are listed below. 


________________
Executive Summary of Findings
Grading Methodology


Each finding was classified according to its severity, reflecting the risk each such vulnerability may pose to the business processes implemented by the application, based on the following criteria:


Critical:         Immediate threat to key business processes.

High:                 Indirect threat to key business processes/threat to secondary business processes.

Medium:         Indirect or partial threat to business processes. 

Low:                 No direct threat exists; vulnerability may be leveraged with other vulnerabilities.

Informational:    No threat; however, it is data that may be used in a future attack.


As the following grid shows, each threat is assessed in terms of both its potential impact on the business and the likelihood of exploitation:


![image5](https://github.com/user-attachments/assets/1cfa032d-279c-42e7-861c-eb8669fb4fca)


 Chart

Description automatically generated with medium confidence 



________________
Summary of Strengths


While the assessment team was successful in finding several vulnerabilities, the team also recognized several strengths within Rekall’s environment. These positives highlight the effective countermeasures and defenses that successfully prevented, detected, or denied an attack technique or tactic from occurring. 


* The ongoing penetration testing is being conducted to identify potential vulnerabilities for mitigation.


Summary of Weaknesses


We successfully found several critical vulnerabilities that should be immediately addressed in order to prevent an adversary from compromising the network. These findings are not specific to a software version but are more general and systemic vulnerabilities.


* The web application is vulnerable to XSS and SQL payload injection
* Credentials stored in HTML source code
* Malicious script successfully shown on the host home page
* Rekall's publicly available physical address displays potential vulnerabilities
* Open Port 21 allows for FTP enumeration through FTP connection on host IP 
which resulted in successful transfer and access/download of vulnerable files
* Github provided necessary credentials to crack password 




________________


Executive Summary



WillyWonka LLC  identified critical vulnerabilities in Rekall's Corp, potentially affecting revenue and credibility, infiltrating sensitive data, and escalating privileges within systems. I tested Rekall's Web Application identifying vulnerabilities such as XSS Reflected (cross-site scripting), Local File Inclusion, XSS Stored, SQL Injection, and Command Injection attacks on the home page, local file upload, Login.php toolbar, and Networking.php page.
________________
Summary Vulnerability Overview




Vulnerability    -------
	                       Severity
                       
	Command Injections
	                     Critical
	IP’s Visible (NMAP)
	                     Critical 
	SQL Injection
	                     Critical
	Sensitive Data Exposure
	                     Critical
	Local File Inclusion
	                     Critical
	FTP Enumeration
	                     Critical
	User Credentials Exposed
	                     Critical
	XSS Stored
	                     High
	XSS Reflected
	                     High
	

	

	

	


The following summary tables represent an overview of the assessment findings for this penetration test:
Scan Type
	                   Total
	Hosts
	172.22.117.20
                192.168.14.35


	Ports
	21 22 80
	Exploitation Risk
	Total
	Critical
	7
	High
	2
	Medium
	0
	Low
	0
	

Vulnerability Findings
Vulnerability 1
	Findings
	Title
	XSS Reflected
	Type (Web app / Linux OS / WIndows OS)
	Web App
	Risk Rating
	High
	Description
	Malicious script successfully shown on the host home page 
<script>alert(Document.cookie)</script>
![image9](https://github.com/user-attachments/assets/604e0aa0-54be-4571-beca-ae7f99e52dff)


	Images
	  

	Affected Hosts
	192.168.14.35
	Remediation
	Input Validation
	

Vulnerability 2
	Findings
	Title
	XSS Stored 
	Type (Web app / Linux OS / WIndows OS)
	Web App
	Risk Rating
	High
	Description
	Comments page, entered <script>alert(“Hi”)</script> 
![image6](https://github.com/user-attachments/assets/e4b5c4e5-047c-4272-b328-1b8f400e5333)

	Images
	  

	Affected Hosts
	192.168.14.35
	Remediation 
	Implement XSS protection to disallow injection of script code
	

Vulnerability 3
	Findings
	Title
	SQL Injection 
	Type (Web app / Linux OS / WIndows OS)
	Web App
	Risk Rating
	Critical
	Description
	Accessing Lohin.php page, payload 1=1 was entered to exploit
![image1](https://github.com/user-attachments/assets/6b64d9fd-75d8-409d-af74-65d8e8dc14e3)

 
	Images
	  

	Affected Hosts
	192.168.14.35
	Remediation 
	Disallow web app to accept direct input and/or implement character 
	




Vulnerability 4
	Findings
	Title
	FTP Enumeration 
	Type (Web app / Linux OS / WIndows OS)
	Windows OS
	Risk Rating
	Critical
	Description
	Open Port 21 allows for FTP enumeration through FTP connection on host IP 
which resulted in successful transfer and access/download of vulnerable files
![image4](https://github.com/user-attachments/assets/1f4d970a-74a1-4342-80d4-865de5214093)



	Images
	  

	Affected Hosts
	172.22.117.20
	Remediation 
	Restrict access to port 21
	


Vulnerability 5
	Findings
	Title
	Command Injection
	Type (Web app / Linux OS / WIndows OS)
	Web App
	Risk Rating
	Critical
	Description
	Networking.php, DNS check inserted www.example.com && cat vendors.txt 
exploit was seen
![image8](https://github.com/user-attachments/assets/7e4ba2e9-697e-470c-9aff-05e732414cc2)


	Images
	  

	Affected Hosts
	192.168.14.35
	Remediation 
	Use input validation
	



Vulnerability 6
	Findings
	Title
	User Credentials Exposed
	Type (Web app / Linux OS / WIndows OS)
	Web App
	Risk Rating
	Critical
	Description
	Access login page highlight the page and see exploit
![image2](https://github.com/user-attachments/assets/cff23bcd-f16e-48e1-8c2e-c63dfc6f50dc)

 
	Images
	  

	Affected Hosts
	192.168.14.35
	Remediation 
	delete HTML
	



Vulnerability 7
	Findings
	Title
	Username and Password hash in Github 
	Type (Web app / Linux OS / WIndows OS)
	Web App
	Risk Rating
	Critical
	Description
	Github provided necessary credentials to crack password 
![image7](https://github.com/user-attachments/assets/97fdd011-86d6-4c87-9a97-151070b81cc6)

 
	Images
	  

	Affected Hosts
	Total Rekall web server
	Remediation 
	remove credentials from Github
	


