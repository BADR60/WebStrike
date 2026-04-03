🛡️ WebStrike Incident Report (SOC Level 1)
📌 Case Overview
Lab Name: WebStrike
Platform: CyberDefenders
Category: Web Log Analysis / Incident Response
Analyst: [badr]

![image alt](https://github.com/BADR60/WebStrike/blob/7d3634acc91649c883fbaa6c4afc0f61ab37a841/Untitled.jpeg)

🚨 Incident Summary

This investigation analyzes suspicious web server activity indicating a potential compromise.
Multiple malicious requests were identified targeting the web application, suggesting exploitation attempts followed by unauthorized access.

The attacker leveraged crafted HTTP requests to probe and potentially exploit vulnerabilities within the web server.

🎯 Objective
Identify malicious activity in web logs
Determine attacker behavior
Extract Indicators of Compromise (IOCs)
Assess impact and provide recommendations
🔍 Investigation Steps

1️⃣ Initial Analysis

The investigation began by reviewing web server logs for unusual patterns such as:

Repeated requests from a single IP
Suspicious HTTP methods
Access to sensitive endpoints

A suspicious IP address was identified generating abnormal traffic volume.

2️⃣ Web Log Analysis

Analysis of HTTP logs revealed:

Multiple GET and POST requests to uncommon endpoints
Attempts to access:
/admin
/login
/phpmyadmin
Presence of encoded payloads in URLs

Example suspicious pattern:

GET /index.php?id=1' OR '1'='1 HTTP/1.1

This indicates a possible SQL Injection attack attempt.

3️⃣ Attacker Behavior

The attacker followed a clear sequence:

Reconnaissance (scanning endpoints)
Exploitation attempts (SQL Injection / brute force)
Access to restricted areas

This behavior suggests automated attack tools or scripts.

4️⃣ Evidence Collection

Evidence Type	Details
Malicious IP	192.168.x.x
Target URLs	/admin, /login
Attack Type	SQL Injection
HTTP Methods	GET, POST

5️⃣ Timeline of Events

10:15 - Multiple requests initiated from suspicious IP  
10:17 - Access attempts to /admin panel  
10:18 - SQL injection payload detected  
10:20 - Repeated login attempts observed

🧠 Analysis & Findings

The attacker attempted to exploit input validation vulnerabilities.
SQL Injection patterns confirm malicious intent.
Repeated login attempts indicate possible brute-force attack.
No clear evidence of full system compromise, but vulnerability exposure exists.

⚠️ Indicators of Compromise (IOCs)

Type	Value
IP Address	192.168.x.x
URL	/admin
Payload	' OR '1'='1
Method	POST

🛠️ Tools Used

Log analysis tools
Web server logs (Apache/Nginx)
Basic traffic inspection techniques

⚡ Impact Assessment

Potential unauthorized access attempts
Exposure of web application vulnerabilities
Risk of data leakage if exploited successfully

🔐 Recommendations

Implement Web Application Firewall (WAF)
Sanitize all user inputs to prevent SQL Injection
Enforce strong authentication mechanisms
Monitor logs continuously using SIEM solutions
Block malicious IP addresses
Apply rate limiting to prevent brute-force attacks

✅ Conclusion

The investigation identified clear signs of malicious activity targeting the web application.
While no confirmed breach was observed, the attack patterns indicate serious vulnerabilities that must be addressed immediately.

Proactive monitoring and improved security controls are essential to prevent future attacks.

👨‍💻 Author

[baadr]
SOC Analyst (Level 1)
