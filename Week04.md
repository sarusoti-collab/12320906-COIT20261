# Week 04 Tutorial – HTTP Clients

**Unit:** COIT20261 Network Services and Automation  
**Student ID:** 12320906  

This report documents the practical work completed for the Week 04 tutorial. The tutorial explores HTTP communication using both a graphical web browser and command-line HTTP clients in a GNS3 network.

---

# Task 1: HTTP Client with GUI

## Aim

The aim of this task was to use a GUI web browser as an HTTP client to access a web server and explore HTTP communication across a routed network.

---

## Step 1 – Create the GNS3 Network

A GNS3 network was created with three subnets connected through two routers.

The network contains:

- Host1 – Firefox HTTP client
- Switch1
- Router1
- Switch2
- Router2
- Switch3
- Server1 – HTTP server

The three network segments are:

- Subnet A – Host1, Switch1 and Router1
- Subnet B – Router1, Switch2 and Router2
- Subnet C – Router2, Switch3 and Server1

The completed GNS3 topology is shown below.

![GNS3 Network Topology](./Images/Screenshot%202026-08-19%20132704.png)

---

## Step 2 – Configure Router1

Static IPv4 addresses were configured on Router1.

Router1 was configured with:

- eth0: `192.168.10.1/24`
- eth1: `192.168.20.1/24`

The configuration was checked using:

`ip addr`

![Router1 IP Configuration](./Images/Screenshot%202026-08-19%20133246%281%29.png)

The routing table was then checked using:

`ip route`

The routing table confirmed that Router1 had routes to the directly connected networks.

![Router1 Routing Table](./Images/Screenshot%202026-08-19%20133343%281%29.png)

---

## Step 3 – Configure Router2

Router2 was configured to connect subnet B and subnet C.

The router configuration was checked using:

`ip addr`

and:

`ip route`

![Router2 IP Configuration](./Images/Screenshot%202026-08-19%20133358%281%29.png)

Router2 connects the `192.168.20.0/24` and `192.168.30.0/24` networks.

---

## Step 4 – Verify Routing

The routing tables were checked to make sure that the routers had the correct directly connected networks.

![Routing Table](./Images/Screenshot%202026-08-19%20133610%281%29.png)

This helped verify that the interfaces and network routes were correctly configured.

---

## Step 5 – Test Connectivity

After configuring the routers, connectivity was tested using the `ping` command.

A connectivity problem was initially observed.

![Unsuccessful Ping Test](./Images/Screenshot%202026-08-19%20134503.png)

The result showed:

`Destination Host Unreachable`

This indicated that the network configuration needed to be checked.

After checking and correcting the configuration, another ping test was performed.

![Successful Connectivity Test](./Images/Screenshot%202026-08-19%20133610%281%29.png)

The successful test showed:

- 5 packets transmitted
- 5 packets received
- 0% packet loss

This confirmed successful communication between the routers.

---

## Step 6 – Configure Host1

Host1 was configured with a static IPv4 address.

The configuration was checked using:

`ip addr`

![Host1 IP Configuration](./Images/Screenshot%202026-08-19%20140147-task%202.png)

The output confirmed that Host1 had been assigned an IPv4 address on the client network.

---

## Step 7 – Configure Server1

Server1 was configured on the server-side network.

The IP configuration was checked using:

`ip addr`

![Server1 IP Configuration](./Images/Screenshot%202026-08-19%20144057%281%29.png)

This server acts as the HTTP server for the practical.

---

## Step 8 – Use Firefox as the HTTP Client

Host1 was used as the graphical HTTP client.

The graphical environment was opened so that Firefox could be used to access the HTTP server.

![Firefox HTTP Client](./Images/Screenshot%202026-08-19%20144216%281%29.png)

This demonstrated the use of a graphical web browser as an HTTP client.

---

# Task 2: HTTP Client with Command Line Interface

## Aim

The aim of Task 2 was to use command-line HTTP clients such as `wget` and `curl` to access the web server.

---

## Step 1 – Prepare the CLI Network

The GUI HTTP client project was used as the basis for the command-line HTTP client task.

The Firefox host was replaced by a Linux Host while keeping the same network structure.

The network continued to use three subnets connected through Router1 and Router2.

![CLI Network Topology](./Images/Screenshot%202026-08-19%20132704.png)

---

## Step 2 – Check Linux Host Configuration

The Linux Host IP configuration was checked using:

`ip addr`

![Linux Host IP Configuration](./Images/Screenshot%202026-08-19%20140147-task%202.png)

This confirmed that the Linux Host was connected to the correct client network.

---

## Step 3 – Check Router Configuration

The Router1 and Router2 interface configurations were checked before testing the HTTP connection.

![Router Configuration 1](./Images/Screenshot%202026-08-19%20133246%281%29.png)

The second router configuration was also verified.

![Router Configuration 2](./Images/Screenshot%202026-08-19%20133358%281%29.png)

---

## Step 4 – Verify Connectivity

Before accessing the HTTP server, connectivity between the network devices was tested.

![Ping Connectivity Test](./Images/Screenshot%202026-08-19%20133610%281%29.png)

The successful ping result confirmed that the network was able to carry traffic between the configured devices.

---

## Step 5 – Access the Server Using wget

The Linux Host was used as a command-line HTTP client.

The `wget` command was used to request the web page from the HTTP server.

Example command:

`wget http://<server-ip>/`

`wget` downloads the requested webpage and saves it on the client.

![wget Test](./Images/Screenshot%202026-08-19%20144119%281%29.png)

---

## Step 6 – Access the Server Using curl

The `curl` command was also used to access the HTTP server.

Example command:

`curl http://<server-ip>/`

Unlike `wget`, `curl` can display the returned web content directly in the terminal.

![curl Test](./Images/Screenshot%202026-08-19%20144216%281%29.png)

---

# Observations

During this tutorial, I learned how HTTP communication works across multiple routed networks.

The practical demonstrated the importance of correct IP addressing and routing before application-layer communication can work.

The `ip addr` command was useful for checking interface addresses, while `ip route` was used to inspect routing information.

The `ping` command was useful for troubleshooting network connectivity. An unsuccessful test produced a `Destination Host Unreachable` message, while a successful test showed 0% packet loss.

I also learned the difference between graphical and command-line HTTP clients. Firefox provides a graphical interface for accessing websites, while `wget` and `curl` allow HTTP requests to be performed directly from the command line.

Command-line HTTP clients are particularly useful for testing and automation because they do not require a graphical browser.

---

# Conclusion

The Week 04 tutorial provided practical experience with HTTP client-server communication in GNS3.

In Task 1, a graphical HTTP client was used to access the HTTP server across a network containing three subnets and two routers.

In Task 2, command-line HTTP clients were used to access the server.

The practical helped develop understanding of:

- Static IPv4 addressing
- Router interface configuration
- Routing tables
- Default gateways
- Connectivity testing
- Network troubleshooting
- HTTP client-server communication
- GUI HTTP clients
- Command-line HTTP clients
- `wget`
- `curl`

Overall, the tutorial demonstrated how HTTP communication depends on correctly configured underlying network connectivity.
