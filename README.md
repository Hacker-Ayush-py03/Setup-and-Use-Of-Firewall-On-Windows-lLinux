# Setup-and-Use-Of-Firewall-On-Winsows/Linux

## 🎯 Objective
The purpose of this lab is to configure and test basic firewall rules on both Windows and Linux (UFW).  
By the end of this task, you will be able to:

- Use Windows Firewall and UFW on Linux
- Add and remove inbound/outbound rules
- Block and allow ports
- Verify rule functionality
- Understand how firewall traffic filtering works

---

## 🛠 Tools Required
- **Windows Firewall with Advanced Security**
- **UFW (Uncomplicated Firewall)** on Linux

---

## 📄 Deliverables
You must include:

- Screenshots of firewall rules created
- Commands or GUI steps used
- A brief summary of how firewall filtering works

---

# 🧭 Step-by-Step Guide (Deep Analysis)

## 1. Open Firewall Configuration Tool

### Windows:
- Open:  
  *Control Panel → System and Security → Windows Defender Firewall → Advanced Settings*
- OR run:
-wf.msc

- ### Linux (UFW):
Open terminal:sudo ufw status
---

## 2. List Current Firewall Rules

### Windows:
- View “Inbound Rules” and “Outbound Rules”

### Linux:
sudo ufw deny 23/tcp

---

## 3. Add a Rule to Block Inbound Traffic (Example: Port 23 - Telnet)

### Windows:
1. Go to **Inbound Rules**
2. Click **New Rule**
3. Select **Port**
4. Choose **TCP**
5. Enter port: 23
6. Choose **Block the connection**
7. Apply to Domain, Private, Public
8. Name the rule and finish

### Linux (UFW):sudo ufw deny 23/tcp
---

## 4. Test the Rule

### Windows / Linux:
Try connecting to port 23:

Local test:telnet localhost 23

Remote test:telnet <target-ip> 23

A blocked port will show **connection failed**.

---

## 5. Add a Rule to Allow Port 22 (SSH)

### Linux (UFW only):

sudo ufw allow 22/tcp

Verify:

sudo ufw status

---

## 6. Remove the Test Block Rule

### Linux:
To remove rule # (shown in numbered list):

sudo ufw status numbered sudo ufw delete <rule_number>

### Windows:
- Find the previously added rule
- Right-click → **Delete**

---

## 7. Document Commands / GUI Steps
Include:
- Screenshots of rules
- Commands used:
  - `sudo ufw allow`
  - `sudo ufw deny`
  - Windows Firewall GUI steps

---

## 8. Summary: How Firewall Filters Traffic
Firewalls filter traffic based on:
- **Source IP / Destination IP**
- **Ports (22, 23, etc.)**
- **Protocols (TCP/UDP)**
- **Direction (Inbound/Outbound)**

They decide whether to:
- **Allow**
- **Deny**
- **Drop**
a packet using rule-based logic.

---

# 📝 Interview Questions (With Short Answers)

### 1. What is a Firewall?
A security system that monitors and controls network traffic based on predefined rules.

### 2. Difference Between Stateful and Stateless Firewalls?
- **Stateful:** Tracks connection states; more secure.
- **Stateless:** Checks packets individually; faster but less secure.

### 3. What Are Inbound and Outbound Rules?
- **Inbound:** Controls traffic coming into the system.
- **Outbound:** Controls traffic leaving the system.

### 4. How Does UFW Simplify Firewall Management?
UFW provides simple commands for managing iptables without dealing with complex syntax.

### 5. Why Block Port 23 (Telnet)?
Telnet sends data in plaintext and is insecure → often exploited.

### 6. Common Firewall Mistakes?
- Allowing too many open ports
- Not removing old rules
- Misconfiguring inbound/outbound policies

### 7. How Does a Firewall Improve Network Security?
By preventing unauthorized access, blocking malicious traffic, and enforcing security policies.

### 8. What Is NAT in Firewalls?
Network Address Translation → hides private IPs and maps internal addresses to public ones.

---

## 🔑 Key Concepts
- Firewall configuration  
- Traffic filtering  
- Inbound/outbound rules  
- Ports (22, 23)  
- UFW  
- Windows Firewall  

---
