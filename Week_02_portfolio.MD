# WEEK 01 - Trasport Layer Protocol

## Creating new project in GNS3

"GNS3 (Graphical Network Simulator-3) is a free, open-source network emulator used by network professionals and students to build, design, and test complex topologies without physical hardware. It combines virtual machines, container environments, and emulated network hardware into a single sandbox"

![alt text](img/w2_newproject.png)

## Making the diagram

Adding four Linux hosts and on ethernet switch connected by LAN. Two hosts' IP address will be changed in 10.1.1.0/24 while the other to is as is (Default)

![alt text](img/w2_diagram.png)

IP Address of Host 1:

![alt text](img/w2_ipah1.png)

IP Address of Host 2:

![alt text](img/w2_ipah2.png)

## Changint static ip addreess via console

Using Linux command `nano /etc/network/interface`

![alt text](img/w2_interfacesedit.png)
![alt text](img/w2_nano.png)

Rather than changing it via web UI, we use linux command to change it explicitly

![alt text](img/w2_changedip.png)

change IP Address for the 4th host using explicit command

`ip addr add 10.1.1.4/24 dev eth0`

![alt text](img/w2_h4.png)

## Ping to hosts in the network

Pinging other hosts via host1 using command `ping 10.1.1.2`

![alt text](img/w2_ping.png)
![alt text](img/w2_netstats.png)

Pinging non-existent host ip
![alt text](img/w2_pingchiling.png)

Trying different command lines by changing count of ping, interval, and size

-c is count of ping
`ping -c 3 10.1.1.2`
![alt text](img/w2_ping-c.png)

-i is interval, meaning time before next ping
`ping -i 10 10.1.1.2`
![alt text](img/w2_ping-i.png)

-s is packet size (Default is bytes)
`ping -s 100 10.1.1.2`
![alt text](img/w2_ping-s.png)

combining all commands
`ping -c 2 -i 7 -s 100 10.1.1.2`
![alt text](img/w2_pingall.png)
