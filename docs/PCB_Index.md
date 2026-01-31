# RGBtoHDMI PCB Index

This document provides a comprehensive index of all PCBs documented in the RGBtoHDMI project, organized by category, use case, and technical specifications.

## Quick Reference Guide

### Find Your Board Quickly

**By Target System**:
- [BBC Micro/Electron](#bbc-microelectron) → Main RGBtoHDMI boards
- [Acorn Atom](#acorn-atom) → Atom-specific boards
- [Commodore Amiga](#commodore-amiga) → Amiga adapters
- [Atari ST](#atari-st) → Atari ST pickup adapters
- [Commodore 128](#commodore-128) → C128 adapter

**By Signal Type**:
- [6-bit TTL RGB](#6-bit-ttl-rgb) → Main and 6-bit boards
- [12-bit TTL RGB](#12-bit-ttl-rgb) → Amiga/Atari adapters
- [Analog RGB](#analog-rgb) → Analog boards
- [Buffer/Extension](#buffer-and-extension-boards) → Buffer boards

## Board Categories

### 1. Main RGBtoHDMI Boards

**Purpose**: Core interface boards for Pi Zero with CPLD
**Target**: BBC Micro, BBC Electron
**Signal**: 6-bit TTL RGB

| Board | Version | Location | Status | Features |
|-------|---------|----------|--------|----------|
| RGBtoHDMI Main | v1-v4 | `kicad/v1-v4/` | v4 Current | Production-ready, proven design |
| RGBtoHDMI Atom | v1-v2 | `kicad_atom/v1-v2/` | v2 Current | Atom-specific with LM319 comparator |

**Documentation**: [01_Main_Boards.md](01_Main_Boards.md)

### 2. Commodore Amiga Adapters

**Purpose**: Interface with Amiga video circuitry
**Target**: Amiga 500, 500+, 600, 1200, 2000, 3000, 4000
**Signal**: 12-bit TTL RGB

| Adapter | Version | Location | Form Factor | Status |
|---------|---------|----------|-------------|---------|
| Denise Adapter | V1 | `kicad_AmigaAdapter/V1/` | Small PCB | Legacy |
| Denise Adapter | V2 | `kicad_AmigaAdapter/V2/` | Small PCB | Legacy |
| Denise Adapter | Small | `kicad_AmigaAdapter/Small/` | Ultra-compact | Current |
| VideoSlot Adapter | V1.1 | `kicad_AmigaAdapter/VideoSlot/V1/` | Slot card | Current |

**Documentation**: [02_Commodore_Amiga.md](02_Commodore_Amiga.md)

### 3. Atari ST Adapters

**Purpose**: Interface with Atari ST Shifter chip
**Target**: Atari ST, STFM, STE, Mega ST, Mega STE
**Signal**: 12-bit TTL RGB

| Adapter | Type | Location | Status | Features |
|---------|------|----------|--------|----------|
| Atari ST Pickup | Buffered | `Kicad_Atari_ST_12Bit_Buffered_Pickup/V1/` | Current | Signal buffering, long cable support |
| Atari ST Pickup | Unbuffered | `Kicad_Atari_ST_12Bit_UnBuffered_Pickup/V1/` | Current | Direct signal, lower cost |

**Documentation**: [04_Atari_ST.md](04_Atari_ST.md)

### 4. Acorn Computers

**Purpose**: Complete support for Acorn computer range
**Target**: BBC Micro, BBC Electron, Acorn Atom
**Signal**: 6-bit TTL RGB (various timing)

| System | Compatible Boards | Connection Type | Notes |
|--------|-------------------|----------------|-------|
| BBC Micro | RGBtoHDMI v1-v4 | 15-pin D-sub | All modes supported |
| BBC Electron | RGBtoHDMI v1-v4 | Expansion port | Requires adapter |
| Acorn Atom | RGBtoHDMI Atom v1-v2 | Expansion port | Atom-specific timing |

**Documentation**: [02_Acorn_Computers.md](02_Acorn_Computers.md)

### 5. 6-bit RGB Boards

**Purpose**: Dedicated 6-bit RGB solutions
**Target**: General 6-bit TTL systems
**Signal**: 6-bit TTL RGB

| Board | Version | Location | Status | Key Features |
|-------|---------|----------|--------|--------------|
| 6-bit RGB | v4 | `Kicad_6Bit/v4/` | Current | Production optimized |
| 6-bit RGB | v3_Standard | `Kicad_6Bit/v3_Standard/` | Legacy | Resistor networks |
| 6-bit RGB | v3_Template | `Kicad_6Bit/v3_Template/` | Legacy | Development template |
| 6-bit RGB | v3_Case | `Kicad_6Bit/v3_CASE_DRILLING/` | Legacy | Case mounting |
| 6-bit RGB | v2 | `Kicad_6Bit/v2/` | Legacy | Proven design |
| 6-bit RGB | v1 | `Kicad_6Bit/v1/` | Legacy | Original design |

**Documentation**: [05_6Bit_RGB_Boards.md](05_6Bit_RGB_Boards.md)

### 6. Analog Solutions

**Purpose**: Handle analog RGB video signals
**Target**: Systems with analog RGB output
**Signal**: Analog RGB (0-0.7V)

| Board | Version | Location | Status | Features |
|-------|---------|----------|--------|----------|
| Analog 6-bit | v3 | `kicad_analog_6bit/V3/` | Current | Enhanced A/D conversion |
| Analog 6-bit | v2 | `kicad_analog_6bit/V2/` | Legacy | Standard conversion |
| Analog 6-bit | v1 | `kicad_analog_6bit/V1/` | Legacy | Basic implementation |

**Documentation**: [06_Additional_Boards.md](06_Additional_Boards.md#analog-6-bit-boards)

### 7. Buffer and Extension Boards

**Purpose**: Signal integrity and distance extension
**Target**: Various systems requiring signal buffering
**Signal**: Multiple signal types

| Buffer Type | Bit Depth | Location | Status | Use Case |
|-------------|-----------|----------|--------|----------|
| 3-bit Buffer | 3-bit | `kicad_Extender_3_bit_buffer/V1/` | Current | Simple RGB extension |
| 6-bit Buffer | 6-bit | `kicad_Extender_6_bit_buffer/V1/` | Current | Standard RGB extension |
| 8-bit Buffer | 8-bit | `kicad_Extender_8_bit_buffer/V1/` | Current | Enhanced color depth |
| 12-bit Buffer | 12-bit | `kicad_Extender_12_bit_adapter/` | V2 Current | Premium quality |
| PC Buffer | Variable | `kicad_Extender_PC_buffer/` | V2 Current | Universal solution |

**Documentation**: [06_Additional_Boards.md](06_Additional_Boards.md#buffer-and-extender-boards)

### 8. Special Purpose Boards

**Purpose**: Specific technical solutions
**Target**: Specialized applications

| Board | Purpose | Location | Status | Features |
|-------|---------|----------|--------|----------|
| Clock Fixer | Timing correction | `kicad_Clock_fixer/V1/` | Current | Clock signal regeneration |
| C128 Adapter | VIC-IIe interface | `Kicad_Amiga_12Bit_Buffered_Pickup/V1/` | Current | C128 40-column support |

**Documentation**: [06_Additional_Boards.md](06_Additional_Boards.md#special-purpose-boards)

## Technical Specifications Matrix

### Signal Types and Compatibility

| Signal Type | Color Depth | Voltage Range | Typical Use |
|-------------|-------------|---------------|-------------|
| 6-bit TTL RGB | 64 colors | 0-5V TTL | BBC Micro, Electron |
| 12-bit TTL RGB | 4096 colors | 0-5V TTL | Amiga, Atari ST |
| Analog RGB | Variable | 0-0.7V | Various systems |
| Buffered TTL | Various | Regenerated | Signal extension |

### Form Factors

| Form Factor | Typical Size | Mounting | Examples |
|-------------|--------------|----------|----------|
| Pi Zero HAT | 65x30mm | GPIO pins | Main boards, 6-bit boards |
| Small PCB | Variable | Adhesive/screws | Amiga adapters |
| Slot Card | Standard PCI | Screw mounting | Amiga VideoSlot |
| Socket Adapter | Variable | Chip socket | Atari ST, C128 |

## System Compatibility Chart

### Complete Compatibility Matrix

| Computer System | Recommended Board | Signal Type | Installation Difficulty |
|------------------|-------------------|-------------|------------------------|
| BBC Micro B/B+ | RGBtoHDMI v4 | 6-bit TTL | Easy |
| BBC Master | RGBtoHDMI v4 | 6-bit TTL | Easy |
| BBC Electron | RGBtoHDMI v4 + adapter | 6-bit TTL | Medium |
| Acorn Atom | RGBtoHDMI Atom v2 | TTL custom | Medium |
| Amiga 500 | Denise Adapter V2/Small | 12-bit TTL | Medium |
| Amiga 500+ | Denise Adapter V2/Small | 12-bit TTL | Medium |
| Amiga 600 | Denise Adapter Small | 12-bit TTL | Hard |
| Amiga 1200 | Denise Adapter V2/Small | 12-bit TTL | Medium |
| Amiga 2000 | VideoSlot Adapter | 12-bit TTL | Easy |
| Amiga 3000/4000 | VideoSlot Adapter | 12-bit TTL | Easy |
| Atari ST | Atari ST Pickup (either) | 12-bit TTL | Hard |
| Atari STE | Atari ST Pickup (either) | 12-bit TTL | Hard |
| Commodore 128 | C128 Adapter | TTL | Hard |
| Analog Systems | Analog 6-bit v3 | Analog | Variable |

## Manufacturing Information

### Production Status

| Category | Current Versions | Legacy Versions | Notes |
|----------|------------------|-----------------|-------|
| Main Boards | v4, Atom v2 | v1-v3 | v4 recommended |
| Amiga Adapters | Small, VideoSlot V1.1 | V1, V2 | Choose by model |
| Atari ST | Both versions | N/A | Buffered for long cables |
| 6-bit Boards | v4 | v1-v3 | v4 is current |
| Analog Boards | v3 | v1-v2 | v3 has best performance |
| Buffer Boards | V2 (12-bit), others V1 | N/A | All current |

### File Availability

**Design Files**:
- **Schematics**: Available for all boards
- **PCB Layouts**: KiCad format (.kicad_pcb)
- **Gerber Files**: Manufacturing ready
- **BOMs**: Most boards have component lists

**Manufacturing Support**:
- Gerber archives for PCB production
- Drill files included
- Pick and place files where applicable
- Component libraries for KiCad

## Selection Guide

### How to Choose the Right Board

**Step 1: Identify Your System**
- Determine the target computer model
- Identify video output type (TTL vs analog)
- Check available connection points

**Step 2: Determine Signal Requirements**
- 6-bit vs 12-bit color depth
- TTL vs analog signal levels
- Special timing requirements

**Step 3: Consider Installation Constraints**
- Available space inside computer
- Technical skill level required
- Need for permanent vs temporary installation

**Step 4: Evaluate Extension Needs**
- Cable length requirements
- Signal quality concerns
- Multiple display requirements

### Recommendations

**For Beginners**:
- BBC Micro: RGBtoHDMI v4 (easiest)
- Amiga 500: Denise Small adapter
- Atari ST: Unbuffered pickup (simpler)

**For Enthusiasts**:
- BBC Master: RGBtoHDMI v4 with custom cable
- Amiga 2000: VideoSlot adapter (professional)
- Atari STE: Buffered pickup (best quality)

**For Professionals**:
- All systems: Use buffered solutions where available
- Long cables: Always use appropriate buffer boards
- High quality: Choose latest versions available

## Documentation Structure

### Document Organization

```
docs/
├── PCB_Documentation.md          # This overview
├── 01_Main_Boards.md              # Core RGBtoHDMI boards
├── 02_Acorn_Computers.md         # Acorn systems
├── 02_Commodore_Amiga.md         # Amiga adapters
├── 04_Atari_ST.md                # Atari ST adapters
├── 05_6Bit_RGB_Boards.md         # 6-bit specific boards
├── 06_Additional_Boards.md        # Analog, buffer, special boards
└── PCB_Index.md                  # This index document
```

### Related Documentation

**Main Project Documentation**:
- `README.md` - Main project overview
- Source code documentation
- CPLD firmware documentation
- Software user guides

**Technical Resources**:
- KiCad project files
- Manufacturing specifications
- Component datasheets
- Application notes

## Community and Support

### Getting Help

**Documentation First**:
- Check the specific board documentation
- Review the main project README
- Consult troubleshooting guides

**Community Resources**:
- RGBtoHDMI GitHub discussions
- Retrocomputing forums
- System-specific user groups
- Discord/Slack communities

**Technical Support**:
- File GitHub issues for specific problems
- Check existing issues for solutions
- Provide detailed system information
- Include photos when helpful

### Contributing

**Documentation Contributions**:
- Corrections and improvements
- Additional build guides
- Compatibility reports
- Translation projects

**Technical Contributions**:
- Board design improvements
- New adapter designs
- Component alternatives
- Manufacturing optimizations

---

*This index is maintained as part of the RGBtoHDMI project. For the most current information, check the main project repository and individual board documentation.*