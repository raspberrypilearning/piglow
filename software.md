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

You'll need to create a `pyglow` folder, and download the PyGlow module and a test file from GitHub, with the following commands:

```bash
mkdir pyglow
cd pyglow
wget http://goo.gl/zQ3CHB -O PyGlow.py --no-check-certificate
wget http://goo.gl/18fwzn -O test.py --no-check-certificate
```

## Enable I2C driver modules

You'll also need to enable the I2C driver module.

1. Edit the modules configuration file:

    ```bash
    sudo nano /etc/modules
    ```

1. Then add the following line at the end of the file, if it's not already there:

    ```bash
    i2c-dev
    ```

    Press `CTRL + X`, followed by `Y` and `Enter` to save your changes.
    
1. Enter `sudo raspi-config` to open the Raspberry Pi Configuration Tool.

1. Select `Advanced Options` and then choose `I2C` with the keyboard's up/down keys. Enable the I2C interface and kernel module when prompted, and you'll be prompted to reboot the Pi when finishing.
    
## Test it works

To test this works, enter:

```bash
sudo python test.py
```

It should ask you to enter a series of colour values. If you get an error, check you have entered the commands above correctly.
