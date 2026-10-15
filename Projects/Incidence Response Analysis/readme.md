# A DDoS Incident Response Analysis

## 📎Project Overview

I are tasked with using a security event to create a plan to improve a company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). This project was given me during my **Connect and Protect: Networks and Network Security** course with Google.

This project demonstrates how the **NIST Cybersecurity Framework (NIST CSF)** can be applied to analyze and improve an organization's response to a cybersecurity incident.

---

## Scenario

You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services. 

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a denial of service (DoS) attack. 

To address this security event, the network security team implemented: <br>
1️⃣ A new firewall rule to limit the rate of incoming ICMP packets <br>
2️⃣ Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets <br>
3️⃣ Network monitoring software to detect abnormal traffic patterns <br>
4️⃣ An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics <br>

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF).

<br>
---

# 🕵️‍♂️ **The Incidence Response Analysis:**

The incident is analyzed through five NIST CSF functions:

**Identify → Protect → Detect → Respond → Recover**. <br>


| Summary | Our multimedia company recently experienced a denial of service (DoS) attack that compromised the internal network for two hours until it was resolved. During the attack, network services suddenly stopped responding due to an incoming flood of ICMP packets, preventing normal internal network traffic from accessing any network resources. Investigation by the cybersecurity team revealed that a malicious actor exploited an unconfigured firewall to send a flood of ICMP pings into the network, overwhelming organizational resources. |
| --- | --- |
| Identify | The incident management and cybersecurity teams audited the network devices and configurations involved in the attack to identify security gaps. They found that an unconfigured firewall left the network exposed, allowing a malicious attacker to launch a DoS attack by flooding the network with ICMP packets without sufficient restrictions. |
| Protect | To prevent similar attacks in the future, the network security team implemented new defensive measures. They set in place new firewall rule to limit the rate of incoming ICMP packets **and** Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets |
| Detect | To detect abnormal traffic patterns and unauthorized access attempts moving forward, the team implemented a network monitoring software to detect abnormal traffic patterns **and** an IDS/IPS system to filter out ICMP traffic based on suspicious characteristics. |
| Respond | During the security event, the incident management team took immediate action by:- Blocking incoming ICMP packets- Taking all non-critical network services offline- Restoring critical network services to mitigate the impact of the flood |
| Recover | The team successfully restored critical network services after the two-hour disruption. Normal internal network operations and resource accessibility were fully recovered once the malicious traffic was mitigated and protective firewall rules were applied.|

🪞 Reflections/Notes:
Moving forward, regular audits of firewall configurations and continuous monitoring through network analysis software and intrusion detection systems will be critical to ensuring early detection and rapid mitigation of potential DoS attacks.


[View other Featured Projects](../../../README.md#-featured-projects)
