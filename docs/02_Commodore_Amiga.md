# Commodore Amiga Adapters

This section documents the various Amiga-specific adapter boards designed to interface RGBtoHDMI with Commodore Amiga computers.

## Overview

The Amiga adapters are designed to connect directly to the Amiga's video output circuitry, providing high-quality 12-bit RGB signal capture. Different variants support different Amiga models and installation methods.

## Adapter Variants

### 1. Denise Adapter V1

**Location**: `kicad_AmigaAdapter/V1/`
- **Target**: Amiga 500, 500+, 600, 1200, 2000
- **Connection**: Direct Denise chip replacement/attachment
- **Signal Type**: 12-bit TTL RGB
- **Form Factor**: Small PCB that attaches near Denise chip
- **Features**:
  - Direct connection to Denise chip outputs
  - 12-bit RGB capture (4096 colors)
  - Compatible with original Denise (8362) and Super Denise (8373)
  - Minimal installation footprint

**Installation**:
- Requires access to Denise chip on motherboard
- Board sits adjacent to Denise chip
- Wire connections to Denise pins
- Jumper configuration for Denise type

**Status**: Legacy

### 2. Denise Adapter V2

**Location**: `kicad_AmigaAdapter/V2/`
- **Target**: Amiga 500, 500+, 600, 1200, 2000
- **Connection**: Enhanced Denise interface
- **Signal Type**: 12-bit TTL RGB
- **Form Factor**: Improved PCB layout
- **Features**:
  - Improved signal routing and integrity
  - Better Denise compatibility handling
  - Enhanced timing stability
  - Cleaner installation process

**Improvements over V1**:
- Better component placement
- Improved signal paths
- Enhanced reliability
- Better EMI performance

**Status**: Legacy

### 3. Small Denise Adapter

**Location**: `kicad_AmigaAdapter/Small/`
- **Target**: Space-constrained Amiga installations
- **Connection**: Compact Denise interface
- **Signal Type**: 12-bit TTL RGB
- **Form Factor**: Ultra-compact design
- **Features**:
  - Minimal footprint for tight spaces
  - Essential functionality only
  - Direct Denise connection
  - Simplified wiring

**Use Cases**:
- Amiga 600 tight installations
- Cases with limited space
- When minimal modification is desired

**Status**: Current (for specific applications)

### 4. Video Slot Adapter V1

**Location**: `kicad_AmigaAdapter/VideoSlot/V1/`
- **Target**: Amiga 2000, 3000, 4000 (big box Amigas)
- **Connection**: Video slot (Zorro/Video slot)
- **Signal Type**: 12-bit TTL RGB
- **Form Factor**: Video slot card
- **Features**:
  - Installs in video slot (no motherboard modification)
  - Direct video slot signal access
  - 7MHz signal derived from C1 XNOR C3
  - Dual button connectors for flexible control
  - Bracket mounting for rear access
  - Card edge connector with bevel space

**Key Innovations**:
- **7MHz Signal Generation**: Uses C1 XNOR C3 since 7MHz not directly available
- **Dual Button Support**: Rear bracket button + additional remote button
- **Professional Installation**: Proper video slot mounting

**Version History**:
- **V1.00**: Initial version
- **V1.01**: Added 47pF capacitor (C6) for image stability, grounded unused inputs
- **V1.1**: Major routing improvements, eliminates "sparkling" on certain patterns, no longer requires excessive overclocking

**Installation Notes**:
- Set Denise jumper for chip type (8373 for Super Denise, 8362 for original)
- Orient PCB with bracket mounting holes facing rear
- Card edge connector allows for beveling (1mm space provided)

**Status**: Current Production

## Technical Specifications

### Common Features

**Signal Processing**:
- **Color Depth**: 12-bit RGB (4096 colors)
- **Signal Type**: TTL digital RGB
- **Sync**: Composite sync extraction
- **Timing**: Precise Amiga-specific timing

**Electrical Specifications**:
- **Power**: +5V from Raspberry Pi
- **Current**: Minimal (<100mA)
- **Voltage Levels**: TTL compatible
- **Impedance**: Optimized for Amiga signals

### Denise Chip Compatibility

**Original Denise (8362)**:
- Used in Amiga 500, 2000, early models
- Standard resolution modes
- Jumper setting: "Denise"

**Super Denise (8373)**:
- Used in Amiga 500+, 600, 1200
- Enhanced video modes
- Jumper setting: "Super Denise"

**Installation Requirements**:
- Correct jumper configuration
- Verify chip identification
- Test compatibility before final installation

## Installation Guide

### Denise Adapter Installation

**Preparation**:
1. Power off and unplug Amiga
2. Remove case covers as needed
3. Identify Denise chip location
4. Determine Denise chip type

**Physical Installation**:
1. Clean Denise chip area
2. Position adapter board
3. Connect signal wires to appropriate Denise pins
4. Set jumper for Denise type
5. Secure board with adhesive or mounting
6. Route cables to RGBtoHDMI board

