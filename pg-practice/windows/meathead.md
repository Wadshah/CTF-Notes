# Meathead

Starting of with an NMap scan

![](<../../.gitbook/assets/image (33).png>)

Found a few files on ftp

![](<../../.gitbook/assets/image (22).png>)

Cracked the MYSQL\_BAK file using john

![](<../../.gitbook/assets/image (21).png>)

![](<../../.gitbook/assets/image (11).png>)

Using the creds to open the file&#x20;

![](<../../.gitbook/assets/image (10).png>)

We have another set of creds

Got Foothold using the creds

![](<../../.gitbook/assets/image (17).png>)

Getting a proper shell

Started a smb server hosting nc.exe

&#x20;

![](<../../.gitbook/assets/image (5).png>)

and on the limited shell ran

![](<../../.gitbook/assets/image (34).png>)

It fetches the exe from our server on ehich nc.exe is hosted

![Now we have a proper shell](<../../.gitbook/assets/image (32).png>)



### Priv Esc

Using whoami /priv

![](<../../.gitbook/assets/image (3).png>)

It shows SeImpersonatePriv is enabled

We can use PrintSpoofer.exe to get admin access

![](<../../.gitbook/assets/image (19).png>)
