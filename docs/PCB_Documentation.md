# RGBtoHDMI PCB Documentation

This directory contains comprehensive documentation for all PCB designs in the RGBtoHDMI project.

## Table of Contents

- [Main Boards](01_Main_Boards.md) - Core RGBtoHDMI interface boards
- [Acorn Computers](02_Acorn_Computers.md) - BBC Micro, Electron, and Atom adapters
- [Commodore Amiga](03_Commodore_Amiga.md) - Amiga-specific adapters and buffers
- [Atari ST](04_Atari_ST.md) - Atari ST pickup solutions
- [Buffer Boards](05_Buffer_Boards.md) - Signal integrity and extension solutions
- [Analog Solutions](06_Analog_Solutions.md) - Analog RGB input boards
- [Special Purpose](07_Special_Purpose.md) - Clock fixers and other specialized boards

## Board Categories

### Main Interface Boards
These are the primary RGBtoHDMI interface boards that connect to the Raspberry Pi Zero:
- RGBtoHDMI v1-v4 (6-bit and 12-bit variants)
- RGBtoHDMI Atom v1-v2 (Acorn Atom specific)

### System-Specific Adapters
Boards designed for specific computer systems:
- Amiga Denise adapters (V1, V2, Small, VideoSlot)
- Amiga 12-bit buffered pickup
- Atari ST 12-bit pickup (buffered and unbuffered)
- Commodore 128 VIC-IIe adapter

### Signal Integrity Solutions
Buffer and extender boards for improved signal quality:
- 3-bit, 6-bit, 8-bit, 12-bit buffer boards
- PC buffer for general purpose use
- Various extender solutions

### Analog Input Solutions
Boards for handling analog RGB signals:
- Analog 6-bit RGB boards (V1-V3)

### Special Purpose Boards
Specialized hardware solutions:
- Clock fixer for timing correction
- Custom drilling templates

## Documentation Standards

Each PCB documentation includes:
- **Overview**: Purpose and target systems
- **Features**: Key technical specifications
- **Hardware**: Bill of materials and component details
- **Assembly**: Build instructions and tips
- **Installation**: How to install and configure
- **Compatibility**: Supported systems and requirements
- **Version History**: Evolution and changes
- **Files**: Links to schematics, layouts, and manufacturing files

## Quick Reference

| Board Type | Target System | Signal Type | Versions | Status |
|-------------|---------------|-------------|----------|---------|
| Main RGBtoHDMI | BBC Micro/Electron | 6/12-bit TTL | v1-v4 | Production |
| Atom Adapter | Acorn Atom | TTL | v1-v2 | Production |
| Amiga Denise | Commodore Amiga | 12-bit TTL | V1,V2,Small,VideoSlot | Production |
| Amiga Pickup | Amiga External | 12-bit TTL | V1 | Production |
| Atari ST | Atari ST/STE | 12-bit TTL | Buffered/Unbuffered | Production |
| Analog Boards | Various analog | Analog RGB | V1-V3 | Production |
| Buffer Boards | Signal extension | Various | Multiple | Production |

## Getting Started

1. Identify your target computer system
2. Determine the signal type (digital TTL vs analog)
3. Check the compatibility chart above
4. Navigate to the relevant documentation section
5. Follow the assembly and installation instructions

## Manufacturing Notes

- All designs use KiCad format
- Gerber files available for production
- BOMs include part numbers and alternatives
- PCB manufacturers recommended in individual docs

## Support

For technical support:
- Check individual board documentation first
- Review the main RGBtoHDMIdocumentation
- Consult the project GitHub issues
- Contact the community forums

---

*This documentation is maintained as part of the RGBtoHDMI project. For the most up-to-date information, visit the main project repository.*