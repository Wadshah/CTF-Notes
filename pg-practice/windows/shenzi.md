# Shenzi

#### Starting of with a Nmap scan

![](<../../.gitbook/assets/image (12).png>)

#### Checking for smbclient

![](<../../.gitbook/assets/image (5).png>)

Doing guess work we can use this as a directory on the webpage

![](<../../.gitbook/assets/image (4).png>)

**Enumeration of smbmap**

![](<../../.gitbook/assets/image (3).png>)

![](<../../.gitbook/assets/image (6).png>)

![](<../../.gitbook/assets/image (11).png>)



**Now we have some passwords that can be used to login into wordpress**

![](<../../.gitbook/assets/image (10).png>)



### Foothold

We can upload a webshell

![](../../.gitbook/assets/image.png)

Browsing to the webpage we have it running and executing commands

![](<../../.gitbook/assets/image (8).png>)
