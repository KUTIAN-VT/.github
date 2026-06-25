# KUTIAN-VT

酷天微电子专注于无人系统无线通信、图像传输和控制链路产品，面向无人机、无人车、无人船、机器人、安防巡检和行业应用客户，提供无线数传模组、图传链路、遥控终端及配套技术支持。

KUTIAN Microelectronics develops wireless communication, video transmission, and control-link products for unmanned systems and industrial remote-control applications.

---

## Product Lines

### 图传模组 · VT Module

| 产品 | 描述 | 关键特性 |
|---|---|---|
| **P401 / P410 / P451** | 高带宽 2×2 MIMO 无线数传模组，面向嵌入式集成 | TDD、OFDM、自适应跳频、动态 MCS、1.25–40 MHz 可配带宽 |
| **L4-MINI** | 基于 P401 的紧凑型图传板卡 | 36×36 mm 板卡尺寸，30.5×30.5 mm 安装孔位，MMCX/IPEX 天线选项 |

### 图传盒子 · VT Box

| 产品 | 描述 | 关键特性 |
|---|---|---|
| **L4 Link Suite** | 地面端 AP + 天空端 DEV 成套图传/数传链路 | 以太网、USB、UART、SBUS 透传；低延时；1.4G / 2.4G / 5.8G 频段可选 |

### 带屏遥控器 · Remote Controller

| 产品 | 描述 | 关键特性 |
|---|---|---|
| **K4R-MINI** | 集成遥控与地面站的一体化终端 | Android 系统，高亮屏，SBUS/MAVLink/网络传输，远距离链路 |
| **P4Q-MINI** | 紧凑型带屏遥控器 | Android 系统，便携设计 |
| **P4Q-PRO** | 专业级带屏遥控器 | 高规格配置，适合行业应用 |

### FPV 摄像头 · FPV Camera

| 产品 | 描述 |
|---|---|
| **C3-4F** | FPV 摄像头模组 |

---

## Repositories

### 📄 文档与产品资料

