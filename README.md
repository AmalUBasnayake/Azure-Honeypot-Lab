# 🛡️ Azure Honeypot & Threat Monitoring Lab

## 📖 Overview
This project demonstrates the deployment of a **Windows Server 2022** virtual machine on **Microsoft Azure** to act as a "Honeypot." By intentionally opening network ports, the server was exposed to the public internet to capture and analyze real-time RDP brute-force attack attempts.

---

## 🛠️ Tools & Technologies
* **Cloud Platform:** Microsoft Azure (Virtual Machines, Network Security Groups)
* **Operating System:** Windows Server 2022
* **Monitoring Tool:** Windows Event Viewer (Event ID 4625)
* **Intelligence:** IP Geolocation API

---

## 🚀 Lab Steps

### 1. Virtual Machine Setup
The lab began by provisioning a Windows Server 2022 instance named `AmalLabs`. I monitored the deployment to ensure all networking and storage resources were successfully validated and created.

![Deployment Validation](https://github.com/YOUR_USERNAME/YOUR_REPO/blob/main/AZ-01.png?raw=true)
*Figure 1: Azure VM Deployment Validation*

![VM Running](https://github.com/YOUR_USERNAME/YOUR_REPO/blob/main/AZ-03.png?raw=true)
*Figure 2: Virtual Machine successfully running on Azure*

### 2. Network Security Configuration
To simulate a vulnerable environment, I modified the **Network Security Group (NSG)**. I added an inbound rule to allow all **ICMP (Ping)** traffic, making the server visible to automated scanners across the globe.

![NSG Rule Creation](https://github.com/YOUR_USERNAME/YOUR_REPO/blob/main/AZ-05.png?raw=true)
*Figure 3: Configuring Inbound Security Rules*

![NSG Rule Completed](https://github.com/YOUR_USERNAME/YOUR_REPO/blob/main/AZ-06.png?raw=true)
*Figure 4: Custom ICMP rule successfully added*

### 3. Attack Analysis & Monitoring
Inside the VM, I utilized **Windows Event Viewer** to monitor security logs. Shortly after exposure, the system began logging **Event ID 4625 (Audit Failure)**, indicating failed login attempts.

![Security Logs](https://github.com/YOUR_USERNAME/YOUR_REPO/blob/main/AZ-07.png?raw=true)
*Figure 5: Capturing real-time Brute-Force attack logs*

### 4. Geolocation Tracking
I extracted the source IP addresses from the failed logon events and used a Geolocation tool to map the origin of the attack, identifying the ISP and geographic location.

![IP Geolocation](https://github.com/YOUR_USERNAME/YOUR_REPO/blob/main/AZ-08.png?raw=true)
*Figure 6: Mapping the attacker's IP address (Dialog Axiata, Sri Lanka)*

---

## 💡 Key Findings & Conclusion
* **Instant Discovery:** Cloud assets are discovered by automated bots almost immediately after being exposed to the internet.
* **Log Significance:** Monitoring **Event ID 4625** is critical for identifying and responding to unauthorized access attempts.
* **Cost Management:** Successfully deallocated resources after the lab to prevent unnecessary costs.

![VM Stopped](https://github.com/YOUR_USERNAME/YOUR_REPO/blob/main/image_1c1cbc.png?raw=true)
*Figure 7: Resources deallocated post-lab*

---

## 📅 What's Next?
In the next phase of this project, I will integrate **Microsoft Sentinel (SIEM)** to visualize these global attacks on a live map!
