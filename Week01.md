# Week 01 Tutorial – Introduction to GNS3

**Unit:** COIT20261 Network Services and Automation  
**Student ID:** 12320906  

---

## Section A – Unit and Software Setup

In Week 01, I became familiar with the requirements of COIT20261 Network
Services and Automation and the software that will be used throughout the
unit.

The main software and platforms used for the practical activities are:

- GNS3 for creating and testing network topologies
- VirtualBox for virtualisation
- GitHub for maintaining the weekly portfolio and practical evidence
- Markdown for documenting practical activities

I also created my GitHub repository for storing the weekly tutorial work,
screenshots and portfolio documentation.

---

# Section B – Task 1: Introduction to GNS3 Basics

## Aim

The aim of this activity was to become familiar with the basic functions of
GNS3.

The activity included creating a GNS3 project, adding a Linux Host,
configuring an IPv4 address, starting the node, opening its console and
checking the IP address from Linux.

---

## Step 1 – Create the GNS3 Project

I opened GNS3 and created a project for the introductory networking
activity.

A single Linux Host node named **Host1** was added to the GNS3 workspace.

The following screenshot shows the Linux Host that was created in GNS3.

![GNS3 Linux Host](./Images/Screenshot%202026-07-22%20144543.png) 

**Observation:**  
This activity introduced me to the GNS3 workspace and showed me how network
devices can be added and positioned inside a project.

---

## Step 2 – Configure the Linux Host

The next part of the activity involved configuring a static IPv4 address
for the Linux Host.

The network configuration is performed on the `eth0` interface using the
Linux network interfaces configuration.

The general configuration format used in the tutorial was:

    auto eth0
    iface eth0 inet static
        address <IP address>
        netmask <network mask>

For this simple topology, a default gateway was not required because only
one Linux Host was being configured.

The tutorial also introduced the option of disabling IP forwarding on a
normal Linux host using:

    up sysctl net.ipv4.ip_forward=0

This ensures that the Linux Host behaves as an end host rather than acting
as a router.

---

## Step 3 – Start the Linux Host

After configuring the interface, I started the Linux Host in GNS3.

Starting the node allows the Linux operating system to load the network
configuration assigned to the interface.

I then opened the web console for the Linux Host.

---

## Step 4 – Check the IP Address

The IP address of a Linux Host can be checked using:

    ip address show

A shorter command that can also display interface information is:

    ip addr

The output displays the available interfaces, including `lo` for the
loopback interface and `eth0` for the Ethernet interface.

The IPv4 address assigned to `eth0` can then be identified from the
`inet` entry.

### Supporting Evidence from Later Practical Work

The original Week 01 console screenshot was not retained. However, the
following evidence from later practical work demonstrates the same Linux
`ip addr` command and interface verification procedure introduced during
Week 01.

![Linux Host IP Address Verification](./Images/Screenshot%202026-08-19%20133149.png)

The screenshot demonstrates the use of the Linux console to inspect the
network interface and confirm the IPv4 address assigned to `eth0`.

---

## Commands Practised

The main Linux networking command practised in this activity was:

    ip address show

or:

    ip addr

This command is useful for checking the IP addresses and current state of
network interfaces.

---

## What I Learned

From this tutorial, I learned the basic process of creating and working with
a GNS3 project.

I learned how to:

1. Create a project in GNS3.
2. Add a Linux Host to the GNS3 workspace.
3. Configure a static IPv4 address on the `eth0` interface.
4. Start and stop a node.
5. Open the Linux console.
6. Use `ip address show` or `ip addr` to inspect network interfaces.
7. Record practical work and screenshots in GitHub using Markdown.

This introductory activity helped me understand the basic GNS3 environment
before working with larger network topologies in later tutorials.

---

## Conclusion

Week 01 provided an introduction to GNS3, Linux network configuration and
GitHub portfolio documentation.

The practical activity demonstrated how a Linux Host can be created in
GNS3, configured with a static IPv4 address and checked using Linux
networking commands.

The knowledge gained from this introductory tutorial provides the
foundation for later activities involving multiple hosts, switches,
routers, routing and network services.
