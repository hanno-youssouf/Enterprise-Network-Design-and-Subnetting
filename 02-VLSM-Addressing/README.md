VLSM and CIDR Addressing

This folder explains how we divide one network into four smaller networks.

Main Network

192.168.10.0/24

Department Networks

Department	Network	Prefix
Administration	192.168.10.0	/25
Informatique	192.168.10.128	/26
Comptabilité	192.168.10.192	/27
Direction	192.168.10.224	/28

Goal

Each department has its own network.

VLSM helps us use IP addresses better.
