---
description: https://app.hackthebox.com/machines/229
---

# Sauna

Nmap

![](<../../.gitbook/assets/image (5) (1) (1) (1) (1) (1).png>)

Taking a look at the website on port 80

![We can store them in a file](<../../.gitbook/assets/image (3) (1) (2).png>)

![](<../../.gitbook/assets/image (4) (1) (1) (1) (1).png>)

Using [username-anarchy](https://github.com/urbanadventurer/username-anarchy)

![](<../../.gitbook/assets/image (7) (1) (1) (1) (1) (1).png>)

![](<../../.gitbook/assets/image (1).png>)

### Kerberos pre authentication

We can exploit the feature as it is disabled using the username list that we generated

![We get the hash](<../../.gitbook/assets/image (6) (1) (1) (1) (1) (1).png>)

Cracking the hash is fairly easy

### Foothold

![](<../../.gitbook/assets/image (2) (1) (1) (1).png>)

