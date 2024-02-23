# ROS interface for Geomagic Touch HID
- Note: the touch driver contained in this repository is only for Geomagic Touch HID

- Tested on Ubuntu 20.04 w/ ROS noetic

- For [Medical FUSION Lab](https://wp.wpi.edu/medicalfusionlab/) use

## Installation
1. install touch driver

    In the root folder:
    ``` sh
    cd TouchDriver_2023_01_12/
    chmod +x install_haptic_driver
    ./install_haptic_driver
    ```

2. reboot system

3. configure geomagic touch
    
    In the root folder:
    ``` sh
    cd bin/
    chmod +x Touch_AdvancedConfig
    ./Touch_AdvancedConfig
    ```
    A dialog window will come up where you can find the haptic device by selecting its serial number from the drop-down menu at the top of the GUI. If there is no valid serial number available, navigate to ```~/.3dsystems/config/``` and delete all files under that folder. Then rerun the above command.

4. install openhaptics library

## Usage
