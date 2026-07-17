# Arduino-Control-of-Four-Servo-Motors
This project uses an Arduino Uno to control four servo motors simultaneously. The servos move together from 0° to 180°, then from 180° to 0° over a total of 2 seconds. After completing these movements, all four servos stop and remain fixed at 90°. The servo motors are connected to digital pins 6, 9, 10, and 11.

## Components
- Arduino Uno
- 4 × Servo Motors
- Breadboard
- Jumper Wires

## Pin Connections

| Servo Motor | Arduino Pin |
|-------------|-------------|
| Servo 1 | D6 |
| Servo 2 | D9 |
| Servo 3 | D10 |
| Servo 4 | D11 |
<img width="520" height="313" alt="image" src="https://github.com/user-attachments/assets/bf8645a4-fe4c-4b42-90fd-0da3183daeea" />

Power connections:
- Red wire → 5V
- Black wire → GND
- Orange wire → Signal Pin
- brown wire → Negitive 
- yellow wire →postive

## Program Behavior

The program performs the following sequence:

1. All four servo motors move to **180°**.
2. They then move to **0°**.
3. Finally, all servos stop and remain at **90°**.

The first two movements take a total of **2 seconds**, after which the motors stay fixed at **90°**.
# video
in the file

## Arduino Code

```cpp
#include <Servo.h>

Servo servo1, servo2, servo3, servo4;

void moveAll(int angle) {
  servo1.write(angle);
  servo2.write(angle);
  servo3.write(angle);
  servo4.write(angle);
}

void setup() {
  servo1.attach(6);
  servo2.attach(9);
  servo3.attach(10);
  servo4.attach(11);

  moveAll(180);
  delay(1000);

  moveAll(0);
  delay(1000);

  moveAll(90);
}

void loop() {
}
```

## Expected Output

- Four servo motors move together to **180°**.
- They move back to **0°**.
- They stop and remain at **90°**.
- No further movement occurs after reaching **90°**.
- 
