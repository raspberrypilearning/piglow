# Getting Started with PiGlow

This project gives you the opportunity to put your PiGlow to good work by programming it using Python. First you will need to set up your Raspberry Pi by configuring some files and downloading some modules. Then you can start to make individual LEDs blink, before getting them to pulse in pretty ways for displays! (ooh - that rhymed)

## Test your PiGlow using the PyGlow Module

1. Open the Terminal application from the desktop or applications menu.

1. Enter `ls` to see the files and folders in your home directory. You should see a `pyglow` folder - if not, please refer to the instructions in the [software installation](software.md) page before continuing.

1. Enter the `pyglow` folder with the command `cd pyglow`.

1. Run the command `ls` again to see what's inside this folder. You should see two files: `PyGlow.py` and `test.py`.

1. Run the test file:

    ```bash
    sudo python test.py
    ```

1. The program will ask you to set a number between `0` (off) and `255` (brightest) for each colour. Type the following values:

    ```python
    White: 10
    Blue: 20
    Green: 30
    Yellow: 40
    Orange: 50
    Red: 60
    All: 1
    ```

Press `Enter` after each one and you should be able to see the PiGlow light up in sequence!

## Creating a PiGlow Program

Now that you have all the files that you need for your PiGlow, it is time to create your very first glowing led program using Python. In this step you will learn how to import the functions that you need from the modules to turn on and off individual LEDs on the PiGlow.

1. Open the Python editor IDLE with the command `sudo idle &`.

1. Once the Python Shell has loaded click on `File` and `New Window` to open a new text editor file.

1. Save this file as `FirstPiGlow.py` by clicking on `File` and `Save As`.

1. Being your program by importing the Pyglow module and the `sleep` function from the `time` module.

    ```python
    from PyGlow import PyGlow
    from time import sleep
    ```

1. Now create a connection to the PiGlow by typing underneath:

    ```python
    pyglow = PyGlow()
    ```

1. Next set all the LEDs on the PiGlow to `0` or **off**:

    ```python
    pyglow.all(0)
    ```

1. We are now going to turn on LED number 1 on the PiGlow for a second and then off again by typing:

    ```python
    pyglow.led(1, 100)
    sleep(1)
    pyglow.led(1, 0)
    sleep(1)
    ```

1. To light up the LEDs add:

    ```python
    pyglow.update_leds()
    ```

1. Save your file with `Ctrl + S` and run with `F5`.

    Make sure you keep an eye on your PiGlow to see if LED 1 lights up!

Now that you have LED1 turning on and off, why not see if you can turn any of the other LEDs on and off in a similar way!

## Add a Loop to make the Lights Flash

In the last step you created a program to turn on and off LED1 on the PiGlow. We can now add a loop to repeatedly turn on and off groups of coloured LEDs.

1. Open the file `FirstPiGlow.py` in `IDLE`.

1. Underneath `pyglow.all(0)` type:

    ```python
    while True:
        pyglow.color("blue", 100)
        sleep(1)
        pyglow.color("blue", 0)
        pyglow.color("red", 100)
        sleep(1)
        pyglow.color("red", 0)
    ```

1. Click `File` and `Save As` and save it as `FlashPiGlow.py`.

1. Run with `F5`.

Can you create a loop where all the LED colours come on in sequence? The colours include:

- "White"
- "Green"
- "Yellow"
- "Orange"
- "Red"
- "Blue"

## Pulsing PiGlow

Finally, why not get your PiGlow pulsing for the ultimate in Raspberry Pi geek chic? We can write a simple program that uses a pulsing function from the PyGlow module.

1. Open a new text editor file in `IDLE`.

1. Type the following code:

    ```python
    from PyGlow import PyGlow
    from time import sleep

    pyglow = PyGlow()

    pyglow.all(0)

    while True:
        pyglow.all(brightness=150, speed=500, pulse=True)
        sleep(1)

    pyglow.update_leds()
    ```

1. Save the file as `pulse.py` by clicking on `File` and `Save As`.

1. Run with `F5`.

## What's next?
- Can you create an original light show using PiGlow?
- Can you use the PiGlow lights to tell you when an event has taken place, like a tweet or email notification?