**Wiring Connections**:
- RGB signals: R0-R3, G0-G3, B0-B3
- Sync signals: HSYNC, VSYNC
- Ground connections
- Power connections

### Video Slot Adapter Installation

**Preparation**:
1. Power off Amiga
2. Remove video slot cover
3. Identify available video slot
4. Prepare mounting bracket

**Physical Installation**:
1. Insert adapter into video slot
2. Secure with bracket screws
3. Connect button cables as desired
4. Route cables to RGBtoHDMI
5. Replace slot cover with adapter

**Button Configuration**:
- **Rear Button**: For convenient access
- **Remote Button**: Mount in desired location
- **Both usable**: Simultaneous operation possible

## Compatibility Matrix

| Amiga Model | Compatible Adapter | Installation Type | Notes |
|-------------|-------------------|-------------------|-------|
| Amiga 500 | Denise V1, V2, Small | Direct to Denise | Original Denise chip |
| Amiga 500+ | Denise V1, V2, Small | Direct to Denise | Super Denise chip |
| Amiga 600 | Denise Small recommended | Direct to Denise | Space constraints |
| Amiga 1200 | Denise V1, V2, Small | Direct to Denise | Super Denise chip |
| Amiga 2000 | Denise V1, V2, VideoSlot | Both options | Video slot preferred |
| Amiga 3000 | VideoSlot only | Video slot | Different architecture |
| Amiga 4000 | VideoSlot only | Video slot | Different architecture |

## Assembly Instructions

### Common Components

**Core Components**:
- 74LVC86 or similar logic chips
- Resistors and capacitors
- Headers and connectors
- Jumpers for configuration
- LEDs for status indication

**Tools Required**:
- Fine-tip soldering iron
- Solder wire and flux
- Wire strippers and cutters
- Multimeter for testing
- Heat shrink tubing

### Assembly Process

**Step 1: Solder Components**
1. Install resistors first
2. Add capacitors
3. Solder logic ICs (use sockets if possible)
4. Install headers and connectors
5. Add jumpers and LEDs

**Step 2: Testing**
1. Check for shorts with multimeter
2. Verify power connections
3. Test signal paths (if possible)
4. Inspect for solder bridges

**Step 3: Final Assembly**
1. Install jumpers for Denise type
2. Add button connectors (VideoSlot)
3. Apply labels if desired
4. Package with documentation

## Troubleshooting

### Common Issues

**No Video Output**:
- Check Denise jumper setting
- Verify wire connections to Denise pins
- Test RGBtoHDMI board separately
- Check power connections

**Poor Image Quality**:
- Verify all signal connections
- Check for signal interference
- Ensure proper Denise type setting
- Test cable quality

**Sync Issues**:
- Verify sync wire connections
- Check Denise jumper configuration
- Test with different Denise chip if available
- Check for timing issues

**Video Slot Issues**:
- Ensure proper slot insertion
- Check bracket mounting
- Verify card edge connector contact
- Test button connections

### Advanced Troubleshooting

**Signal Analysis**:
- Use oscilloscope to verify signals at Denise pins
- Check signal integrity at adapter inputs
- Verify timing relationships
- Look for noise or interference

**Component Testing**:
- Test logic chips with logic probe
- Verify resistor values
- Check capacitor functionality
- Test jumper configurations

## Files and Resources

### Design Files
- **Schematics**: `.sch` files in each adapter directory
- **PCB Layouts**: `.kicad_pcb` files
- **Gerber Files**: Manufacturing outputs
- **BOMs**: Component lists where available

**Video Slot Specific**:
- **Card Edge Library**: From Amiga-KiCad-Library
- **Bracket Files**: Mounting specifications
- **Button Wiring**: Control cable documentation

### Documentation
- **Assembly Guides**: Detailed build instructions
- **Installation Manuals**: Step-by-step procedures
- **Compatibility Charts**: Model-specific information
- **Interactive BOM**: VideoSlot V1 includes ibom.html

## Version Comparison

| Adapter | Target | Form Factor | Features | Status |
|---------|--------|-------------|----------|---------|
| Denise V1 | All Amigas | Small PCB | Basic 12-bit capture | Legacy |
| Denise V2 | All Amigas | Small PCB | Improved routing | Legacy |
| Denise Small | Space-limited | Ultra-compact | Essential features | Current |
| VideoSlot V1 | Big box Amigas | Slot card | Professional install | Current |

## Future Development

**Active Development**:
- VideoSlot adapter refinements
- Component availability management
- Installation simplification

**Potential Improvements**:
- Additional Amiga model support
- Enhanced signal processing
- Automated calibration features

## Support Resources

For technical support with Amiga adapters:
- Check adapter-specific documentation
- Review the VideoSlot README for detailed installation
- Consult Amiga community forums
- File GitHub issues for specific problems