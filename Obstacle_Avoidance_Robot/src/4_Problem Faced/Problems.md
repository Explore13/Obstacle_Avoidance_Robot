## 2 MOTORS VS 4 MOTORS

- You can ask me why I do not use 4 motors in the bot.
- If you use four motors then your battery will run out fastly.
- Motor Driver may heat more.
- There is a chance not to take turn to left or right smoothly if you use 4 motors.

##### At first, we use 4 motors in our bot but the movement (left and right) was not so smooth as we want.So,we use 2 motor and 1 caster wheel.After that the movement (left/right) becomes so smooth. 

## MOTOR PROBLEM

- You can control voltage from the outside.
- But beside the voltage there is also an important parameter called `Current`.
- You do not know how many current is taken by the BO Motors.
- It is not possible to check each and every motor before using.
- So, I suggest you to add `4.7 ohm/5 watt` Resistor in series with the motor.
- Note it that value of the resistance depends upon the Voltage Source.
- If you use two `3.7 volt` battery then `4.7 ohm/5 watt` is OK.


## SHORT CIRCUIT

- Please do not make any `Short Circuit` while soldering the Motor Driver Shield or Arduino Uno.
- Otherwise,the components will burn out.

##### Once we mistakenly made a short circuit in Arduino in another project.Our components burnt out and we got a shock of Rs.1500/-
                 STAY CALM WHILE SOLDERING. 