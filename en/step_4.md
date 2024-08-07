## Robot class

If you had a robot with two wheels you would want to control the two motors together, rather than separately, just like you did for the two pins of each motor. Luckily, there's also a `Robot` class in GPIO Zero.

+ Import the `Robot` class:

    ```python
    from gpiozero import Robot
    ```

+ Now create a `Robot` instance using the pin numbers for each motor:

    ```python
    robot = Robot((4, 14), (17, 27))
    ```

    Note: to make it easier to see which pin is which, you can use `Robot(left=(4, 14), right=(17, 27))` for future reference.

+ Now drive one of the motors forward using the following code:

    ```python
    robot.forward()
    ```

    Both motors should now be driving forwards.

+ And backwards:

    ```python
    robot.backward()
    ```

    Both motors should now be driving backwards.

+ Try reverse a few times:

    ```python
    robot.reverse()
    robot.reverse()
    robot.reverse()
    ```

+ Or try half speed:

    ```python
    robot.forward(0.5)
    ```

+ That's not all! What would happen if the left wheel went forwards and the right wheel went backwards? The robot would turn right. Try it:

    ```python
    robot.right()
    ```

+ Then try this:

    ```python
    robot.left()
    ```

+ Now stop the robot:

    ```python
    robot.stop()
    ```
