# Acorn Computers

This section documents adapters and solutions specifically designed for Acorn computer systems including BBC Micro, BBC Electron, and Acorn Atom.

## Overview

Acorn computers use specific video output formats that require specialized adapter solutions. The RGBtoHDMI project provides comprehensive support for the entire Acorn computer range.

## Board Variants

### 1. BBC Micro Adapters

The main RGBtoHDMI boards (documented in [Main Boards](01_Main_Boards.md)) are designed primarily for BBC Micro systems.

**RGBtoHDMI v1-v4**
- **Target**: BBC Micro Model B, B+, Master Compact
- **Connection**: 15-pin D-sub or edge connector
- **Signal Type**: 6-bit TTL RGB (64 colors)
- **Features**:
  - All BBC Micro video modes supported
  - Mode 7 teletext support
  - Automatic calibration
  - Enhanced resolution options

**Installation**:
- Direct connection to BBC Micro video output
- Compatible with standard RGB cables
- Supports both TTL and sync-on-green configurations

### 2. BBC Electron Adapters

BBC Electron compatibility is provided through the main RGBtoHDMI boards with appropriate cabling.

**RGBtoHDMI v1-v4**
- **Target**: BBC Electron, Plus 1, Plus 3
- **Connection**: Electron expansion port
- **Signal Type**: 6-bit TTL RGB
- **Features**:
  - All Electron video modes
  - Expansion port compatibility
  - Enhanced display modes

**Special Considerations**:
- Requires Electron-specific cable adapter
- Different sync timing from BBC Micro
- Expansion port power management

### 3. Acorn Atom Adapters

Dedicated Atom adapters provide specialized support for the Acorn Atom computer.

**RGBtoHDMI Atom v1-v2**
- **Location**: `kicad_atom/`
- **Target**: Acorn Atom (all variants)
- **Connection**: Atom expansion port
- **Signal Type**: TTL RGB with Atom-specific timing
- **Features**:
  - Atom-specific video timing
  - Custom signal processing
  - Direct expansion port interface
  - LM319 comparator for signal conditioning (v2)

**Atom-Specific Challenges**:
- Non-standard video timing
- Different sync requirements
- Variable resolution modes
- Expansion port signal routing

## Technical Specifications

### Video Signal Characteristics

**BBC Micro**:
- **Resolution**: Various (320x256, 640x256, etc.)
- **Color Depth**: 6-bit TTL (64 colors)
- **Sync**: Separate HSYNC/VSYNC or composite
- **Timing**: Standard 50Hz PAL timing

**BBC Electron**:
- **Resolution**: Similar to BBC Micro with variations
- **Color Depth**: 6-bit TTL
- **Sync**: Composite sync
- **Timing**: Slightly different from BBC Micro

**Acorn Atom**:
- **Resolution**: 256x192 (typical)
- **Color Depth**: Variable timing
- **Sync**: Custom sync requirements
- **Timing**: Atom-specific (non-standard)

### Signal Processing

**Common Features**:
- TTL signal level handling
- Sync signal extraction and conditioning
- Timing generation and synchronization
- Color space conversion

**BBC Micro Specific**:
- Mode 7 teletext support
- Enhanced resolution modes
- Overscan handling

**Atom Specific**:
- Custom timing generation
- LM319 comparator circuitry (v2)
- Signal level adaptation

## Installation Guide

### BBC Micro Installation

**Required Components**:
- RGBtoHDMI main board (v4 recommended)
- BBC Micro video cable (15-pin D-sub)
- Raspberry Pi Zero with RGBtoHDMI software
- HDMI cable and monitor

**Installation Steps**:
1. Assemble RGBtoHDMI board on Pi Zero
2. Connect BBC Micro video cable
3. Connect HDMI output to monitor
4. Power on and configure
5. Run calibration procedure

**Cable Options**:
- 15-pin D-sub to RGBtoHDMI adapter
- Edge connector direct wiring
- Custom cable configurations

### BBC Electron Installation

**Required Components**:
- RGBtoHDMI main board
- Electron expansion port adapter
- Custom cable or adapter board

