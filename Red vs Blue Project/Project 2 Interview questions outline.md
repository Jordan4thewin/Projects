Restate the Problem “”How to execute an offensive attack.””
Provide a Concrete Example Scenario

In Project 2, which VMs were on the network? **“Kali, Elk, & Capstone server”** 

What was the purpose of each? **“Kali is the attacker machine” , “Elk is monitoring the traffic”, “capstone was the victim machine”**

Which of these VMs did you have to infiltrate? **The capstone was infiltrated**.

What was your goal in infiltrating each VM? **The goal Infiltrating the capstone was to gain remote access through webdav and upload a reservse shell**

Which tools did you use to perform the infiltration? **Brute Force attack, WebDAV connection & reverse shell uploads**

What kinds of security measures, if any, were enabled on the network?

Explain the Solution Requirements

How did you identify your targets? **Scanning ports, Searching for hidden dir once inside** 
How did you identify vulnerabilities in each target and which did you exploit? **Once I had access to secret directory file after cracking users login credentials**

What did you do after infiltrating? **After infiltration a reverse shell was created**

Explain the Solution Details

Which tools and commands did you use to identify your targets and their vulnerabilities **Nmap id the target, brute force cracked the password uploading reverse shell allows remote access**

Which exploits did you use against these vulnerabilities and how did you deliver them?

How did you achieve your goal after infiltration? **Once pw was obtained I was able to access via webdav. With access to webdav I connected to server via a revese shell and had full access.**

Identify Advantages and Disadvantages of the Solution

Were your methods covert or detectable by monitoring solutions? T**he Webdav connection easily went unnoticed because of login creditials, With the large number of packets in time frame the entrence through a open port is hard to detect**
How could you achieve your goal with greater stealth?