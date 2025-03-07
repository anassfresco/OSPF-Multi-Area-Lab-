![OSPF Topology](https://github.com/anassfresco/OSPF-Multi-Area-Lab-/blob/main/LAB_OSPF.png?raw=true)

## Overview
This lab simulates an **enterprise-grade OSPF (Open Shortest Path First) multi-area network**, integrating various routing concepts such as redundancy, security, and optimized traffic flow. The topology is designed to reflect real-world scenarios with multiple OSPF areas, VPN tunneling, and firewall integration.

## Network Topology
The network consists of multiple OSPF areas:
- **Area 0 (Backbone)**
- **Area 1 (Stub)**
- **Area 2 (NSSA)**
- **Area 3 (Standard OSPF area)**
- **Area 4 (Totally Stub)**
- **Area 5 (Totally NSSA)**

## Key Features ✅
- **OSPF Multi-Area Implementation**: Efficient routing and LSA control.
- **GRE over IPSEC**: Secure communication between remote sites.
- **HSRP (Hot Standby Router Protocol)**: Ensuring network redundancy.
- **Virtual Links**: Connecting non-contiguous OSPF areas to the backbone.
- **Static Routing with Fortinet Firewall**: Interfacing with external networks.
- **PPP Links**: Simulating WAN connections.

## Lab Components 🛠️
- **Routers** configured with OSPF, HSRP, GRE over IPSEC, and static routes.
- **Fortinet Firewall** for secure network access and static routing.
- **Multiple Network Segments** to simulate an enterprise environment.

## Configuration Examples ⚙️
### OSPF Configuration Example:
```cisco
router ospf 1
 router-id 1.1.1.1
 network 10.0.0.0 0.0.255.255 area 0
 network 10.1.0.0 0.0.0.255 area 1
 network 10.2.0.0 0.0.0.255 area 2 nssa
```

### GRE over IPSEC Example:
```cisco
interface Tunnel0
 ip address 10.0.13.1 255.255.255.0
 tunnel source GigabitEthernet0/1
 tunnel destination 192.168.1.2
 tunnel mode gre ip
```

## How to Use 📌
1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/ospf-lab.git
   ```
2. Load the topology in **GNS3 / EVE-NG**.
3. Configure routers and firewalls based on the provided configurations.
4. Test connectivity and OSPF routing tables using:
   ```cisco
   show ip route ospf
   show ip ospf neighbor
   ```

## Lessons Learned 📖
- **OSPF area design impacts performance and convergence time.**
- **Using GRE over IPSEC ensures secure site-to-site communication.**
- **Virtual links help connect isolated OSPF areas to the backbone.**

## Contributing 🤝
Feel free to submit **pull requests** or **issues** to improve this lab setup. Let's make this an even better learning resource!

## License 📜
This project is open-source and available under the **MIT License**.

---

### 📩 Connect with Me
If you have any questions or suggestions, feel free to reach out on **LinkedIn** or open an **issue** in this repository.

#Networking #OSPF #CyberSecurity #Routing #GNS3 #EVE-NG #NetworkEngineering
