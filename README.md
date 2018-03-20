# runonbootpi
Run scripts on startup Raspberry PI

1. Create a bash script
```
sudo nano start.sh
```
Example:
```
#!/bin/sh
sleep 10
cd /
cd home/pi/
sudo python program.py &
cd /
```
2. Change rights to 775
```
sudo chmod 775 start.sh
```
3. Make a crontab
```
sudo crontab -e
```
4. Make a log file to catch all the errors
```
mkdir logs
chmod 775 logs
```
5. Add the following line to the crontab
```
@reboot sudo sh /home/pi/start.sh >/home/pi/logs/cronlog 2>&1
```
6. Now reboot
```
sudo reboot
```
