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

# Port range (n-m)
```
nmap -sT 192.168.0.5 -p 1-9999
```


# show progress
```
nmap -sT 192.168.0.5 -v
```
