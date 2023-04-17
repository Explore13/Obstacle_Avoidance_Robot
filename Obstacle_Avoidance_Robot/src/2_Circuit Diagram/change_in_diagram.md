## READ IT CAREFULLY

- If you see the ckt diagram then you can see that 
there I add two motors in M3 and M4 port of L293D Motor driver Shield..
- But I will recommend you to add one motor in M4 and another one in M2 because if we use M3 and M4 pins only then the nearest L293D IC will produce heat and it may damage our motor driver..
- Now,if you use M2 replacing M3 then you have to change the code.
 
##### In the place of `AF_DCMotor motor1(3, MOTOR12_8KHZ);` you have to write `AF_DCMotor motor1(2, MOTOR12_8KHZ);`

- Now, you have to connect a LED which will blink when the bot will detect an Obstacle..

 | LED    | MOTOR DRIVER    |
 |--------|-----------------|
 | -VE    | GND             |
 | +VE<br/>(100 Ohm Resistor in series) | Digital Pin 12  |