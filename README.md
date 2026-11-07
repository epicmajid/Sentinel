<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:09090b,100:00ffcc&height=200&section=header&text=SENTINEL&fontSize=70&fontColor=ffffff&fontAlignY=35&desc=Universal%20File%20Inspector%20%26%20Threat%20Analyzer&descAlignY=55&descSize=20&animation=fadeIn" alt="Header" width="100%" />

### 🛡️ Next-Gen Forensic File Analysis & Threat Detection Platform 🚀

[![Developer](https://img.shields.io/badge/Crafted%20by-epicmajid-00ffcc?style=for-the-badge&logo=github&logoColor=00ffcc&labelColor=09090b)](https://github.com/epicmajid)
[![Platform: Windows](https://img.shields.io/badge/Platform-Windows%2010%2F11-00ffcc?style=for-the-badge&logo=windows&logoColor=00ffcc&labelColor=09090b)](https://www.microsoft.com/windows)
[![Python 3.10+](https://img.shields.io/badge/Python-3.10%2B-00ffcc?style=for-the-badge&logo=python&logoColor=00ffcc&labelColor=09090b)](https://www.python.org)
[![UI: PySide6](https://img.shields.io/badge/UI-PySide6%20%2F%20Qt6-00ffcc?style=for-the-badge&logo=qt&logoColor=00ffcc&labelColor=09090b)](https://doc.qt.io/qtforpython/)
[![License: MIT](https://img.shields.io/badge/License-MIT-00ffcc?style=for-the-badge&logo=opensourceinitiative&logoColor=00ffcc&labelColor=09090b)](LICENSE)
[![Build Status](https://img.shields.io/badge/Build-Passing-00ffcc?style=for-the-badge&logo=githubactions&logoColor=00ffcc&labelColor=09090b)](#)

<br/>

[`#cybersecurity`](https://github.com/topics/cybersecurity) 
[`#forensics`](https://github.com/topics/forensics) 
[`#reverse-engineering`](https://github.com/topics/reverse-engineering) 
[`#virustotal`](https://github.com/topics/virustotal) 
[`#pyside6`](https://github.com/topics/pyside6) 
[`#python-security`](https://github.com/topics/python-security)

---

</div>

## 📌 Executive Summary

**SENTINEL** is a high-performance, dark-themed static binary inspection tool engineered for **security analysts**, **reverse engineers**, and **developers**. Built with Python 3.10 and PySide6 (Qt6), SENTINEL provides deep structural insights into any file format (Executables, Images, Documents, and Archives) without needing to execute untrusted code.

From reading magic numbers and inspecting PE header anomalies to querying VirusTotal APIs and visualizing entropy levels, **SENTINEL** packs full-scale malware static analysis into an intuitive cyberpunk interface.

---

## 🔥 Key Highlights & Features

| Feature | Capabilities & Technical Specs |
| :--- | :--- |
| **🔬 Universal File Parser** | Parses `PE`, `ELF`, `MACH-O`, `PDF`, `Zip/Archive`, and generic binaries seamlessly. |
| **🧠 Deep Magic Number ID** | Reads initial binary magic bytes (e.g., `MZ`, `PK`, `\x7fELF`) to bypass spoofed extension tricks. |
| **🛡️ Heuristic Threat Engine** | Uses fast, pure-Python pattern scanners to detect Ransomware indicators, keyloggers, and reverse shells. |
| **🌐 VirusTotal v3 API Hub** | Computes `MD5`, `SHA-1`, `SHA-256` hashes and queries 70+ Antivirus engines via VT Cloud API. |
| **📊 Shannon Entropy Visualizer** | Graphically highlights high-entropy sections (Signals packed, obfuscated, or encrypted payloads). |
| **🖼️ Built-in Media Renderer** | Dynamic preview panel for PNG, JPG, BMP, and SVG files with metadata extraction (EXIF). |
| **🔍 Interactive Hex & ASCII Explorer**| Ultra-fast memory-efficient Hex viewer with ASCII regex filtering and string extraction. |

---

## 🏗️ Architecture & Technical Stack

SENTINEL is architected around modular static-analysis sub-routines:

```mermaid
flowchart TD
    A[📂 Drop Any File Target] --> B[Phase 1: Magic Number Header Analysis]
    B --> C[Phase 2: Multi-Algorithm Hashing SHA-256 / MD5]
    C --> D[Phase 3: Shannon Entropy Calculation]
    D --> E[Phase 4: Static Heuristic Signature Scan]
    E --> F[Phase 5: Asynchronous VirusTotal Lookup API]
    F --> G[💻 Render Results in Dark Qt6 Interface]
```

### 💻 Technologies & Libraries
- **GUI Engine:** [PySide6](https://pypi.org/project/PySide6/) (Qt for Python 6)
- **Asynchronous Execution:** Qt `QThread` pool to ensure zero UI freezes during heavy analysis.
- **Crypto & Math:** Native `hashlib`, `math`, `re` modules for high-speed string and entropy math.
- **API Integration:** `requests` / `urllib3` with rate-limiting and cache handling for VirusTotal REST v3 API.

---

## 📸 Interface Showcase

<div align="center">

| **SENTINEL Cyberpunk Interface Preview** |
| :---: |
| <img src="Sentinel .png" alt="SENTINEL UI Preview" width="100%" style="border-radius: 12px; border: 1px solid #00ffcc;" /> |
| *Sleek dark-mode terminal layout featuring universal drag-and-drop file inspection.* |

</div>

---

## 🚀 Quick Start (Executable & Source)

### Option 1: Standalone Portable Executable (`.exe`) 📦

If you just want to run **SENTINEL** without installing Python:

1. Download the latest binary release from the **[Releases](../../releases)** page.
2. Unpack `SENTINEL.zip`.
3. Launch `SENTINEL.exe` *(No installation required, completely portable)*.

---

### Option 2: Running from Source 🐍

#### Prerequisites
- **OS:** Windows 10/11 *(Linux/macOS support coming soon)*
- **Python:** `3.10` or higher

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/epicmajid/sentinel.git
   cd sentinel
   ```

2. **Create a Virtual Environment:**
   ```bash
   python -m venv venv
   # On Windows
   .\venv\Scripts\activate
   ```

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch SENTINEL:**
   ```bash
   python main.py
   ```

---

## ⚡ Binary Optimization & Compression Notes

To guarantee maximum execution speed and minimum distribution footprint, **SENTINEL** is optimized using **PyInstaller** paired with **UPX (Ultimate Packer for Executables)**.

> 💡 **Developer Note:** Unused Qt modules are excluded to reduce standard builds from ~85 MB down to ~20 MB.

```bash
# Recommended Optimized Build Command
pyinstaller --noconfirm --onedir --windowed \
    --name "SENTINEL" \
    --icon=assets/icon.ico \
    --exclude-module PySide6.QtWebEngine \
    --exclude-module PySide6.Qt3D \
    --exclude-module PySide6.QtNetworkAuth \
    --add-data "assets;assets/" main.py
```

### 📉 Compression Benchmarks

| Build Strategy | Output Type | Binary Size | Launch Speed |
| :--- | :---: | :---: | :---: |
| Standard Build (No UPX) | `--onedir` | ~85 MB | Instant (~0.4s) |
| **Optimized + UPX** | `--onedir` | **~24 MB** | **Fast (~0.5s)** |
| Standalone Packed | `--onefile` + UPX | **~18 MB** | Direct (~1.2s) |

---

## 🗺️ Roadmap & Upcoming Features

- [x] Initial PE & Universal Static Analysis
- [x] VirusTotal API v3 Hash Lookup Integration
- [x] High-Speed Hex Dump & ASCII Extraction
- [ ] **YARA Rules Engine Support:** Custom external `.yar` rule file loading.
- [ ] **PE Section Inspector:** Deep PE section parsing (`.text`, `.rsrc`, `.reloc`).
- [ ] **Cross-Platform Release:** Native Linux & macOS PyQt builds.

---

## 🤝 Contributing

Contributions are what make the open-source community an incredible place to learn, inspire, and create. Any contributions you make are **greatly appreciated**!

1. **Fork** the Project.
2. Create your Feature Branch (`git checkout -b feature/AwesomeFeature`).
3. **Commit** your Changes (`git commit -m 'Add some AwesomeFeature'`).
4. **Push** to the Branch (`git push origin feature/AwesomeFeature`).
5. Open a **Pull Request**.

---

## 👤 Developer Profile

<div align="center">

<a href="https://github.com/epicmajid">
  <img src="https://img.shields.io/badge/Lead%20Developer-Majid%20(%40epicmajid)-00ffcc?style=for-the-badge&logo=github&logoColor=00ffcc&labelColor=09090b" alt="Majid Profile" />
</a>

| **Lead Developer** | **GitHub Profile** | **Project Repository** |
| :---: | :---: | :---: |
| **Majid** | [@epicmajid](https://github.com/epicmajid) | [epicmajid/sentinel](https://github.com/epicmajid/sentinel) |

</div>

---

## 📜 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for more details.

<div align="center">
  <sub>Engineered with ⚡ & ❤️ by <a href="https://github.com/epicmajid">@epicmajid</a></sub>
</div>