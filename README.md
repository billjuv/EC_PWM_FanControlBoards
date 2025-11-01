# EC-PWM Fan Control Boards - USB-C

These were designed for use with EC fans which use USB-C connectors for controlling the speed through PWM. They are modifications of Kyle Gabriel’s (Mycodo) fan control boards for TerraBloom EC fans using USB-C connectors instead of audio connectors. They provide voltage level shifting for use with Raspberry Pi or ESP boards and monitoring of tach signals (RPM) from compatible fans.  
  
These boards safely control the PWM speed for EC fans supplying 10VDC from a USB-C cable (AC Infinity fans ("UIS") or Vivosun fans ("SGS") - and perhaps others) from Raspberry Pi GPIO pins or ESP32 pins. I’ve verified the PWM control works well on the AC Infinity Airlift S Series Shutter Fans (with tach) and the AC Infinity Cloudray S6 6” clip fan (no tach function). I’ve also tested it on the VIVOSUN AeroWave E6 Gen2, Grow Tent Clip Fan 6” (no tach on this fan, unsure about the larger fans). These tests were done from a Raspberry Pi 4 using Mycodo and from ESP32 boards using ESPHome and MQTT.  
  
<img src=Attachments/IMG_1477.jpg width="60%"/>   

<img src=Attachments/IMG_1484.jpg width="60%"/>  

I’ve included Gerber files for three board variations (see README in Gerber folder):  
  
- Left: ‘USB-C_Breakout_x_2.54’ (Gerber is modified for offset transistor lead footprint).  
- Center: ‘2.54x2_Breadboard’ (board is short enough for jumpers on both ends).  
- Right: ‘JST-PH_x_2.54’ (for use with ‘xiwai’ 4-pin cabinet mount cable (link below)).  
  
All boards have 10v and GND pads for tapping into fan power if needed. 


<img src=Attachments/cable.jpg width="50%"/>

[Amazon link to above cable](https://www.amazon.com/Female-Waterproof-Terminal-Pigtail-Extension/dp/B0D7CN4BTV/ref=sr_1_1?crid=22DIPVZJ6NLNA&dib=eyJ2IjoiMSJ9.5A5gh8wlE1dA5xzyWRfnF6wJ0fd9cFGKaGoMoL32RONrxG9_nN8LmJ9rJli3ujotLw90tzZNpYxllE3eMCpda7KoQPOh_-vPp3rROVUxTw11IfYGYRkTlLA7TaCoP3jR.uXNtln_9dJgcMFb5AaFasS38uiNJQxI2SMAjDUyGoKk&dib_tag=se&keywords=xiwai%2B5pcs%2FSet&qid=1761968034&sprefix=xiwai%2B5pcs%2Fset%2Caps%2C101&sr=8-1&th=1)

<img src=Attachments/IMG_4349.jpg width="50%"/> 
Hole sizes for above cable mount



![GPIO Header:](Attachments/Screenshot%202025-08-11%20at%205.42.39%E2%80%AFPM.PNG) 
Note: transistors are both 2N3904



 
<img src=Attachments/IMG_0289.jpg width="60%"/> 
<img src=Attachments/IMG_0293.jpg width="60%"/>  
The two pictures above show the use of the cabinet mounted USB-C cables using Kyle's boards, and the reason I designed the JST-PH version of the board.