| 仓库 | 描述 | 内容 |
|---|---|---|
| **[P401-DOC](https://github.com/KUTIAN-VT/P401-DOC)** | P401 系列产品对外文档库 | 模组简介、L4/L4-MINI 盒子快速使用手册、K4R-MINI/P4Q 遥控器介绍、C3-4F 摄像头介绍（共 8 份 PDF） |

### 💻 SDK 开发包

| 仓库 | 平台 | 语言 | 描述 |
|---|---|---|---|
| **[L4_Linux_SDK](https://github.com/KUTIAN-VT/L4_Linux_SDK)** | Linux (x86_64 / ARM64) | C | L4 链路/P401 模组 Linux 平台完整开发包 |

**L4_Linux_SDK** 提供以下组件：

```
app/          — 客户端库 libar8030_client.so（动态库，封装 RPC 通信）
daemon/       — l4_daemon 后台服务（设备访问、消息转发、热插拔）
examples/     — 7 个 API 示例程序
com/          — 公共头文件、RPC 框架、日志、缓冲区等基础模块
docs/         — 完整开发手册
```

示例程序覆盖：

| 示例 | 功能 |
|---|---|
| `l4_basic_info` | 设备基础信息/版本查询 |
| `l4_pair_manager` | 图传对频与配对管理 |
| `l4_link_monitor` | 链路状态、质量、吞吐、测距监控 |
| `l4_link_config` | 频段、信道、频宽、MCS 配置 |
| `l4_config_file` | 配置文件导入/导出/恢复 |
| `l4_minidb_config` | MiniDB 持久化配置读写 |
| `l4_ota_upgrade` | 固件 OTA 升级工具 |
| `l4_tuntap` | 网络透传工具 |

| 仓库 | 平台 | 语言 | 描述 |
|---|---|---|---|
| **[L4_Windows_SDK](https://github.com/KUTIAN-VT/L4_Windows_SDK)** | Windows 10/11 x64 | C | 从 L4_Linux_SDK 0.3.0 移植的独立 Windows SDK |

- Visual Studio 2022 / MSVC 编译
- USB 后端：libusb + WinUSB；UART 后端：Win32 Overlapped I/O
- 包含客户端 DLL、daemon、全部示例及工具
- 一键编译脚本 `.\build`

| 仓库 | 平台 | 语言 | 描述 |
|---|---|---|---|
| **[L4-Android-SDK](https://github.com/KUTIAN-VT/L4-Android-SDK)** | Android (minSdk 24) | Java | L4 链路/P401 模组 Android 平台 SDK 与示例工程 |

SDK 组件（全部以 AAR 形式提供）：

| AAR 库 | 功能 |
|---|---|
| `aoalibrary` | USB (AOA) 通信 |
| `cflibrary` | 核心功能（设备控制、配置管理） |
| `fflibrary` | FFmpeg 视频编解码 |
| `medialibrary` | 多媒体处理 |
| `loglibrary` | 日志系统（可选） |

示例工程完整展示了设备连接、视频流解码播放、MQTT/UDP 通信、串口通信等的集成方式。

### 🛠 工具

| 仓库 | 平台 | 描述 |
|---|---|---|
| **[L4_Config_Tool](https://github.com/KUTIAN-VT/L4_Config_Tool)** | Windows | L4 链路配置工具桌面版 |

- 基于 Qt + Web 前端的图形化配置工具
- 功能：设备连接与管理、链路参数配置（频段/频宽/MCS 等）、固件 OTA 升级、配置文件管理
- 开箱即用，解压即可运行，含完整使用手册

### 🔧 Fork 项目

| 仓库 | 上游 | 许可 | 描述 |
|---|---|---|---|
| **[Nxt-FC](https://github.com/KUTIAN-VT/Nxt-FC)** | — | GPL-3.0 | Mini PX4 for UAV Group，面向无人机群的轻量飞控 |
| **[PX4-Autopilot](https://github.com/KUTIAN-VT/PX4-Autopilot)** | [PX4](https://px4.io) | BSD-3-Clause | PX4 开源飞控软件 |

---

## SDK 架构概览

所有平台的 SDK 遵循统一的分层架构：

```
┌──────────────────────────────────────┐
│         用户应用程序                   │
│   (custom app / examples / tools)     │
├──────────────────────────────────────┤
│           SDK 客户端库                │
│  libar8030_client / AAR SDK          │
│  封装配置、监控、升级等 API 接口       │
├──────────────────────────────────────┤
│        l4_daemon 后台服务              │
│     设备枚举、消息路由、热插拔         │
├──────────────────────────────────────┤
│        硬件传输层 (USB / UART)         │
├──────────────────────────────────────┤
│       L4 链路 / P401 模组设备         │
└──────────────────────────────────────┘
```

- **daemon** 负责与硬件通信，监听设备插拔，转发消息
- **SDK 客户端库** 封装 RPC 调用，用户程序通过 API 间接访问设备
- 同一台 PC 上可运行多个用户程序，共享一个 daemon 实例

---

## Application Areas

- UAV 视频传输、遥测、遥控一体化
- UGV / USV 通信与指挥链路
- 云台、IP 相机、LiDAR 等载荷数据回传
- 远距离以太网、UART、USB、SBUS 透明传输
- 工业巡检、安防监控及特种无线链路

## Technical Highlights

| 领域 | 能力 |
|---|---|
| 无线频段 | 1.4 GHz、2.4 GHz、5.8 GHz 产品可选 |
| RF 架构 | 2×2 MIMO、OFDM、TDD |
| 调制方式 | BPSK / QPSK / 16QAM / 64QAM 自适应调制 |
| 数据接口 | USB、Ethernet/RMII、UART、SBUS、GPIO、Debug UART |
| 产品形态 | 模组、紧凑板卡、盒式链路、带屏遥控器系统 |
| 开发支持 | Linux / Windows / Android 三平台 SDK |

## Quick Start

1. **了解产品** → 查看 [P401-DOC](https://github.com/KUTIAN-VT/P401-DOC) 选择适合的硬件
2. **集成开发** → 根据目标平台选择对应的 SDK：
   - 嵌入式/Linux 系统： [L4_Linux_SDK](https://github.com/KUTIAN-VT/L4_Linux_SDK)
   - Windows 上位机：[L4_Windows_SDK](https://github.com/KUTIAN-VT/L4_Windows_SDK)
   - Android 地面站：[L4-Android-SDK](https://github.com/KUTIAN-VT/L4-Android-SDK)
3. **配置调试** → 使用 [L4_Config_Tool](https://github.com/KUTIAN-VT/L4_Config_Tool) 图形化配置链路参数
4. **飞控对接** → 参考 [PX4-Autopilot](https://github.com/KUTIAN-VT/PX4-Autopilot) 和 [Nxt-FC](https://github.com/KUTIAN-VT/Nxt-FC)

---

## Contact

酷天（厦门）微电子有限公司  
KUTIAN (Xiamen) Microelectronics Co., Ltd.

- 联系人：刘伟 (Liu Wei)
- 电话：+86 13696965498
- 邮箱：wei.liu@cecooleye.cn
- 地址：福建省厦门市集美区天阳路 16 号 5 楼

产品选型、固件定制、集成技术支持，请联系酷天技术支持。
