# Atari ST Adapters

This section documents the Atari ST-specific pickup adapters designed to interface RGBtoHDMI with Atari ST computer systems.

## Overview

Atari ST computers use a custom video chip called the "Shifter" that generates 12-bit RGB output. The Atari ST adapters interface directly with this chip to capture high-quality video signals for conversion to HDMI.

## Adapter Variants

### 1. Atari ST 12-bit Buffered Pickup

**Location**: `Kicad_Atari_ST_12Bit_Buffered_Pickup/V1/`
- **Target**: Atari ST, STFM, STE, Mega ST, Mega STE
- **Connection**: Direct Shifter chip interface
- **Signal Type**: 12-bit TTL RGB (buffered)
- **Form Factor**: Shifter socket replacement board
- **Features**:
  - Buffered signal outputs for improved signal integrity
  - Direct connection to Shifter chip pins
  - 12-bit RGB capture (4096 colors)
  - Enhanced signal conditioning
  - Improved noise immunity
  - Better long cable performance

**Technical Details**:
- **Buffering**: Active buffering of RGB signals
- **Signal Integrity**: Reduced signal degradation
- **Noise Reduction**: Better EMI performance
- **Distance**: Suitable for longer cable runs

**Installation**:
- Requires desoldering of original Shifter chip
- Adapter plugs into Shifter socket
- Shifter chip plugs into adapter
- RGB signals available from adapter output pins

### 2. Atari ST 12-bit Unbuffered Pickup

**Location**: `Kicad_Atari_ST_12Bit_UnBuffered_Pickup/V1/`
- **Target**: Atari ST, STFM, STE, Mega ST, Mega STE
- **Connection**: Direct Shifter chip interface
- **Signal Type**: 12-bit TTL RGB (unbuffered)
- **Form Factor**: Shifter socket replacement board
- **Features**:
  - Direct pass-through of Shifter signals
  - Minimal signal modification
  - Lower component count
  - Simpler design
  - Lower cost
  - Direct signal preservation

**Technical Details**:
- **Signal Path**: Direct from Shifter to output
- **Latency**: Minimal signal delay
- **Complexity**: Reduced circuit complexity
- **Cost**: Lower manufacturing cost

**Installation**:
- Similar installation to buffered version
- Direct connection to Shifter chip
- Output signals taken directly from Shifter pins

## Technical Specifications

### Shifter Chip Compatibility

**Supported Shifter Chips**:
- **Standard Shifter**: Used in Atari ST, STFM
- **Enhanced Shifter**: Used in Atari STE, Mega STE
- **Mega Variants**: All Mega ST/STE models

**Signal Characteristics**:
- **Color Depth**: 12-bit RGB (4 bits per channel)
- **Resolution**: Various (320x200, 640x200, 640x400)
- **Refresh Rate**: 50Hz (PAL) or 60Hz (NTSC)
- **Sync**: Separate HSYNC/VSYNC

### Signal Outputs

**RGB Signals**:
- **R0-R3**: Red channel (4 bits)
- **G0-G3**: Green channel (4 bits)
- **B0-B3**: Blue channel (4 bits)
- **MONO**: Monochrome signal (for mono modes)

**Sync Signals**:
- **HSYNC**: Horizontal synchronization
- **VSYNC**: Vertical synchronization
- **DE**: Data enable (where available)

**Control Signals**:
- **CLK**: Pixel clock
- **LOAD**: Load control
- **GND**: Ground connections

## Installation Guide

### Pre-Installation Requirements

**Tools Required**:
- Soldering iron with temperature control
- Desoldering pump or desoldering station
- Fine-tip soldering iron
- Solder wick (for cleanup)
- Multimeter for testing
- Chip extractor tools (helpful)

**Safety Precautions**:
- Power off and unplug Atari ST
- Use proper ESD precautions
- Work in well-lit area
- Have replacement parts available

### Installation Process

**Step 1: Disassembly**
1. Remove Atari ST case
2. Identify Shifter chip location
3. Document original wiring
4. Take photos for reference

**Step 2: Chip Removal**
1. Apply heat to Shifter chip pins
2. Use desoldering pump to remove solder
3. Carefully lift chip from socket
4. Clean socket holes completely

**Step 3: Adapter Installation**
1. Install adapter PCB in Shifter socket
2. Solder adapter in place
3. Install Shifter chip in adapter socket
4. Verify all connections

**Step 4: Connection Testing**
1. Check for shorts with multimeter
2. Verify power connections
3. Test signal outputs (if possible)
4. Reassemble partially for testing

### Wiring Instructions

**Signal Connections**:
- Connect RGB signals to RGBtoHDMI input
- Connect sync signals appropriately
- Ensure proper ground connections
- Route cables away from interference sources

