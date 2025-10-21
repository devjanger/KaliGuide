# TCP scan(-sT)
```
nmap -sT 192.168.0.5
```

# UDP scan(-sU)
```
nmap -sU 192.168.0.5
```

# Stealth scan(-sS)
```
nmap -sS 192.168.0.5
```


# scanning OS information(-O)
```
nmap -O 192.168.0.5
```

# Port range (0-65535)(-p 0-65535)
```
nmap -sT 192.168.0.5 -p 80-90
```


# show progress(-v)
```
nmap -sT 192.168.0.5 -v
```


# probe service version(-sV)
```
nmap -sV -p22 192.168.0.15
```
