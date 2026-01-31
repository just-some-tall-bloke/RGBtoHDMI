# RGBtoHDMI

A comprehensive open-source hardware and software solution for converting legacy RGB video signals from vintage computers to modern HDMI displays. The RGBtoHDMI interface provides pixel-perfect digital conversion of analog RGB signals, preserving the authentic visual experience of classic computing hardware on contemporary monitors and televisions.

## Table of Contents

- [Overview](#overview)
- [Supported Computers](#supported-computers)
- [Hardware Requirements](#hardware-requirements)
- [Software Features](#software-features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Configuration](#configuration)
- [Building from Source](#building-from-source)
- [Hardware Variants](#hardware-variants)
- [CPLD Firmware](#cpld-firmware)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Overview

The RGBtoHDMI project is a sophisticated video conversion solution designed specifically for retrocomputing enthusiasts who want to connect their vintage computers to modern HDMI displays without compromising image quality. Unlike generic composite-to-HDMI converters that often introduce artifacts, lag, and poor color reproduction, RGBtoHDMI provides:

- **Pixel-perfect conversion**: Each RGB pixel is sampled and converted with precise timing
- **Zero lag**: Direct digital conversion eliminates processing delays common in other solutions
- **Multiple platform support**: Compatible with various retro computers through different hardware adapters
- **Advanced calibration**: Built-in calibration system for optimal video quality
- **Open-source**: Fully open hardware and software for community development and modification

The system consists of two main components:
1. **Hardware Interface**: A custom CPLD (Complex Programmable Logic Device) mounted on a Raspberry Pi Zero HAT
2. **Firmware**: Custom software running on the Raspberry Pi that handles video processing and output

## Supported Computers

RGBtoHDMI supports a wide range of vintage computers through different hardware configurations:

### Primary Support
- **BBC Micro**: Full support for all standard video modes including Mode 7 (teletext)
- **BBC Electron**: Complete compatibility with Electron's video output modes
- **Acorn Atom**: Support for Atom's video display modes

### Extended Support (with adapters)
- **Amiga**: 12-bit buffered pickup solutions for various Amiga models
- **Atari ST**: 12-bit buffered and unbuffered pickup options
- **Commodore 128**: Adapter support for 40-column mode through VIC-IIe integration

### Video Signal Types
- **RGB TTL**: Direct digital RGB signals (6-bit, 8-bit, and 12-bit variants)
- **RGB Analog**: Analog RGB signals with proper level conversion
- **YUV**: YUV video signal support for compatible systems
- **Various Sync Signals**: Support for different horizontal and vertical sync configurations

## Hardware Requirements

### Core Components
1. **Raspberry Pi Zero (W or WH)**: The main processing unit
   - Pi Zero 2W recommended for enhanced performance
   - Standard Pi Zero W sufficient for basic operations
   - Requires microSD card (8GB minimum, Class 10 recommended)

2. **RGBtoHDMI HAT**: Custom hardware interface board
   - Contains CPLD for signal conditioning and timing
   - Provides connection points for RGB signals
   - Includes level conversion circuitry
   - Available in various configurations for different computers

3. **Video Cable**: Appropriate connection cable for target computer
   - BBC Micro/Acorn Atom: Custom 15-pin D-sub or edge connector
   - Amiga: 23-pin video port adapters
   - Atari ST: 13-pin DIN connector adapters
   - Commodore 128: VIC-IIe socket adapter

### Optional Components
- **Extension Cables**: For flexible positioning of the Pi Zero
- **Buffer Boards**: For signal integrity in long cable runs
- **Clock Fixer**: For systems with timing issues
- **3D Printed Cases**: For protection and mounting

### Power Requirements
- Powered through Raspberry Pi Zero (5V via USB or GPIO)
- Typical power consumption: 200-400mA
- No external power supply required for most configurations

## Software Features

### Core Video Processing
- **Multi-mode Support**: Automatic detection and handling of different video modes
- **Real-time Processing**: Live video conversion with minimal latency (< 1ms)
- **Color Space Conversion**: Accurate RGB to HDMI color space translation
- **Scaling Options**: Integer scaling for pixel-perfect display
- **Overscan Compensation**: Configurable overscan handling

### Calibration System
- **Automatic Calibration**: Self-calibrating system for optimal signal timing
- **Manual Adjustment**: Fine-tune sampling points, phase, and timing
- **Profile Management**: Save and load calibration profiles for different systems
- **Sync Analysis**: Advanced sync signal analysis and optimization

### User Interface
- **On-Screen Display (OSD)**: Comprehensive configuration menu system
- **Real-time Parameter Adjustment**: Modify settings without reboot
- **Profile Selection**: Easy switching between saved configurations
- **System Information**: Display current settings and hardware status
- **Debug Mode**: Advanced diagnostic tools for troubleshooting

### Advanced Features
- **Double Resolution**: Enhanced resolution modes for supported systems
- **Scanline Effects**: Optional scanline simulation for authentic retro look
- **Color Enhancement**: Adjustable color temperature and saturation
- **Video Filters**: Optional filtering for noise reduction and edge enhancement
- **Frame Rate Control**: Support for different refresh rates (50Hz/60Hz)

## Project Structure

```
RGBtoHDMI/
├── src/                          # Main source code
│   ├── cpld_*.c                  # CPLD interface implementations
│   ├── geometry.c                # Video geometry handling
│   ├── osd.c                     # On-screen display system
│   ├── rgb_to_hdmi.c             # Main application
│   └── ...                       # Additional source files
├── vhdl*/                         # CPLD firmware designs
│   ├── vhdl_RGB_6bit/           # 6-bit RGB CPLD design
│   ├── vhdl_RGB_12bit/          # 12-bit RGB CPLD design
│   ├── vhdl_YUV_8bit/           # 8-bit YUV CPLD design
│   └── ...                       # Other VHDL variants
├── kicad*/                        # Hardware design files
│   ├── kicad/                    # Main HAT designs
│   ├── kicad_*_adapter/         # Various adapter boards
│   └── kicad_*_buffer/          # Signal buffer designs
├── tools/                        # Build and development tools
├── contrib/                      # Community contributions
└── docs/                         # Documentation
```

### Key Components

#### Source Code (`src/`)
- **CPLD Interfaces**: Modular drivers for different CPLD variants
- **Video Processing**: Core video capture and conversion algorithms
- **OSD System**: Menu system for user configuration
- **Calibration**: Automated and manual calibration procedures
- **Hardware Abstraction**: Platform-independent hardware interface

#### VHDL Designs (`vhdl*`)
- **Multiple Implementations**: Different CPLD designs for various signal types
- **Version Management**: Multiple versions for compatibility and improvements
- **Synthesis Ready**: Complete Xilinx ISE project files
- **Programming Files**: Pre-compiled .xsvf files for direct programming

#### Hardware Designs (`kicad*`)
- **Schematics**: Complete electronic schematics for all boards
- **PCB Layouts**: Production-ready PCB designs
- **Gerber Files**: Manufacturing files for PCB production
- **Bill of Materials**: Complete parts lists with specifications

## Installation

### Prerequisites
- Raspberry Pi Zero (configured with Raspberry Pi OS)
- MicroSD card (8GB minimum, class 10 recommended)
- Appropriate RGBtoHDMI hardware for your target computer
- Video cable for your computer system

### Step-by-Step Installation

1. **Prepare Raspberry Pi Zero**
   ```bash
   # Flash Raspberry Pi OS Lite to microSD card
   # Enable SSH for headless setup
   # Update system packages
   sudo apt update && sudo apt upgrade -y
   ```

2. **Install Dependencies**
   ```bash
   # Install required development tools
   sudo apt install -y git build-essential cmake
   
   # Install Raspberry Pi specific packages
   sudo apt install -y libraspberrypi-dev libraspberrypi-bin
   ```

3. **Clone and Build RGBtoHDMI**
   ```bash
   # Clone the repository
   git clone https://github.com/hoglet67/RGBtoHDMI.git
   cd RGBtoHDMI
   
   # Build the software
   mkdir build && cd build
   cmake ..
   make
   
   # Install the software
   sudo make install
   ```

4. **Configure Auto-start**
   ```bash
   # Configure RGBtoHDMI to start automatically
   sudo systemctl enable rgbtohdmi
   sudo systemctl start rgbtohdmi
   ```

5. **Hardware Installation**
   - Power down all systems
   - Connect RGBtoHDMI HAT to Raspberry Pi Zero
   - Connect video cable from target computer to RGBtoHDMI
   - Connect HDMI output to your display
   - Power up the system

### Initial Configuration

On first boot, RGBtoHDMI will automatically:
- Detect the connected computer type
- Perform initial calibration
- Display the OSD menu for further configuration

Use the following key controls:
- **Button 1 (GPIO 3)**: Menu navigation/selection
- **Button 2 (GPIO 2)**: Menu navigation/back
- **Hold Button 1**: Access advanced options

## Configuration

### Menu System

The on-screen display provides comprehensive configuration options:

#### Main Menu
- **Profiles**: Select and manage saved configurations
- **Geometry**: Adjust video positioning and scaling
- **Sampling**: Fine-tune video sampling parameters
- **Colors**: Adjust color settings and enhancements
- **Advanced**: Advanced system options and diagnostics
- **System**: System information and status

#### Key Configuration Options

**Video Geometry**
- **Horizontal Position**: Adjust left/right placement
- **Vertical Position**: Adjust up/down placement  
- **Horizontal Size**: Adjust width scaling
- **Vertical Size**: Adjust height scaling
- **Aspect Ratio**: Configure proper aspect ratio preservation

**Sampling Parameters**
- **Sampling Phase**: Fine-tune pixel sampling timing
- **Clock Divider**: Adjust sampling clock rate
- **Sync Edge**: Select sync signal edge detection
- **Delay**: Add sampling delay for timing adjustment

**Color Settings**
- **Brightness**: Adjust overall brightness level
- **Contrast**: Adjust image contrast
- **Color Temperature**: Warm/cool color balance
- **Saturation**: Adjust color intensity
- **Individual RGB Gains**: Fine-tune each color channel

**Advanced Options**
- **Double Resolution**: Enable enhanced resolution modes
- **Scanlines**: Add simulated scanline effects
- **Filtering**: Enable video filtering options
- **Debug Mode**: Access diagnostic information

### Profile Management

RGBtoHDMI supports multiple profiles for different use cases:
- **Factory Profiles**: Pre-configured settings for common systems
- **Custom Profiles**: User-saved configurations
- **Auto-switching**: Automatic profile selection based on detected mode

## Building from Source

### Development Environment Setup

For development and custom builds, set up the following environment:

```bash
# Install development dependencies
sudo apt install -y gcc-arm-none-eabi binutils-arm-none-eabi
sudo apt install -y cmake git build-essential

# Install Raspberry Pi development libraries
sudo apt install -y libraspberrypi-dev libraspberrypi-doc
```

### Build Process

1. **Clone Repository**
   ```bash
   git clone --recursive https://github.com/hoglet67/RGBtoHDMI.git
   cd RGBtoHDMI
   ```

2. **Configure Build**
   ```bash
   mkdir build && cd build
   cmake -DCMAKE_BUILD_TYPE=Release ..
   ```

3. **Compile Software**
   ```bash
   make -j$(nproc)
   ```

4. **Build CPLD Firmware (Optional)**
   ```bash
   # Navigate to desired VHDL directory
   cd ../vhdl_RGB_12bit/
   
   # Use Xilinx ISE to compile the VHDL design
   # Or use pre-compiled .xsvf files
   ```

5. **Package for Deployment**
   ```bash
   # Create distribution package
   make package
   ```

### Build Options

The build system supports several configuration options:
- **BUILD_TYPE**: Release/Debug builds
- **PLATFORM**: Target platform selection
- **FEATURES**: Optional feature inclusion
- **CPLD_VERSION**: CPLD firmware version selection

## Hardware Variants

RGBtoHDMI supports multiple hardware configurations:

### Main Board Variants

**Standard RGBtoHDMI HAT**
- Base design for BBC Micro/Electron
- 6-bit and 12-bit RGB support
- Integrated signal conditioning

**Extended Variants**
- **Amiga Adapter**: Specialized for Amiga computers
- **Atari ST Adapter**: Optimized for Atari systems
- **Commodore 128 Adapter**: VIC-IIe integration
- **Universal Adapter**: Multi-system compatibility

### Buffer Options

**Signal Buffer Boards**
- **6-bit Buffer**: For 6-bit RGB signals
- **8-bit Buffer**: For 8-bit RGB signals
- **12-bit Buffer**: For 12-bit RGB signals
- **PC Buffer**: General purpose signal buffering

**Extension Boards**
- **Clock Fixer**: For timing correction
- **Extender Boards**: For physical extension
- **Analog Frontend**: For analog RGB signals

## CPLD Firmware

The CPLD (Complex Programmable Logic Device) firmware is responsible for:
- **Signal Conditioning**: Amplification and level shifting
- **Timing Generation**: Precise sampling clock generation
- **Sync Processing**: Horizontal/vertical sync detection
- **Data Latching**: Pixel data capture and timing

### Firmware Variants

**RGB TTL Variants**
- 6-bit RGB: Standard 64-color RGB
- 12-bit RGB: Enhanced 4096-color RGB

**RGB Analog Variants**
- Analog to digital conversion
- Variable input level support
- Enhanced color depth

**YUV Variants**
- YUV signal support
- Component video compatibility

### Firmware Updates

To update CPLD firmware:
1. Download the appropriate .xsvf file
2. Use the built-in firmware update utility
3. Select the firmware from the OSD menu
4. Follow on-screen instructions

The system supports:
- **Safe Updates**: Verify firmware before programming
- **Rollback Support**: Return to previous firmware versions
- **Version Management**: Track firmware versions and changes

## Troubleshooting

### Common Issues

**No Video Output**
- Check all cable connections
- Verify power to Raspberry Pi Zero
- Confirm correct HDMI input selection
- Try different HDMI cable or monitor

**Poor Image Quality**
- Run automatic calibration from OSD menu
- Check for loose connections
- Verify correct video mode selection
- Adjust sampling parameters manually

**Sync Issues**
- Check sync cable connections
- Verify correct sync polarity settings
- Try different sync edge detection modes
- Check for signal interference

**System Stability**
- Ensure adequate power supply
- Check for overheating
- Verify stable power connections
- Monitor system logs for errors

### Diagnostic Tools

RGBtoHDMI includes several diagnostic tools:
- **Signal Analyzer**: Real-time signal monitoring
- **Calibration Assistant**: Guided calibration process
- **System Information**: Hardware and software status
- **Debug Mode**: Advanced troubleshooting options

### Getting Help

For additional support:
- Check the project Wiki for detailed guides
- Review GitHub Issues for common problems
- Join community forums for user discussions
- Contact the development team for technical assistance

## Contributing

RGBtoHDMI is a community-driven project that welcomes contributions in many forms:

### Ways to Contribute

**Code Contributions**
- Bug fixes and improvements
- New features and functionality
- Performance optimizations
- Documentation updates

**Hardware Contributions**
- New adapter designs
- PCB layout improvements
- Component substitutions
- Manufacturing documentation

**Testing and Feedback**
- Bug reports and testing
- Feature suggestions
- Compatibility testing
- User experience feedback

### Development Process

1. **Fork the Repository**: Create your own fork on GitHub
2. **Create Branch**: Work on features in separate branches
3. **Submit Pull Request**: Follow project contribution guidelines
4. **Code Review**: Participate in review process
5. **Documentation**: Update relevant documentation

### Coding Standards

- Follow existing code style and conventions
- Add appropriate comments and documentation
- Test changes thoroughly
- Ensure compatibility with existing systems

## License

RGBtoHDMI is released under the GNU General Public License v3.0 (GPLv3).

### License Summary

This license provides:
- **Freedom to Use**: Use the software for any purpose
- **Freedom to Modify**: Modify and improve the software
- **Freedom to Distribute**: Share with others
- **Freedom to Study**: Access and study the source code

### Requirements

- **Source Availability**: Must provide source code with distributions
- **License Preservation**: Must include the original license
- **Modification Notices**: Must indicate changes made
- **Same License**: Derivative works must use the same license

### Full License Text

The complete GPLv3 license text is included in the [LICENSE](LICENSE) file in this repository.

## Acknowledgments

RGBtoHDMI is made possible by the contributions of many individuals and organizations:

### Core Contributors
- **hoglet67**: Project founder and lead developer
- **scarybeasts**: Hardware design and development
- **dom**: Raspberry Pi expertise and optimization
- **Sector24**: Amiga adapter development
- **Community Members**: Testing, feedback, and contributions

### Hardware Support
- **Raspberry Pi Foundation**: Platform and development tools
- **Xilinx**: CPLD development tools and support
- **KiCad Community**: PCB design software and libraries

### Special Thanks
- **Retrocomputing Community**: For inspiration and feedback
- **Beta Testers**: For extensive testing and bug reports
- **Documentation Contributors**: For guides and tutorials
- **Hardware Manufacturers**: For component support and samples

### References

This project builds upon and references various prior works:
- Retrocomputing video signal research
- Digital video processing techniques
- FPGA/CPLD development practices
- Open hardware design principles

---

For more detailed information, please visit the project [Wiki](../../wiki) or check out our [GitHub repository](https://github.com/hoglet67/RGBtoHDMI).