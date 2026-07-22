# Week 01 – Transport Layer Protocol

## Creating a New Project in GNS3

**GNS3 (Graphical Network Simulator 3)** is a free and open-source network emulator that enables network professionals and students to design, build, and test complex network topologies without requiring physical networking hardware. It integrates virtual machines, containers, and emulated network devices into a single simulation environment.

![Creating a new GNS3 project](img/w2_newproject.png)

---

## Building the Network Topology

The network topology consists of four Linux hosts connected to an Ethernet switch within the same LAN.

- **Host 1** and **Host 4** were configured with static IP addresses in the **10.1.1.0/24** subnet.
- **Host 2** and **Host 3** retained their default network configurations.

![Network topology](img/w2_diagram.png)

### Host 1 IP Configuration

![Host 1 IP address](img/w2_ipah1.png)

### Host 2 IP Configuration

![Host 2 IP address](img/w2_ipah2.png)

---

## Configuring Static IP Addresses

Static IP addresses were configured using the Linux terminal instead of the graphical interface.

Edit the network interface configuration file:

```bash
nano /etc/network/interfaces
```

![Editing network interfaces](img/w2_interfacesedit.png)

Modify the configuration using the Nano text editor.

![Nano editor](img/w2_nano.png)

After saving the configuration, the new static IP address is applied.

![Updated IP configuration](img/w2_changedip.png)

For **Host 4**, a temporary IP address was assigned directly from the command line:

```bash
ip addr add 10.1.1.4/24 dev eth0
```

![Host 4 configuration](img/w2_h4.png)

---

## Testing Network Connectivity

Connectivity between hosts was verified using the `ping` command.

Example:

```bash
ping 10.1.1.2
```

This sends ICMP Echo Request packets from **Host 1** to **Host 2** to verify network connectivity.

![Ping test](img/w2_ping.png)

Network statistics after the ping test:

![Ping statistics](img/w2_netstats.png)

### Pinging a Non-Existent Host

Attempting to ping an IP address that is not assigned to any device results in no response.

![Ping non-existent host](img/w2_pingchiling.png)

---

## Using Ping Options

### Limit the Number of Packets (`-c`)

The `-c` option specifies the number of ICMP Echo Requests to send.

```bash
ping -c 3 10.1.1.2
```

![Ping count](img/w2_ping-c.png)

---

### Set the Time Interval (`-i`)

The `-i` option defines the interval (in seconds) between each ping request.

```bash
ping -i 10 10.1.1.2
```

![Ping interval](img/w2_ping-i.png)

---

### Specify Packet Size (`-s`)

The `-s` option changes the payload size (in bytes) of each ICMP packet.

```bash
ping -s 100 10.1.1.2
```

![Ping packet size](img/w2_ping-s.png)

---

### Combining Multiple Options

Multiple options can be used together in a single command.

```bash
ping -c 2 -i 7 -s 100 10.1.1.2
```

This command sends **2** ICMP packets with a **7-second interval** and a **100-byte payload**.

![Combined ping options](img/w2_pingall.png)
