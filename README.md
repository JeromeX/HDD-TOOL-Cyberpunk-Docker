# 🛠️ TUXHAUSEN HDD-ToolBox (Secure Edition)

> **TUXHAUSEN HDD-ToolBox** is a highly specialized "Swiss Army Knife" for storage media. It combines professional Linux low-level utilities with a modern cyberpunk web interface and artificial intelligence.

This distribution is based on **Ubuntu 24.04 (Noble Numbat)** and is delivered as a hardened Docker image with an encrypted application core.

---

## ✨ Features at a Glance

### 🤖 NOVA AI Assistant
- **Intelligent Analysis:** NOVA evaluates terminal outputs and S.M.A.R.T. data in real-time to provide actionable recommendations.
- **Natural Language Control:** Issue complex commands in plain language; NOVA generates and explains the appropriate shell command for you.
- **Contextual Knowledge:** NOVA recognizes the condition of your drives and provides proactive warnings about potential risks.

### 🩺 Diagnostics & Monitoring
- **Deep S.M.A.R.T. Check:** Full attribute analysis for HDD, SSD, and NVMe drives.
- **Hardware Self-Tests:** Trigger Short and Long self-tests directly from the web interface.
- **Live Status:** Real-time display of temperature, power-on hours, and overall health status.

### 🧩 Partitioning & Formatting
- **Auto-Setup:** 1-Click partitioning for Linux (EXT4), Windows (NTFS), macOS (HFS+), or Universal (exFAT).
- **GPT/MBR Management:** Full support for modern and legacy partition tables via `parted` and `fdisk`.
- **Wipe Option:** Optional "Zero-Fill" (overwriting sectors) during the formatting process.

### 🔒 Data Security & Sanitization
- **ATA Secure Erase:** Hardware-based erasure for SATA drives (via `hdparm`).
- **NVMe Format:** Specialized low-level formatting for modern M.2/U.2 SSDs.
- **DoD Standard:** Secure wiping with multiple passes using `shred`.
- **SSD Blkdiscard:** Instant resetting of SSD cells via TRIM/Discard commands.

### 💾 Backup & Recovery
- **Image Cloning:** Create 1:1 raw images of your drives (.img).
- **Web Download:** Download your backups directly through your browser.
- **Restore:** Safely write local images back to physical drives.
- **File Restore:** Integrated support for recovering deleted files using `extundelete`.

---

## 🚀 Installation

### 1. For PC / Server (AMD64)
**File:** `docker-compose.yml`
```yaml
services:
  hdd-toolbox:
    image: ghcr.io/jeromex/hdd-toolbox-amd64:latest
    container_name: hdd-toolbox
    hostname: hdd-tool-station
    privileged: true
    restart: always
    ports:
      - "5000:5000"
    volumes:
      - /dev:/dev
      - /run/udev:/run/udev:ro
      - ./data:/opt/tuxhausen/data
      - /mnt:/mnt:rshared
      - /media:/media:rshared
----------------------------------------------------------------------------------------
### 2. For Raspberry Pi (ARM64 / RPI)
**File:** `docker-compose.yml`
```yaml
services:
  hdd-toolbox:
    image: ghcr.io/jeromex/hdd-toolbox-rpi:latest
    container_name: hdd-toolbox-rpi
    hostname: hdd-tool-pi
    privileged: true
    restart: always
    ports:
      - "5000:5000"
    volumes:
      - /dev:/dev
      - /run/udev:/run/udev:ro
      - ./data:/opt/tuxhausen/data
      # Required for accessing external USB drives on Raspberry Pi OS
      - /media:/media:rshared
      - /mnt:/mnt:rshared

<img width="1920" height="1080" alt="2026-04-16 19_03_10-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/d28d951d-71ee-4b54-b668-175ee1214fe4" />
<img width="1920" height="1080" alt="2026-04-16 19_02_59-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/0a95edfd-34a8-4088-838c-551fb0eda844" />
<img width="1920" height="1080" alt="2026-04-16 19_02_43-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/b6a8e5b8-acc4-49fd-972d-22cea0a4a481" />
<img width="1920" height="1080" alt="2026-04-16 19_02_25-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/82aee349-36de-4b7a-bced-5f6d613ab769" />
<img width="1920" height="1080" alt="2026-04-16 19_04_32-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/b2da4fb4-de81-4db0-9884-a95cbf05a84d" />
<img width="1920" height="1080" alt="2026-04-16 19_04_27-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/dd8102d8-b072-40b6-bd0c-323f9f24cdff" />
<img width="1920" height="1080" alt="2026-04-16 19_04_16-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/789ff6da-30e8-40bd-9d9b-40bc5e69bed0" />
<img width="1920" height="1080" alt="2026-04-16 19_04_03-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/f6b8127f-7ef3-4479-83eb-7b1f54cfe62f" />
<img width="1920" height="1080" alt="2026-04-16 19_03_58-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/c1406f65-2dcd-41e6-9809-0fdd99ca9cf8" />
<img width="1920" height="1080" alt="2026-04-16 19_03_36-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/9c6229d7-8a4e-4ff5-ae66-bd86075673f5" />
<img width="1920" height="1080" alt="2026-04-16 19_03_23-HDD-ToolBox (Cyberpunk Docker) und 3 weitere Seiten - Persönlich – Microsoft​ Ed" src="https://github.com/user-attachments/assets/e45df8d3-56a6-43c7-81e3-3424c5c66df0" />
