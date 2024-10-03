---
title: 아두이노 자율주행
date: 2022-01-01
---

## 코드 분실로 사진과 텍스트로 대체

Ⅰ) 기술 스택  
사용 언어:  
- C언어

Ⅱ) 주요 기능  
- 휴대폰으로 원격제어 가능  
- 초음파 센서로 감지하여 10미터 앞에 장애물이 있으면 90도 회전 후 1초 쉬고 다시 자율주행  
- 장애물 감지 시 후진 후 90도 회전 가능

Ⅲ) 장비  
- 준비물: L293D Motor Shield, DC Motor 2개, Servo Motor 1개, 초음파 센서 1개, 외부 전원 2개, 아두이노 우노


## Arduino 코드

```cpp
#include <AFMotor.h>
#include <Servo.h> 
#include <NewPing.h>

AF_DCMotor motor1(3);
AF_DCMotor motor2(4);

Servo servo;
const int servoPin = 10;
const int TRIG = A4;
const int ECHO = A5;
const int MAX_DISTANCE = 100;
NewPing sonar(TRIG, ECHO, MAX_DISTANCE);

int speed = 200;
int state = 10;
int angle = 90;

void setup() {
  motor1.setSpeed(speed);
  motor2.setSpeed(speed);
  motor2.run(RELEASE);
  motor2.run(RELEASE);

  servo.attach(servoPin);
  servo.write(angle);
  delay(1000);

  // Start
  motor1.run(FORWARD);
  motor2.run(FORWARD);  
}

void loop() {
  // 초음파 센서 회전
  servo.write(angle);
  delay(50);
  
  int distance = sonar.ping_cm();

  // 장애물 감지
  if (distance > 0 && distance < 15) {
    movePattern(); 
    motor1.run(FORWARD);
    motor2.run(FORWARD);  
  }   

  // 회전 각도
  if (angle == 140) state = -10;    
  else if (angle == 40) state = 10; 
  angle += state;
}

void movePattern() {
  motor1.run(BACKWARD);
  motor2.run(BACKWARD);
  delay(500);   

  if (angle >= 90) {
    motor1.run(FORWARD);
    motor2.run(BACKWARD);
    delay(500);   
  } else {
    motor1.run(BACKWARD);
    motor2.run(FORWARD);
    delay(500);   
  }
  
  angle = 90;
  servo.write(angle);
  delay(100);
}
