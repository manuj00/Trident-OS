🔱 Trident OS 

A Minimal 32-bit Operating System built from scratch

📌 Overview

Trident OS is a custom-built 32-bit operating system developed from scratch using x86 Assembly and C. The project demonstrates low-level system design concepts including bootloading, memory management, protected mode, and direct hardware interaction.

This project is designed to bridge the gap between theoretical OS concepts and real-world system-level implementation.

🚀 Features

🔹 Custom Bootloader (512 bytes, BIOS-based)

🔹 Transition from Real Mode → Protected Mode

🔹 Global Descriptor Table (GDT) implementation

🔹 Basic Kernel written in C

🔹 Direct VGA text buffer output

🔹 Interrupt Descriptor Table (IDT)

🔹 Keyboard input handling

🔹 Basic shell with custom commands

🔹 Memory management (paging - optional/partial if implemented)

🔹 FAT16 file system support (if implemented)

🔹 Modular and extensible architecture

🧠 What You Learn

This project helps you deeply understand:

How a computer boots from power-on

BIOS and boot sector execution

Memory segmentation and addressing

Switching to Protected Mode (32-bit)

Low-level hardware communication

Interrupt handling and system calls

Kernel design fundamentals

File system basics (FAT16)

🏗️ Architecture
+----------------------+
|      User Input      |
+----------+-----------+
           |
           v
+----------------------+
|       Shell          |
+----------+-----------+
           |
           v
+----------------------+
|       Kernel         |
|  - Memory Mgmt       |
|  - Interrupts        |
|  - Drivers           |
+----------+-----------+
           |
           v
+----------------------+
|     Hardware         |
+----------------------+
⚙️ Tech Stack

Language: C, x86 Assembly

Compiler: i686-elf-gcc (cross compiler)

Assembler: NASM

Emulator: QEMU

Debugger: GDB

Build System: Bash scripts / Makefile

📂 Project Structure
Trident-OS/
│
├── src/
│   ├── boot/
│   │   └── boot.asm        # Bootloader (512 bytes)
│   ├── kernel/
│   │   ├── kernel.c        # Main kernel logic
│   │   ├── terminal.c      # VGA output
│   │   ├── idt.c           # Interrupt handling
│   │   └── memory.c        # Memory management
│   ├── include/
│   │   └── kernel.h
│
├── build/                  # Object files
├── bin/                    # Final OS image
├── scripts/
│   └── build.sh
│
└── README.md
🛠️ Build & Run
🔧 Prerequisites

Make sure you have:

nasm

i686-elf-gcc (cross compiler)

qemu-system-x86

gdb (optional)

🧱 Build the OS
chmod +x build.sh
./build.sh
▶️ Run in QEMU
qemu-system-x86_64 -hda ./bin/os.bin
🐞 Debug (Optional)
qemu-system-x86_64 -hda ./bin/os.bin -S -gdb stdio

Then in another terminal:

gdb
target remote | qemu-system-x86_64 -hda ./bin/os.bin -gdb stdio -S
🧪 Example Output
Trident OS Booted Successfully!
Welcome to Trident Shell
> _
🔥 Custom Shell Commands (Example)
Command	Description
help	Show available commands
clear	Clear screen
echo	Print text
info	Display system info
💡 Future Improvements

Full paging implementation

Multitasking / scheduling

File system write support

User mode vs kernel mode

Networking stack

ELF executable loader

GUI support

📚 Key Concepts Implemented

Boot Sector (MBR)

Segmentation (GDT)

Interrupt Handling (IDT)

Hardware I/O (Ports)

Memory Management

Low-level Debugging (GDB + QEMU)

👨‍💻 Author

Manuj Pant

Aspiring DevOps Engineer

Passionate about Linux, Systems, and Low-Level Programming

GitHub: https://github.com/manuj00
