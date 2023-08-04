---
layout: post
title: Computer Networks
date: 2023-08-02 09:56:00-0400
description: Reviewing my 5th course in OMSCS - Computer Networks
tags: OMSCS
categories: masters-review
related_posts: false
toc:
  sidebar: left
---
In the Summer of 2023, I took the Computer Networks course at OMSCS that provided an in-depth exploration of various aspects of computer networks, ranging from fundamental protocols to cutting-edge technologies. 

## Course Summary

The course commences with a comprehensive overview of Internet architecture and its evolution over time. By tracing the historical development of the Internet, I gained insights into the foundations that have shaped today's interconnected world which lays the groundwork for the subsequent topics in computer networks.

### Protocols

One of the course's strengths lies in its coverage of protocols and algorithms that span across all layers of the Internet protocol stack. The exploration of protocols like TCP (Transmission Control Protocol) and congestion control mechanisms equipped me with a solid understanding of how data transmission and flow control occur within the network. This knowledge forms the basis for effective communication and resource management, fundamental to maintaining a stable network environment.

### Routing and SDN

Intradomain and interdomain routing, along with discussions on peering and network relationships, are pivotal areas covered in the course. Understanding how data is efficiently routed within and between networks helped me comprehend the intricacies of data delivery across the vast expanse of the Internet. 

The course also explores Software Defined Networking (SDN) technologies, providing information on its ability to centralize network control and programmatically manage network resources.

### Network Security and Attacks

Addressing the intersection of network security and computer networks, the course talks about critical issues such as attacks on Internet routing, particularly BGP (Border Gateway Protocol) hijacking. 

This segment underscores the significance of safeguarding the integrity and authenticity of network data, highlighting the challenges posed by malicious actors seeking to exploit vulnerabilities within the network infrastructure.

### Multimedia Applications and the role of CDN

The final part of the course explores multimedia applications and Content Delivery Networks (CDNs). This segment acknowledges the growing significance of multimedia content in today's digital landscape and examines how CDNs optimize content delivery by strategically distributing data across geographically dispersed servers.

One interesting [paper](https://arxiv.org/pdf/1606.05519.pdf) we read was about the OpenConnect framework implemented by Netflix to deliver video content efficiently across the globe.


### Course Projects

*Project 1: Spanning Tree Protocol Implementation*

The first project challenged me to develop a simplified distributed version of the Spanning Tree Protocol. The primary objective of the project is to converge on a single solution that yields a spanning tree, demonstrating the practical application of network convergence principles.

*Project 2: Distributed Bellman-Ford Algorithm for Routing*

The second project tasked me with designing a distributed Bellman-Ford algorithm capable of calculating routing paths within a network.This exploration involves weighted links reflecting business relationships among nodes, providing a practical understanding of Path Vector protocols.

*Project 3: Software Defined Networking (SDN) Firewall Implementation*

The third project delved into the realm of Software Defined Networking (SDN) principles. Through practical engagement with OpenFlow-enabled switches and controllers, I created a configurable firewall. 

The project consists of phases that include familiarization with Mininet and Wireshark, and culminates in the implementation of an SDN-based firewall that blocks traffic based on rule configurations.


*Project 4: Exploring Internet Measurements*

The fourth and final project introduced me to the realm of Internet Measurements, with a focus on large-scale data collection systems and techniques. 
By working with tools like BGPStream and PyBGPStream, I performed BGP data analysis, exploring topics such as characterizing Internet growth, identifying short-lived announcements and withdrawals, and inferring possible DDoS attacks.