**Cable Recommendations**:
- Use shielded cable for longer runs
- Keep cable lengths reasonable
- Properly ground cable shields
- Use appropriate connectors

## Atari ST Model Compatibility

### Compatible Models

**Atari ST Series**:
- **Atari 260ST**: Base model
- **Atari 520ST**: Standard model
- **Atari 1040ST**: Enhanced model
- **Atari STFM**: FM sound version

**Atari STE Series**:
- **Atari STE**: Enhanced version
- **Mega ST**: Professional model
- **Mega STE**: Enhanced professional

**Special Considerations**:
- **ST vs STE**: Different Shifter chip versions
- **Mega Models**: May have different board layouts
- **STFM**: Additional sound circuitry nearby

### Model-Specific Notes

**Atari ST**:
- Standard Shifter chip
- Consistent pinout across models
- Straightforward installation

**Atari STE**:
- Enhanced Shifter chip
- Additional video modes
- May require jumper changes

**Mega ST/STE**:
- Different motherboard layout
- Possibly larger working area
- Enhanced shielding considerations

## Assembly Instructions

### Buffered Version Assembly

**Components Required**:
- 40-pin IC socket (for Shifter)
- Buffer ICs (74LVC series or similar)
- Resistors and capacitors
- Header pins for signal output
- PCB with appropriate footprint

**Assembly Steps**:
1. Install IC socket for Shifter chip
2. Solder buffer ICs
3. Install resistors and capacitors
4. Add header pins for outputs
5. Test signal paths

### Unbuffered Version Assembly

**Components Required**:
- 40-pin IC socket (for Shifter)
- Header pins for signal output
- Minimal passive components
- PCB with appropriate footprint

**Assembly Steps**:
1. Install IC socket for Shifter chip
2. Add header pins for direct connection
3. Install minimal passive components
4. Verify connections

## Troubleshooting

### Common Installation Issues

**No Video Output**:
- Verify Shifter chip is properly seated
- Check adapter socket connections
- Test with original Shifter (if possible)
- Verify RGBtoHDMI connections

**Poor Image Quality**:
- Check for cold solder joints
- Verify proper Shifter installation
- Test cable connections
- Check for signal interference

**Sync Problems**:
- Verify sync signal connections
- Check proper ground connections
- Test with different sync configurations
- Verify RGBtoHDMI sync input settings

**Model-Specific Issues**:
- Confirm correct Shifter chip type
- Check for model-specific differences
- Verify adapter compatibility
- Consult model-specific documentation

### Advanced Troubleshooting

**Signal Analysis**:
- Use oscilloscope to verify Shifter outputs
- Check signal levels and timing
- Verify RGB signal integrity
- Test sync signal quality

**Compatibility Testing**:
- Test with different software
- Try various video modes
- Test with different Atari models
- Verify compatibility with RGBtoHDMI firmware

## Files and Resources

### Design Files
- **Schematics**: `.sch` files for both versions
- **PCB Layouts**: `.kicad_pcb` files
- **Gerber Files**: Manufacturing outputs
- **Footprints**: Custom Shifter socket footprints

**Component Libraries**:
- **Shifter Footprint**: 40-pin DIP footprint
- **Custom Parts**: Any specialized components
- **Standard Libraries**: Common KiCad libraries

### Documentation
- **Assembly Guides**: Detailed build instructions
- **Installation Manuals**: Step-by-step procedures
- **Compatibility Charts**: Model-specific information
- **Schematics**: Circuit diagrams and explanations

## Version Comparison

| Feature | Buffered Version | Unbuffered Version |
|---------|------------------|--------------------|
| Signal Integrity | Enhanced | Direct |
| Noise Immunity | Better | Standard |
| Cable Length | Longer | Limited |
| Complexity | Higher | Lower |
| Cost | Higher | Lower |
| Installation | Same | Same |
| Compatibility | Full | Full |

## Future Development

**Potential Improvements**:
- Enhanced buffering options
- Additional signal conditioning
- Improved installation methods
- Better compatibility testing

**Research Areas**:
- STe-specific enhancements
- Mega model optimizations
- Reduced installation complexity
- Automated calibration features

## Support Resources

For technical support with Atari ST adapters:
- Check Atari ST community forums
- Consult RGBtoHDMI documentation
- Review Atari ST technical references
- File GitHub issues for specific problems

### Atari ST Community Resources

**Forums and Communities**:
- Atari-Forum
- AtariAge forums
- Retrocomputing communities
- ST-specific user groups

**Technical Resources**:
- Atari ST hardware documentation
- Shifter chip specifications
- Video timing references
- Service manuals

---

*Note: Installation of these adapters requires advanced soldering skills and knowledge of Atari ST hardware. If you're not confident in your abilities, seek assistance from experienced technicians.*