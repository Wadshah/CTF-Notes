---
description: https://app.hackthebox.com/machines/212
---

# Forrest

## Nmap

![](<../../.gitbook/assets/image (1) (1).png>)

RPC-client

![](<../../.gitbook/assets/image (4) (1).png>)

We get a list of users through rpcclient



### ARP Roasting

Using GetNPusers to get the hash for svc account

![](<../../.gitbook/assets/image (2) (1).png>)

### Cracking the hash

![](<../../.gitbook/assets/image (3) (1).png>)

### Foothold

![](<../../.gitbook/assets/image (5) (1).png>)
