# 🌐 NetPractice - 42 Cursus Project

A comprehensive networking fundamentals project from 42 School that teaches IP addressing, subnetting, routing, and network configuration through interactive practical exercises.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Learning Objectives](#learning-objectives)
- [Topics Covered](#topics-covered)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [How to Use](#how-to-use)
- [Key Concepts](#key-concepts)
- [Examples & Solutions](#examples--solutions)
- [Tips for Success](#tips-for-success)
- [Resources](#resources)

---

## 📖 Overview

**NetPractice** is an interactive networking exercise platform that helps you master the fundamentals of computer networking. The project focuses on understanding and configuring IP networks, subnetting, and routing protocols. Rather than traditional code, you'll solve network topology puzzles by correctly assigning IP addresses and routing tables.

This project is designed to:
- Build strong networking foundations
- Develop problem-solving skills in network design
- Prepare you for real-world network administration tasks
- Complement your understanding of the OSI model and TCP/IP stack

---

## 🎯 Learning Objectives

After completing NetPractice, you will be able to:

- ✅ Understand IPv4 addressing and subnetting
- ✅ Calculate network addresses, broadcast addresses, and host ranges
- ✅ Design and configure networks with appropriate CIDR notation
- ✅ Configure static routing in network topologies
- ✅ Troubleshoot connectivity issues using logical analysis
- ✅ Work with network masks and determine host bits
- ✅ Configure interfaces, routes, and network devices
- ✅ Apply best practices in network design

---

## 📚 Topics Covered

### 1. **IPv4 Addressing Basics**
   - IP address structure (4 octets)
   - Decimal to binary conversion
   - Classful vs Classless addressing (CIDR)
   - Public vs Private IP ranges

### 2. **Subnetting & Network Masks**
   - Subnet masks and CIDR notation (/8, /16, /24, /30, etc.)
   - Network address calculation
   - Broadcast address identification
   - Host range determination
   - Subnet splitting and merging

### 3. **Routing**
   - Static routing configuration
   - Route tables and routing decisions
   - Default routes and gateways
   - Routing between multiple networks

### 4. **Network Interfaces**
   - Interface configuration
   - Multiple addresses on single interfaces
   - Link-local addressing

### 5. **Network Topology Design**
   - LAN (Local Area Network) design
   - Connecting multiple networks
   - DMZ (Demilitarized Zone) concepts
   - Network segmentation

---

## 🚀 Getting Started

### Prerequisites
- Access to the official NetPractice platform (usually at your 42 school)
- Basic understanding of how computers communicate
- Patience and logical thinking skills
- No programming required!

### How to Access

1. **Log into your 42 school portal** or the dedicated NetPractice platform
2. **Start with Level 1** - Begin with introductory exercises
3. **Progress sequentially** - Each level builds on previous knowledge
4. **Solve at your own pace** - There's no time limit for individual exercises

---

## 💻 How to Use

### Solving Exercises

Each exercise presents a network topology where you must configure:

1. **IP Addresses** for network interfaces
   - Assign appropriate IPs to each interface
   - Ensure devices can communicate
   - Follow subnet requirements

2. **Network Masks** (Subnet Masks)
   - Specify how many bits are for the network
   - Keep consistent across communicating devices
   - Use appropriate CIDR notation

3. **Routes** (on routers)
   - Define how packets should be forwarded
   - Specify destination networks
   - Set next-hop gateways
   - Use appropriate metrics if required

### Validation

- Click "Check" to validate your solution
- The system will tell you if it's correct
- If incorrect, review the error hints and recalculate

---

## 🧠 Key Concepts

### Binary & Decimal Conversion
```
Example: Convert 192.168.1.0 to binary
192 = 11000000
168 = 10101000
1   = 00000001
0   = 00000000
Result: 11000000.10101000.00000001.00000000
```

### Subnet Mask Notation
```
/8   = 255.0.0.0           (Network: 1 octet, Host: 3 octets)
/16  = 255.255.0.0         (Network: 2 octets, Host: 2 octets)
/24  = 255.255.255.0       (Network: 3 octets, Host: 1 octet)
/30  = 255.255.255.252     (Network: 30 bits, Host: 2 bits = 2 usable hosts)
```

### Network Address Calculation
```
Example: Find network address for 192.168.1.130/25
Binary IP:     11000000.10101000.00000001.10000010
Binary Mask:   11111111.11111111.11111111.10000000
Network Addr:  11000000.10101000.00000001.10000000 = 192.168.1.128
Broadcast:     11000000.10101000.00000001.11111111 = 192.168.1.255
Usable hosts:  192.168.1.129 - 192.168.1.254 (126 hosts)
```

### Routing Decision
```
When Interface D receives a packet destined for 10.0.0.0/8:
- Check routing table for matching network
- Follow the route that has the longest prefix match
- Send to specified next-hop gateway
```

---

## 📝 Examples & Solutions

### Level Example: Simple Network

**Scenario:** Two computers need to communicate on the same network

**Configuration:**

| Device | Interface | IP Address | Subnet Mask |
|--------|-----------|-----------|-------------|
| PC1    | eth0      | 192.168.1.1 | 255.255.255.0 (/24) |
| PC2    | eth0      | 192.168.1.2 | 255.255.255.0 (/24) |

✅ Both are on the same /24 network → They can communicate

### Routing Example

**Scenario:** Connect two networks through a router

**Network 1:** 192.168.1.0/24  
**Network 2:** 10.0.0.0/24  
**Router:** Connected to both networks

**Router Configuration:**

| Destination | Subnet Mask | Gateway/Interface |
|-------------|-------------|------------------|
| 192.168.1.0 | 255.255.255.0 | eth0 (direct) |
| 10.0.0.0 | 255.255.255.0 | eth1 (direct) |

---

## 💡 Tips for Success

### 1. **Understand Binary First**
   - Master binary-to-decimal conversion
   - Use online calculators initially, then practice manually
   - Understand bit positions and their values

### 2. **Visualize the Network**
   - Draw the topology on paper
   - Mark each network segment
   - Trace packet paths from source to destination

### 3. **Use Subnetting Tools Wisely**
   - Online calculators can verify your work
   - Use them to learn, not replace understanding
   - Eventually, you should calculate manually

### 4. **Check Common Mistakes**
   - ❌ Assigning network or broadcast address to a host
   - ❌ Using mismatched subnet masks on the same network
   - ❌ Forgetting routes for intermediate networks
   - ❌ Breaking the host bits rule (all 0s or all 1s are reserved)

### 5. **Work Methodically**
   - Read the exercise description carefully
   - Identify all networks involved
   - Work device by device
   - Verify each configuration logically

### 6. **Test Connectivity**
   - After each configuration, check: Can A reach B?
   - Follow the routing logic step by step
   - Ensure bidirectional communication when needed

---

## 📖 Resources

### Learning Materials
- **Official 42 Subject PDF** (`en.subject.pdf`) - Read carefully!
- **OSI Model** - Understand layers 2-4 (Data Link, Network, Transport)
- **TCP/IP Stack** - How internet protocols work together

### Online Tools & Calculators
- **Subnet Calculator:** ipcalc.com, subnetting.net
- **Binary Converter:** browserling.com/tools/bin-to-dec
- **Network Visualizers:** lucidchart.com, draw.io

### Recommended Study Topics
1. IPv4 address structure and classes
2. CIDR notation and variable-length subnet masking (VLSM)
3. Default route and longest prefix matching
4. ARP (Address Resolution Protocol) basics
5. ICMP and ping/traceroute concepts

### Books & References
- "*TCP/IP Illustrated*" by W. Richard Stevens
- "*Networking Basics*" CompTIA Network+ Study Guide
- Cisco Networking Academy free courses

---

## ✅ Completion Checklist

- [ ] Read and understand the official subject PDF
- [ ] Master binary/decimal conversion
- [ ] Complete all levels (1-10 or as provided)
- [ ] Solve each level without external solutions
- [ ] Understand **why** each solution works
- [ ] Help others understand the concepts
- [ ] Reflect on lessons learned

---

## 🤝 Contributing

If you find issues with this README or want to add helpful resources:
1. Create a new branch
2. Make your improvements
3. Submit a pull request

---

## 📌 Notes

- **Time Investment:** Expect 20-40 hours total
- **Difficulty Curve:** Starts easy, gets progressively harder
- **Persistence is Key:** Don't rush—take time to understand
- **Replicability:** You should be able to recreate solutions without notes

---

## 🎓 42 School Context

This project is part of the 42 Cursus common core. It serves as a foundation for understanding:
- System administration
- Network security
- Cloud infrastructure
- DevOps practices
- Any IT career path

---

## ⚠️ Important Reminders

- 🚫 No copy-paste solutions from the internet
- 📝 Document your learning process
- 🔍 Verify your understanding, not just the answers
- 💬 Discuss concepts with peers (but solve individually)
- 🎯 The goal is learning, not just completion

---

**Last Updated:** March 2026 
