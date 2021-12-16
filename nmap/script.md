# TCP scan
```
nmap -sT 192.168.0.5
```

# UDP scan
```
nmap -sU 192.168.0.5
```

# Stealth scan(need root's perm)
```
nmap -sT 192.168.0.5
```


# scanning OS information
```
nmap -O 192.168.0.5
```

# Port range (0-65535)
```
nmap -sT 192.168.0.5 -p 80-90
```


# show progress
```
nmap -sT 192.168.0.5 -v
```


# probe service version
```
nmap -sV -p4858 192.168.0.15
```
