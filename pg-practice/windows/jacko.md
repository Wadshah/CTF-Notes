# Jacko

Starting of with NMap

![](<../../.gitbook/assets/image (23).png>)

Going to port 80 H2 Database is found



Searching for exploits

![](<../../.gitbook/assets/image (13).png>)

Following the steps from exploit database&#x20;

![](<../../.gitbook/assets/image (28).png>)

I uploaded nc.exe and got back a rev shell

![](<../../.gitbook/assets/image (14).png>)

### Priv Esc

Taking a look at files

&#x20;

![](<../../.gitbook/assets/image (30).png>)

![](<../../.gitbook/assets/image (26).png>)

After reading the exploit a few changes were made

![](<../../.gitbook/assets/image (19).png>)

Now we can generate a dll file using msfvenom

![](<../../.gitbook/assets/image (15).png>)

Uploading the dll and exploit on the shell&#x20;

and then executing it with a listener listening&#x20;

![](<../../.gitbook/assets/image (5).png>)

![](<../../.gitbook/assets/image (17).png>)

![](<../../.gitbook/assets/image (22).png>)

I receive a admin shell
