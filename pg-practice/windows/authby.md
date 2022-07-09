# AuthBy

Starting off with Nmap

![](<../../.gitbook/assets/image (4).png>)

Checking for ftp&#x20;

![](<../../.gitbook/assets/image (10).png>)

There seem to be 3 accounts

&#x20;Trying hydra to bruteforce the accounts

![](<../../.gitbook/assets/image (8).png>)

We can login using admin in the ftp

After logging in I found .htpasswd file in the ftp

![](<../../.gitbook/assets/image (27).png>)

We can crack the password using john

![](<../../.gitbook/assets/image (24).png>)

Using the password for creds in the webpage

![](<../../.gitbook/assets/image (9).png>)

We can also use the ftp to put a reverse shell on the web page and get a rev shell back

![](<../../.gitbook/assets/image (6).png>)

Navigating to the webpage the rev shell triggers

![](<../../.gitbook/assets/image (21).png>)



### Priv Esc

Using whoami /priv

![](<../../.gitbook/assets/image (12).png>)

SeImpersonatePriv is enabled



I used this version of Juicy Potato&#x20;

[https://github.com/ivanitlearning/Juicy-Potato-x86/releases](https://github.com/ivanitlearning/Juicy-Potato-x86/releases)

There is a great writeup explaining this

{% embed url="https://medium.com/r3d-buck3t/impersonating-privileges-with-juicy-potato-e5896b20d505" %}

![](<../../.gitbook/assets/image (32).png>)
