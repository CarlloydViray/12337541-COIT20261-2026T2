# Week 03 – Classful & Classless Addressing

## Task 1

Create a network consisting of three subnets: **Subnet A**, **Subnet B**, and **Subnet C**.

- **Subnet A** contains:
  - A switch
  - A Firefox Host (HTTP client)
- **Subnet B** contains:
  - A switch connecting **Router 1** and **Router 2**
- **Subnet C** contains:
  - A switch
  - A Linux Server (HTTP server)

**Network topology:**

![Task 1 Network Topology](img/w4_task1.png)

### Using the VNC Client on Host1

From the VM shell, edit the VNC startup script:

```bash
nano ./start-vnc.sh
```

Configure it to use ports **5900** and **6080**, then save the file and start the VNC service.

Open the following URL in your browser:

```text
http://192.168.56.101:6080/vnc.html
```

![VNC Client](img/w4_vnc.png)

Once the VNC session opens, launch the Mozilla Firefox host and enter the IP address of the Linux server.

While accessing the web server, capture the packets on **Subnet B** using Wireshark.

![Web Server Access](img/w4_server01.png)

### Ping Packet Capture

Perform a ping test from the client to the server and capture the packets traversing **Subnet B**.

![Ping Packet Capture](img/w4_pingcap.png)

---

## Task 2

Repeat **Task 1**, but replace the **Firefox Host** with a **Linux Host**.

**Network topology:**

![Task 2 Network Topology](img/w4_task2.png)

### Accessing the Web Server with `wget`

From the Linux Host terminal, use:

```bash
wget http://10.10.3.102
```

This downloads the default web page from the Linux server.

![wget Output](img/w4_wget.png)

### Accessing the Web Server with `curl`

To display the web page directly in the terminal, run:

```bash
curl http://10.10.3.102
```

![curl Output](img/w4_curl.png)
