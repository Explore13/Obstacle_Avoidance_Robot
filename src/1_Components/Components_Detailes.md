## NOTE :
I made this repository for project competition.SO,I added `Component Detailes` also 
so that you can easily answer the questions of judges..

#### Arduino Uno:
An Arduino is a microcontroller board used for building digital devices and interactive objects.
- A Microcontroller based on `ATmega328P`chip
- It has 14 digital input/output pins, 6 analog input pins
- Supports serial communication protocols such as SPI, I2C, and UAR
- Can be programmed using `Arduino IDE` using `C/C++`
- DC Current per I/O Pin: 20 mA
- DC Current for 3.3V Pin: 50 mA
- Power Sources: 
  - USB connector: USB bus has a voltage range of `4.75 to 5.25` volts. The official Uno boards have a USB-B connector.
  - 5.5mm/2.1mm barrel jack connector: Uno boards support `6 to 20` volts, though `7 to 12`  volts is recommended.
  - VIN pin on shield header: It has a similar voltage range of the barrel jack. Since this pin doesn't have reverse voltage protection, power can be injected or pulled from this pin. When supplying power into VIN pin, an external series diode is required in case barrel jack is used. When board is powered by barrel jack, power can be pulled out of this pin.

#### L293D Motor Driver Shield :
- The L293D shield is a driver board based on the L293D IC that can simultaneously drive four DC motors and two stepper or servo motors.
- This module has a maximum current of 1.2A per channel and will not operate if the voltage is greater than `25v` or less than `4.5v`
- Servo Motor
- 
#### Ultrasonic Sensor :
An ultrasonic sensor is a device that emits high-frequency sound waves and detects the echo reflected back from an object to measure the distance between the sensor and the object. It typically consists of a transmitter, a receiver, and a control circuit. The transmitter emits ultrasonic waves, which bounce off the object and are detected by the receiver. The control circuit calculates the time taken for the waves to travel to the object and back and uses this information to determine the distance to the object. Ultrasonic sensors can operate at frequencies ranging from 20 kHz to several megahertz and can detect objects at a distance of up to several meters.

#### Servo Motor :
A servo motor is a rotary actuator that allows for precise control of angular position, velocity, and acceleration. It consists of a DC motor, gears, and a control circuit. The control circuit receives a signal from a microcontroller or other device, which specifies the desired position of the servo motor. The control circuit then adjusts the speed and direction of the motor to move the shaft to the desired position. Servo motors are commonly used in robotics, automation, and remote-controlled vehicles due to their accuracy and controllability. They can typically rotate up to 180 degrees and can be programmed to move in a specific direction or pattern. Some servo motors also come with feedback mechanisms to provide information about their position and movement.

#### 3.7 Volt Laptop Battery :
- A 3.7 volt battery is a lithium-ion rechargeable battery with a nominal voltage of 3.7 volts.
- It has a capacity ranging from a few hundred to several thousand mAh.
- It is commonly used in portable electronic devices and hobbyist electronics projects.
- It is lightweight and compact, making it ideal for portable applications.

#### Caster Wheel :
- Caster wheels can be used in obstacle-avoiding cars to provide stability and help the robot move smoothly over uneven terrain.
- Caster wheels are typically mounted at the front of the car, and can pivot 360 degrees to enable the car to turn quickly and easily.

#### BO Motor :
A BO motor is a type of electric motor that is powered by a rechargeable battery.
- Rated Speed : 100 RPM
- Rated Torque : 1 Kg-cm
- Input Voltage: 3~12 volt
- No Load Current : 40-180 mA

#### 4.7 ohm,5 watt Resistor :
- We used it in series with the Motors to protect the 
motor and the motor driver

#### 100k Ohm Resistor :
- We use this to protect the LED used to indicate if the current
is flowing.