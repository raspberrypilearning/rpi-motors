## Robot class

If you had a robot with two wheels you would want to control the two motors together, rather than separately, just like you did for the two pins of each motor. Luckily, there's also a `Robot` class in GPIO Zero.

--- task ---

Import the `Robot` class:

    ```python
    from gpiozero import Robot
    ```

--- /task ---

--- task ---

Now create a `Robot` instance using the pin numbers for each motor:

    ```python
    robot = Robot((4, 14), (17, 27))
    ```

    Note: to make it easier to see which pin is which, you can use `Robot(left=(4, 14), right=(17, 27))` for future reference.

--- /task ---

--- task ---

Now drive one of the motors forward using the following code:

    ```python
    robot.forward()
    ```

    Both motors should now be driving forwards.

--- /task ---

--- task ---

And backwards:

    ```python
    robot.backward()
    ```

Both motors should now be driving backwards.

--- /task ---

--- task ---

Try reverse a few times:

    ```python
    robot.reverse()
    robot.reverse()
    robot.reverse()
    ```

--- /task ---

--- task ---

Or try half speed:

    ```python
    robot.forward(0.5)
    ```

--- /task ---

--- task ---

That's not all! What would happen if the left wheel went forwards and the right wheel went backwards? The robot would turn right. Try it:

    ```python
    robot.right()
    ```

--- /task ---

--- task ---

Then try this:

    ```python
    robot.left()
    ```

--- /task ---

--- task ---

Now stop the robot:

    ```python
    robot.stop()
    ```

--- /task ---