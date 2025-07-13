# 🎵 ESP32-S3 Digital Audio Player

An open-source, iPod-style audio player built around the ESP32-S3 microcontroller. Plays high-quality audio from a microSD card through a DAC and headphone amplifier, all powered by USB-C.

---

## 📷 Overview

This compact digital audio player leverages the power of the ESP32-S3 for audio decoding and control. Audio files are stored on a microSD card, decoded via I²S, and sent to a high-performance DAC, then amplified for headphone output. Ideal for embedded audio projects, MP3 players, or portable media devices.

---

## 🧩 Hardware Architecture

### 🧠 Microcontroller: **ESP32-S3**
- Controls SD card interface, DAC, USB, and external memory
- I²S output for digital audio
- Wi-Fi/Bluetooth ready
- Uses external Flash + PSRAM for expanded storage and buffering

### 💾 Storage: **microSD Card**
- Molex 1051620001 slot
- SPI-connected via level-shifted interface
- Holds audio files (MP3, WAV, etc.)

### 🎧 Audio Chain:
#### 1. **DAC: PCM5102A**
- Converts I²S digital audio to analog
- Internal charge pump for true ground-referenced output
- Low-pass filtered analog output

#### 2. **Amplifier: TPA152DG4**
- Drives headphones with clean audio
- Input high-pass and output low-pass filters
- Depop resistors prevent power-on pops
- 3.5mm stereo jack output

### 🔌 USB-C Interface
- Accepts 5V power input
- ESD protected data lines (optional USB audio or serial)
- LC power filter for clean VBUS

### ⚡ Power Management
- AMS1117-3.3 LDO provides 3.3V rail
- Decoupling and filtering for analog and digital domains

### ⏱️ Clocking
- 40 MHz crystal with load caps for ESP32-S3
- Stable timing for WiFi and core processing

---

## 📐 Schematics

The design is divided into modular blocks:
- `MCU (ESP32-S3)`
- `External Flash & PSRAM`
- `DAC (PCM5102A)`
- `Headphone Amp (TPA152)`
- `microSD Interface`
- `USB-C Power & Data`
- `+3
