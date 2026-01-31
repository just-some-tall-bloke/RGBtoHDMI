# 6-bit RGB Boards

This section documents the 6-bit RGB board variants that provide essential RGBtoHDMI functionality for systems with 6-bit TTL video outputs.

## Overview

6-bit RGB boards are designed for computer systems that output 6-bit TTL RGB signals (64 colors). These boards provide the core RGBtoHDMI functionality with optimized performance for 6-bit systems.

## Board Variants

### 1. RGBtoHDMI 6-bit v4

**Location**: `Kicad_6Bit/v4/`
- **Target**: General 6-bit RGB systems (BBC Micro, etc.)
- **Signal Type**: 6-bit TTL RGB
- **Form Factor**: Standard Pi Zero HAT
- **Features**:
  - Current production version
  - Optimized signal routing
  - Enhanced stability
  - Improved component placement
  - Better EMI performance
  - Simplified assembly

**Technical Improvements**:
- Enhanced signal integrity
- Better power distribution
- Improved timing characteristics
- Reduced component count
- Optimized PCB layout

**Status**: Current Production

### 2. RGBtoHDMI 6-bit v3 Variants

The v3 series offers multiple configurations for different use cases.

#### v3_Standard
**Location**: `Kicad_6Bit/v3_Standard/`
- **Target**: Standard 6-bit applications
- **Signal Type**: 6-bit TTL RGB
- **Form Factor**: Standard Pi Zero HAT
- **Features**:
  - Standard configuration
  - Resistor networks for signal termination
  - Multiple configuration jumpers
  - Stable and proven design

**Key Features**:
- **Resistor Networks**: SIP resistor arrays for signal conditioning
- **Configuration Jumpers**: Flexible setup options
- **Standard Layout**: Familiar component placement
- **Proven Design**: Extensively tested configuration

#### v3_Template
**Location**: `Kicad_6Bit/v3_Template/`
- **Target**: Development and customization
- **Signal Type**: 6-bit TTL RGB
- **Form Factor**: Standard Pi Zero HAT
- **Features**:
  - Development template
  - Extensible design
  - Additional mounting points
  - Customization-friendly layout

**Use Cases**:
- Custom board development
- Feature experimentation
- Educational purposes
- Prototype development

#### v3_CASE_DRILLING
**Location**: `Kicad_6Bit/v3_CASE_DRILLING/`
- **Target**: Case-specific installations
- **Signal Type**: 6-bit TTL RGB
- **Form Factor**: Custom mounting options
- **Features**:
  - Custom drilling templates
  - Alternative mounting holes
  - Case integration features
  - Specialized mechanical design

**Special Features**:
- **Custom Mounting**: Non-standard hole patterns
- **Case Integration**: Designed for specific enclosures
- **Mechanical Optimizations**: Enhanced physical fit
- **Alternative Layouts**: Case-friendly component placement

### 3. RGBtoHDMI 6-bit v2

**Location**: `Kicad_6Bit/v2/`
- **Target**: Legacy 6-bit systems
- **Signal Type**: 6-bit TTL RGB
- **Form Factor**: Standard Pi Zero HAT
- **Features**:
  - Proven legacy design
  - Reliable operation
  - Standard functionality
  - Good signal quality

**Technical Specifications**:
- Standard RGB signal processing
- Basic signal conditioning
- Proven reliability
- Good compatibility

**Status**: Legacy

### 4. RGBtoHDMI 6-bit v1

**Location**: `Kicad_6Bit/v1/`
- **Target**: Original 6-bit implementation
- **Signal Type**: 6-bit TTL RGB
- **Form Factor**: Standard Pi Zero HAT
- **Features**:
  - Original design concept
  - Basic functionality
  - Simpler circuit
  - Minimal features

**Historical Significance**:
- First production design
- Proof of concept
- Learning platform
- Simplicity-focused

**Status**: Legacy/Archival

## Technical Specifications

### Signal Processing

**6-bit RGB Characteristics**:
- **Color Depth**: 6 bits total (2 bits per channel)
- **Color Count**: 64 possible colors
- **Signal Type**: TTL digital (0V/5V)
- **Bandwidth**: Standard for 6-bit systems
- **Timing**: System-specific

**Signal Conditioning**:
- **Input Protection**: ESD and overvoltage protection
- **Level Matching**: TTL to CPLD compatible levels
- **Impedance Matching**: Signal integrity preservation
- **Noise Filtering**: EMI reduction

### Common Features

**Core Components**:
- **CPLD**: Xilinx XC9572XL or equivalent
- **Pi Zero Header**: 40-pin GPIO connection
- **Signal Inputs**: 6-bit RGB input connectors
- **Power Management**: 5V power regulation
- **Status Indicators**: LED status display

**Input Options**:
- **Direct Input**: Direct TTL connection
- **Buffered Input**: With signal buffering
- **Configurable**: Jumpers for different configurations

## Version Comparison

### Evolution Timeline

**v1 → v2**:
- Improved signal routing
- Enhanced power regulation
- Better component placement

**v2 → v3**:
- Added resistor networks
- Multiple configuration options
- Enhanced flexibility

**v3 → v4**:
- Simplified design
- Improved signal integrity
- Better manufacturability
- Enhanced reliability

