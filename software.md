# Software installation

You'll need to make sure you have the following packages installed to proceed with the worksheet:

- smbus for Python 2
- PyGlow for Python 2

You'll need to be online to install packages.

First update and upgrade your system. Open the terminal by clicking on Main Menu, Accessories and then selecting Terminal. Enter the following commands:

```bash
sudo apt-get update
sudo apt-get upgrade
```

Install `smbus` with the following command:

```bash
sudo apt-get install python-smbus
```

Check you have it installed correctly by entering:

```bash
sudo python -c "import smbus"
```

If you get an error saying `No module named 'smbus'` then check you have entered the commands above correctly.

You'll need to create a `pyglow` folder and download the PyGlow module and a test file from GitHub with the following commands:

```bash
mkdir pyglow
cd pyglow
wget http://goo.gl/zQ3CHB -O PyGlow.py --no-check-certificate
wget http://goo.gl/18fwzn -O test.py --no-check-certificate
```

To test this works, enter:

```bash
sudo python test.py
```

It should ask you to enter a series of colour values. If you get an error, check you have entered the commands above correctly.

## Enable i2c driver modules

You'll also need to enable the i2c driver module.

1. Edit the modules configuration file:

    ```bash
    sudo nano /etc/modules
    ```

1. Then either **add** or ensure the following lines are at the end of the file:

    ```bash
    i2c-dev
    i2c-bcm2708
    ```

    Press `CTRL + X`, followed by `Y` and `Enter` to save your changes.

1. You may also need to ensure the driver modules are not blacklisted by editing the blacklist configuration file. Type:

    ```bash
    sudo nano /etc/modprobe.d/raspi-blacklist.conf
    ```

1. Comment out the following lines, by adding a hash symbol `#` at the start of the line. So:

    ```bash
    blacklist spi-bcm2708
    blacklist i2c-bcm2708
    ```

    ...should become...

    ```bash
    #blacklist spi-bcm2708
    #blacklist i2c-bcm2708
    ```

    Then save and exit by pressing `CTRL` and `X`, followed by `Y` and `Enter`
