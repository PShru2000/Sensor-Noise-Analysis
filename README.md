# In-depth Characterization and Mitigation of IMU Sensor Noise

## Overview

In this project, I focused on understanding and characterizing noise in IMU sensors to enhance sensor selection and performance in robotic applications. I developed a device driver for the VectorNav IMU to facilitate communication over USB serial, collected and analyzed data on rotation, acceleration, magnetometer readings, and rotational rates. Through the use of Allan variance plots, I identified sensor noise parameters and discussed the impact of environmental noise on sensor performance.

## Tasks Completed

- **Developing the Device Driver**: Implemented a Python device driver that communicates with the VectorNav IMU, parsing $VNYMR strings for comprehensive sensor data including acceleration, gyroscopic, orientation, and magnetometer readings.
- **Noise Characterization**: Identified critical IMU parameters such as angle random walk, bias stability, and rate random walk through Allan variance analysis, providing insights into the sensor's performance under various conditions.
- **Environmental Noise Analysis**: Explored and documented the effects of environmental noise sources on the accuracy and reliability of IMU data.

## Key Aspects

- **Setting up Serial Communication**: Established serial port communication at 115200 baudrate to interact with the IMU, ensuring efficient data transfer without relying on external libraries prone to checksum errors.
- **Custom ROS Service**: Created a ROS service named `convert_to_quaternion` for converting Euler angles to quaternions
- **Custom ROS Message**: Designed a `Vectornav.msg` to encapsulate IMU data within ROS, thereby focusing on integration and manipulation of sensor data within the ROS environment
- **Data Rate Configuration**: Configured the VectorNav to output data at 40 Hz directly via register manipulation, ensuring real-time data collection without external delays.
- **Hardware and Software Integration**: Validated the entire setup on the physical VectorNav IMU hardware, following rigorous testing protocols to ensure accuracy and reliability.

## Analysis

- Conducted stationary noise analysis by collecting 5 minutes of data in a controlled environment, minimizing external disturbances to isolate sensor noise.
- Generated time series plots and histograms to visualize gyroscopic, acceleration, and orientation data, calculating mean, median, and standard deviation for each axis to quantify noise levels.
- Utilized Allan variance plots to dissect noise components, extracting parameters that define the sensor's performance, including rate random walk, angle random walk, and bias stability.
- Through comparative analysis of Allan variance plots from multiple datasets, deduced the impact of environmental conditions on sensor noise, aiding in the selection of IMU sensors for specific robotic applications.

## Conclusion

This project highlights the importance of thorough sensor characterization in a system design. By developing a custom device driver and analyzing sensor noise through Allan variance, I gained valuable insights into the selection and optimization of IMU sensors for enhanced navigation and sensing in robotics
