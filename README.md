# 🔱 Trident OS  
*A Minimal 32-bit Operating System built from scratch*

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
- Device Drivers (Keyboard & VGA)  
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
|--------|---------|
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
