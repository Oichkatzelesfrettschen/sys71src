# Mac System 7.1 Subsystem Documentation

## OS Kernel Components

### Memory Manager (`OS/MemoryMgr/`)
**Purpose**: Core memory allocation and heap management

**Key Files**:
- `MemoryMgr.a` - Main memory manager implementation
- `MemoryMgr.make` - Build configuration

**Features**:
- Handle-based allocation (relocatable blocks)
- Pointer-based allocation (fixed blocks)
- Heap zones and sub-zones
- Block compaction and purging
- 24-bit and 32-bit addressing modes

---

### HFS - Hierarchical File System (`OS/HFS/`)
**Purpose**: Primary file system for Macintosh volumes

**Key Subdirectories**:
- `Cache/` - Disk cache implementation
- `Extensions/` - HFS extensions
- `HFSVolumes/` - Volume management

**Architecture**:
- B*-tree catalog structure
- Two-fork files (data + resource)
- Volume bitmap allocation
- Directory hierarchy

---

### SCSI Manager (`OS/SCSIMgr/`, `OS/SCSIMgr4pt3/`)
**Purpose**: SCSI bus device communication

**Versions**:
- Original SCSI Manager (synchronous)
- SCSI Manager 4.3 (asynchronous, CAM-based)

**Key Components**:
- XPT (Transport layer)
- SIM (Interface Module)
- ACAM (Apple CAM layer)

---

### Power Manager (`OS/PowerMgr/`)
**Purpose**: Power management for portable Macs

**Features**:
- Sleep/wake management
- Battery monitoring
- PMU (Power Management Unit) communication
- Display dimming

---

### ADB Manager (`OS/ADBMgr/`)
**Purpose**: Apple Desktop Bus protocol handling

**Devices Supported**:
- Keyboards
- Mice and trackballs
- Graphics tablets

---

### Start Manager (`OS/StartMgr/`)
**Purpose**: System boot and initialization

**Boot Sequence**:
1. ROM initialization
2. Hardware detection
3. RAM test
4. System file loading
5. Extension loading

---

### Trap Dispatcher (`OS/TrapDispatcher/`)
**Purpose**: OS and Toolbox trap handling

**Implementation**:
- A-line exceptions (68k)
- Trap dispatch tables
- Toolbox vs OS trap routing

---

### Gestalt (`OS/Gestalt/`)
**Purpose**: System configuration queries

**Usage**: Applications query hardware/software capabilities

---

### FPU Emulation (`OS/FPUEmulation/`)
**Purpose**: 68881/68882 floating-point emulation

**For Macs Without FPU**:
- Software SANE implementation
- IEEE 754 compliance

---

### MMU (`OS/MMU/`)
**Purpose**: Memory Management Unit control

**Features**:
- Address translation
- Memory protection
- Virtual memory support

---

### PPC (`OS/PPC/`)
**Purpose**: PowerPC transition code

**Contains**:
- Mixed-mode manager preparation
- 68k-to-PPC bridges

---

### Slot Manager (`OS/SlotMgr/`)
**Purpose**: NuBus expansion slot management

**Features**:
- Slot device detection
- Declaration ROM parsing
- Resource loading

---

### Time Manager (`OS/TimeMgr/`)
**Purpose**: Time-based event scheduling

**Services**:
- Periodic tasks
- Timer interrupts
- Extended time manager

---

### Video Digitizer (`OS/VDig/`)
**Purpose**: Video capture interface

**For**: QuickTime video capture support

