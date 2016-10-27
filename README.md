# RPI-ESP8266-TORNADO-SERVER

#### This project aim to setup Tornado Web Server in Rpi and create a Web Socket Client with NodeMCU.
---

#### Tornado Webserver Setup on Raspberry

I follow [This Guide](https://developer.mbed.org/cookbook/Websockets-Server) to setup and testing Tornado Webserver.
```sh
sudo apt-get update
sudo pip3 install tornado
```
After setup is complete, Run [test-Server.py](https://github.com/Project-MAR/RPI-ESP8266-TORNADO-SERVER/blob/master/test-Server.py) to start a Tornado Server. Use [HelloWorld.html](https://github.com/Project-MAR/RPI-ESP8266-TORNADO-SERVER/blob/master/HelloWorld.html) (open it with your browser) to confirm that your server is run correctly. Becarefull, Your Web Browser must support Web Socket, for me, I use Google Chrome.

---
#### Web Socket Client Setup on NodeMCU

Start with [Links2004 Project](https://github.com/Links2004/arduinoWebSockets), Download and run [test-Client.ino](https://github.com/Project-MAR/RPI-ESP8266-TORNADO-SERVER/blob/master/test-Client.ino) then enjoy with basic Web Socket Communication.

---

#### Rename Rpi hostname and setup Bonjour

First.
```sh
sudo nano /etc/hostname
```
This file contains one line, Hostname. Edit which you want then save it.

Second.
```sh
sudo nano /etc/hosts
```
The second file also cantians the hostname but it's only use for some software. Find the line starting with 127.0.0.1 and change it

Third.
Setup Bonjour. This will allow you to access to RPi from hostname.local (adding .local after your hostname). RPi may have it installed already, but if not then.
```sh
sudo apt-get update
sudo apt-get install libnss-mdns
```

---

#### CAUTION: provisional headers are shown” in Chrome debugger
On page load websocket works, but after that when applied with click event, then its not working     
 - Type "chrome://net-internals" in the address bar and hit enter.
 - Open the page that is showing problems.
 - Go back to net-internals, click on events (###) and use the textfield to find the event related to your resource (use parts of the URL).
Finally, click on the event and see if the info shown tells you something.   

---