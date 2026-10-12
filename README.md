# Light Following Robot

This is a small Arduino robot that follows light. Two LDR sensors on the front tell it where the light is brighter, and it drives its motors to turn toward that side. Shine a flashlight in front of it and it will chase the beam around.

I made it to learn how sensors, a microcontroller and motors work together, and it is a good first robotics project if you are just starting with Arduino.

## How it works

The two LDRs sit on the left and right sides and measure the light that falls on them. The Arduino reads both values all the time and compares them:

- If the light is stronger on the left, the robot turns left
- If the light is stronger on the right, the robot turns right
- If both sides get the same light, it moves forward
- If neither side sees enough light, it stops

The Arduino does not drive the motors directly. They are connected through an L293D motor driver shield, which supplies the current the motors need and lets them spin both forward and backward.

## Hardware

- Arduino Uno R3
- L293D motor driver shield
- Two LDRs (light dependent resistors)
- Two 10k ohm resistors
- DC gear motors
- 2WD robot chassis
- AA batteries or another power supply
- Jumper wires

Software: Arduino IDE, with the AFMotor library installed for the motor shield.

## Pins

- Left LDR on A0
- Right LDR on A1
- Four motors on the shield, ports M1 to M4, all set to speed 180

## How to run it

1. Install the Adafruit Motor Shield library (AFMotor) from the Library Manager in the Arduino IDE.
2. Mount the shield on the Arduino and connect the motors to it.
3. Wire each LDR with a 10k resistor to the analog pins A0 and A1.
4. Open the code, select Arduino Uno and your port, then upload.
5. Put the robot on the floor and use a flashlight to guide it.

The sensor values are also printed on the Serial Monitor at 9600 baud, which helps a lot when you need to tune the light threshold in the code, since the best value depends on your room and wiring.

## Limitations

- It works best with one light source
- It cannot detect obstacles
- Room light can affect how well it follows

## Ideas for later

- Add an ultrasonic sensor so it avoids obstacles
- Add a third sensor in the middle for smoother steering
- Use it for something like solar panel alignment

## Report

The full report with the circuit diagram is in this repository as final_report-Light-following-car.docx.

## Author

Muneeb Ur Rehman
