# Week 06

## Create openvswitch

hosts are 192.168.5.0/24 subnet

![alt text](img/w6_map.png)

Run command:

```bash
nano sh /etc/openvswitch/init.sh
nano ovs-vsctl show
```

![alt text](img/w6_ovs.png)

Assign each port to an id or tag

```bash
nano ovs-vsctl set port eth0 tag=10
```

Do this for all hosts depending on what port number are the using.
This will assign tags to ethernet ports

![alt text](img/w6_tags.png)
