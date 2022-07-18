# Slort

Starting of with a Nmap scan

![](<../../.gitbook/assets/image (29).png>)

Using dirb to enumerate directories&#x20;

![
](<../../.gitbook/assets/image (7) (1) (1).png>)

The web directory site had rfi

### Getting a foothold using RFI



Make 2 files on attacker machine

![](<../../.gitbook/assets/image (16).png>)



![](<../../.gitbook/assets/image (2) (1).png>)

Place nc.exe in the same location where the other 2 files are present



Start a listener on 443 and a web server in the directory congaing files and nc binary



Now we will run curl 2 times to fetch the 2 files

![](<../../.gitbook/assets/image (25) (1).png>)

After the second command hangs&#x20;

![We have a shell](<../../.gitbook/assets/image (18) (1).png>)

### Priv Esc

I found a backup.txt file that was running as admin which can be identified using&#x20;

`icacls`

![](<../../.gitbook/assets/image (3) (1).png>)

It executes TFTP.exe every 5 minutes

We can create our own reverse shell using msfvenom

and place it in backup folder

![](<../../.gitbook/assets/image (11) (1) (1).png>)



After some time it gets executed and we have admin shell

![](<../../.gitbook/assets/image (20) (1) (1).png>)

