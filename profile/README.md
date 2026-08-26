<div align="center">

<!-- ===== Hero Banner ===== -->
<!-- Replace with your actual banner image. Recommended size: 1280×400 -->
![UbiBot Open Source](./assets/banner.png)

# UbiBot Open Source

**Open IoT, Open Future**

*A lightweight IoT platform built for everyone*

[![Website](https://img.shields.io/badge/🌐-Commercial%20Version-2563EB?style=for-the-badge)](https://www.ubibot.com)
[![Docs](https://img.shields.io/badge/📖-Documentation-10B981?style=for-the-badge)](https://github.com/ubibot-open/ubibot-docs)
[![Discord](https://img.shields.io/badge/💬-Community-5865F2?style=for-the-badge&logo=discord)](https://discord.gg/ubibot)
[![License](https://img.shields.io/badge/License-Apache%202.0-orange?style=for-the-badge)](./LICENSE)

</div>

---

## 🎯 What is UbiBot Open?

> ⚠️ **Important Notice**
> UbiBot Open is an open-source project that is **completely independent from the commercial UbiBot platform**. It is not a free replacement for the commercial edition. Instead, it is a streamlined version specifically designed for:
> - ✅ **Rapid Setup**: Deploy locally in minutes and experience the full IoT pipeline immediately.
> - ✅ **Education**: Clean, well-commented codebase ideal for coursework, labs, and capstone projects.
> - ✅ **Academic Research**: Fully modifiable full-stack source code for protocol analysis and algorithm validation.
> - ✅ **Prototyping**: Build low-cost IoT PoCs (Proof of Concepts) without relying on cloud services.
>
> 🏢 For enterprise-grade stability, advanced analytics, multi-tenancy, and professional technical support, please visit [UbiBot Commercial Edition](https://www.ubibot.com).

### Core Capabilities (Lite Edition)

| Capability | Description | Difference from Commercial Edition |
|:---|:---|:---|
| 📡 **Basic Device Access** | Supports HTTP protocol | Does not include MQTT / LoRaWAN / Modbus / NB-IoT or other enterprise protocols |
| 📊 **Lightweight Data Management** | Sensor data collection, storage, and basic visualization | Does not include multi-dimensional analytics or advanced alerting modules |
| 🔌 **Standard API** | RESTful API for easy secondary development | Does not include advanced permission management or audit logging |
| 🏠 **One-Click Private Deployment** | Single-node Docker Compose deployment with zero operational overhead | Does not include cluster HA or auto-scaling |

### 👥 Who Is This For?

| Audience | What You Can Do With It |
|:---|:---|
| 🎓 **Students** | Complete IoT course projects and graduation theses; understand the full HTTP protocol interaction flow |
| 🔬 **Researchers** | Modify firmware or platform source code for protocol security analysis and edge computing algorithm validation |
| 🛠️ **Makers / Hobbyists** | Build home environment monitoring stations with your own hardware, keeping full ownership of your data |
| 💼 **Developers** | Quickly evaluate the UbiBot architecture as a technical pre-study before integrating the commercial edition |

---

## 🗂️ Project Ecosystem

### 🏗️ Core Platform

| Project | Description | Status |
|:---|:---|:---:|
| [ubibot-server](https://github.com/ubibot-open/ubibot-server) | Core IoT platform services (device management / data storage / basic rule engine) | 🟢 Active |
| [ubibot-dashboard](https://github.com/ubibot-open/ubibot-dashboard) | Web data visualization dashboard & admin console | 🟢 Active |

### 📡 Device & Firmware

| Project | Description | Status |
|:---|:---|:---:|
| [ubibot-firmware](https://github.com/ubibot-open/ubibot-firmware) | ESP32 open-source reference firmware (with detailed comments) | 🟢 Active |
| [ubibot-protocols](https://github.com/ubibot-open/ubibot-protocols) | Communication protocol specification (HTTP) | 📖 Docs |

### 🔌 API & Integrations

| Project | Description | Status |
|:---|:---|:---:|
| [ubibot-api](https://github.com/ubibot-open/ubibot-api) | RESTful API specification & SDKs (Python / JS / Go) | 🟢 Active |
| [ubibot-integrations](https://github.com/ubibot-open/ubibot-integrations) | Home Assistant integration plugin | 🟢 Active |

### 📚 Docs & Learning

| Project | Description | Status |
|:---|:---|:---:|
| [ubibot-docs](https://github.com/ubibot-open/ubibot-docs) | Official documentation (architecture overview & protocol deep dives) | 📖 Docs |
| [ubibot-examples](https://github.com/ubibot-open/ubibot-examples) | Step-by-step tutorials & scenario examples (from Hello World to complete projects) | 🟢 Active |

---

## ⚡ Quick Start (5-Minute Setup)

```bash
# 1. Clone the core service repository
git clone https://github.com/ubibot-open/ubibot-server.git
cd ubibot-server

# 2. One-click launch via Docker Compose (includes database + backend + frontend)
docker compose up -d

# 3. Wait ~30 seconds, then open the console
open http://localhost:8080

# Default credentials: admin / ubibot_open
