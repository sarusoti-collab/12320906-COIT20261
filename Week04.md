# Week 04 Tutorial – HTTP Clients

**Unit:** COIT20261 Network Services and Automation  
**Student ID:** 12320906

This report documents the practical activities completed for the Week 04 tutorial. The tutorial focused on accessing an HTTP server using both a graphical HTTP client and command-line HTTP clients in a GNS3 network.

---

# Task 1: HTTP Client with GUI

## Aim

The aim of this task was to use a GUI web browser as an HTTP client to access a website and explore HTTP communication across a routed network.

---

## Step 1 – Create the GNS3 Network

A GNS3 network was created using three subnets: A, B and C.

The network contains:

- Host1 / Firefox Host
- Switch1
- Router1
- Switch2
- Router2
- Switch3
- Server1 / Linux Server

Router1 connects subnet A and subnet B, while Router2 connects subnet B and subnet C.

The network topology used for the practical is shown below.

![GNS3 Network Topology](./Images/Screenshot%202026-08-12%20141335.png)

---

## Step 2 – Configure Router1

Router1 was configured with static IPv4 addresses so that it could connect subnet A and subnet B.

The interface configuration was checked from the Router1 console.

![Router1 Interface Configuration](./Images/Screenshot%202026-08-19%20132630.png)

The Router1 configuration was checked again after applying the required settings.

![Router1 Configuration Verification](./Images/Screenshot%202026-08-19%20132704.png)

---

## Step 3 – Check Router1 Routing Table

The `ip route` command was used to check the routing information on Router1.

![Router1 Routing Table](./Images/Screenshot%202026-08-19%20133149.png)

The routing table showed the networks directly connected to Router1.

---

## Step 4 – Configure Router2

Router2 was configured to provide connectivity between subnet B and subnet C.

The Router2 routing information was checked using the `ip route` command.

![Router2 Routing Table](./Images/Screenshot%202026-08-19%20133158.png)

The interface configuration was then checked using `ip addr`.

![Router2 Interface Configuration](./Images/Screenshot%202026-08-19%20133246.png)

This verified the IPv4 addresses assigned to the Router2 interfaces.

---

## Step 5 – Check Host and Gateway Configuration

The host configuration was checked to make sure that the client was connected to the correct subnet.

![Host IP Configuration](./Images/Screenshot%202026-08-19%20133343.png)

The routing/default gateway information was also checked.

![Host Routing Configuration](./Images/Screenshot%202026-08-19%20133358.png)

Correct default gateway configuration is necessary because the client and HTTP server are located on different subnets.

---

## Step 6 – Test Router Connectivity

A ping test was performed to verify connectivity between Router1 and Router2.

![Successful Router Ping](./Images/Screenshot%202026-08-19%20133610.png)

The successful result showed that packets could travel between the two routers.

The test returned replies with no packet loss, confirming successful communication across subnet B.

---

## Step 7 – Additional Network Verification

The network configuration was checked further before HTTP communication was attempted.

![Network Configuration Verification](./Images/Screenshot%202026-08-19%20133702.png)

This helped verify that the required interfaces and network settings were active.

---

## Step 8 – Troubleshoot Connectivity

During the practical, a connectivity problem was encountered.

A ping test returned a `Destination Host Unreachable` message.

![Connectivity Troubleshooting](./Images/Screenshot%202026-08-19%20134503.png)

This indicated that the destination could not initially be reached.

The network configuration, IP addresses, gateways and routing information were checked as part of troubleshooting.

---

## Step 9 – Configure the HTTP Client

The HTTP client configuration was checked before accessing the server.

![HTTP Client Configuration](./Images/Screenshot%202026-08-19%20140147-task%202.png)

This ensured that the client had an appropriate IPv4 configuration for the network.

---

## Step 10 – Configure the HTTP Server

The Linux Server was configured on the server-side network.

The server interface configuration was checked using the Linux networking commands.

![Linux Server Configuration](./Images/Screenshot%202026-08-19%20144057.png)

The Linux Server acts as the HTTP server in this practical.

---

## Step 11 – Verify the Network Before HTTP Testing

The completed network configuration was checked before testing HTTP communication.

![Network Before HTTP Testing](./Images/Screenshot%202026-08-19%20144119.png)

This ensured that the required devices were running and connected.

---

## Step 12 – Use the Graphical HTTP Client

The graphical environment for Host1 was opened so that the HTTP client could be accessed.

