
# Task 1: Simple Application Communications with Netcat

The completed GNS3 practical activities for Week 03 are documented in this report. It adheres to the provided instructional framework, which consists of basic application connection with Netcat, packet capture of ping and Netcat traffic, and transfer of the capture to the host machine.

**Aim:** To test basic application connections between Linux hosts, learn the fundamentals of Netcat (nc).

## Step 1: set up the LAN topology.
The four-host GNS3 LAN that was already in place was utilised. Switch1 is linked to Hosts 1, 2, 3, and 4 via their Ethernet ports. Every link is displayed as active. This enables direct communication between the hosts on a single LAN.

![Netcat](./Images/3.1.png)
_Figure 1. prepare the lan topology_


## Step 2 – Verify IP connectivity
Host1 was verified with `ip a` prior to utilising Netcat, revealing address 10.1.0.1/24 on eth0. Then, using three requests for each location, Host 1 was able to successfully ping 10.1.0.2, 10.1.0.3, and 10.1.0.4. Prior to application-level testing, each test confirmed that the hosts could be reached by returning 3 sent, 3 received, and 0% packet loss.

![Netcat](./Images/3.1.png)


## Step 3 – Start a Netcat listening server
`nc -l -p 12345` was used to create a Netcat listener. The `-p` option indicates the local port, while the `-l` option puts Netcat in listen mode. The provided proof demonstrates that a remote Netcat client's text is accepted by the listener.

![Netcat](./Images/3.1.png)
_Figure 2. verify ip connectivity._

## Step 4 – Connect a Netcat client to the server
Targeting Host1 at IP address 10.1.0.1 and TCP port 12345, the Netcat client was launched on a different host with the command `nc 10.1.0.1 12345`. The screenshots, which include the student ID and name/message content, demonstrate effective two-way text conversation. This demonstrates application-level communication between the two Linux hosts.

![Netcat](./Images/3.1.png)
_Figure 5. start a netcat listening server._

