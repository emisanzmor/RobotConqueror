# Conqueror Robot Tank

## Description

The Conqueror Robot Tank is an autonomous/remote-controlled vehicle with various functionalities and directional movement. It is composed of tracked motors, sensors, and a microcontroller that allow it to perform tasks such as moving forward, backward, turning, and stopping.

---

## Components & Hardware

- **Chassis**: Tracked Robot Tank
- **Microcontroller**: Raspberry Pi 4 / Arduino / ESP32
- **Motors**: DC motors with motor driver

  - **Sensors**:
    - Ultrasonic Sensor HC-SR04 (used for obstacle detection)
    - Infrared Sensor (used for line-following)

- **Communication**: Via WiFi / Elegoo App / Remote Control
- **Power Supply**: Rechargeable battery (Lipo 11.1 V)

---

## Dependencies

To run this project, install the following Python libraries:

- `pyduinocli`: Used to compile and upload code to the Arduino.
- `pyserial`: Used to detect the serial port connected to the Arduino.

### Installation

```bash
pip install pyduinocli pyserial
```

---

### `RobotController.py`

This file contains the `RobotController` class, which manages robot movement and uploads the code to the Arduino. It also includes the `ArduinoSketchManager` class, which generates the Arduino sketch.

---

## Class Methods

### `RobotController` Class

| Method           | Parameters               | Description                                                                 |
|------------------|---------------------------|-----------------------------------------------------------------------------|
| `move_forward`   | `duration=3`, `power=128` | Moves the robot forward for a set duration and power level.                |
| `move_backward`  | `duration=3`, `power=128` | Moves the robot backward for a set duration and power level.               |
| `turn_left`      | `duration=2`, `power=100` | Turns the robot to the left for a set duration and power level.            |
| `turn_right`     | `duration=2`, `power=100` | Turns the robot to the right for a set duration and power level.           |
| `stop`           | `duration=2`, `power=50`  | Stops the robot.                                                           |
| `upload_sketch`  | None                      | Compiles and uploads the sketch to the Arduino.                             |

> You can adjust the method parameters as needed.

---

### `ArduinoSketchManager` Class

| Method             | Parameters                     | Description                                                 |
|--------------------|--------------------------------|-------------------------------------------------------------|
| `add_movement`     | `command`, `duration`, `power` | Adds a movement block to the Arduino sketch.                |
| `finalize_sketch`  | None                           | Finalizes the sketch by adding the `loop()` function.       |

---

## Installation

1. Clone the repository:

```bash
git clone https://github.com/TC1001S-2025/Tank.git
```

This repository already includes the necessary libraries for the Conqueror Robot Tank.

2. Install the required dependencies:

```bash
pip install pyduinocli
pip install pyserial
```

---

## Execution

1. Connect your Arduino to the computer.
2. Run the `demo1.py` script to generate the Arduino code and upload it.

```bash
python demo1.py
```

You can also create your own script if needed.

---

## Notes

- Make sure your Arduino is properly connected and the serial port is correctly set.
- The generated Arduino code is saved in: `commands/commands.ino`

---

## License

This project is for educational use. Distributed under the academic course's terms of use.
