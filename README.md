<h1>Cybersecurity Home Lab</h1>

<h2>Description</h2>
This home lab is made up of several virtual machines in a virtual network through Oracle's VirtualBox. The Home Lab is used to simulate a cyber attack into a company's network and how the company's security measures are able to monitor, detect, and mitigate against those attacks. The name of the NAT Network is called 'Project X' where all the company's devices were connected to a domain controller which would assign user/computer permissions through Active Directory.  This was good, hands-on practice to see how, with various tools, techniques, and procedures, attackers are able to compromise an organization's network. 
<br />


<h2>Languages and Tools Used</h2>

- Microsoft Active Directory
- Wazuh
- Powershell
- Postfix
- NMap
- Hydra

<h2>Environments Used </h2>

- <b>Oracle VirtualBox</b>
- <b>Windows 11 Enterprise</b>
- <b>Windows Server 2025</b>
- <b>Ubuntu Server</b>
- <b>Ubuntu Desktop 22.04</b>
- <b>Security Onion</b>
- <b>Kali Linux</b>

<h2>Cyber Attack Simulation:</h2>

<p align="left" width="100%">
  Basic Network Topology using Cisco Packet Tracer:
  <img width="100%" height="400" alt="Image" src="https://github.com/user-attachments/assets/8db4304f-561a-4cc2-9f43-0b59a0d08289" />
  <br/><br/><br/>

1. First, the attacker uses Nmap to search for open ports on vulnerable email server and implements brute force attack using Hydra to exploit username and password:  
  <img width="100%" alt="Image" src="https://github.com/user-attachments/assets/e02f7026-dc20-4991-b454-d4f6d4fa1624" />
  <br/><br/><br/>

2. Next, the attacker remotes into the email server through open port 22 (SSH), using the victim's root account, and network IP address:
  <img width="100%" alt="Image" src="https://github.com/user-attachments/assets/ea5d48dd-2046-4c5c-9215-77fbbad24170" />
  <br/><br/><br/>

3. Once logged into the company's email server, the attacker can search through their file system to find usernames and passwords of other accounts on the device:
  <img width="100%" alt="Image" src="https://github.com/user-attachments/assets/59b474d7-0646-490c-abe2-7231c25e6175" />
  <br/><br/><br/>

4. Again using Nmap, while acting as the email server, search for open ports and devices on the company's network using the network subnet mask. This Nmap function also provides attacker with details about each device such as their operating system, ports that each device has open, and each device MAC address:
  <img width="100%" height="550px" alt="Image" src="https://github.com/user-attachments/assets/9b7ac898-d622-4d62-a18a-eee748c6e3c8" />  
  <img width="100%" alt="Image" src="https://github.com/user-attachments/assets/5d639a89-e8ec-41a8-8f03-7af048d6fa7b" />
  <br/><br/><br/>
  
5. Here the attacker accesses the email server's inbox and sends a phishing email to a Linux machine that is connected to the email server in an attempt to steal sensitive information. When opened by the Linux machine, it will prompt the user to click on a website link in order to verify their username and password used to log into that device:
  <img width="100%" height="500px" alt="Image" src="https://github.com/user-attachments/assets/f881e8bc-9e47-40cf-b6ca-4bac0b487124" />
  <br/><br/><br/>

6. When the victim user clicks on the malicious link, they are taken to this webpage:
  <img width="100%" alt="Image" src="https://github.com/user-attachments/assets/aa8ad606-81ec-47db-be93-2d44a09e3990" />
  <br/><br/><br/>

7. Once the user inputs their username, password, and clicks on verify, the script embedded into the malicious webpage creates a 'creds.log' file on the attacker machine where the attacker has successfully captured the credentials of the Linux machine user.
  <img width="100%" height="500px" alt="Image" src="https://github.com/user-attachments/assets/e8906968-745a-47e9-bef9-fc2dbc73a13a" />
</p>
