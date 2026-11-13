Device Configurations

1. Router R1

The router connects the four departments.

Router subinterfaces

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

2. VLAN Configuration

We created four VLANs for the four departments.

VLAN ID	Department
10	ADMINISTRATION
20	INFORMATIQUE
30	COMPTABILITE
40	DIRECTION

3. Trunk Configuration

The trunk ports carry traffic from different VLANs.

Central switch

Ports Fa0/1 to Fa0/5 are trunk ports.

Department switches

Port Fa0/1 is the trunk port on each department switch.

4. PC IP Addressing

PC	IP Address	Subnet Mask	Gateway
PC0	192.168.10.2	255.255.255.128	192.168.10.1
PC1	192.168.10.130	255.255.255.192	192.168.10.129
PC2	192.168.10.194	255.255.255.224	192.168.10.193
PC3	192.168.10.226	255.255.255.240	192.168.10.225

5. Network Result

The router connects all four VLANs.

The PCs can communicate with each other using inter-VLAN routing.
