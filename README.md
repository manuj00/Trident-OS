<p align="center">
  <h1 align="center">🔱 Trident OS</h1>
  <p align="center"><i>A Minimal 32-bit Operating System built from scratch</i></p>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Architecture-x86-8A2BE2?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Language-C%20%7C%20Assembly-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Bootloader-Custom-important?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Mode-Protected%20Mode-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Emulator-QEMU-orange?style=for-the-badge"/>
</p>

---

## 📌 Overview  

**Trident OS** is a fully custom-built **32-bit operating system** developed using **x86 Assembly and C**, focused on deep system-level understanding.

This project implements:

- Bootloader → Kernel pipeline  
- Protected Mode transition  
- Interrupt handling (IDT)  
- **Device Drivers (Keyboard & VGA)**  
- Basic shell interaction  

---

## 🚀 Features  

✔ Custom BIOS Bootloader (512 bytes)  
✔ Real Mode → Protected Mode transition  
✔ Global Descriptor Table (GDT)  
✔ Interrupt Descriptor Table (IDT)  
✔ Kernel written in C  
✔ VGA Text Mode Driver  
✔ Keyboard Driver (IRQ-based)  
✔ Basic Shell Interface  
✔ Modular architecture  

---

## 🧠 Core Concepts Implemented  

| Domain | Concepts |
|------|--------|
| Booting | BIOS, MBR, Bootloader |
| CPU Modes | Real Mode, Protected Mode |
| Memory | Segmentation (GDT) |
| Interrupts | IDT, ISR, IRQ |
| Drivers | Keyboard, VGA |
| Kernel | Low-level C + Assembly |

---

## 🏗️ System Architecture  

```mermaid
flowchart TD
    A[User Input] --> B[Shell]
    B --> C[Kernel]

    C --> C1[Memory Mgmt]
    C --> C2[Interrupt Handling]

    C --> D[Device Drivers]
    D --> D1[Keyboard Driver]
    D --> D2[VGA Driver]

    D --> E[Hardware]



📂 Project Structure
Trident-OS/
│
├── src/
│   ├── boot/
│   │   └── boot.asm
│   │
│   ├── kernel/
│   │   ├── kernel.c
│   │   ├── idt.c
│   │   ├── memory.c
│   │
│   ├── drivers/
│   │   ├── keyboard.c
│   │   ├── vga.c
│   │
│   ├── shell/
│   │   └── shell.c
│   │
│   └── include/
│
├── build/
├── bin/
└── build.sh
🛠️ Setup & Run
🔧 Prerequisites

nasm

i686-elf-gcc

qemu-system-x86

gdb (optional)

🧱 Build
chmod +x build.sh
./build.sh
▶️ Run
qemu-system-x86_64 -hda ./bin/os.bin
🐞 Debug
qemu-system-x86_64 -hda ./bin/os.bin -S -gdb stdio
🧪 Sample Output
🔱 Trident OS Booted Successfully!

[ OK ] GDT Loaded
[ OK ] IDT Initialized
[ OK ] Keyboard Driver Loaded
[ OK ] VGA Driver Initialized

Welcome to Trident Shell
> _
🔌 Device Drivers
🖮 Keyboard Driver

IRQ1 interrupt-based input

Reads from port 0x60

Scancode → ASCII conversion

Feeds shell input

🖥️ VGA Driver

Direct memory access at 0xB8000

Handles text rendering

Cursor control

💡 Future Enhancements

Paging & Virtual Memory

Multitasking Scheduler

User Mode vs Kernel Mode

Disk Drivers (ATA)

File System (FAT16 full support)

Networking Stack

ELF Loader

🧑‍💻 Author

Manuj Pant
Aspiring DevOps Engineer
🔗 https://github.com/manuj00