**Installation Steps**:
1. Connect adapter to Electron expansion port
2. Route signals to RGBtoHDMI input
3. Configure for Electron timing
4. Test with Electron software

### Acorn Atom Installation

**Required Components**:
- RGBtoHDMI Atom board (v2 recommended)
- Atom expansion port connector
- Appropriate cabling

**Installation Steps**:
1. Connect Atom adapter to expansion port
2. Install RGBtoHDMI Atom board on Pi Zero
3. Configure for Atom-specific timing
4. Test with Atom software

## Compatibility Matrix

| Computer | Compatible Board | Connection | Notes |
|----------|------------------|------------|-------|
| BBC Micro B | RGBtoHDMI v1-v4 | 15-pin D-sub | All modes supported |
| BBC Micro B+ | RGBtoHDMI v1-v4 | 15-pin D-sub | Enhanced modes |
| BBC Master | RGBtoHDMI v1-v4 | 15-pin D-sub | Master-specific timing |
| BBC Electron | RGBtoHDMI v1-v4 | Expansion port | Requires adapter |
| Acorn Atom | RGBtoHDMI Atom v1-v2 | Expansion port | Atom-specific board |

## Assembly Instructions

### Main Board Assembly

**Components Required**:
- XC9572XL CPLD (44-pin VQFP)
- GPIO header and connectors
- Resistors, capacitors, LEDs
- Crystal oscillator

**Assembly Steps**:
1. Solder surface mount CPLD first
2. Install through-hole components
3. Add headers and connectors
4. Test and program CPLD

### Atom Adapter Assembly

**Additional Components**:
- LM319 comparator chips (v2)
- Atom-specific connectors
- Custom timing components
- Expansion port interface

**Special Considerations**:
- LM319 chip handling and socketing
- Atom connector pin identification
- Timing component selection

## Troubleshooting

### Common Issues

**No Video Output**:
- Check cable connections
- Verify RGBtoHDMI board programming
- Test with different video mode
- Check power supply

**Poor Image Quality**:
- Run calibration procedure
- Check cable quality
- Verify signal integrity
- Adjust sampling parameters

**Mode 7 Issues (BBC Micro)**:
- Verify teletext mode selection
- Check sync signal quality
- Adjust timing parameters
- Update firmware if needed

**Atom Timing Issues**:
- Verify Atom-specific configuration
- Check LM319 circuitry (v2)
- Test with different Atom software
- Adjust timing parameters

### Advanced Troubleshooting

**Signal Analysis**:
- Use oscilloscope to verify signals
- Check timing relationships
- Verify sync signal integrity
- Look for noise or interference

**Compatibility Testing**:
- Test with different software
- Try various video modes
- Check with different monitor
- Verify cable integrity

## Files and Resources

### Design Files
- **Schematics**: Available for all board variants
- **PCB Layouts**: KiCad format files
- **Gerber Files**: Manufacturing outputs
- **BOMs**: Component specifications

### Software Resources
- **Firmware**: CPLD programming files
- **Drivers**: Pi Zero software
- **Profiles**: System-specific configurations
- **Calibration Tools**: Setup utilities

### Documentation
- **Assembly Guides**: Build instructions
- **Installation Manuals**: Setup procedures
- **User Guides**: Operation instructions
- **Technical References**: Detailed specifications

## Version History

### Main RGBtoHDMI Boards
- **v1-v3**: Legacy versions with incremental improvements
- **v4**: Current production version with enhanced features

### Atom Adapters
- **v1**: Initial Atom-specific design
- **v2**: Enhanced version with LM319 comparators

## Future Development

**Planned Improvements**:
- Enhanced calibration algorithms
- Additional video mode support
- Improved signal processing
- Component availability management

**Research Areas**:
- Higher resolution modes
- Enhanced color processing
- Better compatibility with rare systems

## Support Resources

For technical support with Acorn computer adapters:
- Check individual board documentation
- Review BBC Micro/Electron community resources
- Consult Acorn user forums
- File GitHub issues for specific problems

### Community Resources

**BBC Micro**:
- Stardot forum
- BBC Micro community groups
- Retrocomputing communities

**Acorn Atom**:
- Atom development community
- Acorn user groups
- Vintage computer forums