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


# scanning with OS information
```
nmap -sT 192.168.0.5 -A
```

# Port range (0-65535)
```
nmap -sT 192.168.0.5 -p 80-90
```


# show progress
```
nmap -sT 192.168.0.5 -v
```
