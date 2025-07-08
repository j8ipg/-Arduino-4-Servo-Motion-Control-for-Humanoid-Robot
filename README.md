# 🤖 Arduino 4-Servo Motion Control for Humanoid Robot
![Super Tumelo-Maimu](https://github.com/user-attachments/assets/829185bf-e4ed-4f3e-bf8d-ef7448e1ba80)
## 📋 Description
This project demonstrates how to control four servo motors on a humanoid robot using Arduino. The program performs the following sequence:

1. All servos perform a sweeping motion (0° to 180° and back) for approximately **2 seconds**.
2. After the sweep, all servos **lock and hold at 90 degrees**.

It also includes a basic algorithm for simulating humanoid walking behavior using servo motors.

---

## 🔧 Hardware Used
- Arduino UNO (or compatible)
- 4 x Servo Motors (e.g., SG90)
- Jumper Wires
- Optional: External Power Supply for servos

---

## 📜 Code Behavior

- **Phase 1 – Sweep Motion:**
  All four servos move from 0° to 180° and back for ~2 seconds using a loop.

- **Phase 2 – Hold Position:**
  All servos are set to 90°, simulating a neutral or standing posture.

---

## 🚶‍♂️ Walking Motion Algorithm for Humanoid Robot

To simulate a basic humanoid walking motion, the following steps can be programmed:

1. **Start in Neutral Position:**
   - All joints set to 90°.

2. **Step with Right Leg:**
   - Lift right leg using hip and knee servos.
   - Slightly tilt torso to the left to maintain balance.
   - Swing leg forward and place it down.

3. **Return to Balance:**
   - Center the body posture with both feet on the ground.

4. **Step with Left Leg:**
   - Repeat mirrored motion on the left side.

5. **Loop:**
   - Alternate both sides to simulate continuous walking.

> Fine-tuning servo angles and adding delays between motions is essential for balance and realism.

---

## 🧠 Arduino Code – `servo_walk.ino`

```cpp
#include <Servo.h>

// Create 4 servo objects
Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;

void setup() {
  // Attach each servo to its pin
  servo1.attach(6);
  servo2.attach(9);
  servo3.attach(3);
  servo4.attach(11);

  unsigned long startTime = millis();
  
  // Sweep motion for 2 seconds
  while (millis() - startTime < 2000) {
    for (int angle = 0; angle <= 180; angle++) {
      servo1.write(angle);
      servo2.write(angle);
      servo3.write(angle);
      servo4.write(angle);
      delay(5);
    }
    for (int angle = 180; angle >= 0; angle--) {
      servo1.write(angle);
      servo2.write(angle);
      servo3.write(angle);
      servo4.write(angle);
      delay(5);
    }
  }

  // Hold all servos at 90°
  servo1.write(90);
  servo2.write(90);
  servo3.write(90);
  servo4.write(90);
}

void loop() {
  // Do nothing, servos hold at 90 degrees
}
```



## 📷 Preview
in tinkercad:
![Super Tumelo-Maimu](https://github.com/user-attachments/assets/829185bf-e4ed-4f3e-bf8d-ef7448e1ba80)

In reality:
pic:  ![4servo pic](https://github.com/user-attachments/assets/fd40f897-354f-4b4d-bb0e-3274da60658d)



vid:  https://github.com/user-attachments/assets/7887c846-acb7-4aa6-a05b-c3d868323232





https://github.com/user-attachments/assets/e645ce67-960e-4b87-853e-81cf73950a46

https://github.com/user-attachments/assets/7d9dee0a-f1ae-41c9-b111-c06512b91f8d




