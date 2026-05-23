# AIFRIS-STM32
AIFRIS: Bare-Metal Non-Blocking Adaptive Intelligent Framework for Real-time Instrumentation Systems on STM32F103C8 (Blue Pill) using Proteus &amp; GNUPlot.

# AIFRIS: Adaptive Intelligent Framework for Real-time Instrumentation Systems

This project implements an **Adaptive Intelligent Framework for Real-time Instrumentation Systems (AIFRIS)** on the STM32F103C8 (Blue Pill) microcontroller. It focuses on a bare-metal, non-blocking architecture to manage multi-sensor data acquisition and PID adaptive control, replacing heavy RTOS overhead with a lightweight super-loop scheduler.

## Features
- **ADC Polling Sequential:** Efficient data acquisition for PV, Disturbance, and Setpoint.
- **Dual-Mode Adaptive PID:** Intelligent threshold-based switching between Aggressive and Standard PID modes for optimal transient response.
- **Bare-Metal Scheduler:** Deterministic task execution based on `HAL_GetTick()` to prevent simulator freezing.
- **Telemetry Stream:** Non-blocking serial logging for real-time monitoring.

## System Architecture
- **Microcontroller:** STM32F103C8 (ARM Cortex-M3).
- **Toolchain:** STM32CubeMX, Keil uVision, Proteus 8.xx, GNUPlot.

## Documentation
- **Diagrams:** (Include your AIFRIS_block_diagram.drawio.png here)
- **Flowchart:** (Include your AIFRIS_flowchart.drawio.png here)

## How to Run
1. Open the `.pdsprj` file in **Proteus 8.xx**.
2. Flash the `firmware.hex` file to the STM32 Blue Pill model.
3. Observe the **Virtual Terminal** for data logs and the **Oscilloscope** for PWM signals.
4. Export the terminal log to `.dat` and use GNUPlot to visualize the transient response.

## Analysis Results
*(Add your comparison graph here: grafik_perbandingan_PV_2D.png)*

## License
This project is open-source under the MIT License.
