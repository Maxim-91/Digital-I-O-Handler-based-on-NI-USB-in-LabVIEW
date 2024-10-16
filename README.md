# NI-USB-600x Digital IO Handler

**NI-USB-600x Digital IO Handler** is a LabVIEW-based application that utilizes the NI-USB-600x series hardware for performing digital input and output operations. This program uses NI-DAQmx for handling digital signals, allowing users to write and read digital signals from specific ports.

## Features:
- **Digital Output (DO)**: Writes digital signals to a specified digital output port using the NI-USB-600x device.
- **Digital Input (DI)**: Reads digital signals from the input port and displays the data in real-time.
- **Configurable Timings**: The program allows for setting loop timings for consistent data writing and reading.

## Components:
- `запис цифрових.vi` (Digital Output Writer):
  - The `Dev1/port0/line0` is used to send digital signals.
  - A boolean signal is generated and sent to the output in a loop. The user can specify the rate at which signals are generated.
  - The loop continuously updates the output with digital values every 1000 ms.
  
- `зчитування цифрових.vi` (Digital Input Reader):
  - This program reads digital input values from two digital lines (`Dev1/port0/line0` and `Dev1/port0/line1`).
  - The input values are processed and displayed on the user interface. A loop reads the data every 200 ms.

## How It Works:
1. **Digital Output**:
   - The user can configure the output channel (`Dev1/port0/line0`) to send a digital signal.
   - The program writes a boolean signal (true/false) to the digital output in a loop at defined intervals.
  
2. **Digital Input**:
   - The program reads from two input channels, `Dev1/port0/line0` and `Dev1/port0/line1`.
   - The input values are read, processed, and displayed in real-time.
   
3. **Stop Condition**:
   - The program includes a `stop` button to safely terminate the execution of the digital read/write processes.

## Requirements:
- LabVIEW (with NI-DAQmx drivers installed)
- NI-USB-600x device (e.g., USB-6008, USB-6009)
- Proper wiring to the digital input/output terminals

## Usage:
1. **Digital Output**:
   - Set up the digital output terminal on the NI-USB-600x and ensure it is connected to the appropriate hardware.
   - Run the `запис цифрових.vi` to start sending digital signals.
   - The program will output a digital boolean signal to `Dev1/port0/line0`.

2. **Digital Input**:
   - Configure the input terminals to the corresponding ports (`Dev1/port0/line0` and `Dev1/port0/line1`).
   - Run the `зчитування цифрових.vi` to read the incoming digital signals.
   - The signals will be displayed on the user interface in real-time.

3. **Stop the Program**:
   - Both digital writing and reading operations can be stopped by pressing the `stop` button provided in the respective VIs.

## Example:
- Use `запис цифрових.vi` to output a digital high (1) or low (0) signal to `Dev1/port0/line0`.
- Simultaneously, use `зчитування цифрових.vi` to read incoming digital signals from the two lines (`Dev1/port0/line0` and `Dev1/port0/line1`).

## Troubleshooting:
- Ensure the NI-DAQmx driver is installed and recognized by LabVIEW.
- Verify the correct port and line configuration for both input and output channels.
- Confirm that the NI-USB-600x device is connected and properly powered.
