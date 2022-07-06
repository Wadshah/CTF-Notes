# L2 MAC Flooding & ARP Spoofing

Finding answers is easy but getting to know how to do it is hard.

This guide is all about it

![](https://cdn-images-1.medium.com/max/1000/1\*AOcORUZF9dJu1E6FAQqqyQ.png)

#### Initial Access

SSHing into the target

> $ ssh -oKexAlgorithms=diffie-hellman-group14-sha256 admin@10.10.167.176

![](https://cdn-images-1.medium.com/max/1000/1\*SOvCrqco6-uQD9J64zL7Lw.png)

\


#### Network Discovery

I scanned for thr internal network

> ip address show eth1

![](https://cdn-images-1.medium.com/max/1000/1\*3q3pEJJOMwZe9lytLVizWQ.png)

For scanning the internal network a **nmap** binary is needed that is transferred to the machine

![](https://cdn-images-1.medium.com/max/1000/1\*GoY-tjArxtB\_FXwHWqw0sQ.png)

Scanning internal hosts

![](https://cdn-images-1.medium.com/max/1000/1\*G1fWa3\_K-jP2iz-4hK4NfQ.png)

![](<../.gitbook/assets/image (1) (1) (1) (1).png>)

![](<../.gitbook/assets/image (3) (1) (1) (1).png>)

#### Passive Network Sniffing

Trying to **sniffing** traffic on this network

> tcpdump -i eth1

![](https://cdn-images-1.medium.com/max/1000/1\*2QbtYh\_e3xz\_rNlOZKw34g.png)

We can transfer the contents to a pcap file and examine them using **wireshark**

> tcpdump -A -i eth1 -w /tmp/tcpdump.pcap

Transferring the file to attacker machine

![](https://cdn-images-1.medium.com/max/1000/1\*aPwj8Sq9Gu8mplN-sEgtzg.png)

We can examine packets using

![](https://cdn-images-1.medium.com/max/1000/1\*IibpV6uO-5fMDfwIzNvCDQ.png)

\


#### Sniffing while MAC Flooding

We will require 2 ssh sessions&#x20;

1st one to capture the packets

![](https://cdn-images-1.medium.com/max/1000/1\*uUt7SK4bu2Qsh7NUGbzAOg.png)

2nd to flood the switch

![](https://cdn-images-1.medium.com/max/1000/1\*hpsLcjGxD6pG9\_2yBBZaAw.png)

Again we can transfer the file using scp and examine the packets

\


#### Man-in-the-Middle: Sniffing

Scanning the internal network using the nmap binary

![](https://cdn-images-1.medium.com/max/1000/1\*3BRUG3qavdN5Uwry7WCHow.png)

3 hosts are found that can be accessed using the machine

**Launching ARP spoofing attack**

![](https://cdn-images-1.medium.com/max/1000/1\*9BHRZpoQBGBb57Zgi9YAzw.png)

The service is being used by other host

![](https://cdn-images-1.medium.com/max/1000/1\*6V5AnOUP9yhEshXca62hBw.png)

Running nmap on the ip shows the host name

![](https://cdn-images-1.medium.com/max/1000/1\*RK6YqET6yDwMxowtoMeyCQ.png)

**Performing Mac Flooding**

Again we require 2 shells

1st to capture packet

![](https://cdn-images-1.medium.com/max/1000/1\*c5WQR4JzrJnzNoZR2PpnZw.png)

2nd to flood the switch

![](https://cdn-images-1.medium.com/max/1000/1\*PzohQJhRbZV1B-9Nmn1VgA.png)

Transfer the pcap file and open it using wireshark

\
