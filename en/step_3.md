## Coding a motor

--- task ---

Once you have your motor connected, open a new Python file.

--- /task ---


### Motor class

You can use the built-in `Motor` class to control motors.


--- task ---

Import the `Motor` class:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 
---
from gpiozero import Motor
--- /code ---

--- /task ---

--- task ---

Now create a `Motor` instance using the pin numbers for each motor:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 3-4
---
from gpiozero import Motor

motor1 = Motor(4, 14)
motor2 = Motor(17, 27)

--- /code ---


Note: to make it easier to see which pin is which, you can use `Motor(forward=4, backward=14)` for future reference.

--- /task ---

--- task ---

Now drive one of the motors forward using the following code:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 6
---
from gpiozero import Motor

motor1 = Motor(4, 14)
motor2 = Motor(17, 27)

motor1.forward()

--- /code ---


--- /task ---

--- task ---

And the other backwards:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 7
---
from gpiozero import Motor

motor1 = Motor(4, 14)
motor2 = Motor(17, 27)

motor1.forward()
motor2.backward()

--- /code ---


--- /task ---

--- task ---

Or try half speed:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 7
---
from gpiozero import Motor

motor1 = Motor(4, 14)
motor2 = Motor(17, 27)

motor1.forward(0.5)
motor2.backward(0.5)

--- /code ---


--- /task ---

The `Motor` class also allows you to reverse the motor's direction. 

--- task ---

Try using this loop:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 2, 10-13
---
from gpiozero import Motor
from time import sleep  #Sleep allows us to set running times for commands

motor1 = Motor(4, 14)
motor2 = Motor(17, 27)

motor1.forward()
motor2.backward()

while True:   #Repeat this section forever
    sleep(5)  #Continue for 5 seconds
    motor1.reverse()
    motor2.reverse()

--- /code ---


This will make the motors spin in opposite directions, then switch every five seconds. Press **Stop** to exit the loop.

--- /task ---
