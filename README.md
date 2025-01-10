# AZURE SIEM

## Objective

In this project, I implemented a Security Information and Event Management (SIEM) solution using Microsoft Sentinel on Microsoft Azure's cloud based platform in order to enhance security monitoring and log analysis. The focus of this project was to track and analyze Remote Desktop Protocol (RDP) login attempts to a virtual machine, capturing both successful and unsuccessful login events over the RDP connection.

This project demonstrates proficiency in setting up Microsoft Sentinel for security monitoring and also highlights my ability to configure, analyze, and respond to security events on virtual machines in a cloud environment.

### Skills Learned
[Bullet Points - Remove this afterwards]

- Configuring log sources from the virtual machine to Microsoft Sentinel for real-time monitoring.
- Setting up automated alerts to notify administrators of suspicious login attempts, such as repeated failed logins, to detect potential brute force or unauthorized access attempts.
- Leveraging query capabilities within Sentinel to analyze RDP login patterns, improving incident response and enhanced security on a virtual machine.

### Tools Used

- Microsoft Azure as a cloud hosting platform for the Virtual Machine and SIEM.
- Microsoft Sentinel as a SIEM interface for the Windows Security Logs from the Virtual Machine.

## Task 1: Set up Machines and Sentinel
![3 - SIEM can be connected to](https://github.com/user-attachments/assets/44b5dc44-ec82-42b5-bf8c-cba22a0468cf)

*Ref 1: Virtual Machine created, and port 3389 is accessible for RDP connections. /This machine is no longer active/*

<br/>![5 - Adding Microsoft Sentinel to Log Analytics](https://github.com/user-attachments/assets/4a77d771-995e-498c-8670-5a268725a20c)

*Ref 2: Added Microsoft Sentinel to the Log Analytics*

<br/>![8 - 2 Connectors](https://github.com/user-attachments/assets/684525f1-8904-4296-9ae3-638726929616)

*Ref 3: Added 2 connectors through the content hub, both related to Windows Security Events*

## Task 2: Set up Rule Codes
![10 - Sentinel Rule Code](https://github.com/user-attachments/assets/58da4bde-4dcd-4c76-8dd9-47dbc7115d38)

*Ref 4: Security Rule to create an incident when there's a non-system, successful login to the virutal machine through RDP*

<br/>![11 1 - Rule Continued](https://github.com/user-attachments/assets/618973b0-ecb7-4749-85fa-34db0a1ec42d)

*Ref 5: Every 5 minutes the SIEM will look for an event, where any login event will trigger an alert*

<br/>![14 - RPD Unsuccessful Login](https://github.com/user-attachments/assets/c0acfaa0-7211-4473-b2a3-38902d4c7416)

*Ref 6: A second Security Rule created for unsuccessful login attempts, looking for at least 5 unsuccessful logins within 5 minutes to trigger an alert. If there is a brute force attempt, it will send the information to the logs.*

## Task 3: SIEM Event Logs
![14 - RDP Unsuccessful Logins on SIEM](https://github.com/user-attachments/assets/027d8cdb-a20c-4e06-a7a3-09f35fc9027a)

*Ref 7: I completed 3 separate logins - one where I successfully logged into the SIEM account with RDP, one where I unsuccessfully logged into the SIEM account with RDP at least 5 times, and one where I unsuccessfully logged into an account that did not exist with RDP at least 5 times. These logins all showed as incidents within the Sentinel platform.*

<br/>![15 - Another option for RDP Unsuccessful Logins, only our admin account](https://github.com/user-attachments/assets/db5c8650-5f50-4323-9244-407fe877d66f)

*Ref 8: Another rule I edited that would only show unsuccessful logins for our admin account, SIEM.*
