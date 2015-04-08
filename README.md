# roboFeeder
##nodejs code to run RFID pet feeder using a Raspberry Pi

[github repository](https://github.com/DrCord/roboFeeder)

[project website](http://robofeeder.cordslatton.com)

Dependencies:
* NodeJS
* async https://github.com/caolan/async
* body-parser https://www.npmjs.com/package/body-parser
* express http://expressjs.com
* nedb https://github.com/louischatriot/nedb
* npmlog https://github.com/npm/npmlog
* rpi-gpio https://www.npmjs.com/package/rpi-gpio
* serialport https://www.npmjs.com/package/serialport

TODO LIST
* improve look of the web app pages
* add picture(s) to website and git readme display on github
* allowed tags - complex programs via ui for allowed times, max time, etc.

Parts List:
* Raspberry Pi ([B+](http://www.adafruit.com/products/1914), [Pi 2](http://www.adafruit.com/products/2358))
* Micro SD card (8GB+) compatible with Raspberry Pi with Raspbian installed ([Adafruit](http://www.amazon.com/s/?ie=UTF8&keywords=8gb+sd+mini))
* Wireless network dongle compatible with Raspberry Pi with a decent antenna ([Adafruit](http://www.adafruit.com/products/1012))
* PIR Sensor ([SparkFun](https://www.sparkfun.com/products/8630))
* RFID Sensor with serial output (9600 bps to use codebase without changing) ([AliExpress](http://www.amazon.com/Anti-Jamming-Capability-HZ-1050-Module-Reader/dp/B00NJCB8NO))
* Logic Level Converter 5v - 3.3V (bi-directional) ([SparkFun](https://www.sparkfun.com/products/12009))
* L293D Chip - Dual H-Bridge Motor Driver ([Adafruit](https://www.adafruit.com/products/807))
* AdaFruit Half-size Perma-proto Raspberry Pi ([Adafruit](http://www.adafruit.com/products/1148))
* Downgrade GPIO Ribbon Cable for Pi A+/B+/Pi 2 - 40p to 26p ([Adafruit](https://www.adafruit.com/products/1986))
* Resistors (220, 1K, 10K, Other) //TODO: Note other resistor resistance
* Wire (ideally of various colors) //TODO: estimate total length and optimal number of colors
* Momentary Push Button Switch x2 ([Adafruit](https://www.adafruit.com/products/1119))
* CD/DVD-ROM Drive (Up-cycled - as long as the drive tray and motor work, the older the better, older drives are more robust)
* Hinge (1-2 inch) //TODO: measure
* Hook and Eye Latch //TODO: measure
* Small self tapping screws //TODO: Measure size and count quantity
* 3/4 inch wood //TODO - get minimum measurements of piece that all pieces can be cut from
* 5.5v - 23v output Standard AC to DC wall plug - Size M (ideally recycle an unused one from something else or get one from your local reuse store)
* Size M DC Coaxial input power jack ([Radioshack](http://www.radioshack.com/size-m-panel-mount-coaxial-dc-power-jack/2741563.html))
* Hobbywing 5V/6V 3 Amp Switch-Mode Ultimate BEC ([DealExtreme](http://www.dx.com/p/hobbywing-5v-6v-3a-switch-mode-ultimate-bec-ubec-15149))
* Shrink Tubing([Adafruit](http://www.adafruit.com/products/1649))
* Male Single Row Headers ([Adafruit](http://www.adafruit.com/products/392))
* Female Headers([Adafruit](http://www.adafruit.com/products/598))

Setup Instructions
* setup wifi credentials //TODO: update wifi file location
* disable shell and kernel messages via serial in the raspi-config utility
* connect to the pi via ssh, make sure you are in the pi user's home directory (/home/pi/) and run `git clone https://github.com/DrCord/roboFeeder.git`
* `cd roboFeeder` then `sudo npm install`
* add this code to the `/etc/rc.local` file before the `exit 0` line

    `#autorun node.js server,js file on boot`
    
    `su pi -c 'sudo node /home/pi/roboFeeder/app.js < /dev/null &'`
    
    `#autorun the soft shutdown switch code`
    
    `python /home/pi/roboFeeder/softShutdownSwitch.py`

License

Software, parts list and CAD files to build and run a Raspberry Pi controlled pet feeder
Copyright (C) 2015  Cord Slatton-Valle 
cord42@gmail.com
(cordslatton.com)[http://www.cordslatton.com]

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
