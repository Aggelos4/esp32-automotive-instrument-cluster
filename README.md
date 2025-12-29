ESP32 Automotive Instrument Cluster
Overview

This project presents the design and implementation of a custom automotive digital instrument cluster based on an ESP32 microcontroller. The system replaces traditional analog indicators and incandescent warning lamps with OLED graphical displays, designed for a real motorcycle electrical environment.

The project was developed for an Aprilia Pegaso 650 (2002) — a carbureted motorcycle without an ECU — requiring direct acquisition of discrete vehicle signals and robust electrical protection.

The goal was to design a reliable, modular, and expandable automotive electronics system, suitable for real-world use and professional portfolio presentation.

Key Features

ESP32-based embedded architecture

Three OLED displays (SSD1306, 128×32)

Six vehicle indicators displayed simultaneously

I²C display multiplexing using TCA9548A

Optocoupler-isolated vehicle signal inputs

Bitmap-based graphical user interface

Modular and expandable firmware structure

Ignition-controlled power management

Display Layout

Each OLED display is logically divided into two independent regions:

Left half: 64×32 pixels

Right half: 64×32 pixels

This allows two indicators per display, minimizing hardware complexity while maintaining clarity.

Indicator Allocation
Display	Left Indicator	Right Indicator
OLED 1	Oil Pressure	Neutral Gear
OLED 2	Turn Signals	Low Beam
OLED 3	High Beam	Low Fuel
System Architecture

The system architecture follows automotive design principles, emphasizing signal isolation, noise immunity, and modularity.

Main components:

ESP32 microcontroller

TCA9548A I²C multiplexer

3× SSD1306 OLED displays

Optocoupler input stage

Ignition-switched power supply with fuse protection

Refer to the diagram below for the high-level system overview:




Hardware Design
Power Supply

Power sourced from ignition-switched 12V line

Inline automotive blade fuse (1A)

DC/DC regulation to 5V and 3.3V

Decoupling capacitors for transient suppression

Input Protection

All vehicle signals are electrically isolated using optocouplers to protect the ESP32 from:

Voltage spikes

Inductive transients

Ground potential differences

This approach ensures long-term reliability in a motorcycle environment.

Firmware Architecture

The firmware is written using the Arduino IDE and structured with modular design principles:

Centralized configuration

Separate handling of inputs and displays

Clear function-level responsibilities

Prepared for future feature expansion

Core Responsibilities

Read digital vehicle inputs

Manage multiple OLED displays via I²C multiplexer

Render bitmap-based indicators

Ensure synchronized display updates

Development and Testing

Testing was performed incrementally:

Individual OLED validation

I²C multiplexer integration

Bench testing with simulated inputs

Power cycling and stability tests

This staged approach minimized integration risk and improved system robustness.

Expandability

The system was intentionally designed to support future enhancements, including:

Engine RPM measurement

Coolant temperature display

Diagnostic indicators

Data logging

Wireless communication (Bluetooth / Wi-Fi)

The ESP32 platform provides sufficient performance and peripherals to support these features.

Technologies Used

ESP32

Arduino IDE

C / C++

I²C Communication

OLED (SSD1306)

Automotive signal conditioning

Embedded systems design

Project Status

✅ Completed

The system is fully functional and validated through bench testing, with hardware and firmware designed for real-world vehicle integration.

Author

This project was developed as a personal automotive electronics and embedded systems portfolio project.
