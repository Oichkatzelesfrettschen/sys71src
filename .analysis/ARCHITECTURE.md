# Apple Macintosh System 7.1 Architecture

## System Overview

Mac System 7.1 (1992) was a major release featuring:
- 68k Motorola architecture (m68000 family)
- Early PowerPC (PPC) transition code
- Cooperative multitasking via Process Manager
- Hierarchical File System (HFS)

## Directory Structure

```
sys71src/
├── OS/                 # Core operating system kernel
│   ├── MemoryMgr/      # Memory allocation and management
│   ├── HFS/            # Hierarchical File System
│   ├── SCSIMgr/        # SCSI device management
│   ├── PowerMgr/       # Power management (PowerBooks)
│   ├── ADBMgr/         # Apple Desktop Bus (keyboard/mouse)
│   ├── SlotMgr/        # NuBus slot management
│   ├── StartMgr/       # System startup/boot
│   ├── TimeMgr/        # Time and timing services
│   ├── Gestalt/        # System configuration queries
│   ├── FPUEmulation/   # Floating point unit emulation
│   ├── MMU/            # Memory Management Unit
│   ├── PPC/            # PowerPC transition code
│   └── VDig/           # Video digitizer
│
├── Drivers/            # Hardware device drivers
│   ├── Video/          # Display drivers
│   ├── Sony/           # Floppy disk drivers
│   ├── IOP/            # I/O Processor drivers
│   └── Backlight/      # LCD backlight control
│
├── ProcessMgr/         # Process/application management
│
├── Interfaces/         # API headers and definitions
│   ├── AIncludes/      # Assembly includes
│   ├── CIncludes/      # C includes
│   ├── PInterfaces/    # Pascal interfaces
│   └── RIncludes/      # Rez (resource) includes
│
├── Internal/           # Internal headers (not public)
│
├── Libs/               # System libraries
│   ├── Libraries/      # Object libraries
│   ├── CLibraries/     # C runtime libraries
│   └── PLibraries/     # Pascal libraries
│
├── Patches/            # ROM patches by machine type
│   ├── PatchIIciROM.a  # Mac IIci patches
│   ├── PatchPlusROM.a  # Mac Plus patches
│   └── ...
│
├── LinkedPatches/      # Dynamic patch loader system
│
├── Make/               # Build system
│   ├── Universal.make  # Universal ROM build
│   ├── RISC.make       # PowerPC build
│   └── DBLite.make     # PowerBook build
│
├── Misc/               # Resources and miscellaneous
│
└── DeclData/           # Declaration ROM data
```

## Key Subsystems

### Memory Manager (OS/MemoryMgr/)
- Handle-based memory allocation
- Zone management
- Heap compaction
- Block allocation (NewPtr, NewHandle)

### HFS - Hierarchical File System (OS/HFS/)
- B-tree catalog structure
- Fork-based files (data + resource)
- Volume management
- Cache system (OS/HFS/Cache/)

### SCSI Manager (OS/SCSIMgr/, OS/SCSIMgr4pt3/)
- SCSI bus protocol implementation
- Device driver interface
- Async I/O support (4.3 version)
- ACAM (Apple SCSI CAM layer)

### Process Manager (ProcessMgr/)
- Cooperative multitasking
- Application launching
- Apple Events support
- Context switching

### ADB Manager (OS/ADBMgr/)
- Apple Desktop Bus protocol
- Keyboard and mouse input
- Device polling

## Build System

The Make/ directory contains MPW (Macintosh Programmer's Workshop) makefiles:
- `Universal.make` - Universal ROM for multiple Mac models
- `RISC.make` - PowerPC native builds
- Machine-specific targets (LC930, DBLite)

## Language Distribution

| Language | Files | Lines | Purpose |
|----------|-------|-------|---------|
| 68k Assembly (.a) | 546 | ~60k | Core OS, traps |
| C (.c, .h) | 320 | ~84k | Managers, drivers |
| Pascal (.p) | 124 | ~26k | High-level toolbox |
| Rez (.r) | 42 | ~37k | Resources |

## Historical Notes

- System 7.1 introduced Fonts folder, WorldScript II
- Code shows transition from 68k to PowerPC
- Many hardware-specific patches (Mac Plus through Quadra)
- Early modular driver architecture visible
