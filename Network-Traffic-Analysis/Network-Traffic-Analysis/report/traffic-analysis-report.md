## Traffic Analysis Report

## Project Title

# Network Traffic Analysis Using Wireshark

## Objective

The objective of this report is to document the analysis of captured network traffic using Wireshark in order to understand communication behavior, identify common network protocols, and strengthen practical skills in packet inspection and traffic analysis.

# Scope of Analysis

The traffic analysis focused on reviewing a packet capture in Wireshark and examining protocol behavior, communication flow, and visible request/response activity. The review included selected protocols such as DNS, HTTP, TCP, and ICMP where available in the capture.

# Tools Used

- Wireshark
- Test packet capture / lab traffic
- Local analysis environment

# Analysis Performed

1. General Traffic Overview

The packet capture was reviewed to observe the general flow of traffic between systems. Source and destination IP addresses, protocol types, packet lengths, and packet information were examined to understand the communication taking place within the capture.

2. DNS Traffic Review

DNS packets were reviewed to observe domain name queries and responses. This helped show how systems perform name resolution and how DNS traffic can provide visibility into which domains a device is attempting to access.

3. HTTP Traffic Review

HTTP traffic was inspected to observe how requests and responses are exchanged between a client and a server. This analysis helped strengthen understanding of application-layer communication and how packet captures can reveal web activity.

4. TCP Communication Analysis

TCP packets were reviewed to understand connection behavior and communication flow between systems. Observing the exchange of packets helped demonstrate how TCP sessions support reliable communication.

5. ICMP Observation

Where available, ICMP packets were reviewed to observe basic echo request and reply behavior, helping reinforce understanding of diagnostic and network communication traffic.

# Key Findings

- The packet capture contained multiple protocols that support different stages of communication.
- DNS traffic provided insight into domain resolution activity.
- HTTP traffic demonstrated visible request and response communication.
- TCP packet review helped show structured session-based communication between hosts.
- Packet-level visibility is useful for understanding system behavior and supporting security analysis.

# Security Relevance

Traffic analysis is an important cyber security skill because it helps analysts understand how devices communicate, identify unusual activity, and investigate suspicious behavior. Reviewing packet captures can support incident analysis, network troubleshooting, and the identification of indicators of compromise.

Skills Demonstrated

- Network traffic analysis
- Wireshark usage
- Protocol inspection
- Packet review and observation
- Security documentation
- Analytical reporting

# Conclusion

This project strengthened my practical understanding of packet analysis and network visibility using Wireshark. By reviewing traffic across multiple protocols, I gained better insight into communication behavior and how traffic analysis supports cyber security investigations and monitoring tasks.
