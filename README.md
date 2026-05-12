<img width="961" height="829" alt="04-nmap-scan png" src="https://github.com/user-attachments/assets/6af7af7f-6e37-4449-a6ec-375aad85da0d" /><img width="1916" height="1037" alt="01-Kali-running png" src="https://github.com/user-attachments/assets/2e581d0b-c42c-48af-b292-d870d75f3e84" /># Network Traffic Analysis Labs

## Focus
- Understand live network traffic
- Identify DNS, TCP, TLS, HTTPS flows
- Learn packet capture & filtering

## Tools
- Wireshark (Windows)
- Browser traffic (Edge, Google)

## Lab Status
- Capture: ✅ Completed
- Filters Applied: DNS, TLS
- Data Saved: .pcapng

## Key Observations
- DNS queries resolve domains like google.com, mtalk.google.com
- HTTPS traffic is encrypted (TLS handshake visible, payload hidden)
- Client Hello observed before encrypted application data


### Week 2 Update

#### What I Practiced & Studied
- Reviewed the OSI model and how data is encapsulated and decapsulated across layers
- Connected OSI theory to real network traffic previously captured in Wireshark
- Studied the CIA triad (Confidentiality, Integrity, Availability) and its relevance to network security
- Reviewed common cyber attack types and their high-level impact
- Identified key tools to focus on as a beginner, including Wireshark and Splunk

#### What Clicked
- Encapsulation explains why multiple protocol headers appear in packet captures
- DNS resolution occurs before HTTPS communication begins
- TLS encrypts application-layer data before it is handed to TCP, providing confidentiality
- Even when payloads are encrypted, network metadata remains visible

#### Temporary Constraint
- Hands-on labs paused due to a hardware issue (charger failure)
- Continued learning through review, documentation, and reflection

#### Next Week Focus
- Resume live traffic capture in Wireshark
- Apply OSI layer mapping directly to observed packets
- Practice protocol-based filtering (DNS, TLS, HTTP/HTTPS)
- Begin introductory exposure to log analysis concepts (Splunk)

## Week 3 – HTTP vs HTTPS Traffic Analysis

### Objective
Compare unencrypted HTTP traffic with encrypted HTTPS traffic using Wireshark to understand visibility, encryption, and protocol behavior.

### Tools Used
- Wireshark

### What I Did
- Captured live network traffic on an active interface
- Visited an HTTP website (`http://neverssl.com`)
- Visited an HTTPS website (`https://www.google.com`)
- Applied protocol filters (`http`, `tls`, `dns`) to analyze traffic differences

### Key Observations
- HTTP traffic is visible in plain text, including request details and headers
- HTTPS traffic is encrypted; only TLS handshakes and metadata are visible
- DNS resolution occurs before both HTTP and HTTPS connections
- TLS encrypts application-layer data before it is handed to TCP for transport

### Evidence
![Wireshark Capture – HTTP vs HTTPS](IMG-20260202-WA0033.jpg)

### Week 9 – Kali Linux Virtual Machine Successfully Deployed

This week marked a major milestone in my cybersecurity lab development: I successfully booted and launched Kali Linux inside VirtualBox after previous weeks of virtualization issues and failed boot attempts.

The process involved troubleshooting multiple configuration problems, understanding the differences between VM file types (.vbox, .vdi, .ova), and learning how to properly register and launch prebuilt virtual machines.

Key progress made this week:
- Successfully deployed Kali Linux in VirtualBox
- Resolved previous boot and configuration errors
- Improved understanding of virtualization workflows
- Established a functional attacker environment for future lab exercises

This milestone transitions my lab from setup phase into operational phase. With Kali now working, I can begin practical offensive security tasks such as reconnaissance, scanning, enumeration, and controlled attack simulations.

### Next Week Plan
- Configure networking between Kali and target systems
- Test connectivity (ping / IP discovery)
- Begin basic reconnaissance using Nmap
- Capture traffic with Wireshark during scans
- Start generating logs for Splunk analysis

### Key Takeaway
Persistence during technical failure is a core cybersecurity skill. Solving environment and deployment problems is part of real-world security work, not separate from it.
### Week 10 – SOC Lab Deployment, Network Reconnaissance & Log Analysis

This week marked a major transition from environment setup into practical cybersecurity operations. I successfully built and utilized a functional home SOC lab integrating both offensive and defensive tools.

On the offensive side, I used Kali Linux to perform internal reconnaissance using Nmap. The scan confirmed host availability within the lab network and provided insight into basic network behavior.

To analyze network-level activity, I used Wireshark to capture live traffic during scanning. Using filters such as ARP, I was able to observe device communication and understand how systems discover and interact with each other on the network.

On the defensive side, I configured Splunk to ingest Windows Event Logs from the host machine. I verified log ingestion by querying Application and Security logs, gaining visibility into system activity and event generation.

To further test detection capability, I generated user and system activity (application launches and interactions) and analyzed corresponding logs in Splunk. This introduced the concept of correlating actions with logged events.

Key achievements this week:
- Successfully deployed and operated a Kali Linux attacker environment
- Performed network reconnaissance using Nmap
- Captured and analyzed network traffic using Wireshark
- Configured Splunk SIEM to ingest Windows Event Logs
- Queried and investigated system activity through log analysis

### Next Week Plan
- Improve log visibility (enable and troubleshoot missing System logs)
- Generate and detect specific security events (e.g., failed logins)
- Begin structured threat detection use cases in Splunk
- Enhance documentation and publish first cybersecurity project on GitHub

###Screenshots 
- Kali environment <img width="1916" height="1037" alt="01-Kali-running png" src="https://github.com/user-attachments/assets/aac68e73-f59e-433b-9ab6-44875d7e3512" />

- Nmap reconnaissance <img width="961" height="829" alt="04-nmap-scan png" src="https://github.com/user-attachments/assets/166cc0e0-de1e-413d-a8bb-4233ae583416" />

- Wireshark network traffic <img width="1919" height="1027" alt="03-Wireshark-capture png" src="https://github.com/user-attachments/assets/466275d2-d1e8-4ae0-b39e-a6c47d3f8b1d" />

- Working Splunk <img width="1896" height="879" alt="02-Splunk-dashboard png" src="https://github.com/user-attachments/assets/2568c3b4-8b76-4ccf-bb85-35ead2fc2e2a" />


### Key Takeaway
Cybersecurity is not just about running tools, but about understanding and connecting attacker activity, network behavior, and system logs. This week established the foundation for real-world detection and analysis workflows.
