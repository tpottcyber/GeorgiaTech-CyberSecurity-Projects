# Red Team: Summary of Operations

## Table of Contents
- Exposed Services
- Critical Vulnerabilities
- Exploitation

### Exposed Services

Nmap scan results for each machine reveal the below services and OS details:
Name of VM: Target1
Operating System: Linux
Purpose: Defensive Blue Team
IP Address: 192.168.1.110

**Name of VM: Target2**

Operating System: Linux
Purpose: Offensive Red Team
IP Address: 192.168.1.115

-	Bash
-	$ Command to Scan Target 1
-	 Nmap -sV 192.168.1.110/24


This scan identifies the services below as potential points of entry:

**Target 1**

![image](https://user-images.githubusercontent.com/79764720/131806438-f6db7499-6e48-43e0-993e-f6d2bc40a084.png)

The following vulnerabilities were identified on each target:

**Target 1**

- CVE-2017-15710 Apache https 2.4.10
- CVE-2017-7494 Samba Netbios
- CVE-2021-28041 open SSH

### Exploitation
- Wpscan displays the brute force of users “michael and steven” 

![image](https://user-images.githubusercontent.com/79764720/131807553-7fc3b733-ac3f-4b48-81c8-7fbc5935e8f4.png)

![image](https://user-images.githubusercontent.com/79764720/131807714-c63d3416-fe1b-45c2-94cc-ecdde2194c76.png)


The Red Team was able to penetrate `Target 1` and retrieve the following confidential data:
**Target 1**
  - `flag1.txt`:

![image](https://user-images.githubusercontent.com/79764720/131807808-5c09af2f-6573-49d3-abac-3f5e350c9b5c.png)


  - `flag2.txt`: 

![image](https://user-images.githubusercontent.com/79764720/131807873-cd5b0212-cad9-42ee-bec9-1df9323322f1.png)

