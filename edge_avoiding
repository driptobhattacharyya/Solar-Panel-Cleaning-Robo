//including the libraries
#include <AFMotor.h>

//defining pins and variables 
#define lefts A0

//defining motors 
AF_DCMotor motor1(1, MOTOR12_1KHZ);
AF_DCMotor motor2(2, MOTOR12_1KHZ);
AF_DCMotor motor3(3, MOTOR34_1KHZ);
AF_DCMotor motor4(4, MOTOR34_1KHZ);

void setup() {
  //setting the speed of motors
  motor1.setSpeed(100);
  motor2.setSpeed(100);
  motor3.setSpeed(100);
  motor4.setSpeed(100);
  //declaring pin types 
  pinMode(lefts, INPUT);
  //begin serial communication
  Serial.begin(9600);

}

void loop() {
  //printing values of the sensors to the serial monitor 
  Serial.println(analogRead(lefts));
  //
  if (analogRead(lefts) <= 350) {
    //Forward 
    motor1.run(FORWARD);
    motor2.run(FORWARD);
    motor3.run(FORWARD);
    motor4.run(FORWARD);

  }
  //
  else if (!analogRead(lefts) <= 350) {
    //stop-turn-forward 
    //stop 
    motor1.run(RELEASE);
    motor2.run(RELEASE);
    motor3.run(RELEASE);
    motor4.run(RELEASE);
    delay(500);   //
    //backward 
    motor1.run(BACKWARD);
    motor2.run(BACKWARD);
    motor3.run(BACKWARD);
    motor4.run(BACKWARD);
    delay(500);   //
    //turn left 
    motor1.run(FORWARD);
    motor2.run(FORWARD);
    motor3.run(BACKWARD);
    motor4.run(BACKWARD);
    delay(500);   //
    //stop 
    motor1.run(RELEASE);
    motor2.run(RELEASE);
    motor3.run(RELEASE);
    motor4.run(RELEASE);
    delay(500);   //
  }

}
