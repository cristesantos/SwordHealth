# SwordHealth
Technical challenge for embedded software engineer position
Author: Cristiane Santos
Creation date: 23/02/2025
Source: source cloned from https://github.com/zephyrproject-rtos/zephyr

# Zephyr T2 Topology Setup

This repository sets up Zephyr with a T2 topology

SwordHealth/
├── hello_world/
│   ├── src/
│   │   ├── main.c
│   ├── CMakeLists.txt
│   ├── prj.conf
│   ├── sample.yaml
├── README.md
├── west.yml
└── .gitignore

# Zephyr Hello World with BMI270

This application integrates the BMI270 IMU sensor to read accelerometer, gyroscope, and step count data. Outputs are displayed on the console every second.

## HW Prerequisites

- BMI270 sensor connected to your board via I2C.
- Board with I2C support and Zephyr installed as per the [Zephyr Getting Started Guide](https://docs.zephyrproject.org/latest/develop/getting_started/index.html).

## FW Prerequisites
Follow the instructions at https://docs.zephyrproject.org/latest/develop/getting_started/index.html to set the environment

- **OS**: Linux, macOS, or Windows with WSL
- **Toolchain**: Zephyr SDK (instructions (https://docs.zephyrproject.org/latest/develop/toolchains/zephyr_sdk.html#toolchain-zephyr-sdk-install))
- **Python**: Version 3.x with `west` tool installed (`pip install west`)
- **Git**: Installed and configured

## Setup Instructions
1. Clone the repository:
    ```bash
    git clone https://github.com/cristesantos/SwordHealth.git
    cd SwordHealth/hello_world
    ```

2. Initialize and update the West manifest:
    ```bash
    west init .
    west update
    ```

3. Export environment variables for Zephyr:
    ```bash
    source zephyr/zephyr-env.sh
    ```

4. Build the Hello World application:
    ```bash
    cd applications/hello_world
    west build -b <board-name> .
    ```

   Replace `<board-name>` with the target board (e.g., `nrf52840dk_nrf52840`).

5. Flash the application to the board:
    ```bash
    west flash
    ```

6. Check the console:
    ```
    Hello, World from Zephyr!
    ```

## Project Structure
- **applications/hello_world**: Contains the Hello World application.
- **west.yml**: Manifest file to organize modules and dependencies.
- **README.md**: Setup and usage instructions.