![Graphical HTTP Client](./Images/Screenshot%202026-08-19%20144216.png)

Firefox/noVNC provides the graphical interface required for the GUI HTTP-client part of the tutorial.

---

# Task 2: HTTP Client with Command Line Interface

## Aim

The aim of Task 2 was to use command-line HTTP clients such as `wget` and `curl` to access the web server.

Command-line HTTP clients are useful for testing and automation because they do not require a complete graphical web browser.

---

## Step 1 – Prepare the CLI HTTP Client

The GUI HTTP-client project was used as the basis for Task 2.

The Firefox Host was replaced with a Linux Host, while the routed network structure was retained.

The Linux Host was configured for communication with the HTTP server.

![Linux Host Configuration](./Images/Screenshot%202026-08-19%20140147-task%202.png)

---

## Step 2 – Verify Router1

Router1 was checked to ensure that communication from the client-side network could be forwarded toward the server-side network.

![Router1 Configuration](./Images/Screenshot%202026-08-19%20132630.png)

The routing table was also checked.

![Router1 Routing Table](./Images/Screenshot%202026-08-19%20133149.png)

---

## Step 3 – Verify Router2

Router2 was checked to ensure connectivity between subnet B and the server-side subnet.

![Router2 Routing Table](./Images/Screenshot%202026-08-19%20133158.png)

The Router2 interface configuration was also verified.

![Router2 Interface Configuration](./Images/Screenshot%202026-08-19%20133246.png)

---

## Step 4 – Verify Connectivity

Before accessing the web server using command-line HTTP tools, connectivity was tested.

![Connectivity Test](./Images/Screenshot%202026-08-19%20133610.png)

The successful ping confirmed that network communication was functioning between the tested devices.

---

## Step 5 – Check the Linux Server

The HTTP server configuration was verified before performing the HTTP-client tests.

![HTTP Server Configuration](./Images/Screenshot%202026-08-19%20144057.png)

---

## Step 6 – Use wget

The Linux Host was used as a command-line HTTP client.

The tutorial uses `wget` to request a webpage from the Linux Server.

The general form of the command is:

`wget http://<server-ip>/`

`wget` requests the webpage from the HTTP server and normally saves the received page as a local file.

The command-line practical environment is shown below.

![Command Line HTTP Client](./Images/Screenshot%202026-08-19%20144119.png)

---

## Step 7 – Use curl

The Linux Host was also used with `curl` to access the HTTP server.

The general form of the command is:

`curl http://<server-ip>/`

`curl` can request HTTP content and display the returned information directly in the terminal.

![HTTP Client Test](./Images/Screenshot%202026-08-19%20144216.png)

---

# Packet Capture

The Week 04 tutorial also required packet capture on a link in subnet B between Router1 and Router2.

The packet capture allows the HTTP traffic passing between the two routers to be examined and provides evidence of communication across the routed network.

The packet capture files should be retained with the GNS3 project files as part of the practical evidence.

---

# Observations

During this tutorial, I learned how HTTP communication operates across a network containing multiple subnets and routers.

The practical demonstrated that correct IPv4 addressing, default gateways and routing are required before HTTP communication can work successfully.

The `ip addr` command was useful for checking interface addressing, while `ip route` was used to inspect routing information.

The `ping` command was useful for testing and troubleshooting network connectivity. During the practical, an unsuccessful test produced a `Destination Host Unreachable` result. After checking the network configuration, successful communication between the network devices was demonstrated.

The tutorial also demonstrated two different ways of using an HTTP client.

In Task 1, a graphical web browser was used as the HTTP client.

In Task 2, command-line HTTP clients such as `wget` and `curl` were used.

Command-line HTTP clients are useful for network testing and automation because HTTP requests can be performed without the overhead of a complete graphical web browser.

---

# Conclusion

The Week 04 tutorial provided practical experience configuring and testing HTTP client-server communication in GNS3.

The practical involved:

- Creating a three-subnet network
- Configuring Router1 and Router2
- Assigning static IPv4 addresses
- Configuring default gateways
- Checking interface configuration
- Viewing routing tables
- Testing connectivity with `ping`
- Troubleshooting network connectivity
- Using a graphical HTTP client
- Using command-line HTTP clients
- Working with `wget`
- Working with `curl`
- Capturing network packets

Overall, the tutorial demonstrated that HTTP communication depends on correctly configured underlying IP connectivity and routing.
