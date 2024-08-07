## Coding a motor

--- task ---

Once you have your motor connected, open a new python file.

--- /task ---


### Motor class

You can use the built-in `Motor` class to control motors.


--- task ---

Import the `Motor` class:

    ```python
    from gpiozero import Motor
    ```

--- /task ---

--- task ---

Now create a `Motor` instance using the pin numbers for each motor:

    ```python
    motor1 = Motor(4, 14)
    motor2 = Motor(17, 27)
    ```

Note: to make it easier to see which pin is which, you can use `Motor(forward=4, backward=14)` for future reference.

--- /task ---

--- task ---

Now drive one of the motors forward using the following code:

    ```python
    motor1.forward()
    ```

--- /task ---

--- task ---

And the other backwards:

    ```python
    motor2.backward()
    ```

--- /task ---

--- task ---

Or try half speed:

    ```python
    motor1.forward(0.5)
    motor2.backward(0.5)
    ```

--- /task ---

The `Motor` class also allows you to reverse the motor's direction. 

--- task ---

Try using this loop:

    ```python
    motor1.forward()
    motor2.backward()
    while True:
        sleep(5)
        motor1.reverse()
        motor2.reverse()
    ```

This will make the motors spin in opposite directions, then switch every five seconds. Press **Ctrl C** to exit the loop.

--- /task ---

--- task ---

Now stop the motors:

    ```python
    motor1.stop()
    motor2.stop()
    ```
    
--- /task ---
