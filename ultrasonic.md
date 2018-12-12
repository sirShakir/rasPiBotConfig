# General ultrasonic sensor code
--------------------------------
### Used on Arduino - powered it with 5v to Vcc, and connected pins to Trig and Echo
Arduino code for a single reading:

	digitalWrite(Trig_pin, LOW);

	delayMicroseconds(2);

	digitalWrite(Trig_pin, HIGH);

	delayMicroseconds(10);

	digitalWrite(Trig_pin, LOW);

	duration = pulseIn(Echo_pin,HIGH);

	distance = duration  / 60

#### Pi will be similar, but resistors needed on the GPIO pins

# Pi Setup
-----------------------------------
1. VCC to +5V from Pi
2. GND to GND on Pi
3. Trigger to GCLK output
4. ECHO needs a special circuit otherwise you will not guarantee accuracy of results as you cannot guarantee being able time the ECHO signal coming back. Also needs translation to 3V3 from 5V.

# Pi ultrasonic support
----------------------------
### You can directly connect 3.3V output of Raspberry Pi to TRIGGER input of HC-SR04. It will detect 3.3V as HIGH LEVEL.
### But the 5V ECHO output of HC-SR04 should not be directly connected to 3.3V rated Raspberry Pi input.. It may damage it.. So you should use additional voltage dividing resistors to reduce 5V to 3.3V compatible with Raspberry Pi... You can use a 10K and a 4.7K resistor for that.

# Web Resources for Pi ultrasonic senor setup
----------------------------
* https://pimylifeup.com/raspberry-pi-distance-sensor/
* https://tutorials-raspberrypi.com/raspberry-pi-ultrasonic-sensor-hc-sr04/
* https://iotguider.in/raspberrypi/ultrasonic-distance-sensor-raspberry-pi/
--YOUTUBE
* https://www.youtube.com/watch?v=sXJjfEisjpo
* https://www.youtube.com/watch?v=ShnzQSFwVXQ
* https://pythonprogramming.net/gpio-input-raspberry-pi-tutorials/
