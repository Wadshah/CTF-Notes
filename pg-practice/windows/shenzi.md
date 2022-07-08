# Shenzi

#### Starting of with a Nmap scan

![](<../../.gitbook/assets/image (12) (1).png>)

#### Checking for smbclient

![](<../../.gitbook/assets/image (5) (1).png>)

Doing guess work we can use this as a directory on the webpage

![](<../../.gitbook/assets/image (4) (1).png>)

**Enumeration of smbmap**

![](<../../.gitbook/assets/image (3) (1).png>)

![](<../../.gitbook/assets/image (6) (1).png>)

![](<../../.gitbook/assets/image (11) (1).png>)



**Now we have some passwords that can be used to login into wordpress**

![](<../../.gitbook/assets/image (10) (1).png>)



### Foothold

We can upload a webshell

![](<../../.gitbook/assets/image (2).png>)

Browsing to the webpage we have it running and executing commands

![](<../../.gitbook/assets/image (8) (1).png>)

Uploading nc.exe and getting a proper shell

![](<../../.gitbook/assets/image (10).png>)

&#x20;

![](../../.gitbook/assets/image.png)

Running winpeas on the target shows

![](<../../.gitbook/assets/image (8).png>)

I made a exe using msfvenom

![](<../../.gitbook/assets/image (13).png>)

Got it on my shell and ran it with a lister listening

![](<../../.gitbook/assets/image (18).png>)



And got an admin shell&#x20;

![](<../../.gitbook/assets/image (12).png>)



