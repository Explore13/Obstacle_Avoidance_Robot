```c++
//including the libraries
#include <AFMotor.h>
#include <NewPing.h>
#include <Servo.h>

//defining pins and variables
#define TRIG_PIN A4
#define ECHO_PIN A5
#define MAX_DISTANCE 200
#define MAX_SPEED 200 // sets speed of DC  motors
#define MAX_SPEED_OFFSET 20

#define turn_amount 300

//defining motors,servo,sensor
NewPing sonar(TRIG_PIN, ECHO_PIN, MAX_DISTANCE);
AF_DCMotor motor1(3, MOTOR12_8KHZ);
AF_DCMotor motor2(4, MOTOR12_8KHZ);
Servo myservo;

//defining global variables
boolean goesForward=false;
int distance = 100;
int speedSet = 0;

void setup() {
Serial.begin(9600);
myservo.attach(10);
myservo.write(90);
pinMode(12,OUTPUT);
delay(2000);
distance = readPing();
delay(100);
distance = readPing();
delay(100);
distance = readPing();
delay(100);
distance = readPing();
delay(100);
}

void loop() {
int distanceR = 0;
int distanceL =  0;
delay(40);
Serial.println(distance);

if(distance<=30)
{
Serial.println("Object Detected");
detectLight();
moveStop();
delay(100);
moveBackward();
delay(300);
moveStop();
delay(200);
distanceR = lookRight();
Serial.print("Distance Right = ");
Serial.println(distanceR);
delay(200);
distanceL = lookLeft();
Serial.print("Distance Left = ");
Serial.println(distanceL);
delay(200);

if(distanceR>=distanceL)
{
turnRight();
moveStop();
}
else
{
turnLeft();
moveStop();
}
}
else
{
moveForward();
}

//reseting the variable after the operations
distance = readPing();
}

void detectLight(){
Serial.println("detectLight on ");
digitalWrite(12,HIGH);

}

int lookRight()
{
myservo.write(0);
delay(500);
int distance = readPing();
delay(100);
myservo.write(90);
return distance;
}

int lookLeft()
{
myservo.write(180);
delay(500);
int distance = readPing();
delay(100);
myservo.write(90);
return distance;
delay(100);
}

int readPing() {
delay(70);
digitalWrite(12,LOW);
int cm = sonar.ping_cm();
if(cm==0)
{
cm = 250;
}
return cm;
}

void moveStop() {
motor1.run(RELEASE);
motor2.run(RELEASE);
}

void moveForward() {

if(!goesForward)
{
goesForward=true;
motor1.run(FORWARD);
motor2.run(FORWARD);
for (speedSet = 0; speedSet < MAX_SPEED; speedSet +=2) // slowly bring the speed up to avoid loading down the batteries too quickly
{
motor1.setSpeed(speedSet);
motor2.setSpeed(speedSet+MAX_SPEED_OFFSET);
delay(5);
}
}
}

void moveBackward() {
goesForward=false;
motor1.run(BACKWARD);
motor2.run(BACKWARD);
for (speedSet = 0; speedSet < MAX_SPEED; speedSet +=2) // slowly bring the speed up to avoid loading down the batteries too quickly
{
motor1.setSpeed(speedSet);
motor2.setSpeed(speedSet+MAX_SPEED_OFFSET);
delay(5);
}
}

void turnRight() {
Serial.println("Turning Right");
motor1.run(FORWARD);
motor2.run(BACKWARD);
delay(turn_amount);
motor1.run(FORWARD);
motor2.run(FORWARD);
}

void turnLeft() {
Serial.println("Turning Left");
motor1.run(BACKWARD);
motor2.run(FORWARD);
delay(turn_amount);
motor1.run(FORWARD);
motor2.run(FORWARD);
}
```
## Code Explanation :
The robot car is equipped with an ultrasonic sensor that detects the distance to obstacles in front of it, and two DC motors that allow it to move in different directions. The code includes several functions:

- `setup()`: Initializes the serial communication, servo motor, and ultrasonic sensor.

- `loop()`: This is the main function that runs continuously while the robot is turned on. It first reads the distance to obstacles using the ultrasonic sensor. If an obstacle is detected within 30 cm, the robot stops and backs up. Then, it turns its head right and left to check the distance to obstacles in those directions, and then turns in the direction with the most clearance. If no obstacles are detected within 30 cm, the robot moves forward.

- `moveForward()`: This function makes the robot move forward at a set speed.

- `moveBackward()`: This function makes the robot move backward at a set speed.

- `moveStop()`: This function stops the robot.

- `turnRight()`: This function turns the robot to the right.

- `turnLeft()`: This function turns the robot to the left.

- `detectLight()`: This function turns on a LED to indicate that an obstacle has been detected.

- `lookRight()`: This function turns the robot's head to the right and returns the distance to the closest obstacle.

- `lookLeft()`: This function turns the robot's head to the left and returns the distance to the closest obstacle.




## Note :
- You must  have to add Libraries in the Arduino IDE.
- To add the Library you have to follow the steps:
    - Open `Arduino IDE`
    - Go to `Sketch`
    - Click on `Include Library`
    - Select `Add .ZIP Library...`
- ZIP file of the library is added in `Code & Libraries` Folder in this repo..