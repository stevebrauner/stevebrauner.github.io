---
layout: single
title: "Incident Report Analysis"
excerpt: "Use The NIST Cybersecurity Framework To Respond To A Security Incident"
classes: wide
---

# Incident report analysis

## Scenario

You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services.

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack.

To address this security event, the network security team implemented:

- A new firewall rule to limit the rate of incoming ICMP packets

- Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets

- Network monitoring software to detect abnormal traffic patterns

- An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity event and integrate your analysis into a general security strategy. We have broken the analysis into different parts in the template below. You can explore them here:

- Identify security risks through regular audits of internal networks, systems, devices, and access privileges to identify potential gaps in security.

- Protect internal assets through the implementation of policies, procedures, training and tools that help mitigate cybersecurity threats.

- Detect potential security incidents and improve monitoring capabilities to increase the speed and efficiency of detections.

- Respond to contain, neutralize, and analyze security incidents; implement improvements to the security process.

- Recover affected systems to normal operation and restore systems data and/or assets that have been affected by an incident.

## Incident Report

### Summary

Recently, our internal network stopped responding due to a flood of ICMP requests. Normal internal network traffic could not access any network resources. The incident management team blocked all incoming ICMP packets, stopping all non-critical network services, and restoring critical network services. This effected the internal network for 2 hours until it was resolved.

Upon investigation, the security team found a DDoS ICMP flood attack was initiated in which a flood of ICMP ping requests overwhelmed the network through a firewall that was not configured properly.

### Identify

An external threat actor used a firewall that was not configured properly to initiate a DDoS ICMP flood attack. A flood of incoming ICMP ping packets were initiated from multiple locations to overwhelm our internal network services. Normal internal network access was disrupted for 2 hours.

### Protect

The network security team has implemented the following:

- A new firewall rule to limit the rate of incoming ICMP packets.
- Source IP verification on the firewall to check for spoofed IP addresses on incoming ICMP packets.
- Network monitoring software to detect abnormal traffic patterns.
- An IDS/IPS system to filter ICMP packets based on suspicious characteristics.

### Detect

The Cyber security team will monitor the network activity using the monitoring software and IDS/IPS system.

### Respond

The incident management team responded quickly to the event and was able to restore network services after 2 hours. With the monitoring software we will be equipped to catch future attacks sooner. With the IDS/IPS system the cybersecurity team will be able to prevent some ICMP packets from effecting the network.

### Recover

After 2 hours the network server access was restored. Monitoring the network will help to catch incidents sooner and the IDS/IPS system will stop some ICMP packets that are suspicious in character. Blocking incoming ICMP packets stops non-critical network services while restoring critical network services. The monitoring will reduce the network access down time.
