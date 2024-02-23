# ROS interface for Geomagic Touch HID
- Note: the touch driver contained in this repository is only for ***Geomagic Touch HID***

- Tested on Ubuntu 20.04 w/ ROS noetic

- This project was modified based on the [ros_geomagic](https://github.com/WPI-AIM/ros_geomagic) repository by WPI AIM lab, for WPI [Medical FUSION Lab](https://wp.wpi.edu/medicalfusionlab/) internal use.

## Installation
- WSL2 user needs to follow this [tutorial](https://learn.microsoft.com/en-us/windows/wsl/connect-usb) first to enable USB device connectivity. (compatibility on WSL2 has not been fully tested)

- place the repository under the ```/src``` folder of a catkin workspace before proceeding to the followings.s

1. install touch driver

    ``` sh
    cd TouchDriver_2023_01_12/
    chmod +x install_haptic_driver
    ./install_haptic_driver
    ```

2. reboot system

3. configure geomagic touch
    
    ``` sh
    cd bin/
    chmod +x Touch_AdvancedConfig
    ./Touch_AdvancedConfig
    ```
    A dialog window will come up where you can find the haptic device by selecting its serial number from the drop-down menu at the top of the GUI. If there is no valid serial number available, navigate to ```~/.3dsystems/config/``` and delete all files under that folder. Then rerun the above command.

4. install openhaptics library

    ``` sh
    ./install-3ds-openhaptics-3.4.sh
    ```
    follow the prompt to install any missing dependencies such as ```libncurses5```

5. build the project

    In the root folder of the catkin workspace:
    ``` sh
    catkin_make
    ```

## Usage
- launch the ROS interface with the Touch device visualized in rViz
    ``` sh
    roslaunch geomagic_control geomagic.launch
    ```

- launch the ROS interface with no visualization
    ``` sh
    roslaunch geomagic_control geomagic_headless.launch
    ```