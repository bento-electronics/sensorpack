Sensor Pack
===================

Your sensor kit contains 35 different modules, with a couple duplicates - each individual kit varies as to which modules appear more than once!

There are analog and digital sensors, along with switches and output modules (e.g. LEDs, buzzers, lasers). They can all be classified into a few different types below. Modules of the same type generally share similar Arduino interface code.

All modules in this kit have a GND pin for ground connections and V+ pin to be connected to 5V supply voltage; without these power connections a module will not work!

----------

Switches
-------------
Switch modules output a binary state on the S pin, depending on an action detected by the sensor. A high state (@ supply voltage) means the switch is _closed_ i.e. activated, while a low state (@ ground) means it is _open_ i.e. inactive.

Hooking up the S pin to any pin on an Arduino will allow you to read the switch state using digitalRead(pinNumber);

> **Hall effect magnetic switch**
> Outputs HIGH when in the presence of a magnetic field.
> http://thirdharmonic.co.uk/2014/03/a3114-hall-effect-switch-introduction/

> **Small reed switch**
> Also outputs HIGH when in the presence of a magnetic field.
> https://www.youtube.com/watch?v=yWsvkHM9ISE
> https://www.sparkfun.com/datasheets/Components/Buttons/AN104.pdf

> **Vibration switch**
> Outputs HIGH when vibrated.
> http://learn.linksprite.com/arduino/sensors-kit-for-arduino/ky002-shock-sensor-module/

> **Knock switch**
> Similar to vibration switch, outputs HIGH when jolted (i.e. by tap or knock).
> https://sites.google.com/site/summerfuelrobots/arduino-sensor-tutorials/knock-tap-sensor-ky-031

> **Optical tripwire**
> Outputs HIGH when the sensor slot is obstructed.
> http://learn.linksprite.com/arduino/sensors-kit-for-arduino/ky010-light-block-sensor-module/

> **Tilt switch**
> Outputs HIGH or LOW depending on the orientation of the sensor past horizontal. Comes in 2 versions; one uses a mercury droplet inside a bulb.
> http://henrysbench.capnfatz.com/henrys-bench/keyes-ky-017-arduino-mercury-tilt-switch-tutorial/
> http://misclab.umeoce.maine.edu/boss/Arduino/bensguides/KeyesKY-020Tilt_Sensor_Instructions.pdf

> **Pushbutton**
> Outputs HIGH when pressed down, LOW when unpressed.
> 

--------

Analog Sensors
-------------
Analog sensors in this kit have the same style board (black and square) as switches, but output measurements as a voltage between LOW (ground/0V) or HIGH (VCC). In this way they can represent a range of values rather than just two. 

To receive analog measurements from these sensors, connect S to one of the ANALOG IN pins on an Arduino (A0 - A5 on an UNO board), then use pinMode(pinNumber, IN); in the setup() function and analogRead(pinNumber) to get a byte value between 0 to 255.

> **PS2 Joystick**
> An X/Y joystick similar to those found in the PS2 controllers. There are two analog voltage outputs representing X and Y position, and should be hooked up to separate ANALOG IN inputs.
> https://www.sparkfun.com/tutorials/272

> **Thermistor**
> A temperature-dependent resistor. Output voltage will increase with temperature.
> https://sites.google.com/site/summerfuelrobots/arduino-sensor-tutorials/analogue-temperature-sensor

> **Photoresistor**
> A light-dependent resistor. Output voltage will increase with temperature.
> http://bildr.org/2012/11/photoresistor-arduino/

> **Heartbeat sensor**
> This sensor uses infrared light and a photoresistor to detect pulse when your finger is placed between the IR emitter and sensor. Output voltage increases everytime there is a heartbeat.
> https://www.youtube.com/watch?v=dzV2IehmhR0
> https://tkkrlab.nl/wiki/Arduino_KY-039_Detect_the_heartbeat_module

> **Line follower**
> Uses a photoresistor to measure dark and light surfaces under the sensor. Output voltage decreases on lighter surfaces, i.e. when the line follower "strays" from the dark line.
> https://www.youtube.com/watch?v=gPtBuMpnYtg

> **Obstacle sensor**
> Senses the presence of an object placed in front of it. Output voltage increases with proximity of the object.
> https://www.youtube.com/watch?v=Vqcvmh_9rBo
> https://tkkrlab.nl/wiki/Arduino_KY-032_Obstacle_avoidance_sensor_module

----------


Analog+Switch Sensors
-------------
These modules have two outputs; an analog voltage signal (that can vary from GND to VCC, i.e. 0 to 5V in most applications), and a switch output that is either high or low, depending on whether the sensed measurement crosses a threshold. That threshold can be set by turning the small screw on the blue potentiometer, which is on every board of this type.

Each of these modules therefore has 4 pins: GND, +, AO (analog output), and DO (digital/switch output).

To receive analog measurements from these sensors, connect AO to one of the ANALOG IN pins on an Arduino (A0 - A5 on an UNO board), then use pinMode(pinNumber, IN); in the setup() function and analogRead(pinNumber) to get a byte value between 0 to 255.

To receive binary measurements, connect DO to any other pin and use digitalRead(pinNumber) after initializing pinMode.

> **Linear Hall Effect Magnetic Sensor**
> Similar to the Hall Effect Magnetic Switch, but also outputs the strength of the magnetic field on the AO pin. Voltage increases linearly with magnetic field strength.
> http://softsolder.com/2012/12/10/arduino-snippets-hall-effect-sensor/

