# Real-Time Operating System (RTOS) Development

## Overview
This project focuses on developing a Real-Time Operating System (RTOS) from the ground up, providing an in-depth understanding of embedded systems and OS-level programming. The RTOS will incorporate threading, scheduling, memory protection, and inter-thread communication, enabling users to explore the fundamental building blocks of real-time computing.

## Table of Contents
- [Introduction](#introduction)
- [Project Scope](#project-scope)
- [System Requirements](#system-requirements)
- [Project Setup](#project-setup)
- [RTOS Architecture](#rtos-architecture)
- [Modules and Features](#modules-and-features)
- [Building and Running](#building-and-running)
- [Testing](#testing)
- [Contributors](#contributors)
- [License](#license)

## Introduction
A Real-Time Operating System (RTOS) is an embedded OS designed to handle real-time constraints, ensuring that tasks execute within strict time boundaries. Unlike general-purpose operating systems, an RTOS prioritizes predictability and reliability over throughput and resource utilization.

This project will guide users through building a basic yet functional RTOS that includes task management, scheduling, and hardware interfacing. The project is designed for educational purposes and aims to provide hands-on experience in kernel development.

## Project Scope
This RTOS project will implement:
- **Threading Support**: Managing multiple concurrent threads.
- **Context Switching**: Efficiently switching between tasks.
- **Time Management**: Implementing a round-robin scheduler and preemptive scheduling.
- **Interrupt Handling**: Handling system calls and external events.
- **Memory Protection**: Ensuring safe memory access across tasks.
- **Inter-Thread Communication**: Implementing mechanisms like message queues and mutexes.

## System Requirements
### Hardware:
- Microcontroller: **NXP LPC1768 (ARM Cortex-M3)**
- Keil MCB 1700 Development Board
- UART interface for serial communication

### Software:
- **Keil uVision 5** (for project setup and debugging)
- **PuTTY** (for serial communication testing)
- **GCC ARM Embedded Toolchain** (for compilation)

## Project Setup
1. **Install Required Software**:
   - Install **Keil uVision 5**.
   - Install the **GCC ARM Embedded Toolchain**.
   - Install **PuTTY** for serial debugging.

2. **Clone the Repository**:
   ```sh
   git clone https://github.com/yourusername/RTOS-Kernel.git
   cd RTOS-Kernel
   ```

3. **Set Up the Microcontroller**:
   - Connect the Keil MCB 1700 board to your PC via USB.
   - Open Keil uVision and create a new project for **NXP LPC1768**.
   - Configure the compiler settings to enable **MicroLIB**.
   - Include `lpc17xx.h` for GPIO and peripheral interfacing.

4. **Build the Project**:
   - Compile the project in **Keil uVision**.
   - Load the compiled firmware onto the microcontroller.

## RTOS Architecture
The RTOS consists of the following components:

1. **Kernel**:
   - Core component managing task execution and resource allocation.
   - Handles context switching and scheduling.

2. **Scheduler**:
   - Implements round-robin and preemptive scheduling.
   - Manages task priorities and execution order.

3. **Interrupt Handling**:
   - Uses **PendSV** for context switching.
   - Implements **SysTick Timer** for scheduling.

4. **Memory Management**:
   - Manages stack and heap allocations.
   - Implements dynamic memory allocation using `malloc()` and `free()`.

## Modules and Features
| Feature | Description |
|---------|-------------|
| **Thread Management** | Supports multiple tasks with individual stacks. |
| **Round-Robin Scheduler** | Ensures fair execution time for tasks. |
| **Preemptive Scheduling** | Uses time slices to switch tasks. |
| **Interrupt Handling** | Handles system calls and hardware interrupts. |
| **Memory Protection** | Prevents tasks from interfering with each other. |
| **Mutexes** | Provides inter-task synchronization. |
| **Message Queues** | Enables safe communication between tasks. |

## Building and Running
### Compiling the RTOS
To build the RTOS, run:
```sh
make all
```

### Flashing the Microcontroller
To upload the compiled firmware:
1. Connect the microcontroller to the PC.
2. Open Keil uVision and select **Load**.
3. Press the reset button on the board to start execution.

## Testing
### Basic Functionality
1. **Verify Serial Communication**:
   - Open PuTTY and connect to the correct COM port.
   - Set the baud rate to **115200**.
   - Check if the RTOS prints initialization messages.

2. **Check Task Scheduling**:
   - Create multiple tasks and assign different priorities.
   - Monitor task execution order via serial debug output.

3. **Memory Management**:
   - Allocate and free memory dynamically.
   - Ensure memory leaks do not occur.

4. **Interrupt Handling**:
   - Trigger external interrupts and monitor RTOS response.

## Contributors
- Sean Baker