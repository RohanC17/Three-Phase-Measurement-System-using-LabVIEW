# Design of a Three-Phase AC Measurement System using LabVIEW & Arduino

This repository contains a complete Computer-Aided Data Acquisition (CADA) system designed to measure, visualize, and analyze three-phase Alternating Current (AC) signals in real-time. 

The project leverages an **Arduino Mega 2560** for hardware interfacing and **LabVIEW 2020** for advanced graphical data processing and visualization.

## 📋 Project Overview
The objective is to design a simulation and measurement system for a Three-Phase Power system to study its behavior by adjusting parameters within LabVIEW. 

### Key Features
* **Real-time Acquisition**: Interfacing with Arduino via the Digilent LINX toolkit.
* **Virtual Oscilloscope**: Visualizes three reference voltage waves (230V, 50Hz) alongside measured current waves.
* **Polar Plot (Phasor Diagram)**: A dynamic XY graph representing magnitude and the 120° phase separation.
* **Parameter Simulation**: Utilizes potentiometers to simulate current (0–16A) and phase shifts (±25°).

## 🛠️ Hardware Requirements
* **Microcontroller**: Arduino Mega 2560 (ATmega 2560 based).
* **Inputs**: 6x Potentiometers wired to Analog Pins **8, 9, 10, 11, 12, and 13**.
* **Interface**: USB Cable for Serial communication.

## 💻 Software Components & VIs
The program logic is distributed across the uploaded `.vi` and sub-VI files. Key components include:
* **Digilent LINX**: Uses `LINX Open.VI` for communication and `LINX Analog Read.VI` for data acquisition.
* **Simulate Signal VI**: Generates reference sinusoidal waveforms at 50Hz and 230V.
* **Tone Measurement VI**: Extracts peak amplitude and phase for the Polar Plot.
* **Merge/Split Signals**: Combines individual phases into a composite signal for the Oscilloscope display.
* **While Loop & Stop Control**: Manages continuous real-time execution and safe termination.

## 🚀 How to Use This Repository

### 1. Hardware Setup
1. Connect your Arduino Mega 2560 to your PC.
2. Wire potentiometers to the following Analog pins:
   * **Pins 8, 10, 12**: Amplitude control for Phases 1, 2, and 3.
   * **Pins 9, 11, 13**: Phase shift control for Phases 1, 2, and 3.

### 2. Running the Program
1. Open the main `.vi` file in LabVIEW 2020 or later.
2. Select the correct **Serial Port** (e.g., COM3) on the Front Panel.
3. Click the **START** button to begin the simulation.
4. Navigate the tabs (**Phasor Diagram**, **Oscilloscope**, **Input Data**) to monitor real-time variations.

## 📐 Technical Implementation
The system maps 0–5V potentiometer signals to physical units:
* **Current Scaling**: Analog input is multiplied by 3.2 to represent 0–16A.
* **Phase Scaling**: Input is offset by 2.5 and multiplied by 10 to achieve a ±25° range.
* **Vector Conversion**: Phase is converted to radians to compute X and Y components via Cosine and Sine blocks for the XY Graph.

## 📚 References
* [Difference between Single Phase and Three Phase Systems](https://www.electricaltechnology.org/2020/08/difference-single-phase-three-phase.html)
* [Arduino Mega 2560 Hardware Documentation](https://docs.arduino.cc/hardware/mega-2560/)
* [NI LabVIEW Front Panel & Block Diagram Documentation](https://www.ni.com/en/support/documentation.html)

---
*Developed by Sai Ganesh Abburi and Rohan Channakeshavaiah at Hochschule Bremen.*
