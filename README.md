# Multi-Floor Corporate Network Infrastructure - Cisco Packet Tracer

![Project Banner](screenshots/image1.png) <!-- Replace with your best topology or banner screenshot -->

## Overview
This project simulates a complete **3-floor corporate building network** for a medium-sized company. Each floor contains multiple departments with dedicated VLANs and subnets supporting hundreds of devices. The network includes:

- 9 departmental subnets (Store, Reception, Logistics, Finance, Sales, HR, IT, Admin)
- 3 WAN point-to-point links
- Inter-VLAN routing via 3 routers
- Layer 2 switching with VLAN segmentation
- Centralized IT department with full remote access to all devices
- Five servers (DNS, Mail, TFTP, FTP, Web) hosted in the IT subnet

The design follows best practices for subnetting, VLAN isolation, and server placement. All configurations were built and tested in **Cisco Packet Tracer**.

## Features
- Precise VLSM subnetting to minimize IP waste
- VLANs for security and broadcast control
- Inter-VLAN routing (Router-on-a-Stick / separate router interfaces)
- Static IP management for all switches and servers
- IPv6 configuration on all servers
- TFTP backup of every device configuration
- Full remote management from IT department
- Scalable design supporting 500+ end devices

## Network Topology
The network consists of 3 routers and 3 multilayer switches connected in a hierarchical design (core-distribution-access).


## IP Addressing Scheme

| Subnet Name | Hosts | Network Address     | Default Gateway     | Subnet Mask     | Broadcast Address   |
|-------------|-------|---------------------|---------------------|-----------------|---------------------|
| Store       | 520   | 172.25.0.0/22       | 172.25.0.1/22       | 255.255.252.0   | 172.25.3.255        |
| Reception   | 380   | 172.25.4.0/23       | 172.25.4.1/23       | 255.255.254.0   | 172.25.5.255        |
| Logistics   | 170   | 172.25.6.0/24       | 172.25.6.1/24       | 255.255.255.0   | 172.25.6.255        |
| Finance     | 150   | 172.25.7.0/24       | 172.25.7.1/24       | 255.255.255.0   | 172.25.7.255        |
| Sales       | 60    | 172.25.8.0/26       | 172.25.8.1/26       | 255.255.255.192 | 172.25.8.63         |
| HR          | 55    | 172.25.8.64/26      | 172.25.8.65/26      | 255.255.255.192 | 172.25.8.127        |
| IT          | 35    | 172.25.8.128/26     | 172.25.8.129/26     | 255.255.255.192 | 172.25.8.191        |
| Admin       | 10    | 172.25.8.192/28     | 172.25.8.193/28     | 255.255.255.240 | 172.25.8.207        |
| WAN1        | -     | 172.25.8.208/30     | -                   | 255.255.255.252 | 172.25.8.211        |
| WAN2        | -     | 172.25.8.212/30     | -                   | 255.255.255.252 | 172.25.8.215        |
| WAN3        | -     | 172.25.8.216/30     | -                   | 255.255.255.252 | 172.25.8.219        |

**Unused range:** `172.25.8.220` – `172.25.255.255`

## Statically Assigned Devices

**Switch Management IPs:**
- Switch 1st (VLAN 10/11/12): Reception, Store, Logistics
- Switch 2nd (VLAN 20/21/22): Finance, HR, Sales
- Switch 3rd (VLAN 30/31): Admin, IT

**Servers (IT Subnet 172.25.8.128/26):**
| Device       | IPv4 Address          | IPv6 Address                  |
|--------------|-----------------------|-------------------------------|
| DNS Server   | 172.25.8.130/26       | 2001:DB8:5678:C::2/64         |
| Mail Server  | 172.25.8.131/26       | 2001:DB8:5678:C::3/64         |
| TFTP Server  | 172.25.8.132/26       | 2001:DB8:5678:C::4/64         |
| FTP Server   | 172.25.8.133/26       | 2001:DB8:5678:C::5/64         |
| Web Server   | 172.25.8.134/26       | 2001:DB8:5678:C::6/64         |

## Configuration Files
All `show running-config` outputs and TFTP backups are included:
- Router 1st, Router 2nd, Router 3rd
- Switch 1st, Switch 2nd, Switch 3rd

Screenshots of every `show run` are in the `screenshots/` folder (`image11.png` – `image24.png`).


## How to Run
1. Download and install **Cisco Packet Tracer** (version 8.0+ recommended)
2. Clone this repository
3. Open `Corporate_Building_Network.pkt`
4. Start the devices (they are already configured)
5. Test connectivity:
   - Ping between departments
   - Access web/mail/FTP servers from any PC
   - Remote management from IT department PCs

## Technologies Used
- Cisco Packet Tracer
- VLANs & Trunking (802.1Q)
- VLSM Subnetting
- Inter-VLAN Routing
- Static Routing
- IPv4 & IPv6
- Server Services (DNS, HTTP, FTP, TFTP, Mail)

## Author
**Mohamad**  
Built in 2024 as part of Data Communications & Computer Networks course.

**Tips for your GitHub repo:**
- Create an `screenshots/` folder and put all your images there (image1.png – image24.png).
- Upload the `.pkt` file (it's the most important).
- If you still have the TFTP backup files, add them in a `Configs/` folder.
- Add a license (MIT is fine) and topics: `cisco-packet-tracer`, `network-design`, `vlan`, `subnetting`, `ccna-project`.

Just copy the description and the entire README above — your project will look professional and portfolio-ready! Let me know if you want a dark-mode version or want me to generate a project banner image for you.
