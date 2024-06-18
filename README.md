# CUBOTone

This project's intended purpose is to solve a Rubiks cube using driver boards, servo motors and a stepper motor that communicates with the Raspberry Pi.

Further robot info at: https://www.instructables.com/Rubik-Cube-Solver-Robot-With-Raspberry-Pi-and-Pica/

An impression of the robot: https://www.youtube.com/watch?v=oYRXe4NyJqs

This README will cover general details on how to run the robot once completely assembled.

---


## Raspberry Pi Setup

SSH into your Pi and open the terminal. You will be cloning the following repository:
```
git clone https://github.com/AndreaFavero71/cubotone.git
```

Once that has been successfully cloned, you will need to enter the folder:
```
cd cubotone/src
```

You will then run the following command to start the setup:
```
sudo ./install/setup-sh
```

This will take about 10 minutes or so depending on internet speed. 

**Note: You may run into an error where OpenCV is missing**
If you do run into this error, follow this [guide](https://fernandezvictor.medium.com/installing-opencv-on-raspberry-pi-3fe36da91e86) and it should help you resolve that issue.

If you are missing any other packages or have outdated packages, perform `sudo apt-get update` command to update current packages.

Once the setup is complete, it will prompt you to reboot the Pi, go ahead and press `Y` and then `Enter`.

---


## Host Computer Setup

We will be using a VNC Viewer when running the Python script on the Raspberry Pi. This allows us to see the images taken of all sides of the cube from the Pi Camera. 

You can download VNC Viewer [here](https://www.realvnc.com/en/connect/download/viewer/).

**Be sure to login to VNC Server with your Raspberry Pi's IP address.**
You can find out what your Raspberry Pi's IP address is with `ifconfig`. You may have to download a package to be able to use the `ifconfig` command if you haven't already yet.
Verify that you can VNC Viewer works by logging in with your username and password.

---


## Running Cubotone

Start by entering into the `src` folder by:
```
cd cubotone/src
```

Start up the virtual environment with the following command:
```
source .virtualenvs/bin/activate
```

Then run the Python script:
```
python Cubotone.py
```

You can then place a scrambled cube in the holder and press the `power` button on the outside of the case. From here, calibration is required in order to successfully run the robot. 

To edit parameters and tune your robot, you can make changes in `Cubotone_settings.txt` and `Cubotone_servos_settings.txt`.

---


## Credits

- Andrea Favero for the amazing [repository](https://github.com/AndreaFavero71/Cubotone) and project idea. The PDF with full instructions can be found [here](https://www.instructables.com/Rubik-Cube-Solver-Robot-With-Raspberry-Pi-and-Pica/).
- Damian Goad for assisting with cutting out the enclosure pieces using CNC machinery.
- Kim Rhodes for being an amazing instructor and constantly guiding all of us towards success.
