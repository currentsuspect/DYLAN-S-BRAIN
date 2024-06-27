---
cssclasses:
  - center-titles
  - center-images
  - pen-red
  - page-grid
---

### Chapter 5: Port Scanning Techniques

Port scanning lies at the heart of network reconnaissance, allowing users to identify open ports and services on target hosts. In this chapter, we will explore the various port scanning techniques offered by Nmap and how they can be leveraged to gather valuable information about network assets.

#### TCP Scanning Options
TCP scanning is the most common and versatile method for port scanning. Nmap provides several TCP scanning options, each tailored to specific objectives and network environments:

1. **TCP SYN Scan (-sS)**:
   - Also known as "half-open" scanning, it sends SYN packets to target ports and analyzes the responses to determine port status.
   - Stealthy and fast, suitable for scanning large networks and evading intrusion detection systems.

2. **TCP Connect Scan (-sT)**:
   - Initiates a full TCP connection with each target port, similar to how a regular application would connect.
   - Provides reliable results but is more conspicuous than SYN scanning, making it suitable for environments where stealth is not a concern.

3. **TCP ACK Scan (-sA)**:
   - Sends ACK packets to target ports and analyzes the responses to infer port state.
   - Used to bypass stateful firewalls by determining which ports are filtered.

4. **TCP Window Scan (-sW)**:
   - Utilizes the TCP window field to determine port state, bypassing certain firewall configurations.
   - Can provide valuable insights into the behavior of target systems and firewalls.

#### UDP Scanning Options
UDP scanning is used to identify open UDP ports and services, which are often overlooked by traditional TCP scans due to their connectionless nature. Nmap offers a dedicated UDP scanning option (-sU) for this purpose:

- **UDP Scan (-sU)**:
  - Sends UDP packets to target ports and analyzes the responses to determine port status.
  - Prone to false positives due to the lack of reliable response mechanisms in UDP.

#### Timing and Performance Options
Nmap provides timing and performance options to optimize scan speed and accuracy, allowing users to adjust the aggressiveness of scans according to their requirements:

- **Timing Templates (-T)**:
  - Offers predefined timing profiles ranging from "Paranoid" to "Insane," allowing users to balance scan speed with stealthiness.
  
- **Parallelism (-Pn)**:
  - Controls the number of parallel threads used for scanning, influencing scan speed and resource utilization.
  
- **Host Timeout (--host_timeout)**:
  - Specifies the maximum time to wait for a response from a target host before considering it unreachable.
  
#### Conclusion
Port scanning is a fundamental technique in network reconnaissance, providing valuable insights into the services and vulnerabilities present on target hosts. By mastering the various port scanning options and timing parameters offered by Nmap, users can conduct thorough and efficient scans of their network infrastructure, enabling them to make informed decisions about security measures and risk mitigation strategies. In the following chapters, we will explore advanced scanning techniques and delve deeper into Nmap's capabilities for service detection and version enumeration.