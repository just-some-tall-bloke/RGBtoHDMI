# Main RGBtoHDMI Boards

This section documents the core RGBtoHDMI interface boards that form the foundation of the system.

## Overview

The main RGBtoHDMI boards are designed as HAT (Hardware Attached on Top) boards for the Raspberry Pi Zero. They contain the CPLD (Complex Programmable Logic Device) that handles signal conditioning and timing, along with the necessary circuitry to interface with various retro computer video outputs.

## Board Variants

### 1. Standard RGBtoHDMI Boards (`kicad/`)

These are the general-purpose boards designed primarily for BBC Micro and Electron computers.

#### Version History

**RGBtoHDMI v1**
- **Location**: `kicad/v1/`
- **Target**: BBC Micro/Electron
- **Signal Type**: 6-bit TTL RGB
- **CPLD**: XC9572XL-VQFP44
- **Features**: 
  - Basic 6-bit RGB input
  - GPIO header for Pi Zero
  - Simple signal conditioning
  - Manual calibration required
- **Status**: Legacy

**RGBtoHDMI v2**
- **Location**: `kicad/v2/`
- **Target**: BBC Micro/Electron
- **Signal Type**: 6-bit TTL RGB
- **CPLD**: XC9572XL-VQFP44
- **Features**:
  - Improved signal routing
  - Better power regulation
  - Enhanced stability
- **Status**: Legacy

**RGBtoHDMI v3**
- **Location**: `kicad/v3/`
- **Target**: BBC Micro/Electron
- **Signal Type**: 6-bit TTL RGB
- **CPLD**: XC9572XL-VQFP44
- **Features**:
  - Refined PCB layout
  - Improved component placement
  - Better signal integrity
- **Status**: Legacy

**RGBtoHDMI v4**
- **Location**: `kicad/v4/`
- **Target**: BBC Micro/Electron
- **Signal Type**: 6-bit TTL RGB
- **CPLD**: XC9572XL-VQFP44
- **Features**:
  - Current production version
  - Optimized signal routing
  - Enhanced calibration features
  - Improved power distribution
  - Better EMI performance
- **Status**: Current Production

### 2. RGBtoHDMI Atom Boards (`kicad_atom/`)

Specialized boards designed specifically for the Acorn Atom computer.

#### Version History

**RGBtoHDMI Atom v1**
- **Location**: `kicad_atom/v1/`
- **Target**: Acorn Atom
- **Signal Type**: TTL RGB with Atom-specific timing
- **CPLD**: XC9572XL-VQFP44
- **Features**:
  - Atom-specific connector
  - Custom timing circuitry
  - Direct Atom interface
- **Status**: Legacy

**RGBtoHDMI Atom v2**
- **Location**: `kicad_atom/v2/`
- **Target**: Acorn Atom
- **Signal Type**: TTL RGB with Atom-specific timing
- **CPLD**: XC9572XL-VQFP44
- **Features**:
  - Improved signal conditioning
  - Better compatibility with Atom variants
  - Enhanced stability
  - LM319 comparator circuitry for signal processing
- **Status**: Current Production

## Common Features

### Hardware Components

**Core Components**:
- **CPLD**: Xilinx XC9572XL (VQFP44 package)
  - 72 macrocells
  - 5V tolerant I/O
  - In-system programmable
- **Pi Zero Header**: 40-pin GPIO connector
- **Power**: 5V from Pi Zero, with local regulation
- **Signal Inputs**: Various connector types depending on target

**Signal Processing**:
- **Level Shifting**: TTL to CPLD compatible levels
- **Buffering**: Signal integrity preservation
- **Sync Separation**: Horizontal/vertical sync extraction
- **Timing Generation**: Precise pixel clock generation

### Physical Specifications

**Board Size**:
- Standard: Fits within Pi Zero HAT specifications
- Atom: Slightly larger for Atom-specific connector

**Mounting**:
- Standard Pi Zero mounting holes
- Additional mounting for stability
- Compatible with Pi Zero cases

## Assembly Instructions

### Required Components

