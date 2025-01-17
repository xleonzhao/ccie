- [protocol numbers](#protocol-numbers)
- [addresses](#addresses)
- [Misc.](#misc)

# protocol numbers

| Protocol | Number |
|:--|:--|
| EIGRP | 88
| OSPF | 89
| IGMPv2 | 2
| PIM | 103
| IPSEC AH | 51
| IPSEC ESP | 50
| GRE | 47
| PAgP | 0x0104

# addresses

| Group | Address |
|:--|:--|
| OSPFv2 AllSPFRouters | 224.0.0.5 01:00:5E:00:00:05
| OSPFv2 AllDRouters | 224.0.0.6 01:00:5E:00:00:06
| OSPFv3 AllSPFRouters | FF02::05: | 
| OSPFv3 AllDRouters | FF02::06: |
| All PIM routers | 224.0.0.13 |
| Auto-RP/Cisco-RP-announce | 224.0.1.39 |
| Auto-RP/Cisco-RP-Discovery | 224.0.1.40 |
| VRRP | 224.0.0.18 
| PAgP | 0100:0CCC:CCCC |
| LACP | 0180:C200:0002 |

# Misc.

* STP 
  * root bridge election:
    * the **lowest priority** and then the **lowest MAC** address
* ACL
  * numbered ACL: 1–99 and 1300–1999
  * numbered extended ACL: 100-199 and 2000-2699
* HSRP: 
  * CK: higher priority wins
* Routing
  * lower AD wins
    * 0: directly connected routes
* Metric calculation
  * STP
    * ref. bw (short mode): 20Gbps
    * ref. bw (long mode): 20Tbps
    ![](img/2024-09-19-09-41-37.png)
  * OSPF
    * ref. bw: 100Mbps
    ![](img/2024-10-17-11-54-49.png)
  * EIGRP
    * ref. bw: 10Gbps in Kbps
    ![](img/2024-10-16-11-06-11.png)

* SD-Access Arch.

![](img/2024-11-18-15-27-27.png)
![](img/2024-11-21-11-26-34.png)

* SD-WAN Arch.

![](img/2024-11-22-14-54-07.png)

* ETSI/NFV Arch.

![](img/2024-11-12-10-23-54.png)

|Factor|Puppet|Chef|Ansible|SaltStack
|:--|:--|:--|:--|:--
|Architecture|Puppet servers and puppet agents|Chef server and Chef clients|Control station and remote hosts|Salt master and minions
|Language|Puppet DSL|Ruby DSL|YAML|YAML
|Terminology|Modules and manifests|Cookbooks and recipes|Playbooks and plays|Pillars and grains
|Support for large-scale deployments|Yes|Yes|Yes|Yes
|Agentless version|Puppet Bolt|N/A|Yes|Salt SSH

* EtherChannel successful condition
  * on/on
  * active/passive
  * active/active
  * desirable/auto
  * desirable/desirable.

* DTP port mode

| **Switch A Mode**        | **Switch B Mode**      | **Resulting Port Mode** |
|--------------------------|------------------------|--------------------------|
| **Dynamic Auto**         | Dynamic Auto           | Access 
| **Dynamic Auto**         | Dynamic Desirable      | Trunk  
| **Dynamic Desirable**    | Dynamic Desirable      | Trunk  
| **Dynamic Desirable**    | Dynamic Auto           | Trunk  
| **Dynamic Desirable**    | Trunk                  | Trunk  
| **Dynamic Auto**         | Trunk                  | Trunk  

* BGP AS Path flags
  * `i`: route configured with bgp `network` statement
  * `?`: route learned from another routing protocol like OSPF
  * `e`: route learned from EGP, rarely used

* EIGRP route state
  * passive (P): route stable
  * active (A): route is **computing a new path**