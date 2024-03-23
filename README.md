# TriSineWaveGenerator

## Generating Three Phase SineWave using STM32

### Introduction
This project is developed for the STEVAL spin 3201 board and is aimed at generating a 3-phase sine wave output with specific characteristics. The primary goal is to achieve a fundamental frequency of 2 kHz for the output and a switching frequency of 12 kHz. Additionally, the output voltage amplitude is adjustable via the built-in potentiometer, featuring a unique dead-zone implementation for enhanced control.

## MVP Documentation
For detailed documentation on each Minimum Viable Product (MVP) iteration, including objectives, achievements, and customer feedback, please see our [MVP Documentation](./docs/MVP_DOCUMENTATION.md).

### Features
- **Fundamental Frequency:** 2 kHz
- **Switching Frequency:** 12 kHz
- **Voltage Control:** Adjustable output voltage amplitude using the onboard potentiometer.
- **Dead-Zone Control:** The first 5% of the potentiometer's range acts as a dead-zone, producing zero output voltage. Beyond this range, the voltage linearly increases up to the maximum as the potentiometer moves from 5% to 100%.
- **Activation Mechanism:** The output voltage function is activated by pressing one of the designated buttons while the potentiometer is within the 0-5% level. If the button is pressed while the potentiometer is outside this range, the output voltage function will not be activated.

### Hardware Requirements
- Board: STEVAL spin 3201
- Currently implemented on an STM32F303RET board.

### Implementation Details
The project utilizes the board's DAC and TIM2 at a 32 MHz clock frequency in the APB1 bus with a Prescaler of 8-1 and a counter period of 5-1 to achieve the desired output characteristics.

## Getting Started
To get started with this project:
1. Ensure you have the necessary hardware and software setup.
2. Clone this repository to your local machine.
3. Follow the setup instructions detailed in the subsequent sections to configure your board and environment.

## Setup Instructions

### Prerequisites
- STM32CubeIDE version 1.14.1 installed on your computer.
- STM32F303RET6 MCU and an appropriate development board.
- STM32Cube FW_F3 v1.11.4 firmware package.

### Environment Setup
- **STM32CubeIDE Installation:** Ensure STM32CubeIDE version 1.14.1 is installed. If not, download and install it from the [STMicroelectronics website](https://www.st.com/en/development-tools/stm32cubeide.html).
- **Firmware Package:** The project is developed using the STM32Cube FW_F3 v1.11.4 firmware package. This package should be included by default in STM32CubeIDE, but you can verify and update it through the IDE's package manager if necessary.

### Project Setup
1. **Open STM32CubeIDE:** Launch STM32CubeIDE on your computer.
2. **Import Project:**
   - Go to `File > Import`.
   - Choose `Existing Projects into Workspace` under the `General` category.
   - Navigate to the cloned repository's location and select the project.
   - Click `Finish` to import the project into STM32CubeIDE.
3. **Configure MCU Settings:**
   - In the Project Explorer, right-click on your project and select `Properties`.
   - Navigate to `MCU/MPU Selector`.
   - Ensure that the correct MCU (STM32F303RET6) is selected. If not, use the MCU/MPU Selector to select the STM32F303RET6.
4. **Verify Firmware Package:**
   - In the `Project Properties`, check under `C/C++ General > Paths and Symbols > Includes` to ensure the firmware path corresponds to STM32Cube FW_F3 v1.11.4.
   - If the firmware version needs to be updated, use the STMicroelectronics STM32CubeMX tool integrated into the IDE to update the project settings accordingly.

### Build and Flash the Firmware
1. **Build the Project:**
   - Right-click on your project in the Project Explorer.
   - Select `Build Project`. Wait for the build to complete without errors.
2. **Connect Your Board:**
   - Connect your STM32F303RET development board to your computer via USB.
3. **Flash the Firmware:**
   - Right-click on your project in the Project Explorer.
   - Select `Run As > STM32 MCU C/C++ Application`.
   - Follow the prompts to flash the firmware onto your board.

### Verifying the Setup
- Detailed setup verification instructions will go here.

## Project Output
The Expected 3-phase sine wave output at 2kHz generated by our project:

![Three Phase Sine Wave at 2kHz](https://github.com/aabdelghani/TriSineWaveGenerator/blob/main/docs/img/Three%20phase%20at%202khz.png)

## Usage
Instructions on how to use the software, including how to adjust the potentiometer, how to activate the output voltage,
