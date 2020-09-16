FastDrop, a BPF/XDP firewall, for ports 1-1024.

Usage:

sudo fastdrop --ingress 192.168.1.10 --interface eth0 --udpports 68 --tcpports 81 --block 192.168.1.2,8.8.8.8

OR

sudo ./fastdrop -i 192.168.1.10 -n eth0 -u 68 -t 81 -b 192.168.1.2,8.8.8.8

This will:

1) Set the ingress address to 192.168.1.10.  You want this to be your systems IP address.

2) Set the listening device to eth0

3) Allow incoming traffic on UDP port 68 and TCP port 81.  All other ports up to 1024 will be blocked.

4) Block incoming traffic with the source address of 192.168.1.2 and 8.8.8.8

To do:
- Still need to support IPv6
- C function to convert source and destination addresses into readable addresses
