# Week 02 Tutorial

This report is a documentation of practical work done for Week 02 tutorial in GNS3. 
This tutorial covers three methods for assigning static IPv4 addresses to Linux hosts, verifying interface addressing and using ping to test connectivity and round trip time (RTT).

## Task 1: Setting Static IP Addresses
Goal: Set up four Linux hosts on one LAN and try out various ways of setting static IP addresses.

### 1 – Create the GNS3 topology
We have created a GNS3 project with 4 Linux hosts (Host1, Host2, Host3 and Host4) and one Ethernet Switch (Switch1). 
The links were added after the nodes were placed around the switch. This satisfies the tutorial requirement of having a LAN with four Linux hosts and one switch.


![GNS3 topology](./Images/2.1.png)
_Figure 1. create the gns3 topology._

## Step 2 – Connect all the Hosts to the Ethernet Switch
The eth0 interface of each Linux host was connected to a different port on Switch1. Once the nodes were started, 
the links turned green, indicating that the interfaces and links were active. If all four hosts are connected 
to the same Layer 2 switch, they are able to communicate directly if they have IPv4 addresses that are in the same subnet.

![GNS3 topology](./Images/2.2.png)
_Figure 2. connect all hosts to the ethernet switch._

## Step 3 – Check an assigned address with the ip address show
On Host1 we used the command `ip a` (short for `ip address show`) to see its interfaces.
The screenshot shows eth0 with the IPv4 address 10.1.1.1/24. The /24 prefix matches the subnet mask 255.255.255.0. 
The objective of this command is to check that the host has the desired address applied.

![GNS3 topology](./Images/2.3.png)
_Figure 3. verify an assigned address with ip address show._

## Step 4 – Setup a host in the GNS3 Configure Menu
We opened the GNS3 network configuration editor for Host1. The eth0 part is static, and has the fields `address`, `netmask` and optionally `gateway`. This technique modifies the Linux /etc/network/interfaces configuration from the GNS3 graphical interface. Settings entered here are applied when starting the node.

![GNS3 topology](./Images/2.4.png)

## Step 5 – Edit /etc/network/interfaces in the console
nano /etc/network/interfaces Now I opened the file in nano. The static configuration has `auto eth0`, `iface eth0 inet static`, an IPv4 address and netmask 255.255.255.0. This demonstrates the second method of the tutorial, editing the Linux network configuration file directly from the console.

![GNS3 topology](./Images/2.5.png)

