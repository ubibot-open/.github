<div align="center">

<!-- ===== Hero Banner ===== -->
![UbiBot Open Source](https://raw.githubusercontent.com/ubibot-open/.github/main/assets/banner.png)

# UbiBot Open

*面向开发者、创客与研究者的开源物联网设备平台、固件与配套工具。*

[![官网](https://img.shields.io/badge/🌐-商业版-2563EB?style=for-the-badge)](https://www.ubibot.com)
[![文档](https://img.shields.io/badge/📖-文档-10B981?style=for-the-badge)](https://github.com/ubibot-open/ubibot-open-doc)
[![Discord](https://img.shields.io/badge/💬-社区-5865F2?style=for-the-badge&logo=discord)](https://discord.gg/ubibot)

*[English](README.md)*

</div>

---

## 🎯 UbiBot Open 是什么？

> ⚠️ **重要说明**
> UbiBot Open 是一个**完全独立于商业版 UbiBot 平台**的开源项目，不是商业版的免费替代品，而是专门为以下场景做的精简版本：
> - ✅ **快速搭建**：几分钟内构建出服务端可执行文件并在本地跑起来。
> - ✅ **教学**：代码干净、注释详实，适合课程作业、实验课和毕业设计。
> - ✅ **学术研究**：全栈源码完全可改，适合协议分析和算法验证。
> - ✅ **原型验证**：不依赖云服务，搭建低成本的物联网 PoC（概念验证）。
>
> 🏢 如果需要企业级的稳定性、高级数据分析、多租户支持和专业技术支持，请访问[商业版 UbiBot](https://www.ubibot.com)。

### 核心能力（精简版）

| 能力 | 说明 | 与商业版的差异 |
|:---|:---|:---|
| 📡 **基础设备接入** | HTTP 明文 pid+sn 设备身份（无签名/密钥）、数据上报、基于串口的配网，以及一个最小化的、由管理员触发的指令通道（重启 / 修改上报间隔）——详见[协议参考文档](https://github.com/ubibot-open/ubibot-open-doc) | 不包含 MQTT / LoRaWAN / Modbus / NB-IoT、设备认证签名、OTA，也不包含通用的服务端到设备的推送/配置通道 |
| 📊 **轻量数据管理** | 传感器数据采集与存储，基于嵌入式 SQLite | 不包含多维数据分析或高级告警模块 |
| 🔌 **自包含部署** | 单个 Go 可执行文件内嵌管理界面——不需要单独跑前端服务或数据库服务 | 不包含集群高可用或自动扩缩容 |
| 🔧 **配套工具** | 开源固件、桌面串口调试工具，以及一个不需要硬件的设备模拟器，用于设备的上电调试和测试 | 不在商业版的范围之内 |

### 👥 这个项目适合谁？

| 人群 | 能用它做什么 |
|:---|:---|
| 🎓 **学生** | 完成物联网课程项目和毕业设计；理解完整的 HTTP 设备认证与数据上报流程 |
| 🔬 **研究者** | 修改固件或平台源码，用于协议安全分析和边缘计算算法验证 |
| 🛠️ **创客/爱好者** | 用自己的硬件搭建家庭环境监测站，完全掌控自己的数据 |
| 💼 **开发者** | 在接入商业版之前，先用它快速评估 UbiBot 的技术架构 |

---

## 🗂️ 项目生态

### 🏗️ 核心平台

| 项目 | 说明 | 协议 | 状态 |
|:---|:---|:---:|:---:|
| [ubibot-open-server](https://github.com/ubibot-open/ubibot-open-server) | 物联网后端（Go）——设备身份、数据接入、SQLite 存储——外加一个 React/Ant Design 管理控制台，全部打包进一个自包含的可执行文件 | Apache 2.0 | 🟢 活跃 |

### 📡 设备与固件

| 项目 | 说明 | 协议 | 状态 |
|:---|:---|:---:|:---:|
| [ubibot-open-ws1b](https://github.com/ubibot-open/ubibot-open-ws1b) | UbiBot WS1B 设备的开源 ESP-IDF 固件，支持通过串口在运行时配置 WiFi/服务器地址/序列号——一整批产线设备可以共用一份构建，之后再逐台设置身份 | MIT | 🟢 活跃 |

### 🔌 工具

| 项目 | 说明 | 协议 | 状态 |
|:---|:---|:---:|:---:|
| [ubibot-serial-sync](https://github.com/ubibot-open/ubibot-serial-sync) | 跨平台（Windows/macOS/Linux）的 Qt 6 桌面串口调试工具，面向 UbiBot 设备（WS1、WS1 Pro、GS1-AL4G1RS、SP1……）——设备指令库、数据监控、云端同步的指令集 | LGPLv3 | 🟢 活跃 |
| [ubibot-open-simulator](https://github.com/ubibot-open/ubibot-open-simulator) | 纯 C、可在主机上构建的设备模拟器，协议行为跟 WS1B 固件完全一致——手头没有硬件也能测试后端和管理控制台 | Apache 2.0 | 🟢 活跃 |

### 📚 文档与学习

| 项目 | 说明 | 协议 | 状态 |
|:---|:---|:---:|:---:|
| [ubibot-open-doc](https://github.com/ubibot-open/ubibot-open-doc) | 架构总览、硬件通信协议参考、部署/烧录/上电指南、用户手册与开发者手册（英文 + 中文），以及管理后台/开放 API 参考 | Apache 2.0 | 🟢 活跃 |

---

## ⚡ 快速开始

```bash
# 1. 拉取核心平台仓库
git clone https://github.com/ubibot-open/ubibot-open-server.git
cd ubibot-open-server

# 2. 构建管理后台前端和服务端可执行文件
#    需要：Node.js/npm（前端）和 Go 1.23+（服务端）
./build.sh        # Linux/macOS
# .\build.ps1      # Windows

# 3. 运行——API 和管理界面从同一个地址提供服务
./ubibot-server
# 打开 http://localhost:8080
```

这只覆盖了后端部分。如果还想烧录 WS1B 参考固件、通过串口连接它、并验证"设备 → 后端 → 仪表盘"的
完整链路，见
[系统部署、烧录与上电指南](https://github.com/ubibot-open/ubibot-open-doc/blob/main/guides/deployment-flashing-guide.md)
（也可以看更适合新手的
[用户手册](https://github.com/ubibot-open/ubibot-open-doc/blob/main/manual/README.zh-CN.md)）。

---

## 📄 License

每个仓库都有自己的开源协议——见上面的表格，以及各项目里的 `LICENSE` 文件。

## 💬 贡献

欢迎在各项目自己的仓库里提交 issue 和 PR。通用的贡献流程见本组织的
[CONTRIBUTING.md](https://github.com/ubibot-open/.github/blob/main/CONTRIBUTING.md)（对没有自己
单独一份贡献指南的仓库，默认都适用这一份），以及我们的
[行为准则](https://github.com/ubibot-open/.github/blob/main/CODE_OF_CONDUCT.md)。
