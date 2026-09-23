# LoRa® Studio

## Overview

LoRa Studio is a demonstration and evaluation tool for the Semtech® LoRa Plus™ series radio chips. This software suite enables developers and engineers to explore the capabilities of the LR2021, LR2022 and LR2012 through an intuitive host-based interface that communicates with development kits to execute various radio demonstrations and tests.

## Features

- **Host-based Control**: Python application with pyOCD integration for seamless communication with development kits
- **Multiple Demo Applications**:
  - Ping Pong: Bi-directional communications
  - PER (Packet Error Rate): Link quality and performance testing
  - Continuous Wave: Put the chip in transmission to allow user to make measurements
  - Power consumption measures application: Set the chip in all possible states to finely measure its consumption
  - More to come...
- **Cross-platform Support**: Available for Windows and Linux
- **Multi-platform Dev Kit Support**: Includes firmware for STM32 Nucleo®-L476RG, Nordic® nRF54-DK, and Seeed XIAO nRF54 platforms

## Download

This gitHub project stores all releases version of LoRa Studio, hence it is strongly advised that you _do not_ clone this repository.
Simply download the file using the download link <https://github.com/Lora-net/LoRaStudio/blob/master/LoRaStudio_v1.7.4_windows_Setup.exe>

You can also download the user guide but be aware that the application itself embeds it as documentation page.

## System Requirements

### Host Computer

**Windows:**

- Windows 10 or later (64-bit)
- USB port for dev kit connection

**Linux:**

- Ubuntu 22.04 or later (or equivalent distribution)
- USB port for dev kit connection

### Development Kit

- Compatible Semtech LR20xx development kit (one of the following):
  - Seeed Studio XIAO nRF54 module on expansion board with LR20xx module (official most common dev-kit)
  - STMicroelectronics® Nucleo-L476RG with LR20xx expansion board and Arduino pinout adaptation board
  - Nordic Semiconductor® nRF54-DK with LR20xx expansion board and Arduino pinout adaptation board
- USB cable for host connection
- Power supply as battery pack for standalone running mode (measures on the field)

## Installation

### Option 1: Self-Extracting Installer (Windows)

1. Download `LoRaStudio_v1.7.4_windows_Setup.exe`.
2. Double-click the installer and follow the on-screen instructions. Prefer _User_ installation.
3. The installer will place all necessary files and create desktop shortcuts.
4. Launch LoRa Studio from the Start Menu or desktop shortcut.

### Option 2: Standalone Windows Version

1. Download `LoRaStudio-windows-v1.7.4.tar.gz`.
2. Extract the archive to your preferred location.
3. Navigate to the extracted folder.
4. Run `LoRaStudio.exe` to launch the application.
Note: Choose this if you would rather have multiple versions at your disposal.

### Option 3: Standalone Linux Version

As any AppImage you can simply make it executable and run it as is or, if you need to finely manipulate LoRaStudio elements, you can extract it.

1. Download `LoRaStudio-v1.7.4-linux-x86_64.AppImage`

2. Make it executable:

```bash
chmod +x LoRaStudio-v1.7.4-linux-x86_64.AppImage
```

Double click on it, it shall self extract in a temp folder to execute.

If you want to save time at application startup you can also extract it

```bash
./LoRaStudio-v1.7.4-linux-x86_64.AppImage --appimage-extract
```

This creates a squashfs-root folder where you shall find the application to run.

## Development Kit Setup

The kits are already flashed with Lora Studio software. However, you might want to update them to the latest version.

### Firmware Update

The distribution includes three embedded firmware binaries for different development kit platforms:

- `LoRaStudio_xiao_nrf54_v1.7.4.bin` - For Seeed Studio XIAO nRF54 modules
- `LoRaStudio_nrf54_dk_v1.7.4.bin` - For Nordic nRF54-DK boards
- `LoRaStudio_nucleo_l476rg_v1.7.4.bin` - For STM32 Nucleo-L476RG boards

They can be found in the `binaries` folder in the Lora Studio installation folder.

### Flashing the Development Kit

1. Identify your development kit platform:
   - **XIAO nRF54**: Seeed Studio XIAO nRF54 module
   - **STM32 Nucleo-L476RG**: STMicroelectronics Nucleo board with STM32L476RG MCU
   - **nRF54-DK**: Nordic Semiconductor nRF54 development kit.
   Some pictures are shown on the documentation page of the application for better identification.
2. Connect your development kit to your computer via USB.
3. Launch Lora Studio, go to the connexion page.
4. The application should automatically detect the connected device(s).
5. If not detected, click **Search for devices** button.
6. Select your device and click on the **Connect** button.
7. Once connected, your kit can be upgraded by clicking on the **Update firmware** button (last of the small square buttons on the top left corner of the window), choose the appropriate binary to flash.

**Note for STM32 Nucleo users:** The Nucleo-L476RG board also supports drag-and-drop programming. You can simply copy the firmware binary file to the Nucleo drive that appears when you connect the board to your computer.

If you encounter any issue with your kit, please go to the documentation page in the application.
It is located on the last tab and you can access it by clicking on the "book" button on the left of the main window, at the very bottom.

## Getting Started

To get a full overview of LoRa Studio capabilities and the user guide please open the documentation page directly in the application.

## Troubleshooting

### Device Not Detected

- Ensure the development kit is properly connected via USB
- Check that USB drivers are installed (Windows may require manual driver installation)
- Try a different USB cable or port
- Verify the firmware is properly flashed on the dev kit

### Communication Errors

- Reset the development kit by pressing the reset button
- Restart Lora Studio
- Check USB connection stability
- Ensure no other application is using the same COM port or USB device

## Technical Details

### Architecture

Lora Studio consists of two main components:

1. **Host Application**: Python-based GUI application that runs on the host computer, utilizing pyOCD for device communication and control.

2. **Embedded Firmware**: Dedicated software running on the development kit that processes commands from the host and executes radio operations.

## Support and Documentation

For additional documentation, technical support, or to report issues:

- Refer to the documentation page in the application itself
- Refer to the LR20xx datasheet and application notes
- Contact your Semtech representative

## License

Please refer to the LICENSE file included in this distribution for software license terms and conditions.

## Version Information

**Current Version**: v1.7.4

**Release Date**: September 17, 2026

**Compatible Firmware Versions**: v1.7.4

---

  2025 Semtech Corporation. All rights reserved.