> **Electret Mic**
> When DO is used, acts as a loudness switch (e.g. detecting claps). When A0 is used, voltage directly represents recorded sound amplitude. Also comes in a high-sensitivity version that is better suited for actually recording audio.
> https://sites.google.com/site/summerfuelrobots/arduino-sensor-tutorials/microphones-with-arduino
> https://tkkrlab.nl/wiki/Arduino_KY-037_Sensitive_microphone_sensor_module

> **Capacitive Touch**
> DO outputs HIGH whenever any conductive material (or material with a dielectric constant different to air) touches the exposed sensor pin. AO directly represents the relative capacitance of the object touching the pin.
> https://tkkrlab.nl/wiki/Arduino_KY-036_Metal_touch_sensor_module
> https://www.youtube.com/watch?v=GyU0bWgUDZ0

> **Large Reed Switch**
> Similar to the Small Reed Switch and Linear Hall Effect Magnetic Sensor, outputs presence of magnetic field on DO and field strength on AO. However, AO does not increase linearly with field strength.
> https://tkkrlab.nl/wiki/Arduino_KY-025_Reed_module
> https://www.sparkfun.com/datasheets/Components/Buttons/AN104.pdf

> **Analog Temperature Sensor**
> Similar to the Thermistor, AO voltage increases with temperature. However, DO can also be used as a switch at a threshold temperature.
> 

> **Flame Sensor**
> Detects the presence of a flame (DO goes high when flame is detected), and outputs detected heat (depends on received temperature, which drops off with the square of distance from the source of actual radiated heat)
> http://www.instructables.com/id/Arduino-Modules-Flame-Sensor/
> https://www.youtube.com/watch?v=5cCqJU2uKmA

----------

Digital Sensors
-------------
Digital sensors are similar to the analog sensors in that they output more than just a binary state, but output using a serial protocol rather than just a voltage level.

The details of the protocol can vary significantly between different sensors, and is usually described in the datasheet. As a result, the code for reading data is much more involved, but most common sensors already have Arduino libraries written on them.

Libraries for the digital sensors in this kit are included in the Github repo. You can install them by navigating to _Sketch > Include Library > Add .ZIP library_ in the Arduino IDE and importing the .zip file. Refer to sample code for examples of how to use each sensor's library.

> **Temperature Sensor**
> Based on the DS18B20 sensor, outputs exact measured temperature in Celsius over a custom digital protocol. Refer to the datasheet and Arduino library for specific details.
> https://www.sparkfun.com/products/245

> **Rotary Encoder**
> A "knob" input which outputs the current knob position, represented over 2 outputs pins using a "Gray code". Refer to the datasheet and Arduino library for specific details.
> http://bildr.org/2012/08/rotary-encoder-arduino/
> https://tkkrlab.nl/wiki/Arduino_KY-040_Rotary_encoder_module
> http://henrysbench.capnfatz.com/henrys-bench/keyes-ky-040-arduino-rotary-encoder-user-manual/

> **IR Remote Receiver**
> A receiver for infrared remotes, such as the one found in the starter kits. Will output the specific code received, over a custom digital protocol. Refer to the datasheet and Arduino library for specific details.
> https://tkkrlab.nl/wiki/Arduino_KY-022_Infrared_sensor_receiver_module
> https://learn.sparkfun.com/tutorials/ir-control-kit-hookup-guide?_ga=1.260258509.1591661100.1439619481
> https://www.sparkfun.com/products/11759

> **Humidity Sensor**
> Based on the DHT11 sensor, outputs exact measured humidity over a custom digital protocol. Refer to the datasheet and Arduino library for specific details.
> https://www.adafruit.com/products/386


----------

Output
-------------
These are simple output modules that can be used in various ways, most commonly to indicate states or data from the software. All can be interfaced with 

> **RGB LED (Surface mount)**
> Essentially red, green, and blue LEDs packaged together. Each color can be switched (or brightness controlled using PWM) independently over the respective pin.
> https://learn.sparkfun.com/tutorials/light-emitting-diodes-leds

> **RGB LED (through-hole)**
> https://learn.sparkfun.com/tutorials/light-emitting-diodes-leds

> **5V Power relay**
> Can switch high-current loads on or off at 5V, controlled by a single digital pin from Arduino. Use this for high power outputs, e.g. DC motors or incandescent lamps, which usually require a separate power supply, and cannot safely be driven direct from Arduino pins.
> http://shop.evilmadscientist.com/productsmenu/tinykitlist/544

> **7-colour automatic strobe LED (through hole)**
> An LED that strobes through 7 different colours when turned on.
> https://learn.sparkfun.com/tutorials/light-emitting-diodes-leds

> **Buzzer**
> A simple piezoelectric buzzer. Can only be turned on or off, but using PWM can be made to play different frequencies of square waves.

> **Laser emitter**
> A laser diode. Be careful with this! Do not point it at human beings.
> https://tkkrlab.nl/wiki/Arduino_KY-008_Laser_sensor_module
> https://www.youtube.com/watch?v=KX_-MPOJNXY

> **2-color LED module**
> Unlike the RGB modules, can only mix 2 colors instead of full RGB.
> https://tkkrlab.nl/wiki/Arduino_KY-011_2-color_LED_module

> **Infrared remote transmitter**
> Essentially an IR LED, and can be used with the IRRemote library to transmit remote control codes to the IR remote receiver.
> http://electronics.stackexchange.com/questions/136421/datasheet-for-keyes-ir-transmitter-ky-005-wanted
