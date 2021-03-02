## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Azure Elkstack Cloud Infrastructure Network Diagram](Images/Azure Elkstack Cloud Infrastructure.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the **playbook** file may be used to install only certain pieces of it, such as Filebeat.

  - _my-playbook.yml_
  - _pentest.yml_
  - _install-elk.yml_
  - _filebeat-playbook.yml_
  - _metricbeat-playbook.yml_
  - _ansible.cfg_
  - _filebeat-config.yml_
  - _metricbeat-config.yml_
  

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available and accessible, in addition to restricting unauthorized users to the network.
- What aspect of security do load balancers protect? Helps distribute traffic evenly across the servers and mitigates DDOS Attacks.  What is the advantage of a jump box? Allows a secure means to offer public accessibility for the user community, then allowing those users to access through security groups for internal VM connections. _

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the infrastrucuture, logs, administrative security and system traffic.
- _What does Filebeat watch for? **Collects data bout the file system**_
- _What does Metricbeat record? **Collects machine metrics, such as uptime**_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name        | Function                                      | IP Address | Operating System |
|-------------|--------------------------------------|--------------|-----------------------|
| Jump Box | Gateway                                      | Public IP    | Linux                       |
| Elkstack    |  ElasticSearch Logstash Kibana |  Private IP  | Linux                       |
| Web-1       |  Web Server                                 | Private IP   | Linux                      |
| Web-2       |  Web Server                                 | Private IP   | Linux                      |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _Public IP Address_


Machines within the network can only be accessed by Jump Box and ElkStack.

Which machine did you allow to access your ELK VM? JumpBox What was its IP address?_
- _Private_IP_
- _75.131.6.100_

A summary of the access policies in place can be found in the table below.

| Name        | Publicly Accessible | Allowed IP Addresses     |
|-------------|------------------------|-----------------------------|
| Jump Box | Yes                           | Private IP  40.114.73.49 |
| Web-1       |  No                           |  Private IP                       |
| Web-2       |  No                           |   Private IP                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _What is the main advantage of automating configuration with Ansible? **Increase in consistency, speed and deployment of security and applications**_

The playbook implements the following tasks:
- _In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- _Create Virtual Network_
- _Create a Peer Network Connection_
- _Create a new VM_
- Download and configure a container_
- _Launch and expose container and implement identity and access management_

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![ Docker PS Output ](Project-1-Azure Kibana/Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _List the IP addresses of the machines you are monitoring_

| Name     | IP Addresses Monitored |
|-----------|-----------------------------|
| Web-1    | Private IP                        |
| Web-2    | Private IP                        |


We have installed the following Beats on these machines:
- Specify which Beats you successfully installed_
- _filebeat_
- _metricbeat_
These Beats allow us to collect the following information from each machine:
- _In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

- _Filebeat monitors server logs and system logs provided detailed information regarding connections, errors encountered, etc.  

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the **/etc/ansible/filebeat-config.yml** file to **/etc/filebeat/filebeat.yml**. _
- Update the **filebeat-playbook.yml** file to include commands and source/destination locations. _
- Update the **filebeat-config, metricbeat config, and hosts file to include your private ip addresses**. _
- filebeat-config/metricbeat-config:  output.elasticsearch:  update with your private ip address _
- filebeat-config/metricbeat-config: setup.kibana: update with your private ip address only _
- hosts:  update the webservers section: private ip address ansible_python_interpreter=/usr/bin/python3 (for each web server) _
- hosts: update and create a section to discover the Elk Server just like the web servers - private ip address ansible_python_interpreter=/usr/bin/python3 _
- Run the playbook, and navigate to **Web-1 and Web-2 /etc/filebeat or /etc/metricbeat** to check that the installation worked as expected. _
_Answer the following questions to fill in the blanks:_
- _Which file is the playbook? **-playbook.yml** Where do you copy it? **/etc/ansible**_
- _Which file do you update to make Ansible run the playbook on a specific machine? **filebeat-config.yml and hosts.yml** How do I specify which machine to install the ELK server on versus which to install Filebeat on? **The Elk Server is the VM that will monitor and maintain the data for logging.  The Filebeat is installed on the Web Servers, which will be monitored, the same process is executed for Metricbeat.** _
- _Which URL do you navigate to in order to check that the ELK server is running? **<public_ipaddress>:5601/app/kibana**
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

- _hosts
- _ansible-playbook filebeat-playbook.yml
- _filebeat-config.yml
- _ansible-playbook metricbeat-playbook.yml
- _metricbeat-config.yml