**Basic Components**:
- XC9572XL CPLD (44-pin VQFP)
- 40-pin GPIO header (right-angle)
- Various resistors and capacitors
- Crystal oscillator (if applicable)
- LED and current limiting resistor

**Tools Required**:
- Soldering iron with fine tip
- Solder wire (0.6mm recommended)
- Flux (for surface mount work)
- Tweezers for CPLD handling
- Multimeter for testing

### Assembly Process

1. **Surface Mount Components**:
   - Solder the XC9572XL CPLD first
   - Use appropriate temperature profile
   - Verify all pins are properly soldered

2. **Through-Hole Components**:
   - Install resistors and capacitors
   - Add the GPIO header
   - Install LED and resistors

3. **Testing**:
   - Check for shorts with multimeter
   - Verify power connections
   - Test CPLD programming

## Installation

### Raspberry Pi Setup
1. Install the assembled RGBtoHDMI board on Pi Zero
2. Ensure proper alignment of GPIO pins
3. Secure with mounting hardware if available

### Software Setup
1. Install RGBtoHDMI software on Pi Zero
2. Load appropriate CPLD firmware
3. Configure for target computer
4. Perform initial calibration

## Target System Compatibility

### BBC Micro Compatibility
- **Models**: BBC Micro Model B, B+, Master Compact
- **Video Modes**: All standard modes including Mode 7
- **Connection**: 15-pin D-sub or edge connector
- **Calibration**: Automatic and manual options

### BBC Electron Compatibility
- **Models**: BBC Electron, Plus 1, Plus 3
- **Video Modes**: All Electron modes
- **Connection**: Electron expansion port
- **Special Features**: Electron-specific timing

### Acorn Atom Compatibility
- **Models**: Acorn Atom, various expansions
- **Video Modes**: Atom display modes
- **Connection**: Atom expansion port
- **Special Features**: Custom timing requirements

## Troubleshooting

### Common Issues

**No Video Output**:
- Check CPLD programming
- Verify power connections
- Check target computer video output
- Ensure correct cable connections

**Poor Image Quality**:
- Run automatic calibration
- Check cable quality
- Verify signal levels
- Check for interference

**Sync Issues**:
- Verify sync cable connections
- Check sync polarity settings
- Try different sync edge detection

### Advanced Troubleshooting

**Signal Analysis**:
- Use oscilloscope to check signal quality
- Verify timing relationships
- Check for signal integrity issues

**CPLD Issues**:
- Verify CPLD firmware version
- Re-program if necessary
- Check I/O voltage levels

## Files and Resources

### Design Files
- **Schematics**: `.sch` files in each version directory
- **PCB Layouts**: `.kicad_pcb` files
- **Gerber Files**: Manufacturing outputs
- **BOMs**: Component lists (where available)

### Manufacturing
- **Gerber Archives**: Ready for PCB production
- **Drill Files**: For manufacturing
- **Pick and Place**: For automated assembly

### Documentation
- **Assembly Guides**: Detailed build instructions
- **Installation Manuals**: Setup procedures
- **Calibration Guides**: Software configuration

## Version Comparison

| Version | Target | Features | Status |
|---------|--------|----------|---------|
| RGBtoHDMI v1 | BBC Micro/Electron | Basic 6-bit input | Legacy |
| RGBtoHDMI v2 | BBC Micro/Electron | Improved routing | Legacy |
| RGBtoHDMI v3 | BBC Micro/Electron | Refined layout | Legacy |
| RGBtoHDMI v4 | BBC Micro/Electron | Current production | Current |
| Atom v1 | Acorn Atom | Atom-specific | Legacy |
| Atom v2 | Acorn Atom | Enhanced features | Current |

## Future Development

The main RGBtoHDI boards are mature designs with stable functionality. Future development focuses on:
- Component availability management
- Manufacturing optimization
- Minor performance improvements
- Documentation enhancements

## Support Resources

For technical support with main RGBtoHDMI boards:
- Check individual version documentation
- Review the main RGBtoHDMIdocumentation
- Consult community forums
- File GitHub issues for specific problems