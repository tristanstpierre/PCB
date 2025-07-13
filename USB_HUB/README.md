# 🔌 USB-C to 3x USB-A Hub

A custom-built USB 2.0 hub that converts a single USB-C input into three USB-A ports. Designed specifically for modern laptops like the **MacBook** that have **only USB-C ports**, this board provides legacy USB-A connectivity for peripherals like flash drives, keyboards, and game controllers.

---

## 🧩 System Overview

This USB hub is built around the **TUSB2036** hub controller IC. It takes a single USB 2.0 input over USB-C and distributes it across **three USB-A outputs**. Each output is protected by **TVS diodes**, impedance-matched, and has its own **power switch** with overcurrent protection.

---

## 🖥️ Target Use Case

This board is designed to work with:
- 💻 **MacBooks and ultrabooks** that only offer USB-C ports
- 🧪 Projects requiring USB-A connectivity from a USB-C host
- 🔌 Portable USB hubs for embedded or DIY use

---

## 🧠 Key Components

| Component         | Description                              | Datasheet / Link |
|------------------|------------------------------------------|------------------|
| **TUSB2036**      | USB 2.0 Hub Controller                   | [TI TUSB2036 Datasheet](https://www.ti.com/lit/ds/symlink/tusb2036.pdf) |
| **TPD6E02B6**     | ESD Protection (USB lines)               | [TPD6E02B6 Datasheet](https://www.ti.com/lit/ds/symlink/tpd6e02b6.pdf) |
| **SN65220**       | TVS Diodes (for USB outputs)             | [SN65220 Datasheet](https://www.ti.com/lit/ds/symlink/sn65220.pdf) |
| **TPS2044HD**     | Load switch with OC protection           | [TPS2044HD Datasheet](https://www.ti.com/lit/ds/symlink/tps2044.pdf) |
| **MAX604**        | 3.3V Low Dropout Regulator               | [MAX604 Datasheet](https://datasheets.maximintegrated.com/en/ds/MAX604.pdf) |

---

## 📐 Schematic Overview

Each function is organized into its own schematic section:

| Module            | Preview Image |
|-------------------|---------------|
| **USB Hub IC (TUSB2036)** | ![USB Hub IC](images/USB_HUB_IC.PNG) |
| **USB-A Outputs**         | ![USB-A Out](images/USBA_OUT.PNG) |
| **USB-C Input + LDO**     | ![USB-C Input](images/USBC_input.PNG) |

> Tip: Store images in a GitHub folder like `/images/` for clean references.

---

## 🖼️ PCB Layout

| View | Image |
|------|-------|
| **Top Layer PCB** | ![PCB](images/PCB.PNG) |

The board is designed for compactness, single-sided assembly, and port-aligned output spacing for enclosure mounting.

---

## ⚙️ Functional Blocks

### 🔌 USB-C Input
- Provides 5V VBUS and USB 2.0 differential data lines
- Includes ESD protection and correct CC resistors for host detection

### 🧠 USB Hub IC
- TUSB2036 provides the logic and USB enumeration
- Crystal oscillator provides 6 MHz clock input
- Pull-ups, capacitors, and proper impedance-matching resistors included

### ⚡ Load Switches (TPS2044)
- Protect each USB-A output with:
  - Overcurrent detection
  - Enable/disable control
  - Smoothing capacitors

### 🛡️ TVS Protection
- SN65220 provides USB data and power rail protection for each output
- Improves safety against ESD events and hotplugging

### 🔋 Power Regulation
- MAX604 LDO generates 3.3V for hub logic from USB 5V input
- Decoupled with local ceramic caps

---

## 🚧 Project Status

- [x] Schematic complete  
- [x] PCB layout finished  
- [ ] PCB ordered and assembled  
- [ ] Firmware/EEPROM descriptor config (optional)  
- [ ] Enclosure design for USB ports  

---

## 🛠️ Tools Used

- **KiCad** – Schematic and PCB design
- **TI TUSB Series** – Hub controller
- **JLCPCB / PCBWay** – Fabrication (planned)

---

