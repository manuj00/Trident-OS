# 🧠 Simple x86 Bootloader (Hello World)

A minimal **16-bit x86 bootloader** written in **Assembly (NASM)** that prints a message directly during system boot using BIOS interrupts.

This project demonstrates how a computer executes code **before any operating system loads**.

---

## 📌 Project Goal

The objective of this project is to understand:

* How computers boot
* What happens before an OS starts
* Real Mode programming
* BIOS interrupts
* Boot sector structure
* Low-level Assembly programming

This bootloader fits entirely inside a **single 512-byte boot sector**.

---

## ⚙️ How It Works

When a computer starts:

1. BIOS initializes hardware.
2. BIOS loads the first **512 bytes** from the boot device into memory at `0x7C00`.
3. CPU begins executing this code.
4. The bootloader prints a message using BIOS video services.
5. Execution stops in an infinite loop.

---

## 🧾 Features

✅ Runs directly after BIOS
✅ Written in pure x86 Assembly
✅ Uses BIOS interrupt `INT 0x10`
✅ Character-by-character string printing
✅ Valid boot sector with signature `0xAA55`

---

## 🖥️ Program Output

```
Hello World This is Group 40 Aman kabir manuj
```

---

## 📂 Project Structure

```
bootloader/
│
├── boot.asm     # Bootloader source code
└── README.md
```

---

## 🧩 Key Concepts Used

### Real Mode

The CPU starts in **16-bit Real Mode**, allowing direct access to BIOS services.

### BIOS Interrupts

The bootloader uses:

```
INT 0x10
```

BIOS Video Service used to print characters on screen.

Registers used:

* `AH = 0x0E` → Teletype output function
* `AL` → Character to display
* `BH` → Display page number

---

### Boot Sector Requirements

A valid boot sector must:

* Be exactly **512 bytes**
* End with boot signature:

```
0xAA55
```

---

## 🔧 Build Instructions

### 1. Install NASM

```bash
sudo apt install nasm
```

### 2. Assemble Bootloader

```bash
nasm -f bin boot.asm -o boot.bin
```

### 3. Run Using QEMU

```bash
qemu-system-x86_64 boot.bin
```

---

## 🧠 Learning Outcomes

After studying this project you will understand:

* How BIOS loads a bootloader
* CPU register usage
* Assembly control flow
* Interrupt-based hardware interaction
* Bare-metal programming basics

---

## 🚀 Future Improvements

Possible next steps:

* Load a second-stage bootloader
* Read sectors from disk (`INT 0x13`)
* Switch to Protected Mode
* Write directly to VGA memory
* Load a simple kernel

---

## 👨‍💻 Authors

**Group 40**

* Aman
* Kabir
* Manuj

---

## 📚 Educational Purpose

This repository is created for learning **Operating System fundamentals** and **low-level system programming**.

---
