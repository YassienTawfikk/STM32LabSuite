## STM32LabSuite

---

### Overview

**STM32LabSuite** is a modular umbrella repository featuring three STM32-based embedded systems projects built with the STM32F401VE microcontroller. Designed with real-time control, interrupt-driven behavior, and modular driver abstraction, each project highlights a different aspect of embedded system design — from keypad input and display multiplexing to EXTI interrupt handling and full conveyor control logic.

All projects are fully modular and integrated as Git submodules. Each has its own Proteus simulation, driver structure, and dedicated `README.md` with technical breakdowns and visual demos. Ideal for engineering students, embedded systems learners, and rapid prototyping portfolios.

<p align="center">
  <img src="https://github.com/user-attachments/assets/984412f8-db41-4e62-95c0-4b706ce76adc" width="60%" alt="ConveyorX">
  <img src="https://github.com/user-attachments/assets/71f2e2ad-f7e6-4b17-839e-11ace7bb7ff3" width="49%" alt="InterruptHandler">
  <img src="https://github.com/user-attachments/assets/194055fe-b6da-4612-b0b3-9ff41593cdd5" width="49%" alt="Press2Display">
</p>

---

## Included Projects

| Project            | Description                                                                                         | Link                                                              |
|--------------------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------|
| **ConveyorX**        | Smart conveyor simulation with ADC-based PWM motor control, timer capture, and emergency interrupts. | [ConveyorX](https://github.com/YassienTawfikk/ConveyorX)               |
| **InterruptHandler** | Real-time counter system using EXTI interrupts and 3-digit 7-segment multiplexing.                 | [InterruptHandler](https://github.com/YassienTawfikk/InterruptHandler) |
| **Press2Display**    | Keypad-driven system with lookup-based display logic and GPIO remapping abstraction.               | [Press2Display](https://github.com/YassienTawfikk/Press2Display)       |


Each is included as a **Git submodule**. To clone this suite with all subprojects:

```bash
git clone --recurse-submodules [git@github.com](mailto:git@github.com)\:YassienTawfikk/STM32LabSuite.git

````

---

### Key Features

* **Real-Time Input & Output (InterruptHandler/)**
  * EXTI edge detection, LED toggling, ISR-driven display logic, critical section handling

* **Modular Display and Input Logic (Press2Display/)**
  * Keypad scanning, software multiplexing, GPIO remapping, switchless digit rendering

* **Smart Control System Design (ConveyorX/)**
  * Motor PWM via ADC, velocity via timer capture, IR object detection, EXTI-based safety control

---

### Technical References & Datasheets

All STM32LabSuite projects are designed with strict adherence to official technical documentation. These references were essential for accurate register-level programming, hardware interfacing, and peripheral configuration:

| Manual / Datasheet                     | Role in Project                                                                                                   | Link                                                                           |
| -------------------------------------- | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| **RM0368: STM32F401 Reference Manual** | The core reference for all low-level register configurations, including EXTI, TIM, ADC, NVIC, and GPIO handling.  | [PDF](https://github.com/YassienTawfikk/STM32LabSuite/blob/main/Manuals/rm0368-stm32f401xbc-and-stm32f401xde-advanced-arm-based-32-bit-mcus-stmicroelectronics-en.pdf)   |
| **PM0214: STM32F4 Programming Manual** | Essential for understanding Cortex-M4 instruction set, startup behavior, exception handling, and low-power modes. | [PDF](https://github.com/YassienTawfikk/STM32LabSuite/blob/main/Manuals/pm0214-stm32-cortex-m4-mcus-and-mpus-programming-manual-stmicroelectronics-en.pdf) |
| **STM32F401xE Datasheet**              | Defines all electrical characteristics, pin mappings, memory layout, and package-specific details.                | [PDF](https://github.com/YassienTawfikk/STM32LabSuite/blob/main/Manuals/stm32f401re.pdf)      |
| **HD44780U LCD Controller Datasheet**  | Used in `Press2Display/` to implement custom LCD timing and 4-bit control logic for HD44780-based displays.       | [PDF](https://github.com/YassienTawfikk/STM32LabSuite/blob/main/Manuals/HD44780U%20LCD.pdf)            |

These documents ensure that the projects are not only functional but also compliant with real-world embedded design standards.

---

### Build & Simulation Setup

All projects follow a consistent STM32 + CMake build system. You can use either **CLion** or **STM32CubeIDE** to build the code.

```bash
# Example build flow (IMPORTANT: open each project individually)
cd Press2Display  # or InterruptHandler, ConveyorX
# Set ARM toolchain path inside: cmake/ArmToolchain.cmake
# Then build from your IDE
````

🔺 **Note:** When using **CLion**, do *not* open the entire `STM32LabSuite` superproject. Instead, open each subproject (e.g., `InterruptHandler/`) directly as a standalone CLion project to generate the `.hex` file correctly.

#### To run Proteus simulations:

* Open the respective `.pdsprj` file in **Proteus**
* Load the compiled `.hex` file into the STM32F401VE microcontroller

---

### Contributors

<div>
  <table align="center">
    <tr>
      <td align="center">
        <a href="https://github.com/YassienTawfikk" target="_blank">
          <img src="https://avatars.githubusercontent.com/u/126521373?v=4" width="120px;" alt="Yassien Tawfik"/><br/>
          <sub><b>Yassien Tawfik</b></sub>
        </a>
      </td>
      <td align="center">
        <a href="https://github.com/malak-emad" target="_blank">
          <img src="https://avatars.githubusercontent.com/u/126415070?v=4" width="120px;" alt="Malak Emad"/><br/>
          <sub><b>Malak Emad</b></sub>
        </a>
      </td>    
    </tr>
  </table>
</div>

---
