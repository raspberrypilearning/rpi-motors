## Robot class

If you had a robot with two wheels you would want to control the two motors together, rather than separately, just like you did for the two pins of each motor. Luckily, there's also a `Robot` class in GPIO Zero.

--- task ---

Import the `Robot` class:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights:
---
from gpiozero import Robot

--- /code ---


--- /task ---

--- task ---

Now create a `Robot` instance using the pin numbers for each motor:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 3
---
from gpiozero import Robot

robot = Robot((4, 14), (17, 27))

--- /code ---


Note: to make it easier to see which pin is which, you can use `Robot(left=(4, 14), right=(17, 27))` for future reference.

--- /task ---

--- task ---

Now drive the motors forward using the following code:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 5
---
from gpiozero import Robot

robot = Robot((4, 14), (17, 27))

robot.forward()

--- /code ---


Both motors should now be driving forwards.

--- /task ---

--- task ---

Or make them drive backwards with:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 5
line_highlights:
---
robot.backward()

--- /code ---


--- /task ---

--- task ---

Try using `reverse` a few times to see what happens:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 5-7
---
from gpiozero import Robot

robot = Robot((4, 14), (17, 27))

robot.reverse()
robot.reverse()
robot.reverse()

--- /code ---


--- /task ---

--- task ---

Or try driving forward at half speed:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights:
---
robot.forward(0.5)

--- /code ---


--- /task ---

--- task ---

That's not all! What would happen if the left wheel went forwards and the right wheel went backwards? The robot would turn right. 

Try it using `robot.right()`

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 5
---
from gpiozero import Robot

robot = Robot((4, 14), (17, 27))

robot.right()

--- /code ---


--- /task ---

--- task ---

Then try this:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 2, 6-12
---
from gpiozero import Robot
from time import sleep

robot = Robot((4, 14), (17, 27))

robot.forward(0.5)
sleep(1) # Make the forward command last for 1 second
robot.right()
robot.forward()
sleep(1)
robot.left()
robot.forward()

--- /code ---


--- /task ---

--- task ---

Now stop the robot:

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 13-14
---
from gpiozero import Robot
from time import sleep

robot = Robot((4, 14), (17, 27))

robot.forward(1)
sleep(0.5)
robot.right()
robot.forward()
sleep(1)
robot.left()
robot.forward()
sleep(1)
robot.stop()

--- /code ---


--- /task ---