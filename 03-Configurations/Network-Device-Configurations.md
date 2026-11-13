Network Device Configurations

This document shows the configurations of the network devices.

1. Router R1

The router connects the four departments.

Router Configuration

The router uses subinterfaces for inter-VLAN routing.

enable
configure terminal

interface gigabitEthernet 0/0
no shutdown

interface gigabitEthernet 0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.128

interface gigabitEthernet 0/0.20
encapsulation dot1Q 20
ip address 192.168.10.129 255.255.255.192

interface gigabitEthernet 0/0.30
encapsulation dot1Q 30
ip address 192.168.10.193 255.255.255.224

interface gigabitEthernet 0/0.40
encapsulation dot1Q 40
ip address 192.168.10.225 255.255.255.240

end
write memory

Router Verification

Use this command to check the router interfaces:

show ip interface brief

The four subinterfaces must show up/up.

⸻

2. VLAN Configuration

We created four VLANs for the four departments.

VLAN ID	Department
10	ADMINISTRATION
20	INFORMATIQUE
30	COMPTABILITE
40	DIRECTION

Each department uses its own VLAN.

⸻

3. Trunk Configuration

Trunk ports carry traffic from different VLANs.

Central Switch

Switch	Trunk Ports
SW-CENTRAL	Fa0/1 to Fa0/5

Department Switches

Switch	Trunk Port
SW-ADMIN	Fa0/1
SW-IT	Fa0/1
SW-COMPTA	Fa0/1
SW-DIRECTION	Fa0/1

The trunk links connect the central switch to the department switches.

⸻

4. PC IP Addressing

Each PC has an IP address, a subnet mask and a default gateway.

PC	IP Address	Subnet Mask	Default Gateway
PC0	192.168.10.2	255.255.255.128	192.168.10.1
PC1	192.168.10.130	255.255.255.192	192.168.10.129
PC2	192.168.10.194	255.255.255.224	192.168.10.193
PC3	192.168.10.226	255.255.255.240	192.168.10.225

⸻

5. Network Result

The router connects all four VLANs.

The PCs can communicate with each other using inter-VLAN routing.

The ping tests were successful between the PCs.

The network is working correctly.