### Detailed Comparison

| Feature | v1 | v2 | v3_Standard | v3_Template | v3_Case | v4 |
|---------|----|----|-------------|-------------|---------|----|
| Basic Functionality | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Resistor Networks | ✗ | ✗ | ✓ | ✓ | ✓ | ✓ |
| Configuration Jumpers | Limited | Basic | ✓ | ✓ | ✓ | ✓ |
| Case Mounting | Standard | Standard | Standard | Enhanced | ✓ | ✓ |
| Signal Integrity | Basic | Good | Good | Good | Good | Enhanced |
| Assembly Complexity | Low | Medium | Medium | Medium | Medium | Low |
| Status | Legacy | Legacy | Legacy | Legacy | Legacy | Current |

## Assembly Instructions

### Common Components

**Required for All Versions**:
- XC9572XL CPLD (44-pin VQFP)
- 40-pin GPIO header (right-angle)
- Input connectors (headers or other)
- Power regulation components
- Status LED and resistor

**Version-Specific Components**:
- **v3 Series**: Resistor networks (SIP6)
- **v3_Template**: Additional mounting hardware
- **v3_Case**: Custom mounting hardware
- **v4**: Optimized component selection

### Assembly Process

**Step 1: Surface Mount Components**:
1. Solder CPLD first (most challenging)
2. Use appropriate temperature profile
3. Verify all pins are properly connected
4. Inspect for solder bridges

**Step 2: Through-Hole Components**:
1. Install resistors and resistor networks
2. Add capacitors
3. Install GPIO header
4. Add input connectors
5. Install LED and current-limiting resistor

**Step 3: Configuration**:
1. Set jumpers for desired configuration
2. Verify jumper settings
3. Install any optional components
4. Final inspection

### Quality Assurance

**Testing Procedures**:
1. Visual inspection for defects
2. Multimeter continuity testing
3. Power-on test (without CPLD)
4. CPLD programming test
5. Signal integrity verification

## Installation Guide

### System Compatibility

**Supported Systems**:
- **BBC Micro**: All models with 6-bit RGB
- **BBC Electron**: 6-bit output modes
- **Acorn Atom**: 6-bit video modes
- **Other Systems**: Any 6-bit TTL RGB source

**Connection Methods**:
- **Direct Cable**: Direct TTL connection
- **Buffer Adapter**: With signal buffer
- **Custom Interface**: System-specific adapters

### Physical Installation

**Pi Zero Mounting**:
1. Align board with Pi Zero GPIO
2. Press firmly to ensure proper connection
3. Secure with mounting hardware if available
4. Verify no bent pins

**Cable Connections**:
1. Connect RGB input cable
2. Ensure proper polarity
3. Secure cable connections
4. Route cables away from interference

## Troubleshooting

### Common Issues

**No Video Output**:
- Check Pi Zero GPIO connection
- Verify CPLD programming
- Test input signal presence
- Check power supply

**Poor Image Quality**:
- Verify input cable quality
- Check signal integrity
- Test different configurations
- Verify CPLD firmware version

**Configuration Problems**:
- Verify jumper settings
- Check resistor network values
- Test with known-good configuration
- Consult version-specific documentation

### Advanced Troubleshooting

**Signal Analysis**:
- Use oscilloscope to verify signals
- Check timing relationships
- Verify signal levels
- Look for noise or distortion

**Component Testing**:
- Test resistor networks
- Verify CPLD functionality
- Check power regulation
- Test input connector integrity

## Files and Resources

### Design Files
- **Schematics**: `.sch` files for each version
- **PCB Layouts**: `.kicad_pcb` files
- **Gerber Files**: Manufacturing outputs
- **BOMs**: Component lists and specifications

**Version-Specific Files**:
- **v4**: Current production files
- **v3 Series**: Multiple configuration options
- **v2/v1**: Legacy designs

### Documentation
- **Assembly Guides**: Version-specific instructions
- **Configuration Manuals**: Jumper settings and options
- **Compatibility Charts**: System support information
- **Troubleshooting Guides**: Common issues and solutions

## Manufacturing Notes

### PCB Production
- **Gerber Files**: Ready for manufacture
- **Drill Files**: Standard drilling specifications
- **Solder Mask**: Standard green unless specified
- **Silkscreen**: Clear component labeling

### Component Sourcing
- **CPLD**: Xilinx XC9572XL-VQFP44
- **Resistor Networks**: SIP6 4.7kΩ standard
- **Headers**: Standard 2.54mm pitch
- **Passive Components**: Standard values

## Future Development

**Current Focus**:
- v4 production optimization
- Component availability management
- Minor refinements

**Potential Improvements**:
- Enhanced signal processing
- Additional configuration options
- Better case compatibility
- Simplified assembly

## Support Resources

For technical support with 6-bit RGB boards:
- Check version-specific documentation
- Consult RGBtoHDMI main documentation
- Review community forums
- File GitHub issues for specific problems

### Community Resources

**Forums and Communities**:
- RGBtoHDMI GitHub discussions
- Retrocomputing communities
- BBC Micro/Electron user groups
- Vintage computer forums

**Technical Resources**:
- RGBtoHDMImain documentation
- Version-specific release notes
- Community modifications and improvements