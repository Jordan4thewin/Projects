**Blue Team: Summary of Operations**

**Table of Contents**
Network Topology (IN BLUE TEAM FOLDER)

Description of Targets

Monitoring the Targets

Patterns of Traffic and Behavior

Network Topology
The following machines were identified on the network:

**Kali**

Operating System:
**Linix**

Purpose:
**Pen Tester**

IP Address:
**192.168.1.90**

**ELK**

Operating System:
**Ubuntu**

Purpose:
**Kibana**

IP Address:
**192.168.1.100:5601**

**Target 1**

Operating System:
**Linux**

Purpose: **Wordpress Host**

IP Address:
**192.168.1.110**

**Capstone**

Operating System:
**Linux**

Purpose: **Vulnerable Web Server**

IP Address:
**192.168.1.105**
Network Diagram:

Network Diagram

Description of Targets
The VM on the network that was vulnerable to attack: **Target 1 (192.168.1.110)**

Each VM functions as an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers.

Monitoring the Targets
This scan identifies the services below as potential points of entry:

Target 1

**Port 22/TCP**
 
**Port 80/HTTP**

Nmap Target 1 Ports

Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

**Excessive HTTP Errors**

Excessive HTTP Errors is implemented as follows:

**WHEN count() GROUPED OVER top 5 'http.response.status_code' IS ABOVE 400 FOR THE LAST 5 minutes**

Metric:
**WHEN count() GROUPED OVER top 5 ‘http.response.status_code’**

Threshold:
**IS ABOVE 400**


Vulnerability Mitigated:
**Enumeration/Brute Force**


Reliability:
**The alert is highly reliable. Measuring by 400. error codes and above will filter out any normal responses.**

Excessive HTTP Errors alert logs

**HTTP Request Size Monitor**

HTTP Request Size Monitor is implemented as follows:

**WHEN sum() of http.request.bytes OVER all documents IS ABOVE 3500 FOR THE LAST 1 minute**

Metric:
**WHEN sum() of http.request.bytes OVER all documents**

Threshold:

**IS ABOVE 3500**

Vulnerability Mitigated:
**Code injection in HTTP requests**

Reliability:

**Alert could create false positives. Its not as relieable. **


**CPU Usage Monitor**

CPU Usage Monitor is implemented as follows:

**WHEN max() OF system.process.cpu.total.pct OVER all documents IS ABOVE 0.5 FOR THE LAST 5 minutes**

Metric:

**WHEN max() OF system.process.cpu.total.pct OVER all documents**

Threshold:

**IS ABOVE 0.5**

Vulnerability Mitigated:

**Malicious programs running that taking up resources**

Reliability:

**The alert is reliable. Even if there isn’t a malicious program running this can still help find where to improve on CPU usage.**

