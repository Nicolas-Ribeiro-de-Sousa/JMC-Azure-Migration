# JMC-Azure-Migration
**Cloud Migration - Maputo Retail Business**

From a single desktop to a resilient Azure Infrastructure


## Context

JMC is a small retail company based in Maputo, Mozambique for the past 17 years selling office supplies, consumables and it equipment. It has 11 workers and one physical location.
The business has been running it's entire operation: Invoicing, quotations, inventory and accounts receivable (costumer credit and outstanding debt tracking) - off a single HP desktop sitting in the management room, no redundancy, no backup with any option to work from home or outside of the office.


## Current infrastructure

Network
- Switch: TP-LINK TL-SF1024D (24-port, unmanaged)
- ISP: TV Cabo Mozambique
- Router: Huawei Echolife HG8247H (ISP issued ONT)
- Default gateway: 192.168.100.1
- Subnet: 192.168.100.0/24; 255.255.255.255

Management Room - Main server
- HP desktop: i7-10700; 16GB RAM; 512GB SSD;
- OS: Windows server 2022 standard 21H2 (64-bit)
- ERP: Secin/W&W system
- Database: Cachesys (Intersystems)
- IP: 192.168.100.3
- Backup: None - all data is saved on the desktop computer

Front Store - Sales
- PC-A: i7-8700; 8GB RAM; 512GB SSD; Win 11;
  IP: 192.168.100.7 | 255.255.255.255
- PC-B: i5-10500; 8GB RAM; 512GB SSD; win 11;
  IP: 192.168.100.5 | 255.255.255.255
- Email: Both sales email
- Both are connected to the server by an fixed IP

Administration Room
- PC-C (admin): i5-10500; 8GB RAM; 240GB SDD; win 11
  IP: 192.168.100.6 | 255.255.255.255
  Email: Administration
  
- PC-D (HR): i5-10500; 8GB RAM; 240GB SDD; win 11
  IP: 192.168.100.20 | 255.255.255.255
  Email: HR
  
Both PC's are connected to the switch but are not connected to the server. They operate independently

Warehouse
- PC-E: i5-10500; 8GB RAM; 240GB SDD; win 11

  No IP: Faulty cable



## Problems Identified

**1. No backup strategy**
No backup exists on the discs of the server and workstation. A single hardware failure means permanent, unrecoverable loss of all business data - invoices, quotations, clients debts and inventory history

**2. No remote access**
There is no way to access company system from outside the office. The manager cannot work while travelling. Sales staff cannot send quotes remotely. No one can respond to a system issue without being physically present.

**3. Single point of failure**
The entire operation depends on one consumer-grade HP desktop. It runs the ERP, the database, and acts as the file server simultaneously. If that machine fails — power surge, hardware fault, OS corruption — everything stops. No continuity plan exists.

**4. Outdated ERP**
The Sercin/W&W system running on CacheSys is not cloud-compatible, has no modern API integration capability, and presents a long-term vendor support risk. It is not suitable for a growing business.

**5. Warehouse network disconnected**
The warehouse PC has been offline due to a cable fault. Inventory is not tracked in real time. Stock discrepancies between the warehouse and the front store cannot be detected.

**6. ISP router incompatible with Azure VPN**
The Huawei EchoLife HG8247H issued by Tv Cabo does not appear on the Azure validated VPN device list and only supports PPTP — a deprecated protocol insufficient for Azure site-to-site VPN.



## Status
Infrastructure assessement
✅ Complete

Problems Identified 
✅ Complete

Proposed Solution
In progress - updating as AZ-104 study advances


*Built as a portfolio project during AZ-104 study.*  
*Based on a real business assessment conducted in Maputo, Mozambique.*


## Author
**Nicolas Ribeiro De Sousa**  
[LinkedIn](https://www.linkedin.com/in/nicolas-ribeiro-de-sousa-094653121)  
Maputo, Mozambique
