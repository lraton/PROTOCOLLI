# Company Network Infrastructure Project  
**Computer Networks – Protocols**  
It was created for the *Protocolli* project (2023/2024) by **Filippo Notari & Francesco Brizi**. 

**Authors:**  
- Filippo Notari (ID 330606)  
- Francesco Brizi (ID 350038)  

---

## Project Overview

The company has requested the design and implementation of a complete internal network to connect all departments and offices securely and efficiently.  

The final network topology includes 5 buildings (A–E), each representing different departments. The infrastructure includes internal routing, DMZ, firewall protection, DNS, mail, proxy, and web servers, as well as a secure Internet connection.  

---

## Project Goals

- Design a **physical and logical network topology**
- Subdivide the network into appropriate **subnets**
- Configure **routers**, **switches**, **servers**, and **hosts**
- Implement **routing tables** for all internal and border routers
- Set up **DNS** and **Email servers**
- Configure **firewalls** to protect internal services and infrastructure
- Implement **network monitoring** for enhanced security
- Provide **special protection for the backup server**

---

## Network Layout

![Network Topology](schema rete pt.png)

- **Building A** – 192.168.1.0/24 (100 users, Wi-Fi enabled)
- **Building B** – 192.168.2.0/24 (100 users)
- **Building C** – 192.168.3.0/24 (100 users)
- **Building D** – 192.168.4.0/24 (100 users)
- **Building E** – 192.168.5.0/24 (100 users)
- **DMZ** – 192.168.6.0/24 (external-facing services)
- **Inter-router subnets** – /30 point-to-point networks (e.g. 192.168.99.0/30)

---

## Services Deployed

| Service           | Quantity | Location            |
|------------------|----------|---------------------|
| DNS Server       | 2        | DMZ, Building D     |
| Mail Server      | 1        | DMZ                 |
| Proxy Server     | 1        | DMZ                 |
| Web Server       | 1        | DMZ                 |
| Backup Server    | 1        | Building D (protected) |

---

## Technologies and Equipment

- Routers and Layer 2 switches
- Ethernet links (100 m max per segment)
- Access Points for wireless coverage in Building A
- Firewalls for DMZ isolation and backup server protection
- Adminer or MySQL for host configuration (where applicable)
- Monitoring tools for SNMP/syslog or packet capture

---

## Configuration Summary

### IP Addressing

Each building is assigned a /24 subnet. All router interconnections use /30 subnets for point-to-point links.

### Routing

All routers are configured with **static routing** for full interconnectivity, including proper gateway settings for Internet access via the DMZ.

### Firewall Rules

- Only specific ports are allowed into the DMZ (e.g., 80, 443, 25)
- DNS queries filtered to allow internal resolution only
- Backup server is isolated behind its own router with limited access

### Servers

- DNS: Internal resolution + caching, external on separate instance
- Mail: SMTP/IMAP with antivirus and antispam
- Web: Apache server with static and dynamic content
- Proxy: Transparent for user browsing control

---

## Monitoring and Security

The network is monitored using:

- **SNMP** traps from routers and servers
- **Syslog** forwarding to a centralized log server
- Periodic backup verification and redundancy checks

---

## How to Open the Project

The project simulation file is provided in `.pkt` format (Cisco Packet Tracer).  

1. Open the `.pkt` file with Cisco Packet Tracer (version 8.x or later).
2. Start the simulation.
3. Test connectivity between buildings and services.
4. Examine routing tables, DNS resolution, and firewall behaviors.

---

## Deliverables

- Network topology diagram
- Full `.pkt` simulation file
- Configuration of all routers, servers, and PCs
- Security plan and firewall rules
- Monitoring setup
- Cost estimate for hardware and cabling
- Project documentation (this README)

---

## License

This project is for educational purposes only and part of the "Computer Networks: Protocols" course at the University of Perugia.

