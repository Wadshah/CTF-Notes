# Acute

Starting off with nmap&#x20;

![](<../../.gitbook/assets/image (33).png>)

We can see port 443 is open and leaking the SSL Certificate name

Lets add it to our /etc/hosts file

![](<../../.gitbook/assets/image (14).png>)

Browsing the webpage

![](<../../.gitbook/assets/image (12).png>)

We can download a file using **New Starter Forms** present on the right

The Document seems to be leaking some information

![](<../../.gitbook/assets/image (31).png>)

Moreover upon exiftool on the file

![](<../../.gitbook/assets/image (25).png>)

Computer name and the user can me seen

Lastly we can find a link&#x20;

![](<../../.gitbook/assets/image (22).png>)

Which leads to

![](<../../.gitbook/assets/image (11).png>)

Now we need to list all the info that we have gathered

We can also find a username list from the webpage

![](<../../.gitbook/assets/image (13).png>)

This indicates the first name of the user daves

Upon some tries with the username

![](<../../.gitbook/assets/image (6).png>)

I logged-in into the poweshell

We are in as Daves

![](<../../.gitbook/assets/image (32).png>)



I uploaded nc.exe and tried getting a shell&#x20;

![](<../../.gitbook/assets/image (7).png>)

But it marked nc.exe as an unwanted software

![](<../../.gitbook/assets/image (23).png>)

Navigating around I found

![](<../../.gitbook/assets/image (5).png>)

This folder can be used to test files&#x20;

![](<../../.gitbook/assets/image (19).png>)

So i ran nc.exe in that directory and got a rev shell

![](<../../.gitbook/assets/image (24).png>)

![](<../../.gitbook/assets/image (20).png>)
