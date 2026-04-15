# Mac System 7.1 OS Kernel Components - Detailed Documentation

## Memory Manager (MemoryMgr/)
- Handle-based allocation with relocation
- Zone management and heap compaction
- 24-bit and 32-bit addressing modes
- Files: MemoryMgr.a, MemoryMgrInternal.a, BlockMove.a
- Figment (newer heap manager) sources included

## SCSI Manager (SCSIMgr/ + SCSIMgr4pt3/)
### Original SCSI Manager
- 53C96 controller support
- Files: SCSIMgr96.a, SCSIMgrNew.a, SCSIBoot.a
- Quantum firmware bug workarounds

### SCSI Manager 4.3 (Async)
- XPT (Transport Protocol layer)
- SIM (SCSI Interface Module)
- HAL (Hardware Abstraction Layer)
- Files: XPT.c, SIMCore.c, HALc96.c

## Power Manager (PowerMgr/)
- Battery/thermal management for PowerBooks
- PMU communication
- Sleep/wake, hard disk spindown
- Files: PowerMgr.a, PowerMgrPatches.a

## ADB Manager (ADBMgr/)
- Apple Desktop Bus protocol
- Keyboard/mouse/tablet support
- Autopoll and SRQ handling
- Files: ADBMgr.a, ADBMgrPatch.a

## HFS - Hierarchical File System (HFS/)
- B*-tree catalog structure
- Data and resource forks
- Desktop database
- Cache subsystem (Cache/)
- Files: BTALLOC.a, CMSVCS.a, Cache.a

## Slot Manager (SlotMgr/)
- NuBus expansion slot management
- Declaration ROM parsing
- Driver loading, interrupt routing
- Files: SlotMgr.a, SlotMgrInit.a

## Startup Manager (StartMgr/)
- Three-phase boot sequence
- Extension loading
- Gibby ROM customization
- Files: Boot1.a, Boot2.a, Boot3.a, StartInit.a

## Gestalt (Gestalt/)
- System capability queries
- Machine type detection
- Files: GestaltFunction.a, GestaltExtensions.a

## Trap Dispatcher (TrapDispatcher/)
- A-line trap routing
- Files: Dispatch.a, DispatchPatch.a

## Time Manager (TimeMgr/)
- Microsecond-resolution timing
- Timer task scheduling
- Files: TimeMgr.a, TimeMgrPatch.a

## FPU Emulation (FPUEmulation/)
- 68881/68882 software emulation
- IEEE 754 compliant
- Files: Trig.a, Log.a, Power.a, FPSPMain.a

## Other Key Components
- I2C/ - Serial ROM interface
- MMU/ - Memory management unit
- PPC/ - PowerPC transition code
- VDig/ - Video digitizer
- Keyboard/ - Keyboard drivers
- NetBoot/ - Network boot support
