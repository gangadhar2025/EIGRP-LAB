# EIGRP Lab with DHCP Server and Relay Agent

This repository contains the topology and configuration files for an **EIGRP Lab with DHCP Server and Relay Agent** setup. The lab demonstrates the integration of EIGRP routing, DHCP relay functionality, and server connectivity, designed and tested in GNS3.

## Topology Overview

![EIGRP Lab Topology](topology.png)

### Components:
1. **Routers**:  
   - R1 (10.100.101.1 / 10.100.12.1)
   - R2 (10.100.102.1 / 10.100.12.2 / 10.100.23.2)
   - R3 (10.100.103.1 / 10.100.23.3)
   
2. **Switches**:
   - Switch1 (Department1)
   - Switch2 (Department2)
   - Switch3 (Server Network)

3. **Hosts**:
   - **Department1 (Subnet: 10.100.101.0/24)**:
     - PC1, PC2, PC3
   - **Department2 (Subnet: 10.100.102.0/24)**:
     - PC4, PC5, PC6
   - **Server Network (Subnet: 10.100.103.0/24)**:
     - DHCP Server: 10.100.103.2
     - DNS Server: 10.100.103.3
     - HTTP Server: 10.100.103.4

4. **Routing Protocol**:
   - EIGRP (Autonomous System: 1) is configured between the routers for dynamic routing.

5. **DHCP Relay Agent**:
   - Configured on R1 and R2 to relay DHCP requests from Department1 and Department2 to the DHCP server in the Server Network.

---

## Key Features
- **Dynamic Routing**: Configured EIGRP to propagate routes across the network.
- **DHCP Relay**: Ensures devices in Department1 and Department2 receive IP addresses from a central DHCP server.
- **DNS and HTTP Server Connectivity**: Verified seamless communication between clients and the DNS/HTTP servers.
- **GNS3 Simulation**: Entire lab was created, configured, and tested in GNS3.

---

## IP Addressing
| **Device**        | **Interface**       | **IP Address**       |
|--------------------|---------------------|-----------------------|
| Router1 (R1)      | G0/0                | 10.100.12.1          |
|                    | E4/0                | 10.100.101.1         |
| Router2 (R2)      | G0/0                | 10.100.12.2          |
|                    | G1/0                | 10.100.23.2          |
|                    | E4/0                | 10.100.102.1         |
| Router3 (R3)      | G1/0                | 10.100.23.3          |
|                    | E4/0                | 10.100.103.1         |
| DHCP Server        | N/A                 | 10.100.103.2         |
| DNS Server         | N/A                 | 10.100.103.3         |
| HTTP Server        | N/A                 | 10.100.103.4         |

---

## Configuration Files
Configuration files for the routers, switches, and servers are included in this repository.

- **Router Configurations**:
  - `R1_config.txt`
  - `R2_config.txt`
  - `R3_config.txt`

- **DHCP Server Configuration**:
  - `DHCP_Server_config.txt`

---

## How to Use
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/EIGRP-DHCP-Lab.git


Open the topology in GNS3 and import the configurations into the respective devices.
Start all devices and test connectivity between different nodes.
Verify:

    DHCP leases for PCs in Department1 and Department2.
    Connectivity to DNS and HTTP servers.
