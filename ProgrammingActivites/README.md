# Programming Activities

This folder contains a series of small MicroPython programs that introduce basic hardware and software concepts using a board such as an Arduino-compatible microcontroller. Each file demonstrates a different idea, from printing text to controlling LEDs and motors.

## Project Files

### Project1.py
Prints the message `hello lehigh world` to the console. This is a simple intro program used to verify that Python/MicroPython is running correctly.

### Project2.py
Prints a blank line and then displays the name `Bryan Chuya`. It is a basic example of output formatting in MicroPython.

### Project3.py
Creates a variable named `name` and stores the value `Bryan Chuya`. The program then prints the variable, showing how strings are stored and displayed in Python.

### Project4.py
Controls the built-in LED by turning it on and off in a repeating loop. The LED stays on for 0.25 seconds and off for 0.25 seconds, which is a simple blinking example.

### alarmsystem.py
Reads data from a light sensor and checks whether a button is being pressed. The green LED turns on when the room is bright enough, and the yellow LED turns on only when both conditions are true: the button is pressed and the light level is high. This acts like a basic light-based alarm or alert system.

### servo1.py
Uses a servo motor and a push button to move the motor between 0° and 180°. Each time the button is pressed, the servo switches position. The code includes a short delay to debounce the button so it does not trigger multiple times from one press.

## Summary
These programs together cover fundamental programming concepts such as:
- printing text
- using variables and strings
- controlling LEDs
- reading sensor input
- reacting to button presses
- controlling a servo motor
