<div align="center">

<!-- ===== Hero Banner ===== -->
![UbiBot Open Source](https://raw.githubusercontent.com/ubibot-open/.github/main/assets/banner.png)

# UbiBot Open

*Open-source IoT device platform, firmware, and tooling for developers, makers, and researchers.*

[![Website](https://img.shields.io/badge/🌐-Commercial%20Version-2563EB?style=for-the-badge)](https://www.ubibot.com)
[![Docs](https://img.shields.io/badge/📖-Documentation-10B981?style=for-the-badge)](https://github.com/ubibot-open/ubibot-docs)
[![Discord](https://img.shields.io/badge/💬-Community-5865F2?style=for-the-badge&logo=discord)](https://discord.gg/ubibot)
[![License](https://img.shields.io/badge/License-Apache%202.0-orange?style=for-the-badge)](./LICENSE)

</div>

---

## 🎯 What is UbiBot Open?

> ⚠️ **Important Notice**
> UbiBot Open is an open-source project that is **completely independent from the commercial UbiBot platform**. It is not a free replacement for the commercial edition. Instead, it is a streamlined version specifically designed for:
> - ✅ **Rapid Setup**: Build the server binary and run it locally in minutes.
> - ✅ **Education**: Clean, well-commented codebase ideal for coursework, labs, and capstone projects.
> - ✅ **Academic Research**: Fully modifiable full-stack source code for protocol analysis and algorithm validation.
> - ✅ **Prototyping**: Build low-cost IoT PoCs (Proof of Concepts) without relying on cloud services.
>
> 🏢 For enterprise-grade stability, advanced analytics, multi-tenancy, and professional technical support, please visit [UbiBot Commercial Edition](https://www.ubibot.com).

### Core Capabilities (Lite Edition)

| Capability | Description | Difference from Commercial Edition |
|:---|:---|:---|
| 📡 **Basic Device Access** | HTTP-based device auth (device triplet + HMAC signing), data reporting, and command dispatch | Does not include MQTT / LoRaWAN / Modbus / NB-IoT or other enterprise protocols |
| 📊 **Lightweight Data Management** | Sensor data collection and storage on embedded SQLite | Does not include multi-dimensional analytics or advanced alerting modules |
| 🔌 **Self-Contained Deployment** | Single Go binary with the admin UI embedded — no separate frontend server or database service to run | Does not include cluster HA or auto-scaling |
| 🔧 **Companion Tooling** | Open-source firmware and a desktop serial debugging tool for bringing up and testing devices | Not part of the commercial edition's scope |

### 👥 Who Is This For?

| Audience | What You Can Do With It |
|:---|:---|
| 🎓 **Students** | Complete IoT course projects and graduation theses; understand the full HTTP device-auth and data-reporting flow |
| 🔬 **Researchers** | Modify firmware or platform source code for protocol security analysis and edge computing algorithm validation |
| 🛠️ **Makers / Hobbyists** | Build home environment monitoring stations with your own hardware, keeping full ownership of your data |
| 💼 **Developers** | Quickly evaluate the UbiBot architecture as a technical pre-study before integrating the commercial edition |

---

## 🗂️ Project Ecosystem

### 🏗️ Core Platform

| Project | Description | License | Status |
|:---|:---|:---:|:---:|
| [ubibot-open-server](https://github.com/ubibot-open/ubibot-open-server) | IoT backend (Go) — device identity/auth, data ingestion, command dispatch, SQLite storage — plus a React/Ant Design admin console, built into a single self-contained binary | TBD | 🟢 Active |

### 📡 Device & Firmware

| Project | Description | License | Status |
|:---|:---|:---:|:---:|
| [ubibot-ws1b](https://github.com/ubibot-open/ubibot-open-ws1b) | Open-source ESP-IDF firmware for the UbiBot WS1B device | MIT | 🟢 Active |

### 🔌 Tools

| Project | Description | License | Status |
|:---|:---|:---:|:---:|
| [ubibot-serial-sync](https://github.com/ubibot-open/ubibot-serial-sync) | Cross-platform (Windows/macOS/Linux) Qt 6 desktop serial debugging tool for UbiBot devices (WS1, WS1 Pro, GS1-AL4G1RS, SP1, …) — device command library, data monitor, cloud-synced command sets | LGPLv3 | 🟢 Active |

### 📚 Docs & Learning

| Project | Description | Status |
|:---|:---|:---:|
| ubibot-open-doc | Deployment guides and device communication protocol reference | 🚧 Planned |

---

## ⚡ Quick Start

```bash
# 1. Clone the core platform repository
git clone https://github.com/ubibot-open/ubibot-platform-open.git
cd ubibot-platform-open

# 2. Build the admin frontend and the server binary
#    Requires: Node.js/npm (frontend) and Go 1.23+ (server)
./build.sh        # Linux/macOS
# .\build.ps1      # Windows

# 3. Run it — API and admin UI are served from the same address
./ubibot-server
# open http://localhost:8080
```

---

## 📄 License

Each repository carries its own license — see the table above and the `LICENSE` file in each project.

## 💬 Contributing

Issues and pull requests are welcome on each project's own repository.
