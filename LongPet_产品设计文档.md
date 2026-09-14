# LongPet 产品设计文档

| 文档信息 | 内容 |
| --- | --- |
| 文档版本 | V0.5（编写中） |
| 产品名称 | LongPet |
| 文档类型 | 产品设计文档 |

## 文档修订记录

| 版本 | 日期 | 修订说明 |
| --- | --- | --- |
| V0.1 | 2026-09-13 | 建立正式报告框架与分层目录 |
| V0.2 | 2026-09-13 | 完成报告第六章正文 |
| V0.3 | 2026-09-13 | 完成报告第十章正文 |
| V0.4 | 2026-09-14 | 将第八章拆分为八、九两章，后面章节依次顺延，完成报告第八、九章正文 |
| V0.5 | 2026-09-14 | 完成第七章正文，同步第八章离线语音流程图 |
## 摘要

<!-- 待正文完成后撰写。 -->

## 关键词

<!-- 待正文完成后填写。 -->

## 缩略语与术语表

<!-- 随章节编写补充。 -->

## 图目录

<!-- 随图表插入补充。 -->

## 表目录

<!-- 随图表插入补充。 -->

## 目录

- 文档修订记录
- 摘要
- 关键词
- 缩略语与术语表
- 图目录
- 表目录
- 1 文档概述
  - 1.1 编写目的
  - 1.2 文档范围与读者对象
  - 1.3 产品版本、交付基线与文档关系
  - 1.4 参考资料与证据来源
  - 1.5 完成状态与证据等级说明
- 2 产品概述
  - 2.1 项目背景与问题定义
  - 2.2 产品定位与目标
  - 2.3 目标用户与使用环境
  - 2.4 用户痛点与核心价值
  - 2.5 典型使用场景
  - 2.6 产品形态、组成与交互方式
  - 2.7 产品能力边界与非目标
- 3 产品需求分析
  - 3.1 需求来源、优先级与版本范围
  - 3.2 功能需求总览
  - 3.3 老人端适老交互与本地业务需求
  - 3.4 提醒、今日关怀与状态查看需求
  - 3.5 AI 语音交互与离线陪伴需求
  - 3.6 视觉感知、自动跟头与人物跟随需求
  - 3.7 视频和语音通话需求
  - 3.8 家属端管理与远程控制需求
  - 3.9 运动控制与安全需求
  - 3.10 多模态数据采集、处理与融合需求
  - 3.11 非功能需求
    - 3.11.1 性能与响应时间
    - 3.11.2 稳定性与故障恢复
    - 3.11.3 易用性与适老性
    - 3.11.4 安全性与隐私保护
    - 3.11.5 可维护性与可扩展性
    - 3.11.6 可复现性与可验证性
  - 3.12 平台、硬件、网络与资源约束
  - 3.13 需求验收口径与追踪方式
- 4 系统总体设计
  - 4.1 总体设计原则
  - 4.2 龙芯主控、家属端与运动 MCU 协同架构
  - 4.3 系统功能架构
  - 4.4 物理架构与硬件连接概览
  - 4.5 部署架构与网络边界
  - 4.6 软件分层架构
  - 4.7 四个工程仓库的职责划分
  - 4.8 功能模块与物理模块映射
  - 4.9 主要数据流与控制流
  - 4.10 核心技术路线与选型原则
- 5 硬件系统设计
  - 5.1 硬件总体组成
  - 5.2 龙芯 2K0300 主控平台
  - 5.3 显示与触摸模块
  - 5.4 摄像头模块
  - 5.5 麦克风与音频输出模块
  - 5.6 网络通信模块
  - 5.7 ESP32-S3 运动控制模块
  - 5.8 电机、驱动、编码器与 IMU
  - 5.9 头部舵机机构
  - 5.10 电源、存储与外部接口
  - 5.11 硬件连接关系与信号边界
  - 5.12 关键物料选型依据
  - 5.13 当前硬件限制与工程化缺口
- 6 LoongArch 系统软件平台设计
  - 6.1 目标板约束与平台设计目标
  - 6.2 LoongArch AI 生态的兼容性边界
  - 6.3 Buildroot 软件栈与交叉构建基线
  - 6.4 Python、NumPy 与音频依赖的源码构建
  - 6.5 ONNX Runtime 的无向量指令适配
    - 6.5.1 可加载但数值错误的问题
    - 6.5.2 MLAS 标量路径的源码级修复
    - 6.5.3 算子、模型与部署链路验证
  - 6.6 sherpa-onnx、Qt6、OpenCV 与多媒体能力
  - 6.7 基础系统路线与 Hybrid Rootfs 决策
  - 6.8 Hybrid Rootfs 的合并与校验设计
    - 6.8.1 清单驱动的组件合入和依赖闭包
    - 6.8.2 ABI、架构与 ISA 检查
    - 6.8.3 基础文件保护、locale 与产物校验
  - 6.9 systemd、自启动与自恢复
  - 6.10 验证结论与证据边界
- 7 LongPet 应用软件架构
  - 7.1 应用软件总体分层
  - 7.2 Qt6 表示层与适老界面
  - 7.3 应用控制层与页面流程
  - 7.4 业务服务、Repository 与本地持久化
  - 7.5 设备适配层与能力降级
  - 7.6 AI 语音模块与 Provider 分层
  - 7.7 视觉模块与 TargetObservation 数据通路
  - 7.8 FamilyLink 服务与家属端协同
  - 7.9 MotionService 与运动 MCU 协同
  - 7.10 线程、进程、资源与生命周期管理
- 8 核心业务功能设计
  - 8.1 业务能力与协同关系
  - 8.2 老人端界面与状态反馈
  - 8.3 提醒、今日关怀与天气
  - 8.4 语音交互、工具操作与离线陪伴
  - 8.5 人物感知、AI 视野与自动跟随
  - 8.6 音视频通话与媒体资源
  - 8.7 家属端管理与人工远控
  - 8.8 当前业务边界
- 9 本地 AI 模型与感知系统设计
  - 9.1 端侧 AI 处理链与工程边界
  - 9.2 本地 KWS、声学模型与关键词策略
  - 9.3 自主人物检测模型训练与板端部署
    - 9.3.1 板端模型选型
    - 9.3.2 从随机初始化训练通用人物模型
    - 9.3.3 LongPet 实拍数据与领域微调
    - 9.3.4 V1.2 冻结测试结果
    - 9.3.5 V1.3 泛化实验与版本取舍
    - 9.3.6 ONNX 导出与板端部署
  - 9.4 Detector + Tracker 的持续目标感知
  - 9.5 AI 观测输出与产品接口
  - 9.6 并发资源、验证口径与后续测量
- 10 接口与数据设计
  - 10.1 系统接口总体设计与边界
  - 10.2 LongPet—运动 MCU 串口接口
  - 10.3 LongPet—Family Desktop 接口
  - 10.4 AI Provider 与第三方服务接口
  - 10.5 摄像头、音频、显示与平台硬件接口
  - 10.6 本地业务数据与持久化
  - 10.7 AI 对话、记忆与敏感数据
  - 10.8 视觉观测、训练数据与模型元数据
  - 10.9 配置管理、令牌与隐私保护
  - 10.10 数据一致性、失效与降级处理
- 11 运动控制与系统安全设计
  - 11.1 设计目标与安全原则
  - 11.2 双处理器运动控制架构
  - 11.3 运动执行链路
  - 11.4 控制模式与权限
  - 11.5 UART 协议与输入校验
  - 11.6 多级时效与运动租约
  - 11.7 统一停车、故障锁存与恢复
  - 11.8 家庭远控与控制权仲裁
  - 11.9 视觉跟随安全控制
  - 11.10 安全设计验证与证据追踪
  - 11.11 版本边界与后续优化
- 12 典型业务流程
  - 12.1 开机、自检、登录/连接与服务就绪
  - 12.2 老人端提醒创建、触发与完成
  - 12.3 在线语音对话与工具调用
  - 12.4 断网后的离线基础陪伴
  - 12.5 视觉人物发现、自动跟头与目标丢失
  - 12.6 家属端连接、状态查看与提醒管理
  - 12.7 视频/语音通话
  - 12.8 远程手动控制与停止
  - 12.9 人物跟随启停与安全停车
  - 12.10 故障发生、降级与恢复
- 13 非功能需求落实与工程化设计
  - 13.1 性能预算、响应链路与资源监测
  - 13.2 视觉与语音并发资源调度
  - 13.3 适老可用性与交互一致性
  - 13.4 稳定性、进程隔离与服务恢复
  - 13.5 网络、接口、令牌与隐私安全
  - 13.6 日志、诊断与可观测性
  - 13.7 自动化测试、实机验证与可复现性
  - 13.8 第三方组件、模型来源与许可管理
- 14 构建、部署、发布与运营计划
  - 14.1 四仓库构建链与交付物关系
  - 14.2 龙芯系统、应用、家属端与 MCU 部署概览
  - 14.3 配置、首次启动与验收检查点
  - 14.4 版本基线、发布包与完整性校验
  - 14.5 升级、备份、回退与故障恢复
  - 14.6 原型试用、使用支持与维护计划
  - 14.7 后续运营、反馈收集与迭代计划
- 15 关键技术难点与方案权衡
  - 15.1 2K0300 无 LSX/LASX 的软件兼容问题
  - 15.2 ONNX Runtime 从可加载到数值正确的修复
  - 15.3 基础系统稳定性与 Hybrid Rootfs 取舍
  - 15.4 低算力视觉模型、域适配与 Detector/Tracker 协同
  - 15.5 语音在线/离线链路与资源竞争
  - 15.6 头身协调、距离代理与无地图跟随边界
  - 15.7 远程运动控制的时效性与失效安全
- 16 技术创新与应用价值
  - 16.1 LoongArch 低算力平台的 AI 适配实践
  - 16.2 可校验的 Hybrid Rootfs 交付方法
  - 16.3 面向实拍场景的视觉训练与分层推理
  - 16.4 语音、视觉与家属端协同的适老体验
  - 16.5 多层运动安全机制与可解释边界
  - 16.6 应用价值、推广条件与市场潜力
- 17 当前成果、限制与后续规划
  - 17.1 交付基线与已验证成果
  - 17.2 已实现但验证有限的能力
  - 17.3 实验性能力、接口预留与未完成功能
  - 17.4 已知性能、环境与硬件限制
  - 17.5 后续测试、工程化与产品化路线
- 18 总结
  - 18.1 产品设计总结
  - 18.2 需求、技术方案与证据的对应关系
- 附录
  - 附录 A 需求—模块—测试追踪矩阵
  - 附录 B 系统接口索引
  - 附录 C 关键配置参数表
  - 附录 D 硬件连接与引脚摘要
  - 附录 E 第三方软件、库与模型清单
  - 附录 F 参考资料

---

## 1 文档概述

### 1.1 编写目的

### 1.2 文档范围与读者对象

### 1.3 产品版本、交付基线与文档关系

### 1.4 参考资料与证据来源

### 1.5 完成状态与证据等级说明

## 2 产品概述

### 2.1 项目背景与问题定义

### 2.2 产品定位与目标

### 2.3 目标用户与使用环境

### 2.4 用户痛点与核心价值

### 2.5 典型使用场景

### 2.6 产品形态、组成与交互方式

### 2.7 产品能力边界与非目标

## 3 产品需求分析

### 3.1 需求来源、优先级与版本范围

### 3.2 功能需求总览

### 3.3 老人端适老交互与本地业务需求

### 3.4 提醒、今日关怀与状态查看需求

### 3.5 AI 语音交互与离线陪伴需求

### 3.6 视觉感知、自动跟头与人物跟随需求

### 3.7 视频和语音通话需求

### 3.8 家属端管理与远程控制需求

### 3.9 运动控制与安全需求

### 3.10 多模态数据采集、处理与融合需求

### 3.11 非功能需求

#### 3.11.1 性能与响应时间

#### 3.11.2 稳定性与故障恢复

#### 3.11.3 易用性与适老性

#### 3.11.4 安全性与隐私保护

#### 3.11.5 可维护性与可扩展性

#### 3.11.6 可复现性与可验证性

### 3.12 平台、硬件、网络与资源约束

### 3.13 需求验收口径与追踪方式

## 4 系统总体设计

### 4.1 总体设计原则

### 4.2 龙芯主控、家属端与运动 MCU 协同架构

### 4.3 系统功能架构

### 4.4 物理架构与硬件连接概览

### 4.5 部署架构与网络边界

### 4.6 软件分层架构

### 4.7 四个工程仓库的职责划分

### 4.8 功能模块与物理模块映射

### 4.9 主要数据流与控制流

### 4.10 核心技术路线与选型原则

## 5 硬件系统设计

### 5.1 硬件总体组成

### 5.2 龙芯 2K0300 主控平台

### 5.3 显示与触摸模块

### 5.4 摄像头模块

### 5.5 麦克风与音频输出模块

### 5.6 网络通信模块

### 5.7 ESP32-S3 运动控制模块

### 5.8 电机、驱动、编码器与 IMU

### 5.9 头部舵机机构

### 5.10 电源、存储与外部接口

### 5.11 硬件连接关系与信号边界

### 5.12 关键物料选型依据

### 5.13 当前硬件限制与工程化缺口

## 6 LoongArch 系统软件平台设计

LongPet 在龙芯 2K0300 上运行图形、语音、视觉和多媒体组件。软件平台采用受控交叉构建、标量推理适配和 Hybrid Rootfs，并分别验证产物兼容性、推理数值和板端功能。

### 6.1 目标板约束与平台设计目标

目标主控龙芯 2K0300 采用单核 LA264、约 1 GHz 的 LoongArch64 处理器，不支持 LSX/LASX 向量指令。编入这些指令的二进制包无法在目标板运行；语音、视觉和界面并发时还需控制 CPU 与内存占用。一次板端测试显示系统可见内存约 369 MiB，未配置 swap。

交付基线采用 LoongArch64 LP64D ABI、Linux 6.12.0.lsgd 内核、glibc 2.38 和 Python 3.12。外部 GCC 13.3 工具链以通用 `loongarch64` 和严格对齐为编译目标。ONNX Runtime 产物还需满足目标板内核的 16 KiB ELF 可加载段对齐要求。

软件栈分为基础系统、通用平台、AI 与媒体运行时、应用功能四层（图 6-1）。

```mermaid
flowchart BT
    H["硬件平台<br/>龙芯 2K0300 · LoongArch64<br/>单核 LA264 · 约 1 GHz · 无 LSX/LASX"]
    B["基础系统与设备能力<br/>稳定基础 rootfs · Linux 6.12 · glibc 2.38<br/>驱动 · 网络 · ALSA 音频 · V4L2 · systemd"]
    P["通用软件平台<br/>Qt 6 · Python 3 · NumPy"]
    R["AI 与多媒体运行时<br/>ONNX Runtime 标量 MLAS · sherpa-onnx · OpenCV<br/>sounddevice/PortAudio · FFmpeg · GStreamer"]
    A["LongPet 应用功能<br/>适老 UI · 本地 KWS/语音交互 · Vision<br/>音视频通话 · 设备与家庭服务"]
    H --> B --> P --> R --> A
```

**图 6-1 LongPet 面向 2K0300 的 LoongArch 软件栈总体架构**

### 6.2 LoongArch AI 生态的兼容性边界

预编译的 LoongArch 软件包可能使用 2K0300 不支持的向量指令，运行时的架构判断也可能选错计算内核。关键组件统一交叉构建，并检查指令集、ABI、动态库依赖和推理数值。

源码构建固定版本与编译选项；构建后继续检查 ELF 产物和模型输出。

### 6.3 Buildroot 软件栈与交叉构建基线

Buildroot 2024.08 的 `output-qt6` 构建树使用面向 2K0300 的媒体版 defconfig，包含 Qt、Python/AI、视觉处理及多媒体软件包。主要组件见表 6-1。

**表 6-1 LongPet LoongArch 软件平台关键组件与版本基线**

| 组件 | 当前工程版本 | 构建方式 | 在 LongPet 中的主要用途 | 设计说明 / 关键考虑 |
| --- | --- | --- | --- | --- |
| Qt 6 | 6.8.1 | Buildroot 源码交叉构建 | Widgets 触控界面、网络、SQL、SVG | 采用 `linuxfb` 和触摸输入插件，适配板端显示环境 |
| Python 3 | 3.12.5 | Buildroot 源码交叉构建 | 本地 KWS 及 Python AI 组件运行 | 与基础系统 Python 3.12 运行环境保持兼容 |
| NumPy | 1.25.0 | Buildroot/Meson 源码交叉构建 | 音频数据处理和 AI Python 扩展基础 | 固定工具链与目标 ISA，避免依赖不可控的预编译二进制 |
| OpenCV | 4.10.0 | Buildroot 源码交叉构建 | 摄像头输入、图像预处理与视觉跟踪 | 保留 V4L2、视频处理及目标端所需接口 |
| ONNX Runtime | 1.17.1 | Buildroot 源码交叉构建并应用 MLAS 补丁 | 本地 ONNX 模型推理 | 对无 LSX/LASX 目标启用一致的标量路径，并验证数值正确性 |
| sherpa-onnx | 1.12.15 | Buildroot 源码交叉构建 | 语音推理组件 | 复用系统 ONNX Runtime，避免私有运行库副本不一致 |
| sounddevice | 0.5.1 | Buildroot 源码打包，配套 CFFI/PortAudio | Python 音频采集 | 将动态加载依赖列为合并清单的必需文件 |
| FFmpeg | 6.1.2 | Buildroot 源码交叉构建 | 多媒体工具与编解码库 | 按当前构建基线交付，控制板端实时编码负载 |
| GStreamer | 1.22.9 | Buildroot 源码交叉构建 | 插件化音视频处理能力 | 显式纳入运行时插件，不能只依赖 ELF 依赖闭包 |

Buildroot 生成相互匹配的 target、staging 和交叉 SDK。`output-qt6/target` 为 Hybrid Rootfs 提供软件组件，最终镜像按清单选择合入。

### 6.4 Python、NumPy 与音频依赖的源码构建

部分预编译 NumPy 包使用 2K0300 不支持的扩展指令，因此从 NumPy 1.25.0 源码构建。构建过程使用 Buildroot 的 Meson 交叉编译流程，并将目标端头文件安装到 staging，供下游扩展使用。Python 3.12、NumPy、CFFI、sounddevice 和 PortAudio 构成板端 Python 音频链路。

Buildroot 以 Python 字节码交付，合并时保留 NumPy、sounddevice 的 `.pyc` 文件及二进制扩展。sounddevice 经 CFFI 间接加载 PortAudio，相关文件不会全部出现在 ELF 的 `DT_NEEDED` 中；合并清单因此显式要求 sounddevice、`_sounddevice`、`_cffi_backend` 和 PortAudio 同时存在。板端分别验证数值计算、模块导入和音频设备访问。

### 6.5 ONNX Runtime 的无向量指令适配

#### 6.5.1 可加载但数值错误的问题

ONNX Runtime 1.17.1 的原有 MLAS 路径在无 LSX/LASX 的 2K0300 上出现数值错误。早期板端测试中，FP32 模型输出固定乱码，INT8 模型输出空串，静音输入也得到异常结果；模型可以加载，但推理结果错误。

源码与产物检查发现，原 LoongArch 路径在无向量内核时混用了 16 宽 B 矩阵打包和 4 宽标量计算内核。数据布局不一致导致 MatMul、Gemm、Conv 等计算失真，进而影响 Zipformer ASR 解码。修复前后的算子测试验证了这一定位。

#### 6.5.2 MLAS 标量路径的源码级修复

ONNX Runtime 包新增默认关闭的 `onnxruntime_MLAS_FORCE_SCALAR` 选项，仅在 2K0300 构建规则中启用。补丁调整 MLAS 源文件选择、LoongArch 宏和 LSX 头文件条件，改用通用标量源，并将 B 矩阵打包统一为与标量内核匹配的 4 宽格式。产物仍为 LoongArch64 LP64D 库。

构建使用通用 `loongarch64` 和严格对齐选项。sherpa-onnx 复用 `/usr/lib` 中的 ONNX Runtime，安装时移除 Python 包内的私有运行库副本。部署测试曾因绝对 RPATH 误加载旧库；改用相对 `$ORIGIN` 路径后，隔离库验证通过。验证时需核对实际加载的库版本。

#### 6.5.3 算子、模型与部署链路验证

目标板隔离部署的十项 ONNX Runtime 算子测试均通过。Conv、LayerNorm、Softmax 相对独立参考的最大绝对误差分别约为 `1.9×10⁻⁶`、`1.3×10⁻⁶`、`3.0×10⁻⁸`；其余受测算子为零误差。判定阈值为绝对误差 `1×10⁻⁵`、相对误差 `1×10⁻⁴`。FP32、INT8 流式识别测试中，静音输出为空串，语音结果连续三次一致，四类样例与 x86 参考逐字匹配。x86 参考使用的 sherpa-onnx 版本与板端不同，这些结果仅覆盖受测样例。

构建与镜像检查确认了标量源文件、无 LSX/LASX 指令、16 KiB ELF 可加载段对齐及修复库已纳入交付包。板端隔离部署的算子与语音测试通过；完整 Hybrid Rootfs 的启动与功能验证见项目综合测试报告。

图 6-2 展示从数值错误定位到标量路径修复、板端验证的流程。

```mermaid
flowchart TD
    A["ONNX Runtime 1.17.1<br/>已有 LoongArch64 支持"] --> B["目标 CPU：2K0300<br/>无 LSX/LASX"]
    B --> C["原 MLAS 路径<br/>可交叉编译、可加载"]
    C --> D["数值回归与板端语音验证<br/>可编译、可加载 ≠ 数值推理正确"]
    D --> E["定位：16 宽 SGEMM 打包<br/>与 4 宽标量内核不匹配"]
    E --> F["源码修复：MLAS_FORCE_SCALAR<br/>统一标量源与 4 宽打包"]
    F --> G["重新交叉构建<br/>检查 ISA、ELF 与实际加载库"]
    G --> H["板端算子测试<br/>FP32/INT8 语音样例及参考结果比对"]
    H --> I["进入 LongPet 板端 AI Runtime"]
```

**图 6-2 ONNX Runtime 在无 LSX/LASX 的 2K0300 上的适配与验证路径**

### 6.6 sherpa-onnx、Qt6、OpenCV 与多媒体能力

sherpa-onnx 1.12.15 依赖 ONNX Runtime、Python、NumPy 和 ALSA。构建启用 Python 接口，关闭未使用的 TTS、说话人分离和 GPU 选项，并禁用 Eigen 向量化。LongPet 的本地 KWS 另由独立维护的 Python/ONNX 组件实现。

界面使用 Qt6 Widgets/Network/SQL/SVG，显示采用 `linuxfb`，触摸由输入插件接入。OpenCV 4.10.0 提供 C++/Python 图像处理、V4L2 摄像头和 FFmpeg 视频后端。媒体组件包含 FFmpeg、GStreamer 插件、Opus、VP8、RTP、DTLS、SRTP 与 WebRTC 相关基础库。合并清单显式列出通过运行时注册或 `dlopen()` 加载的插件。板端尚未完成全部 WebRTC 或实时软件编码场景的性能验收；当前也没有已确认可用的通用硬件视频编码器。

### 6.7 基础系统路线与 Hybrid Rootfs 决策

早期实机验证显示，直接套用龙芯buildroot仓库（[open-loongarch/buildroot-2024.08](https://gitee.com/open-loongarch/buildroot-2024.08)）构建的系统，完整替换基础系统后的稳定性未达到项目要求（出现cpu占用率异常波动等问题）。交付方案因此保留已验证的出厂自带基础系统，仅按清单合入所需的用户空间组件。

Hybrid Rootfs 以可启动的板卡基础 rootfs、内核和 ramdisk 为基线，从 `output-qt6/target` 选取 Qt6、Python/AI、OpenCV 和媒体组件。原有内核、模块、固件、动态加载器及核心 C/C++ 运行库保持不变；新增组件通过依赖、ABI 和 ISA 检查后合入。

### 6.8 Hybrid Rootfs 的合并与校验设计

基础系统与 Buildroot target 按清单合并，经依赖、ABI、ISA、基础文件和完整性校验后形成交付包，再进行板端验证（图 6-3）。

```mermaid
flowchart TD
    B["已验证稳定的板端基础系统<br/>内核、驱动、核心运行库"] --> M["Hybrid Rootfs<br/>按 components.yaml 选择性合并"]
    T["Buildroot output-qt6/target<br/>Qt6 · Python/NumPy · OpenCV<br/>ONNX Runtime/sherpa-onnx · FFmpeg/GStreamer"] --> M
    M --> C1["组件必需项与 DT_NEEDED 依赖闭包"]
    C1 --> C2["LoongArch64 ELF、ABI 与 LSX/LASX ISA 检查"]
    C2 --> C3["受保护基础文件、locale 与配置检查"]
    C3 --> C4["归档完整性与 SHA256 自检"]
    C4 --> O["Hybrid Rootfs 交付包"]
    O --> V["部署到 2K0300<br/>启动与运行验证"]
```

**图 6-3 LongPet Hybrid Rootfs 的构建、组件合并与完整性校验流程**

#### 6.8.1 清单驱动的组件合入和依赖闭包

`components.yaml` 以包含/排除规则、必需文件和受保护路径限定合并范围，覆盖 locale、Qt6、OpenCV、NumPy、sounddevice、ONNX Runtime、sherpa-onnx、FFmpeg、V4L2 工具及 GStreamer。必需文件缺失时构建失败；GStreamer 插件和 Python 动态加载依赖需显式列入清单。

解析器递归读取新增 ELF 的 `DT_NEEDED`，优先复用基础 rootfs 中的库，缺失时从 Buildroot target 补齐共享库及链接名，同时保留原有目录布局和受保护文件。合并后检查动态依赖、断链软链接及 Qt5 残留依赖。2026 年 8 月 29 日的记录显示：必需组件缺失 0、未解析依赖 0；检查 1739 个 ELF，断链软链接 0。

#### 6.8.2 ABI、架构与 ISA 检查

合并前核对基础 rootfs 与 target 的 glibc 版本、Python 主版本，以及内核镜像与模块目录；新增 ELF 的 GLIBC、GLIBCXX、CXXABI 符号版本要求不得超出基础运行库能力。8 月 29 日检查时，两套系统均使用 glibc 2.38，新增 ELF 的符号版本要求未超限。

架构检查遍历合并 rootfs 的全部 ELF，要求 `Machine=LoongArch`。ISA 检查默认反汇编本次新增的 ELF，拒绝 LSX/LASX 指令；也可启用全 rootfs 严格扫描。该次检查发现非 LoongArch ELF 0 个，新增 ELF 的向量指令命中 0 次。默认模式的 ISA 检查范围限于新增 ELF。

#### 6.8.3 基础文件保护、locale 与产物校验

清单保护 `/boot`、内核模块、固件、动态加载器、核心 glibc/libstdc++ 与既有系统配置。构建前后对关键基础文件计算 SHA256 并比较；不一致时停止交付。Qt6 所需 UTF-8 环境通过 `locale-archive` 和 `LANG=C.UTF-8` 配置补齐，构建过程校验 archive 非空且包含 C.UTF-8。合并还保留归档的数字属主、权限、扩展属性和 ACL，检查目录层级、关键文件、压缩包完整性，并对 rootfs、内核和 ramdisk 生成及自检 `SHA256SUMS`。

8 月 29 日合并记录显示受保护文件未变、locale 验证通过，rootfs、内核和 ramdisk 的校验通过。现有构建流程可按固定输入和配置重建软件集合；尚无不同主机间逐字节一致的验证记录。

### 6.9 systemd、自启动与自恢复

LongPet 服务以独立的 `longpet` 用户运行，配置显示、触摸、音频、串口权限和私有运行目录，并指定 `linuxfb` framebuffer、`tty1` VT 与触摸输入插件。板端联调解决了 `tty1` 与控制台抢占、设备节点权限问题；整板重启后应用和界面能够恢复。服务通过 `Restart=always` 在进程异常退出后自动重启。

针对特定 Wi-Fi 驱动探测失败，系统配置了条件式恢复服务。时间同步已启用，但 RTC 读取和重启后的同步稳定性仍需验证，提醒服务应检查时钟是否可信。合并系统在 `/etc/locale.conf` 中设置 C.UTF-8；冷启动验收已检查 Qt 字符编码、媒体设备权限、网络恢复及并发资源占用。

### 6.10 验证结论与证据边界

表 6-2 汇总已完成的构建检查与板端测试。具体测试条件见功能与性能报告。

**表 6-2 LongPet LoongArch 平台关键问题、设计决策与验证结果矩阵**

| 工程问题 | 设计决策 | 验证方式 | 当前结果 / 状态 |
| --- | --- | --- | --- |
| 2K0300 无 LSX/LASX | 采用通用目标编译选项，排除不兼容向量路径 | 交叉编译、ELF 架构与新增 ELF 指令扫描 | 构建与 ISA 校验通过 |
| LoongArch AI/Python 组件不能只按架构名称直接复用 | 固定源码、工具链和 ABI 基线 | 目标包构建、符号版本及板端导入检查 | 构建与运行验证通过 |
| NumPy 等 Python 扩展需受控构建 | Buildroot 源码交叉构建，保留字节码与扩展模块 | 构建产物、清单必需项和板端导入检查 | 构建与板端验证通过 |
| ONNX Runtime 可加载但曾出现数值错误 | 强制一致的标量 MLAS 和 4 宽打包路径 | 十项板端算子、FP32/INT8 语音样例及参考结果比对 | 板端数值验证通过 |
| 图形、视觉、语音和媒体组件需在同一目标环境协作 | 扩展 Buildroot Qt6、OpenCV、Python/AI、FFmpeg/GStreamer 配置 | target 构建、运行库与插件合并检查、板端功能验证 | 构建与运行验证通过 |
| 完整替换基础系统的稳定性未达项目要求 | 保留稳定基础系统，选择性合入 Buildroot 用户空间 | Hybrid Rootfs 合并校验和目标板运行验收 | Hybrid 方案板端验证通过 |
| 混合系统可能出现依赖、ABI/ISA 或基础文件冲突 | 对全 rootfs 依赖、符号版本、ISA、受保护文件和 SHA256 分层检查 | 合并报告与最终归档自检 | 依赖、兼容性与完整性校验通过 |
| 嵌入式应用需要自动启动和进程故障恢复 | systemd 管理 LongPet，配置运行权限与自动重启 | 整板重启、服务重启和异常退出恢复测试 | 板端验证通过 |

## 7 LongPet 应用软件架构

LongPet 主程序统一承载本地照护、联网语音、人物感知、家属协同和运动控制。`Application` 负责对象组装与生命周期，本地 `AppController` 和远程 `FamilyLinkController` 接收操作意图，Service 集中处理业务规则；语音、视觉、媒体和运动等外部能力通过 Port 与 Adapter 接入。该结构使不同入口复用同一业务逻辑，并支持可选设备能力的独立降级与后续扩展。

### 7.1 应用软件总体分层

`Application` 在启动时创建对象、注入依赖并连接 Qt 信号，运行时由本地和远程控制入口调用共享的业务服务。Repository 提供持久化边界，设备 Port 提供外部能力边界（图 7-1）。

```mermaid
flowchart TB
    UI[Qt6 页面与 MainWindow] --> AC[AppController 本地流程]
    FD[Family Desktop] --> HTTP[FamilyLinkHttpAdapter]
    HTTP --> FC[FamilyLinkController 远程请求]
    FC --> FL[FamilyLinkService 远程业务边界]
    AC --> S[业务与协同 Service]
    FL --> S
    S --> R[Repository]
    R --> DB[(SQLite 与配置文件)]
    S --> P[能力 Port]
    P --> A[平台 Adapter 与 Provider]
    A --> E[OS 设备 网络服务 MCU]
    APP[Application 组合根] -.创建与注入.-> AC
    APP -.创建与注入.-> FL
    APP -.创建与注入.-> S
    APP -.创建与注入.-> R
    APP -.创建与注入.-> A
```

*图 7-1 LongPet 主程序逻辑分层与依赖方向。虚线表示启动期组装，实线表示运行期业务调用。*

| 模块层 | 主要职责 | 职责边界 |
| --- | --- | --- |
| Qt 表示层 | 呈现页面、表情、状态栏及会话快照；发出语义化用户事件 | 直接读写数据库、发 HTTP 请求、占用音频或摄像头、写串口 |
| 控制层 | 将本地或远程事件映射为业务动作，组织页面跳转和请求/响应 | 复制照护规则、协议实现或设备驱动 |
| Service 层 | 校验业务约束、维护状态机和服务间协作，给出可显示结果 | 依赖某个 Qt 页面或自行解析底层硬件协议 |
| Repository / Port | 隔离持久化与外部能力契约 | 决定用户流程或产品界面 |
| Adapter / Provider | 实现 SQLite 以外的平台、网络、音视频和 UART 接入及错误映射 | 绕开 Service 修改业务状态或决定控制权限 |

*表 7-1 软件层级的职责边界。*

语音、视觉、媒体、天气和运动使用 Port/Adapter 隔离具体实现，便于替换适配器并控制故障影响范围。网络管理等简单能力由 Service 直接使用 Adapter；设置变更由 `SettingsService` 发信号，再由 `Application` 连接音量和背光 Adapter。

### 7.2 Qt6 表示层与适老界面

`MainWindow` 汇集页面并发出提醒保存、通话、语音和设置变更等语义信号。`AppController` 调用 `ReminderService`、`CareService`、`SettingsService`、`VideoCallService` 等业务服务，再将结果返回页面。表情、状态栏、会话状态和提示消息随业务状态更新，使界面与服务状态保持一致。

本地与家属端操作复用同一套提醒规则：`ReminderService` 校验名称、时间和重复设置，页面负责提交草稿与显示结果。页面关闭或切换不影响提醒调度及已保存数据。

### 7.3 应用控制层与页面流程

本地 `AppController` 协调导航、超时返回、页面刷新和语音快捷动作，并呈现服务状态与错误。远程 `FamilyLinkController` 处理路由、鉴权、输入解析和响应映射，再调用 `FamilyLinkService`。两条入口共用业务服务，规则集中在 Service 层。

```mermaid
flowchart LR
    L[触屏与本地语音] --> AC[AppController]
    R[家属端请求] --> FH[FamilyLinkHttpAdapter] --> FC[FamilyLinkController] --> FL[FamilyLinkService]
    AC --> RS[Reminder / Care / Settings / System]
    FL --> RS
    AC --> VC[Voice / VideoCall]
    FL --> VC
    FL --> MV[Motion / Vision 会话能力]
    RS --> REP[Repository]
```

*图 7-2 本地与远程入口对同一业务服务的复用。*

新增本地或家属端页面时，可复用现有业务规则和持久化能力，减少跨端重复实现。

### 7.4 业务服务、Repository 与本地持久化

`ReminderService` 管理提醒校验、调度和完成状态；`CareService` 汇总照护事件形成今日关怀；`SettingsService` 管理持久化设置；`SystemService` 汇聚网络、电源、音量和背光状态；`WeatherService` 定时刷新天气，并在网络恢复后补刷、标记数据时效。各服务按产品功能划分，可同时支持本地与远程操作。

`DatabaseManager` 打开 SQLite 并维护版本化 schema；`ReminderRepository`、`CareEventRepository` 和 `SettingsRepository` 封装查询与更新。AI、天气配置由相应 Repository 读取，Provider 工厂据此选择实现。本地与远程入口通过 Service 访问持久化数据，提醒修订冲突由业务服务处理，Repository 执行持久化。数据库是核心启动依赖，打开失败时 `Application::initialize` 失败。

### 7.5 设备适配层与能力降级

Port 定义服务所需能力，Adapter 对接具体设备或外部实现。`VoiceInteractionService` 使用 ASR、LLM、TTS 和音频 Port；`VisionService` 使用 Camera、Detector、Tracker Port；`MotionService` 和 `VideoCallService` 分别使用运动和媒体 Port。`Application` 在启动时注入实现，使 Service 不依赖单一设备或外部服务的具体实现。

可选能力故障时，系统维持其他功能运行。`VoiceCapabilityService` 根据配置、网络和 Provider 状态判断在线语音可用性，本地快捷指令与陪伴独立运行；天气服务保留带时效标记的最近快照并在网络恢复后补刷；摄像头或视觉模型不可用时，`VisionService` 报告状态。FamilyLink、AI 视野或 Motion 启动失败会被分别记录，不影响其他可用模块初始化。核心数据库故障则由启动流程明确报告。

### 7.6 AI 语音模块与 Provider 分层

`VoiceCommandDispatcher` 根据 KWS 事件、触屏请求、紧急与停止命令以及在线状态选择处理路径。`VoiceInteractionService` 管理录音、ASR、LLM、工具调用、TTS 和播放；`LocalCompanionService` 处理本地陪伴和快捷动作。`VoiceToolRegistry` 校验工具参数并调用现有业务 Service，例如创建提醒，使语音操作遵循与触屏相同的业务规则。`KwsProcessAdapter` 使用 `QProcess` 管理独立 KWS bridge，并向 `KwsPort` 发布事件。

```mermaid
flowchart LR
    K[KWS bridge 独立进程] --> KP[KwsProcessAdapter / KwsPort] --> D[VoiceCommandDispatcher]
    UI[触屏语音入口] --> D
    C[VoiceCapabilityService] --> D
    D -->|在线可用的 KWS 请求或触屏手动尝试| V[VoiceInteractionService]
    D -->|离线 KWS 快捷词| O[LocalCompanionService 与本地动作]
    V --> M[MediaSessionCoordinator]
    V --> A[VoiceAudioPort]
    V --> ASR[AsrProviderPort]
    V --> LLM[LlmProviderPort]
    V --> TTS[TtsProviderPort]
    V --> T[VoiceToolRegistry] --> B[ReminderService 等业务能力]
    ASR --> PA[Provider Adapter]
    LLM --> PA
    TTS --> PA
```

*图 7-3 语音会话、Provider 与业务工具的分层。*

ASR、LLM、TTS 分别配置 Provider Port，`AiProviderFactory` 可按能力选择实现。`ProviderHttpClient` 异步执行网络请求，并以会话 ID 关联结果；取消时中止 Provider 与音频任务，旧会话回调无法更新新会话。在线能力不可用时，KWS 路径仍支持已配置的本地快捷动作和陪伴音频。触屏语音入口显示不可用原因，在线尝试失败后允许重试；离线能力范围保持为快捷指令与本地音频。

### 7.7 视觉模块与 TargetObservation 数据通路

`CameraCaptureAdapter` 实现 `CameraSourcePort`，以单采集进程和 `acquire/release` 计数共享摄像头。`VisionService` 在独立线程中处理最新帧，将 Detector 与 Tracker 的输出统一为 `TargetObservation`。观测提供目标状态、帧序号、采集与发布时间、观测年龄、画面尺寸、人物框、归一化位置及置信度。家属端与自动控制共用该接口，无需依赖模型内部格式；人物框高度用于粗略判断远近。

```mermaid
flowchart LR
    CAM[CameraCaptureAdapter 单采集源] --> VS[VisionService]
    CAM --> FV[FamilyVisionMonitorService]
    CAM --> CALL[VideoCallMediaAdapter]
    DET[Detector Port] --> VS
    TRK[Tracker Port] --> VS
    VS --> OBS[TargetObservation]
    OBS --> FV
    OBS --> AUTO[AutomaticHeadTrackingService]
    AUTO --> MS[MotionService]
    FV --> VIEW[家属端 AI 视野]
```

*图 7-4 摄像头共享与统一视觉观测的多消费者数据通路。*

`AutomaticHeadTrackingService` 根据观测时效与位置提出跟头或跟随请求，由 `MotionService` 统一处理运动权限。`FamilyVisionMonitorService` 复用相机帧和人物观测，向家属端发布 AI 视野，无需重复运行检测器。视频通话使用同一相机源，期间暂停 Vision 推理和自动跟随；仅查看 AI 视野不影响本地 Vision。

### 7.8 FamilyLink 服务与家属端协同

FamilyLink 将家属端请求接入设备已有的业务服务。`FamilyLinkHttpAdapter` 处理 HTTP 传输，`FamilyLinkController` 负责路由、认证和数据转换，`FamilyLinkService` 组合提醒、关怀、设置、系统状态、通话、视觉监看与运动会话能力。远程修改与本地操作共用业务校验和状态机；AI 视野、通话及远控分别由专门的媒体或运动服务处理。

FamilyLink 默认绑定本机地址；配置远程监听时必须提供令牌，否则 `Application` 拒绝启用。远程读写仍通过业务服务校验，AI 视野会话由专门服务管理。

### 7.9 MotionService 与运动 MCU 协同

`MotionService` 统一处理人工远控和自动视觉运动。家属端经 `FamilyLinkService` 取得远控会话，`FamilyMotionControlAdapter` 将实时控制数据转为 `FamilyMotionControlPort` 事件；`AutomaticHeadTrackingService` 提出跟头与跟随请求。`MotionService` 检查模式、人工占用及 MCU 状态，再通过 `MotionPort` 和 `EspSerialAdapter` 发送 UART 命令。

```mermaid
flowchart LR
    FAMILY[FamilyLink 远控会话] --> FPORT[FamilyMotionControlPort / Adapter]
    OBS[TargetObservation] --> AUTO[AutomaticHeadTrackingService]
    FPORT --> MS[MotionService 模式与控制权]
    AUTO --> MS
    MS --> MP[MotionPort] --> ESP[EspSerialAdapter] --> UART[UART] --> MCU[运动 MCU]
    MCU --> ESP --> MS
    MS -. STATUS / head_offset / fault .-> AUTO
    MS -. motion_status .-> FPORT
    FPORT -. 状态反馈 .-> FAMILY
```

*图 7-5 人工与自动控制汇入同一运动服务。实线表示命令，虚线表示状态反馈。*

集中仲裁使视觉策略可独立迭代，也避免远控与自动模式争夺控制权。MCU 的 `STATUS` 更新 `MotionService`，再反馈给视觉策略和家属端；人物跟随仅使用有效的 MCU 状态继续决策。主控发出命令后，实际执行状态以 MCU 后续报告为准。服务停机或链路异常时，`MotionService` 结束相应控制状态，MCU 继续执行独立的命令超时、故障锁存和停车保护。

### 7.10 线程、进程、资源与生命周期管理

`Application` 集中管理资源持有者的创建与关闭，Service 维护会话和状态机，Adapter 管理进程与网络句柄。视觉检测和跟踪运行在 `VisionInferenceThread`；KWS bridge、相机采集、语音录放及通话音频由相应 Adapter 通过 `QProcess` 管理；Provider 使用异步 Qt 网络请求及超时、取消回调。摄像头、麦克风和异步结果分别按资源所有权与会话 ID 协调。

```mermaid
flowchart TB
    APP[Application 启停与连接] --> CAMERA[CameraSourcePort 多消费者 acquire/release]
    APP --> MEDIA[MediaSessionCoordinator 独占音频 owner]
    APP --> VISION[VisionService 推理线程]
    APP --> NET[Provider 网络请求与会话 ID]
    CAMERA --> CV[Vision / AI 视野 / 通话]
    MEDIA --> KWS[KWS 暂停确认与恢复]
    MEDIA --> VA[联网语音 / 离线陪伴 / 通话]
    CALL[VideoCallService 活动状态] --> VISION
    CALL --> AUTO[HEAD_ONLY 暂停 / PERSON_FOLLOW 关闭]
    NET --> FENCE[取消与旧回调隔离]
```

*图 7-6 共享硬件与异步任务的运行期协调。*

| 资源或异步边界 | 当前协调机制 | 异常处理 |
| --- | --- | --- |
| 摄像头 | 一个 `CameraCaptureAdapter` 对 Vision、AI 视野和通话计数共享；最后一位消费者释放后停采集 | 相机或模型不可用时报告状态，其他业务保持运行 |
| 麦克风与音频 | `MediaSessionCoordinator` 为语音、离线陪伴、通话维护 owner；KWS 暂停确认后才允许打开音频，释放后延迟恢复 KWS | 暂停确认超时则中止本次音频操作 |
| 通话与视觉 | 通话状态通知 Vision 和自动控制；媒体 Adapter 使用共享相机源 | 通话时暂停 Vision 与 HEAD_ONLY，并关闭 PERSON_FOLLOW；结束后 Vision 可重新获取新观测，HEAD_ONLY 满足条件才恢复，PERSON_FOLLOW 须家属显式重新开启 |
| 网络请求与会话 | Provider 超时/取消；`VoiceInteractionService` 以 session ID 拦截旧 ASR、LLM、TTS 和播放回调 | 当前会话返回错误或结束，旧结果与新会话隔离 |
| 运动控制 | `MotionService` 统一模式、会话和状态；Adapter 承接网络与 UART | 控制能力退出，MCU 继续执行独立安全保护 |

*表 7-2 主要共享资源与异步边界。*

关闭时，`Application::shutdown` 先停止媒体超时与 KWS 恢复调度，再依次停止语音、天气、视觉、自动运动、Motion、家属端监听、提醒及平台监测，最后释放对象并关闭数据库。活跃任务由对应 Service 取消，设备与网络句柄由 Adapter 释放。`deploy/longpet.service` 负责自启动和异常重启，与应用内资源释放共同构成恢复边界。


## 8 核心业务功能设计

LongPet 将日常陪伴、照护提醒和家庭联系整合在同一设备中。老人通过 1024×600 触屏或语音快速进入常用功能；家属通过桌面端设置提醒、查看设备、发起通话并提供远程协助，形成老人易用、家属可参与的双端体验。

### 8.1 业务能力与协同关系

老人端集中呈现提醒、今日关怀、天气和语音入口，减少日常操作步骤；家属端提供设备查看、通话及远程协助。视觉功能让设备主动关注人物，并向家属展示当前感知画面；人物跟随与人工远控均在独立运动安全校验下运行。

```mermaid
flowchart LR
    E[老人端<br/>触摸与语音] --> D[日常陪伴与照护<br/>提醒·今日关怀·天气]
    E --> C[家庭联系<br/>音视频通话]
    F[家属端<br/>管理与查看] --> D
    F --> C
    F --> V[AI 视野<br/>了解当前画面与人物状态]
    V --> A[自动关注与受限人物跟随]
    F --> R[人工远控]
    A --> S[运动安全约束]
    R --> S
```

图 8-1 LongPet 核心业务能力关系。

| 核心功能 | 主要使用者 | 当前产品价值 |
| --- | --- | --- |
| 陪伴界面与语音 | 老人 | 用触摸或自然语言进入常用功能，并看懂设备正在倾听、回答还是等待 |
| 提醒与今日关怀 | 老人、家属 | 将提醒触发、老人确认和饮水记录汇成当日可查看的信息 |
| 天气 | 老人 | 在状态栏低成本查看当前天气，并在在线对话中询问天气 |
| 自动关注与 AI 视野 | 老人、家属 | 机器人朝向人物，家属了解它当前看到的画面和感知状态 |
| 人物跟随与人工远控 | 老人、家属 | 在受控场景下靠近人物，或由家属手动协助移动 |
| 音视频通话 | 老人、家属 | 在同一设备上进行家庭联系；语音与视频按所需媒体分别启用 |

表 8-1 核心功能、目标用户与主要价值。

### 8.2 老人端界面与状态反馈

老人端的设计重点是让高频任务一步可见、低频设置少打扰。1024×600 触屏首页显示陪伴表情和简短提示，并直接提供“陪我说话”“今日关怀”“视频通话”三个大按钮。状态栏显示时间、网络，以及有数据时的天气和供电信息，并提供设置入口。老人可从“今日关怀”进入提醒列表，查看事项状态或新增、编辑、确认提醒；较复杂的配置由家属端完成。

```mermaid
flowchart TD
    H[首页<br/>陪伴表情·状态栏·三个常用按钮] --> T[陪我说话<br/>在线对话或离线陪伴]
    H --> G[今日关怀<br/>饮水与当日事项]
    G --> M[查看提醒<br/>列表·编辑·完成]
    H --> P[视频通话<br/>呼叫家属]
    H --> X[状态栏设置入口<br/>必要的本机设置]
```

图 8-2 老人端主要导航。语音不可用时，常用功能仍可通过触屏进入。

陪伴表情用于提示设备状态：待机、倾听、思考、说话和异常分别配有表情或文字反馈。提醒触发时显示提示，并区分已完成与未确认事项；通话页面显示对方、连接状态和挂断入口。网络、AI 或设备能力不可用时，页面提示重试或功能状态，其他本地功能保持可用。表情暂时不承担情绪识别功能。

### 8.3 提醒、今日关怀与天气

提醒用于把饮水、用药等需要记住的事项转成到时可见、完成可查的行动。老人可在本机提醒页触摸创建或修改，家属可远程补充，在线语音也可在限定范围内创建、查询或删除提醒。三种入口指向同一份本地提醒状态，老人不必学会家属端的复杂设置。家属端的写入只有在设备确认成功后才算完成；连接失败或内容冲突会提示刷新、重试，不会显示虚假的保存成功。

```mermaid
flowchart LR
    A[老人触摸] --> R[本地提醒]
    B[家属远程设置] --> R
    C[在线语音工具操作] --> R
    R --> D[到时提醒老人]
    D --> E{老人确认完成?}
    E -- 是 --> F[记录完成<br/>更新今日关怀]
    E -- 尚未确认 --> G[保持未完成状态]
```

图 8-3 提醒的三入口与完成状态。触发后未确认的提醒保持未完成；断网期间已有本地提醒仍依本机时间触发。

“今日关怀”把饮水记录和用药提醒完成等离散事件整理为当日信息。老人可在本机记录喝水并查看进度，家属端可读取同一设备上的关怀摘要；活动分钟、互动次数虽有展示或记录位置，当前并未自动由摄像头或运动传感器生成健康指标，后续会补充相关功能和算法；没有可靠数据时应显示未知或待接入。这些信息有效帮助家庭了解已记录的日常事项。

天气作为无需另开复杂页面的日常信息显示在状态栏，也可作为在线语音回答的已有事实。网络正常且配置可用时更新当前天气；更新失败时，本次运行中已取得的快照会保留，首次无数据则显示“--”。若快照过期，在线语音使用旧快照时会提示信息可能过期。

### 8.4 语音交互、工具操作与离线陪伴

语音让老人少走菜单。在线能力可用时，老人说“小龙小龙”后进入倾听状态，说完需求后看到思考状态，随后听到回答并看到说话状态，结束后回到陪伴状态。老人也可以触摸“陪我说话”进入对话。在线模式支持日常聊天、询问时间和当前天气，以及提醒创建、查询、按明确对象删除和打开限定页面等业务操作。Tool Calling 的价值在于把自然语言请求转为受限的真实产品动作，提高产品的便捷性和智能性。

```mermaid
flowchart TD
    W[小龙小龙] --> N{在线 AI 可用?}
    N -- 是 --> L[倾听需求] --> Q[思考并进行 Tool Calling] --> P[基础的记忆整理] --> O[回答与播报] --> H[返回陪伴]
    N -- 否 --> K[离线快捷提示与关键词]
    K --> B[时间·提醒页面·返回主页等本地动作]
    K --> C[有授权音频时播放陪伴内容]
    B --> H
    C --> H
    T[触摸陪我说话] --> M[手动尝试在线会话]
    M --> L
    M -. 在线请求失败 .-> E[显示错误并允许重试] --> H
```

图 8-4 在线与离线语音流程。在线 AI 不可用时，KWS 唤醒可进入本地快捷功能；触屏入口会先提示不可用原因并尝试在线会话，失败后提示并允许重试，不会自动转为离线大模型对话。

离线时，“小龙小龙”打开本地快捷提示；本地词可打开提醒、报时、返回主页、进入联系家人的通话入口或紧急页面。“陪我说话”可播放已配置的本地陪伴音频，音频文件缺失时页面提示不可播放。通话仍需网络，紧急页面目前不自动报警；语音“停止”用于取消对话或陪伴音频，或触发底盘停车。

通话、录音、播报或陪伴音频占用麦克风时，本地唤醒监听暂停；触屏取消或挂断入口保持可用。在线请求失败时显示失败状态，老人可结束或重试；离线快捷功能仍可通过本地唤醒入口使用。

### 8.5 人物感知、AI 视野与自动跟随

人物感知将同一份实时观测用于自动关注、家属端 AI 视野和人物跟随：老人获得更自然的陪伴反馈，家属可以了解设备关注的画面，并在需要时开启受控跟随。三项功能按各自权限运行。

**自动关注。** 家属开启“仅头部”后，设备根据有效人物位置调整头部朝向，底盘保持静止。目标丢失、画面中断或观测过期时停止使用旧位置。

**AI 视野。** 家属可在桌面端查看当前画面、人物框、感知状态及“关闭／仅头部／人物跟随”模式，并进入人工远控。无有效目标时不显示旧人物框；关闭远程视野页面不影响设备本地视觉功能。

**人物跟随。** 家属开启后，设备先确认目标，再调整头部和机身朝向；目标较远且安全条件满足时低速靠近，到达设定的画面距离后停车。目标丢失、摄像头不可用、人工接管、通话或故障时停止移动。通话或人工远控结束后，家属需重新开启跟随。

```mermaid
flowchart LR
    P[发现人物] --> H[仅头部自动关注]
    H --> V[家属端 AI 视野<br/>画面·人物框·状态]
    V --> U{家属开启跟随?}
    U -- 是 --> F[确认目标并调整朝向] --> M[条件满足时靠近] --> S[距离合适或目标丢失时停车]
    U -- 否 --> H
```

图 8-5 人物感知与受控跟随流程。

### 8.6 音视频通话与媒体资源

老人可从首页“视频通话”主动呼叫家属，家属端可接听或拒绝；老人等待时可取消，呼叫被拒绝时会收到提示。家属端可选择语音或视频呼叫设备；设备播放对应提示并准备媒体后接通，老人端提供挂断入口。通话页显示对象、连接状态和时长，触屏可显示醒目的挂断按钮。

```mermaid
flowchart TD
    A[老人从首页发起视频呼叫] --> B[家属端接听或拒绝]
    C[家属端发起语音或视频呼叫] --> D[设备提示并准备媒体]
    B -- 接听 --> E[双方通话]
    B -- 拒绝 --> R[老人端显示无法接听]
    D --> E
    E --> F[任一端挂断或连接中断] --> G[显示结果并返回首页]
```

图 8-6 双向通话流程。语音通话只使用音频，视频通话使用双方画面和声音。设备发起视频时暂停占用摄像头的视觉任务，通话结束后重新检测人物。摄像头、麦克风或扬声器被占用、权限不足或连接失败时，页面显示失败或忙碌状态并释放已占用资源；断线后退出通话。家庭通话需保持网络连接。

### 8.7 家属端管理与人工远控

老人端提供陪伴、关怀、通话和必要的本机操作。家属端集中管理设备与网络状态、今日关怀、提醒、AI 视野、音视频通话、自动跟头、人物跟随及人工远控。家属端以设备实际反馈为准，失联、能力不可用或写入冲突时提示异常。

```mermaid
flowchart LR
    E[老人端<br/>陪伴·关怀·视频呼叫·必要设置] <-->|同一设备状态| F[家属端<br/>提醒与设置管理·设备状态·AI 视野·通话·远控]
    F --> M[模式选择<br/>关闭／仅头部／人物跟随]
    F --> R[人工远控<br/>按住移动·松开停车]
```

图 8-7 老人端与家属端的功能分工。两端共用设备上的提醒状态；家属端通过刷新获取关怀信息。

家属从“AI 视野”进入人工远控，按住方向按钮或按键时发送控制意图，松开、页面失焦或连接丢失时停车。人工控制优先于自动跟随；退出后，家属需重新开启跟随。运动能力不可用、控制模式不符或设备故障时，界面禁用控制按钮。

### 8.8 当前业务边界

现阶段的业务链覆盖老人端日常使用、家属端远程协助、本地感知与受控运动。表 8-2 集中列出已交付能力及使用条件，便于后续试用和迭代。

| 能力 | 当前交付 | 使用条件与后续方向 |
| --- | --- | --- |
| 老人端适老交互 | 大按钮、浅层导航与状态表情 | 目前表情是交互反馈，可加入情绪识别丰富表情反馈 |
| 提醒与今日关怀 | 触屏、家属端和在线语音共用提醒，完成后形成当日记录 | 已有本地提醒可在断网时触发；完成状态以老人确认为准，活动指标待接入可靠数据源 |
| 天气 | 状态栏显示天气，在线对话可引用已获取的信息 | 联网更新；失败时保留本次运行快照，过期标记待补充 |
| 在线 AI 语音与工具操作 | 自然语言聊天、提醒管理和限定页面操作 | 需要在线服务；具体动作由本机规则授权 |
| 本地唤醒与离线陪伴 | 离线保留关键词唤醒、快捷动作和已配置的陪伴音频 | 通话占用麦克风时暂停监听；长期记忆功能 |
| AI 视野、自动关注与人物跟随 | 家属查看当前画面，设备在受控条件下关注并靠近人物 | 目标无效或模式冲突时停车；身份识别、摔倒检测算法、复杂导航与避障属于后续能力 |
| 音视频通话 | 老人和家属双向联系，按需启用语音或视频 | 依赖网络与媒体设备；家属主动呼叫时设备提示后接通，老人可挂断 |
| 家属管理与人工远控 | 远程设置提醒、查看状态和按住协助移动 | 写入以设备确认为准；松开或失焦停车，左右平移暂缓开放 |

表 8-2 LongPet 已交付的业务能力、使用条件与后续方向。

## 9 本地 AI 模型与感知系统设计

LongPet 在龙芯 2K0300 上完成关键词唤醒（KWS）和人物视觉推理，形成无需云端参与的基础感知链。人物检测模型由项目在 PC 端训练、导出为 ONNX 后部署到板端；在线 ASR、LLM 和 TTS 则补充开放式语音对话能力。

### 9.1 端侧 AI 处理链与工程边界

麦克风输入先经自适应能量 VAD 筛选，再由常驻 FSMN-CTC 模型产生关键词事件；摄像头输入经轻量 Detector 和 Sparse LK Tracker 形成带时效信息的 `TargetObservation`。两条链分别支撑语音入口和人物位置观测，电机动作仍由独立运动控制链路裁决。板端运行依赖标量适配后的 ONNX Runtime、Python/NumPy 音频组件和 OpenCV。

### 9.2 本地 KWS、声学模型与关键词策略

本地 KWS 基于预训练 WeKWS FSMN-CTC ONNX 模型及中文 token 表，项目完成了从音频采集、FBank、CTC 词条匹配、自适应 VAD 到进程桥接和业务动作映射的端侧集成，并针对产品词条配置别名和阈值。声学文件为 `components/longpet-kws/assets/fsmn/fsmn_ctc.onnx`（3,065,258 B；SHA-256 `6febd9f7f15c47caed88d434d810651e34215334c66961b9ba66251fa04d98c4`）。产品 KWS 使用 Python、NumPy 和 ONNX Runtime `CPUExecutionProvider` 运行；声学权重的来源与再分发许可将在发布前核验。

板端默认以 48 kHz 单声道 PCM 每约 100 ms 取一块，转换为模型 16 kHz 输入；自适应能量 VAD 在静音时跳过 ONNX，保留约 300 ms 语音前缀，连续约 500 ms 静音后重置流式缓存。`KwsProcessAdapter` 通过独立 bridge 接收逐行 JSON 事件；模型常驻，暂停时释放采集，异常退出可重启。音频会话只有在带 ID 的暂停确认后才获麦克风；超时按失败处理。

```mermaid
flowchart LR
    A[48 kHz 麦克风/100 ms 音频块] --> B[16 kHz 重采样]
    B --> C[自适应 Energy VAD]
    C --> D[FSMN-CTC ONNX + token/alias]
    D --> E[JSON 事件 → KwsProcessAdapter]
    E --> F[VoiceCommandDispatcher]
    F --> G[在线语音/本地快捷/紧急页面]
    H[录音·TTS·通话] -.麦克风所有权.-> I[MediaSessionCoordinator]
    I -.暂停 KWS 并等待 ACK.-> C
```

图 9-1 本地关键词与音频资源协调。通话和播报期间暂停 KWS 监听。

产品 bridge 为同一声学模型配置 11 个词条：“小龙小龙、你好、陪我说话、救命、停止、打开提醒、现在几点、联系家人、返回主页、音量大点、音量小点”。默认唤醒阈值为 0.15，“你好”为 0.10，其余命令词为 0.05；“救命”配置同音字别名，“返回主页”通过词表中的“反回主页”匹配后归一化。阈值属于 CTC 匹配策略。

| 关键词 | 当前 `VoiceCommandDispatcher.cpp` 的实际行为 |
|---|---|
| “小龙小龙” | 在线可用时开始语音会话，否则打开离线指令窗口 |
| “你好” | 识别后不触发业务操作 |
| “救命” | 取消当前语音/陪伴并打开本地紧急页面，当前不自动拨号或上报 |
| “停止” | 取消当前语音/陪伴并提示用户，不发送底盘 `STOP` |
| “陪我说话”“打开提醒”“现在几点”等 | 在线不可用时执行本地音频、提醒页、报时、联系家人入口、主页或音量调整 |

表 9-1 关键词到业务动作的映射。

通话、录音、播报和离线播放占用麦克风时，KWS 监听暂停。无视觉工况下，KWS 进程在安静环境cpu占用约13%， 嘈杂环境中 CPU 占用约 23%～31%；实测端到端延迟控制在几百毫秒以内。

### 9.3 人物检测模型自主训练与板端部署

LongPet 基于 [ETH-PBL/TinyissimoYOLO](https://github.com/ETH-PBL/TinyissimoYOLO) 的 TinyissimoYOLO-v1-small 网络结构，自主训练人物检测权重。通用模型从随机初始化开始，在 COCO person-only 数据上训练，再使用 LongPet 固定摄像头的实拍数据进行领域微调。

#### 9.3.1 板端模型选型

在单核约 1 GHz 的龙芯 2K0300 上，早期 YOLO11n-Pose 和手部 Landmark 每帧耗时数秒，皆作为废弃方案。后来测试的FastestDet 能检测人物，但推理延迟较高。表 9-2 对比同图、同 benchmark 条件下的纯 CNN 推理耗时，作为轻量模型选型依据。

| 模型 | 输入 | 板端纯推理平均耗时 | 相对速度 |
|---|---:|---:|---:|
| FastestDet | 352×352 | 2,399.16 ms | 1× |
| Tinyissimo V1.1 | 128×128 | 635.41 ms | 约 3.78× |

表 9-2 板端模型选型基线。Tinyissimo V1.1 的单次推理约 0.64 s，比 FastestDet 快约 3.78 倍；正式 V1.2 的并发性能另见表 9-6。

![图 9-2 同口径板端纯推理延迟对比](assets/vision/board_latency_comparison.png)

#### 9.3.2 Tinyissimo 架构来源与 COCO 通用训练

V1.1 从随机权重开始训练，使用 COCO person-only 小样本集：训练集 2,000 张含人图和 500 张无人图，验证集 500 张含人图和 125 张无人图。该版本用于验证架构、ONNX 导出及板端部署。COCO-full 随后独立随机初始化（`pretrained=false`、`resume=false`），用于训练正式通用人物模型；配置与有效数据量见表 9-3。

| 项目 | COCO-full 正式配置或扫描结果 |
|---|---|
| 网络与任务 | TinyissimoYOLO-v1-small，person-only |
| 初始化 | 重新随机初始化；`pretrained=false`、`resume=false` |
| 输入 | 128×128 |
| manifest 选出训练图片 | 69,115（64,115 张含人图、5,000 张无人图） |
| 扫描后有效训练图片 | **69,078**，其中 **4,996** 张空标注背景图 |
| 损坏并忽略 | **37** 张 |
| Optimizer / batch | SGD / 256 |
| 最大 epoch / patience | 150 / 30 |
| 初始学习率 `lr0` / seed | 0.01 / 20260901 |
| AMP | 开启 |

表 9-3 COCO-full 通用人物模型训练配置。manifest 选出 69,115 张图，训练缓存确认 69,078 张有效图，其中 4,996 张为空标注背景图；37 张损坏图被忽略。正式部署前继续使用 LongPet 固定视角数据微调。

```mermaid
flowchart TD
    A[TinyissimoYOLO-v1-small 网络结构<br/>ETH-PBL 上游] --> B[V1.1 独立随机初始化<br/>小集 2500 train / 625 val]
    B --> C[架构与板端可行性验证]
    A --> D[COCO-full 重新随机初始化<br/>pretrained=false；有效训练图 69078]
    D --> E[通用 person checkpoint]
    E --> F[V1.2 产品域微调<br/>366 train / 88 val]
    F --> G[85 张 Frozen Test<br/>不参与训练与模型选择]
    G --> H[V1.2 FINAL_RECOMMENDED<br/>正式部署]
    F --> I[V1.3 从 V1.2 继续训练<br/>170 train / 93 val]
    I --> J[52 张 New Test + 原 Frozen Test]
    J --> K[V1.3 EXPERIMENTAL<br/>扩域评估与跨场景优化]
```

图 9-3 人物检测权重训练谱系。V1.1 与 COCO-full 独立初始化；V1.2 使用 539 张领域数据进行训练、验证和冻结测试划分，V1.3 在 V1.2 基础上开展扩域实验。

#### 9.3.3 LongPet 实拍数据集构建

V1.2 数据来自 36 段自行拍摄的产品视角视频，总长约 332.7 s，分辨率 1920×1080、约 30 FPS，按约 2 FPS 抽帧。使用 dHash 汉明距离和 32×18 灰度差剔除近重复帧；YOLOv8x teacher 在 PC 端初标，低置信、局部人体及疑似漏检由人工复核。同一视频的帧只进入一个 split，避免相邻帧随机划分造成测试泄漏。

V1.2 领域数据集共 539 张：366 张用于训练，88 张用于验证和早停，85 张 Frozen Test 用于独立评估。Frozen Test 在 V1.3 实验中继续保持原有标注和划分，其中没有经确认的纯无人负样本。

```mermaid
flowchart LR
    A[36 段实拍视频] --> B[约 2 FPS 抽帧]
    B --> C[dHash + 32×18 灰度差去重]
    C --> D[YOLOv8x teacher 初标]
    D --> E[低置信/局部人体/漏检人工复核]
    E --> F[视频级固定 split]
    F --> G[366 train]
    F --> H[88 val]
    F --> I[85 Frozen Test]
```

图 9-4 V1.2 实拍数据集构建流程。YOLOv8x teacher 只在 PC 端用于初标，冻结测试集保持独立。

#### 9.3.4 V1.2 领域微调与 Frozen Test

V1.2 从项目 COCO-full `best.pt` 开始领域微调，输入 128×128，使用 SGD、batch 32、`lr0=0.001`、最多 30 epoch、`patience=8`；最佳验证结果出现在第 21 个 epoch。表 9-4 在同一组 85 张 Frozen Test 上比较 COCO-only 与 V1.2 的静态 ONNX 模型。

| 指标 | COCO-only | V1.2 | 变化 |
|---|---:|---:|---:|
| Precision | 1.0000 | 1.0000 | 不变 (均为1是由于第一轮实拍数据采集未收集无人负样本） |
| Recall | 0.8813 | 0.9647 | +0.0834 |
| mAP50 | 0.9777 | 0.9856 | +0.0079 |
| mAP50-95 | 0.7963 | 0.8488 | +0.0525 |
| 正样本逐帧检测成功率 | 84.7% | 96.5% | +11.8 个百分点 |

表 9-4 V1.2 产品域适配结果。在同一组冻结测试帧上，Recall 从 0.8813 提升至 0.9647，正样本逐帧检出率提升 11.8 个百分点。逐帧检出按 `score≥0.25` 且最佳框 `IoU≥0.50` 统计。困难场景 `2场景1人绿左.mp4` 的 3 张测试帧尚未检出；空场误报由 V1.3 新域负样本另行评估。

#### 9.3.5 V1.3 扩域实验与最终版本取舍

V1.3 从 V1.2 checkpoint 继续微调，新增 19 段、总长约 174.4 s 的视频，形成 315 张图：170 张训练、93 张验证、52 张 New Test；其中 226 张含人图、89 张人工确认的无人图。扩域实验同时使用 New Test 和保持不变的 V1.2 Frozen Test，分别评估新旧场景表现。

| 测试域与指标 | V1.2 | V1.3 |
|---|---:|---:|
| **New V1.3 Test（52 张；38 positive / 14 negative）** | | |
| Recall | 0.4689 | 0.7895 |
| mAP50 / mAP50-95 | 0.7062 / 0.2989 | 0.8959 / 0.6136 |
| 正样本逐帧检出率 | 47.37% | 71.05% |
| 确认无人帧误报率 | 28.57% | 0% |
| **Frozen V1.2 Test（85 张；无 confirmed negative）** | | |
| Recall | 0.9647 | 0.9502 |
| mAP50 / mAP50-95 | 0.9856 / 0.8488 | 0.9784 / 0.8086 |
| 正样本逐帧检出率 | 96.47% | 88.24% |

表 9-5 V1.3 在两个测试域上的表现。V1.3 提高了新域召回率和 mAP，14 张确认无人测试帧中未出现误报；原冻结域的逐帧检出率则从 96.47% 降至 88.24%。为保持已验证产品场景的检出表现，正式部署继续使用 V1.2（`FINAL_RECOMMENDED`）；V1.3 作为扩域实验版本（`EXPERIMENTAL`）继续优化。

![图 9-5 按冻结域和新域分别比较 V1.2 与 V1.3](assets/vision/model_evolution_accuracy.png)

图 9-5 V1.2 与 V1.3 在新旧测试域的表现对照。

#### 9.3.6 ONNX 导出与 LoongArch 部署

正式 V1.2 为 person-only FP32 ONNX，opset 17，输入 `[1,3,128,128]`、输出 `[1,5,16]`，约 402,057 个参数，文件 1,620,685 B；SHA-256 为 `cb3defedb3ac01006d4caa5312c21d4a674e5a808e885067f2bc67e8f822f89c`。在 85 张 Frozen Test 上，PyTorch 与 ONNX 原始输出的最大绝对差为 0.00036621、平均绝对差为 0.00000982，均满足 `atol=5e-4`；逐图 `score≥0.25` 的候选框数量一致。

板端通过 ONNX Runtime `CPUExecutionProvider` 运行 V1.2 模型；`deploy/longpet.service` 指向 `tinyissimo-person-128-longpet-v1.onnx`。训练与部署流程包括 COCO 通用训练、产品域微调、Frozen Test、ONNX 一致性检查、LoongArch 部署、板端测量及 Detector+Tracker 调度优化。

### 9.4 Detector + Tracker 持续人物感知

正式 V1.2 的 detector-only 板端测量显示，KWS 并发时 CNN 平均推理约 1,269 ms，检测吞吐约 0.738 FPS。Vision V2.0 使用 Tinyissimo 低频搜索、目标重获和周期纠偏，并由 Sparse Lucas–Kanade Tracker 在检测间隙更新人物框。工作线程只处理摄像头最新帧，避免旧帧排队。

| V1.2 detector-only 板端工况 | 预热 / 测量帧 | 平均推理 | P95 推理 | 平均总链路 | 有效检测吞吐 |
|---|---:|---:|---:|---:|---:|
| Vision 基本独占（主程序停止） | 10 / 65 | 735.26 ms | 759.04 ms | 768.11 ms | 1.285 FPS |
| KWS 并发 | 10 / 33 | 1,268.86 ms | 1,374.13 ms | 1,322.83 ms | 0.738 FPS |

表 9-6 正式 V1.2 detector-only 实机测量。总链路包含 JPEG 解码、预处理、CNN 推理和后处理；两组 RSS 分别为 41,296/41,920 kB，`LongPetVisionBench` 进程 CPU 分别为 90.29%/55.91%。KWS 并发使单核资源竞争加剧。

```mermaid
flowchart LR
    A[Camera latest frame] --> B[SEARCHING]
    B -->|Tinyissimo 检测| C[DETECTED]
    C --> D[Sparse LK 跟踪]
    D --> E[TRACKING]
    E -->|周期纠偏| F[Tinyissimo]
    F --> E
    E -->|跟踪失败| G[LOST]
    G -->|Tinyissimo 重获| H[REACQUIRED]
    H --> D
```

图 9-6 Detector 与 Tracker 的状态流。跟踪特征不足、越界或一致性检查失败时转入目标重搜。

| V2.0 Detector+Tracker 实机工况 | CNN 平均推理 | Detector 总链路 | Detector 实际触发 | 目标位置更新 |
|---|---:|---:|---:|---:|
| KWS 正常运行，单人物 | 992.33 ms | 1,030.19 ms | 0.121 Hz | **8.75 Hz** |
| 真人持续走动，单人物 | 993.922 ms | 1,028.81 ms | 0.247 Hz | **7.23 Hz** |

表 9-7 V2.0 板端感知调度。通过低频 Detector 与高频 Tracker 协同，单人物测试中的目标观测频率达到约 7～9 Hz；真人走动时，6 次跟踪失败均由 Detector 重获。这使受限算力平台也能够持续向上层提供人物位置。

CNN 周期纠偏与 Tracker 目前在同一工作线程同步执行，CNN 推理期间目标更新暂停，结束后继续处理最新帧。`TargetObservation` 的时间戳和 freshness 约束上层消费，避免无限使用旧目标。

### 9.5 TargetObservation 与产品视觉接口

`TargetObservation` 是 Detector 与 Tracker 的统一服务级感知接口，至少包含人物 bbox、归一化中心、`SEARCHING/DETECTED/TRACKING/CORRECTED/LOST/REACQUIRED` 状态、帧序号、采集时间戳、发布时间戳及 age/freshness。家属端 AI 视野、自动跟头和人物跟随消费同一观测；上层无需知道该 bbox 来自 Tinyissimo 检测还是 Sparse LK 跟踪。目标过期、丢失或摄像头故障时，控制策略停止继续使用旧框；是否运动仍由第 11 章的模式、租约与安全约束裁决。
家属端 AI 视野在授权会话中接收共享摄像头已有的 JPEG 与归一化 bbox/视觉元数据，由 Family Desktop 本地绘框。板端无需为叠框再次执行 JPEG 解码、绘制和编码，避免增加 2K0300 的图像处理负担。家属端退出 AI 视野只释放远程查看资源，本地 Vision 继续运行；视频通话则按媒体资源仲裁暂停或重置 Vision。

### 9.6 并发资源、性能验证与当前边界

端侧视觉以 Detector+Tracker 调度在有限算力下保持目标位置更新，并通过最新帧处理与观测时效避免旧画面积压。表 9-6 测量连续 CNN 检测吞吐，表 9-7 测量协同后的目标更新频率。Vision 与 KWS 在单核上竞争 CPU；经过kws的vad检测参数调整后，全部业务开启时，实机测试加载期 CPU 短时约 100%、随后维持在约 40%～80%，内存约 0.18 GB。cpu负载和内存资源占用健康，长期运行安全稳定。

后续验证重点包括无人画面误报、困难场景漏检、多人关联、完全遮挡、快速尺度变化，以及 CNN 同步推理造成的短时更新空档。V1.2 冻结集没有确认的纯无人样本，困难场景未检出时 Tracker 也无法建立目标。V1.3 已改善新域表现，后续训练需兼顾原有场景。

## 10 接口与数据设计

LongPet 的接口设计把“用户或算法提出的意图”与“外部系统确认的事实”分开。主程序不让页面、AI 结果或家属端直接改 SQLite、占用媒体设备或向 MCU 写串口，而是通过 Service、数据契约和受控传输边界协作。本章解释这些边界及失效语义；附录 B 给出接口方向、关键字段和可核对的协议索引。接口行为以当前代码及当前协议为准，历史报告中的计划项不自动视为已实现。

### 10.1 系统接口总体设计与边界

接口可按作用范围分为七类：板内 C++ Service/Port 与模型契约、KWS/音视频等进程间接口、主控—MCU 的 UART 接口、LongPet—Family Desktop 的 HTTP 与 WebSocket 接口、AI/天气第三方 HTTP 接口、相机/音频/显示/触摸设备接口，以及 SQLite/配置/模型文件接口。分类的目的不是增加层数，而是让每类接口都有明确的数据所有者、时效和失败结果。

```mermaid
flowchart LR
    UI[Qt 页面] --> APP[Controller 与 Service]
    FAMILY[Family Desktop] -->|HTTP 控制面| APP
    FAMILY <-->|WebSocket 画面 音频 远控| MEDIA[媒体与远控适配器]
    APP -->|业务读写| DATA[(SQLite 与配置)]
    APP -->|Provider 请求| CLOUD[AI 与天气服务]
    APP -->|设备能力| DEV[Camera Audio Display Input]
    APP -->|运动意图| UART[UART 协议] --> MCU[Motion MCU]
    MCU -->|STATUS 故障状态| UART
```

图 10-1 系统接口全景。HTTP 处理业务控制，WebSocket 承载实时流，UART 将主控意图交给独立 MCU；板内 Service 统一解释外部反馈。

数据流与控制流分离是本设计的关键。例如 AI 视野的 JPEG 帧仅用于显示，人物框元数据须附带新鲜度；人物跟随另由策略层决定是否形成运动命令。家属端控制通道与画面通道独立，避免画面排队拖慢 STOP。通话的 HTTP 信令只管理呼叫状态与媒体会话参数，双向 JPEG/PCM 走独立媒体连接。

### 10.2 LongPet—运动 MCU 串口接口

主控通过 115200 baud、8N1、无流控的双向 UART 与 Motion MCU 通信。主控侧 `MotionService` 生成模式、底盘、头部和视觉目标等运动意图，`EspSerialAdapter` 负责串口写入和状态解析；MCU 固件根据当前模式、参数与自身安全状态决定是否执行。协议是以行结束的 ASCII 命令，主要类别包括 `MODE`、`MOVE`、`HEAD`、`TARGET`、`FOLLOW_MOVE`、`STOP`、`PING` 和 `STATUS`。当前主程序 Adapter 实际发送 `STOP/MODE/MOVE/HEAD/TARGET/FOLLOW_MOVE/STATUS`；`PING` 属于 MCU 协议能力，不能据此宣称主程序定时发送 PING。

`TARGET` 表示人物相对画面中心的偏差和框面积，在 `HEAD_ONLY/FOLLOW` 中服务于头部目标；`FOLLOW_MOVE` 则是 `FOLLOW` 模式下独立的底盘意图，不能由目标像素面积自动推导。`PING` 只确认一般链路流量，不延长移动或目标时效。`STATUS` 回传 mode、motion、stop reason、fault、target、servo、可选 head_offset 和 imu 等事实；主控必须把串口可打开与 MCU 状态仍新鲜区分开。非法行不会成为有效控制；写入失败、状态过期或故障使上层退出控制路径，MCU 仍保有最终执行与停车裁决。完整命令参数及模式矩阵见附录 B.2，安全时效见第 11 章。

### 10.3 LongPet—Family Desktop 接口

设备端 `FamilyLinkController` 提供 `/api/v1` 下的 HTTP/JSON 接口，读取状态、设置、提醒和通话快照，并以短时会话入口开放 AI 视野和远控。家属端通过 Electron 主进程的 HTTP Adapter 发业务请求，渲染进程通过 preload/IPC 获取结果；连接信息只向 Renderer 返回 `hasToken` 摘要。当前连接弹窗仍在 Renderer 输入 Token，且成功后未立即清空输入 state，因此不能宣称长期凭据只存在主进程内存。设备端非回环监听要求配置 Bearer Token，未配置时不开放远程监听。当前 HTTP/WS 是受控局域网方案，不代表可直接公网暴露。

```mermaid
flowchart LR
    R[Family Desktop Renderer] --> IPC[preload / IPC]
    IPC --> MAIN[主进程 FamilyLink HTTP Adapter]
    MAIN -->|REST 状态 设置 提醒 模式 通话信令 会话申请| FL[LongPet FamilyLink]
    FL --> S[既有业务 Service]
    R <-->|AI 视野 WS: JPEG + vision_target| V[视觉流 Adapter]
    R <-->|通话 WS: JPEG + PCM + Control| C[媒体 Adapter]
    R <-->|远控 WS: chassis head stop + status| M[Motion 控制 Adapter]
```

图 10-2 FamilyLink 控制面与三个实时通道。流连接先通过 HTTP 取得临时会话，再用一次性凭据鉴权。

远程提醒和设置写入经过相同业务 Service 的校验及 revision 冲突检查，设备确认前不能显示“保存成功”。AI 视野用共享摄像头帧和 `vision_target` 元数据；旧框在失效或断流后隐藏。人工远控的底盘命令需要按短周期刷新，松开时先发 STOP；即使客户端无法送达 STOP，服务和 MCU 仍独立处理租约超时。音视频通话以 `callId + expectedRevision` 防止旧动作误作用于新呼叫，只有 `connected && mediaReady` 才视为媒体接通。各接口的路径、消息和错误列于附录 B.3。

### 10.4 AI Provider 与第三方服务接口

语音的 ASR、LLM、TTS 分别通过独立 Port 与配置接入：ASR 提交音频并返回文字，LLM 接收上下文并返回文本/流式片段或受限工具调用，TTS 接收文字并返回音频。`AiProviderFactory` 为每项能力单独选实现，因此三项可以使用不同 Provider、模型和凭据。当前代码有 OpenAI-compatible 接口及阿里云实现：兼容接口分别使用 `audio/transcriptions`、`chat/completions`、`audio/speech`；阿里云 ASR/TTS 使用其原生多模态接口，LLM 走兼容协议。`ProviderHttpClient` 处理网络超时、取消和 HTTP 错误，再把带 session ID 的结果交回业务层。自建 LoongArch AI Server 可经 Provider 契约接入，但当前资料不能把服务器端视为正式交付能力。

天气走独立的 `WeatherProviderPort`。当前 `QWeatherProvider` 向配置的专属 Host 发送当前天气 GET，请求头 `X-QW-Api-Key` 携带密钥，不把密钥放入 URL；`WeatherService` 处理缓存、新鲜度、重试和状态栏/语音可用数据。第三方接口失败不应自动变成页面异常或持久业务数据。方法、字段类别和错误归属见附录 B.4。

### 10.5 摄像头、音频、显示与平台硬件接口

主程序把相机视为 `CameraSourcePort`，由一个 `CameraCaptureAdapter` 管理采集进程、最新 JPEG 帧和多消费者 `acquire/release`；Vision、AI 视野和视频通话共用该来源。音频由 `VoiceAudioPort`、通话媒体 Port 及 `MediaSessionCoordinator` 协调，KWS 暂停被确认后才允许语音或通话开启麦克风；Adapter 使用平台媒体进程接入 ALSA/GStreamer。显示与触摸由 Qt 平台插件承接，状态和页面只消费抽象事件；系统状态服务汇聚设备可用性。串口设备访问仅在 Motion Adapter 中实现。

这些接口的设备名、模型路径和 Qt 平台参数由部署配置确定，不应写死在业务服务。设备缺失时返回能力不可用或相应故障，不用伪造摄像头帧、电池百分比或“已应用”设置。硬件连接与系统软件依赖分别见第 5、6 章；附录 B.6 只列当前配置解析规则。

### 10.6 本地业务数据与持久化

`DatabaseManager` 使用 SQLite 版本化 schema。默认数据库文件位于 Qt `AppLocalDataLocation` 下的 `longpet.db`，`LONGPET_DATABASE_PATH` 可覆盖；板端 service 可显式配置部署路径。当前 schema v1 只有 `schema_meta`、`reminders`、`reminder_events`、`care_events`、`settings` 五张表。提醒定义、触发/完成记录、饮水及其他关怀事件和用户设置是持久业务数据；网络状态、电源读数、当前通话、视觉观测、天气快照和运动状态属于运行期状态，不应凭产品设想增设不存在的数据表。

| 数据域 | 主要内容 | 生命周期 | 写入来源 | 主要读取方 |
| --- | --- | --- | --- | --- |
| 提醒与事件 | 提醒草稿、revision、触发/完成记录 | SQLite 持久化 | ReminderService 经 Repository | 本地页面、FamilyLink、照护汇总、语音工具 |
| 关怀事件 | 饮水、活动、交互事件及来源 | SQLite 持久化 | CareService 经 Repository | 今日关怀、本地与家属端状态 |
| 用户设置 | 音量、亮度、宠物风格等键值 | SQLite 持久化 | SettingsService 经 Repository | 本地 UI、FamilyLink、硬件应用链 |
| AI 与天气配置 | Provider、模型、请求参数及密钥 | 独立配置文件/环境覆盖 | 部署配置 | 组合根与 Provider 工厂 |
| 会话与观测 | AI 历史、通话、Vision、Motion、天气快照 | 进程内或当前连接；重启不继承 | 对应 Service/Adapter | 当前页面与会话消费者 |

表 10-1 数据所有权与生命周期。`care_events` 记录的活动或交互取决于实际写入入口，不等于已经有完整的运动/健康数据采集系统。

```mermaid
flowchart LR
    INTENT[本地 家属 语音意图] --> SERVICE[业务 Service 校验]
    SERVICE --> REPO[Repository] --> SQLITE[(SQLite 持久业务数据)]
    CONFIG[受限 INI 与环境配置] --> START[Application 启动时注入]
    START --> RUNTIME[会话 天气 视觉 运动运行态]
    SERVICE --> RUNTIME
    RUNTIME -- 进程退出后不继承 --> END[状态结束]
```

图 10-3 持久业务数据、启动配置与运行期状态的不同生命周期。

### 10.7 AI 对话、记忆与敏感数据

`VoiceInteractionService` 的历史是有限的进程内 `user/assistant` 文本对。默认配置 `historyTurns=4`，可配置范围为 0—20；会话流程正常收束且用户输入、助手回复非空时追加一对，即使 TTS 播放失败也可保留文字回复，并裁剪到最多 `2 × historyTurns` 条。请求会临时组合 system prompt、当前有效天气快照、历史及本轮用户输入。清空历史或重启进程后，这份上下文消失；目前没有长期记忆数据库、跨设备用户画像或云端同步机制。工具调用可通过 `VoiceToolRegistry` 修改提醒等持久业务数据，但工具执行本身不等于把整段对话持久化。因而应严格区分“提醒数据持久化”“有限对话上下文”和“长期记忆”。

音频、对话、第三方请求和家庭状态均可能包含敏感信息。Provider 密钥与 FamilyLink 长期凭据只作为受控配置进入相应进程；正式示例仅写 `<API_KEY>`、`<TOKEN>`、`<BASE_URL>` 等占位符。对话历史不写入当前 SQLite，并不能代替日志、网络和配置权限的隐私控制。

### 10.8 视觉观测、训练数据与模型元数据

Camera 帧带 JPEG、sequence、timestamp 与旋转信息；Detector/Tracker 的具体结果由 `VisionService` 归一为 `TargetObservation`。它包含 `present`、`fresh`、跟踪状态、帧序号、采集/发布时间、`ageMs`、画面尺寸、目标框与归一化中心/尺寸、置信度和诊断。目标缺失时不能凭上次 bbox 继续驱动界面或运动。家属端 AI 视野把可绘制观测序列化为 `[0,1]` 左上角 `x/y`、宽高 `w/h`；`present=false`、`fresh=false` 或 SEARCHING/LOST 时发送 `bbox:null`。自动跟头与人物跟随消费服务级观测，再经 MotionService 形成动作，而非消费 AI 视野的 JSON。

```mermaid
flowchart LR
    FRAME[CameraFrame JPEG sequence timestamp] --> DT[Detector / Tracker]
    DT --> OBS[TargetObservation present fresh age bbox state]
    OBS --> VIEW[AI 视野序列化与绘框]
    OBS --> HEAD[自动跟头策略]
    OBS --> FOLLOW[人物跟随策略]
    FOLLOW --> MOTION[MotionService]
    HEAD --> MOTION
```

图 10-4 视觉数据契约的消费者。训练样本、模型权重和模型元数据是另一类文件资产；运行期观测不写入业务 SQLite，训练过程见第 9 章。字段表见附录 B.5。

### 10.9 配置管理、令牌与隐私保护

配置分为非敏感运行参数、敏感凭据和模型/设备路径。AI 与天气 INI 由各自 Repository 读取，环境变量可覆盖 Provider、模型、超时、密钥等值；FamilyLink 监听地址、端口与 Token 由启动配置决定；数据库路径和视觉模型路径也可覆盖。板端 `longpet.service` 为服务指定运行用户、补充设备组和必要环境，密钥适合通过受限配置或 service drop-in 注入，不应进入源码、公开报告或截图。当前家属端 Electron 主进程 HTTP Adapter 持有后续请求所用的 Bearer Token，连接信息只回传 `hasToken`；但 Renderer 连接弹窗成功后未立即清空本地 Token state，仍有内存残留风险。当前代码未实现自动签发和持久化配对体系。

短时视觉、通话媒体与远控令牌只用于各自 WebSocket 会话，不应写入 URL、日志或长期业务表。受控局域网的 HTTP/WS 明文链路提供接口鉴权，却不提供传输加密；这属于当前部署边界，跨不可信网络时需要另行设计 HTTPS/WSS 或可信中转。附录 B.6 保留配置项名称和抽象路径，不列真实账号或密钥。

### 10.10 数据一致性、失效与降级处理

系统采用“过期即失效”的接口语义，而非让旧数据静默冒充现况。提醒与设置写入使用 revision 检测并发修改；语音请求以 session ID 拦截取消后的 ASR/LLM/TTS 回调；天气快照保留来源与更新时间并标记 stale；视觉目标由 `present/fresh/ageMs` 及状态约束；家属端连接断开后不继续展示在线事实或旧框；通话依 `callId/revision/mediaReady` 区分信令成功与媒体接通；MotionService 同时检查 UART 与 MCU 状态，失联时撤销控制权。

```mermaid
flowchart LR
    INPUT[外部结果或用户命令] --> CHECK{身份 版本 时效 能力有效?}
    CHECK -->|是| APPLY[更新当前状态或执行受控动作]
    CHECK -->|否| REJECT[拒绝 丢弃旧回调 或标记不可用]
    REJECT --> UI[向本地或家属端反馈]
    APPLY --> UI
```

图 10-5 接口结果进入产品状态前的有效性门控。不同接口的具体错误与恢复方式见附录 B.7；该图不替代第 11 章的 MCU 失效安全设计。

## 11 运动控制与系统安全设计

### 11.1 设计目标与安全原则

LongPet 是具备摄像头、网络连接和可运动底盘的适老产品。运动控制的目标不是让底盘“能动”，而是使它**受控、安全、可恢复地动**。系统遵循失效优先停车原则：视觉误检、远控端失焦、串口断线或主控任务阻塞时，底盘不得持续执行上一条运动命令。系统在命令超时、故障、模式冲突或控制源丢失时停车；恢复运动须重新满足模式、命令和时效条件。通信在线与运动授权分别校验。

### 11.2 双处理器运动控制架构

运动安全采用**上层策略约束 + MCU 独立执行保护**。龙芯 2K0300 主控负责远控接入、视觉感知、运动策略和控制权仲裁。ESP32-S3 运动 MCU 负责模式与命令校验、时效检查、传感器故障处理和输出撤销。MCU 与电机直接相连，即使 Linux 应用层失去响应，也能独立停止底盘。

```mermaid
flowchart LR
    A[家属端按住操控 / 模式选择] --> B[LoongArch 主控 LongPet<br/>会话鉴权、控制权仲裁]
    V[Vision 目标观测] --> C[自动视觉运动策略<br/>目标时效、头身与距离决策]
    C --> D[MotionService<br/>模式与命令门控]
    B --> D
    D --> E[UART Motion Protocol V2]
    E --> F[ESP32-S3<br/>严格解析、模式白名单、独立超时、故障锁存]
    F --> G[头部舵机]
    F --> H[TB6612 驱动 / 四轮底盘]
    I[编码器 / IMU] --> F
    F -- STATUS / FAULT --> D
    D -- 状态 / 拒绝原因 --> B
```

图 11-1 双处理器分层控制与安全边界。网络和视觉侧通过 MCU 控制电机；主控失效时，MCU 的租约与链路超时仍能使持续底盘动作停止。

### 11.3 运动执行链路

`MotionService` 集中管理串口、家属端会话、视觉模式和 MCU 状态。`AutomaticHeadTrackingService` 将 `TargetObservation` 的画面偏差转为 `TARGET`；人物跟随时，再结合物理头偏和归一化人物框高度形成 `FOLLOW_MOVE`。Family Desktop 通过 FamilyLink 申请远控会话并发送底盘、头部控制意图。命令经 `MotionService` 和 UART Motion Protocol V2 到达 ESP32-S3，由 MCU 控制舵机、TB6612 四轮麦克纳姆底盘、编码器 PID 与 IMU 航向反馈，并通过双向 UART 返回 `STATUS` 和故障信息。

MCU 启动时执行 `BeginSafe`：先将两组 TB6612 的 STBY 置低，再初始化方向和 PWM 输出，初始模式为 `SAFE`。头部位置受软件脉宽限制；`HEAD` 与 `TARGET` 使用同一左右方向映射。自动跟头设置死区和单次转动幅度上限。

### 11.4 控制模式与权限

MCU 设置 `SAFE`、`HEAD_ONLY`、`MANUAL`、`FOLLOW` 四种模式。切换模式时先停车，清除底盘动作、手动与跟随租约、目标有效性和转向瞬态，再进入新模式。重复发送当前 `MODE` 不清除现有租约；模式切换也不解除故障锁存。

| 模式 | 主要控制来源 | 允许动作 | 禁止动作 | 典型退出或停车条件 |
|---|---|---|---|---|
| `SAFE` | 主控安全管理 | `MODE`、`STOP`、`PING`、`STATUS` | 所有主动底盘及头部命令 | 上电保持停止；显式切换模式前仍不运动 |
| `HEAD_ONLY` | 自动头部跟踪 | `TARGET` 修正头部及通用命令 | `MOVE`、`FOLLOW_MOVE`；目标帧驱动轮组 | 目标丢失/过期、模式切换、故障 |
| `MANUAL` | 已获控制权的家属端 | `HEAD`；持续刷新的 `MOVE` 驱动底盘；通用命令 | `TARGET`、`FOLLOW_MOVE` | 松开/退出主动 `STOP`，链路或 `MOVE` 租约到期、模式切换、故障 |
| `FOLLOW` | LongPet 视觉跟随策略 | `TARGET` 跟头；独立续租的 `FOLLOW_MOVE` 前进、原地旋转或停止；通用命令 | 手动 `MOVE`；`FOLLOW_MOVE` 后退、平移及弧线动作 | 目标丢失/过期、跟随租约或链路到期、模式切换、故障 |

表 11-1 MCU 模式与权限矩阵。各模式均接受诊断、停车和模式命令；`STOP` 立即撤销底盘驱动。协议保留 `SHIFT_LEFT`/`SHIFT_RIGHT` 解析，但当前版本和家属端均未开放左右平移。旧三整数目标格式仅兼容 `TARGET` 输入，不触发按目标面积自动驱动底盘。

### 11.5 UART 协议与输入校验

主控与 MCU 使用逐行 ASCII 串口协议。MCU 使用固定 64 字节行缓冲，限制每次主循环的读取量，并在收到完整行后解析。非可打印 ASCII、控制字符和超长行整行丢弃；未知命令、错误模式、额外字段、整数溢出及越界参数均被拒绝。解析仅接受约定的空格分隔，速度、舵机步长和目标几何量不得越界。

只有格式正确且当前模式允许的完整命令才刷新通用链路时戳；非法输入既不执行，也不刷新运动或目标时效。主控同样校验命令并检查 `STATUS`。V1.3 测试中，半包、超长行、乱码、特殊关键词组合和越界参数复测均通过，未再复现此前的乱码卡死。

### 11.6 多级时效与运动租约

固件分别记录通用链路、手动动作、自动跟随动作和视觉目标的时戳。四项超时当前均为 500 ms，但由各自的有效输入独立刷新。

| 安全时钟 | 仅由什么刷新 | 到期后的含义 |
|---|---|---|
| General Link | 任意被接受的合法命令，包括 `PING`、`STATUS` | 活动底盘无有效链路，停车 |
| MANUAL Motion Lease | `MANUAL` 中合法 `MOVE` | 手动动作不再被持续授权，停车 |
| FOLLOW Motion Lease | `FOLLOW` 中合法、非停止的 `FOLLOW_MOVE` | 自动底盘动作不再被新策略结果授权，停车 |
| TARGET Freshness | `HEAD_ONLY`/`FOLLOW` 中合法目标帧 | 当前有效人物目标过期，清目标并停车 |

表 11-2 四类独立时效约束。`PING`/`STATUS` 仅续通用链路，`TARGET` 不续跟随动作租约；`FOLLOW_MOVE STOP` 立即停车且不建立新租约。目标过期检查仅针对已取得的有效目标。活动底盘完全失联时通常记录 `LINK_TIMEOUT`；链路仍由 `PING` 保持、动作却未刷新时，记录 `MANUAL_COMMAND_TIMEOUT` 或 `FOLLOW_COMMAND_TIMEOUT`。两种情况均停车。

家属端按住底盘按钮时周期发送控制意图，LongPet 仅在远控租约有效时重发 `MOVE`。视觉侧须对新目标观测重新检查时效、模式、头偏和距离，才发送下一条 `FOLLOW_MOVE`。UART 断线时主控尝试停车；命令无法送达时由 MCU 超时停车。

### 11.7 统一停车、故障锁存与恢复

停止请求、模式切换、目标丢失、链路或动作租约到期属于可恢复停车。IMU 初始化或运行时读取失败、活动运动控制周期超限、固件定角转向超时则触发故障锁存。控制周期目标为 100 ms；活动运动间隔超过 250 ms 时，固件报 `CONTROL_OVERRUN` 并停车。定角转向有固件超时保护，但对外 `MOVE` 尚未开放定角转向指令。

```mermaid
flowchart TD
    A[STOP / 切模式 / 目标丢失 / 链路或租约超时] --> S[setStopped]
    B[IMU 异常 / 控制周期超限 / 定角转向超时] --> L[故障锁存并记录首次 FAULT]
    L --> S
    S --> R[Run::Stop]
    R --> O[STBY LOW → PWM 归零、方向撤销<br/>编码器计数、转向与 PID 瞬态清理]
    L --> X[拒绝后续 MOVE / TARGET / 主动 HEAD<br/>直至 MCU 复位或重新上电]
```

图 11-2 统一停车与故障锁存路径。`setStopped` 清除底盘模式、速度及手动、跟随租约，并调用 `Run::Stop`；目标有效位由目标丢失、故障或模式切换路径清除。`Run::Stop` 先撤销 TB6612 STBY，再将 PWM 置零、方向脚置低，清除编码器计数、转向与 PID 瞬态；头部舵机保持当前位置。故障锁存后，`PING`、`STATUS`、`STOP` 和 `MODE` 仍可用于诊断或停车，恢复主动控制须复位或重新上电并排查故障。

`STATUS` 只有一个 `stopReason` 字段。锁存后发送 `STOP` 或切换模式可能覆盖最近的停车原因，但 `fault=1` 保留；排障时应查看首次 `[FAULT]` 记录。

### 11.8 家庭远控与控制权仲裁

Family Desktop 发起远控会话，LongPet 校验会话身份、串口状态、MCU 在线状态及故障状态，同一时间只允许一名远控控制者。进入 `MANUAL` 前，`MotionService` 预留手动控制权、释放自动控制，再执行 `STOP → MODE MANUAL → STATUS`；退出时执行 `STOP → MODE SAFE`。MCU 失联、模式意外变化、故障或串口断线时，主控撤销控制权。长期 Bearer Token 保留在 Electron 主进程，渲染进程使用短时运动会话令牌。当前明文 HTTP/WS 控制端口仅用于局域网，不应直接暴露公网。

底盘控制按住时持续刷新，按钮或键盘释放、页面失焦、隐藏、退出或断线时，家属端发送停止命令并停止刷新；LongPet 远控租约和 MCU 手动租约提供超时停车。头部控制按住时发送有限步进，松开后保持当前位置。界面仅在 MCU 处于 `MANUAL` 且无故障时开放操控。

人工遥控优先于自动视觉运动，视频通话也会暂停相关自动运动。远控或通话结束后，人物跟随须由用户重新开启；头部自动跟踪可在开关有效、视觉恢复且安全条件满足时重新进入 `HEAD_ONLY`，并等待新目标。

### 11.9 视觉跟随安全控制

`HEAD_ONLY` 模式下，`TARGET` 只驱动头部舵机，不驱动轮组。`FOLLOW` 模式下，`TARGET` 更新头部及目标时效；目标稳定、Motion 状态有效时，LongPet 读取 MCU 报告的物理 `head_offset`，判断是否需要原地转动机身，再根据人物框归一化高度的 FAR/GOOD/NEAR 分类决定是否前进。画面中心偏差 `dx` 不直接用于底盘驱动。

头身对齐且分类为 FAR 时，底盘低速前进；GOOD 或 NEAR 时停车，不自动后退。头偏方向变化时先停车并重新确认；目标丢失或过期时停车、清目标，重获后重新确认稳定性。MCU 仅在 `FOLLOW` 模式接受 `FOLLOW_MOVE`，且拒绝后退、平移和弧线动作。视觉观测中断时，上层停止续租，由 MCU 在租约到期后停车。V1.3 测试覆盖人物跟随硬件闭环、距离阈值、独立租约与失联停车，包括台架、悬空轮组和低速落地验证。人物框高度仅是距离代理；系统尚无 SLAM、自主导航及障碍、悬崖检测能力。

### 11.10 安全设计验证与证据追踪

《LongPet 产品运动功能测试报告_2026-09-13_V1.3》附录 A 共列 58 项：56 项通过，左右平移两项（15、16 号）主动暂缓，待验证项为 0。表 11-3 列出运动安全设计与测试编号的对应关系。

| 安全设计机制 | V1.3 测试编号 | 当前结论 |
|---|---|---|
| 上电默认 `SAFE`、底盘不自启 | 1–2 | 通过 |
| 半包、超长行、乱码与异常参数拒绝；压力复测未再卡死 | 23–27（含 25 号压力复测） | 通过 |
| `SAFE` 拒绝 `MOVE`；`HEAD_ONLY` 允许跟头但轮组阻断 | 28–30 | 通过 |
| 模式切换前停车并清旧运动/租约 | 32、55 | 通过 |
| 运动中 `STOP` 与随后重新合法控制 | 33–34 | 通过 |
| 单条 `MOVE` 后静默，通用链路到期停车 | 36 | 通过 |
| `PING`/`STATUS` 不续 MANUAL `MOVE` 租约 | 37 | 通过 |
| UART 断开停车及重连后的受控恢复 | 38–39、56–57 | 通过 |
| IMU 故障、控制周期超限锁存，拒绝动作，复位后恢复 | 40–43 | 通过 |
| 目标过期或丢失清目标；`TARGET` 不直接驱动 FOLLOW 底盘 | 46–48 | 通过 |
| 非 FOLLOW 模式拒绝 `FOLLOW_MOVE`；FOLLOW 禁止后退/平移 | 49、54 | 通过 |
| `TARGET`、`PING`/`STATUS` 不续 FOLLOW 独立租约 | 50–51 | 通过 |
| `FOLLOW_MOVE STOP` 立即撤销运动并清租约 | 53 | 通过 |
| V2.3 人物跟随硬件闭环及距离阈值 | 报告正文 5.5、5.6；附录 A 48–58 | 通过 |

表 11-3 安全设计与 V1.3 测试证据追踪。测试编号见报告附录 A；人物跟随硬件闭环还对应报告正文 5.5 的实机结果。

### 11.11 版本边界与后续优化

`SHIFT_LEFT`/`SHIFT_RIGHT` 横向平移暂缓交付。`speed` 是内部控制量，尚未标定为 cm/s；精确速度、转角误差、停车距离及 `stopReason` 的诊断可读性仍需改进。

`Run::Stop` 将 TB6612 的 STBY 置低，使电机进入高阻自由滑行状态；实际停车距离受速度、惯性、地面和负载影响。现阶段运动功能须在有人看护的低速环境中使用，人物框高度不能充当碰撞检测。后续应增加物理急停、驱动默认禁能、限流与供电保护、电源切断路径、外部 STBY 下拉及障碍、悬崖感知，并量化速度、转角和停距。

## 12 典型业务流程

### 12.1 开机、自检、登录/连接与服务就绪

### 12.2 老人端提醒创建、触发与完成

### 12.3 在线语音对话与工具调用

### 12.4 断网后的离线基础陪伴

### 12.5 视觉人物发现、自动跟头与目标丢失

### 12.6 家属端连接、状态查看与提醒管理

### 12.7 视频/语音通话

### 12.8 远程手动控制与停止

### 12.9 人物跟随启停与安全停车

### 12.10 故障发生、降级与恢复

## 13 非功能需求落实与工程化设计

### 13.1 性能预算、响应链路与资源监测

### 13.2 视觉与语音并发资源调度

### 13.3 适老可用性与交互一致性

### 13.4 稳定性、进程隔离与服务恢复

### 13.5 网络、接口、令牌与隐私安全

### 13.6 日志、诊断与可观测性

### 13.7 自动化测试、实机验证与可复现性

### 13.8 第三方组件、模型来源与许可管理

## 14 构建、部署、发布与运营计划

### 14.1 四仓库构建链与交付物关系

### 14.2 龙芯系统、应用、家属端与 MCU 部署概览

### 14.3 配置、首次启动与验收检查点

### 14.4 版本基线、发布包与完整性校验

### 14.5 升级、备份、回退与故障恢复

### 14.6 原型试用、使用支持与维护计划

### 14.7 后续运营、反馈收集与迭代计划

## 15 关键技术难点与方案权衡

### 15.1 2K0300 无 LSX/LASX 的软件兼容问题

### 15.2 ONNX Runtime 从可加载到数值正确的修复

### 15.3 基础系统稳定性与 Hybrid Rootfs 取舍

### 15.4 低算力视觉模型、域适配与 Detector/Tracker 协同

### 15.5 语音在线/离线链路与资源竞争

### 15.6 头身协调、距离代理与无地图跟随边界

### 15.7 远程运动控制的时效性与失效安全

## 16 技术创新与应用价值

### 16.1 LoongArch 低算力平台的 AI 适配实践

### 16.2 可校验的 Hybrid Rootfs 交付方法

### 16.3 面向实拍场景的视觉训练与分层推理

### 16.4 语音、视觉与家属端协同的适老体验

### 16.5 多层运动安全机制与可解释边界

### 16.6 应用价值、推广条件与市场潜力

## 17 当前成果、限制与后续规划

### 17.1 交付基线与已验证成果

### 17.2 已实现但验证有限的能力

### 17.3 实验性能力、接口预留与未完成功能

### 17.4 已知性能、环境与硬件限制

### 17.5 后续测试、工程化与产品化路线

## 18 总结

### 18.1 产品设计总结

### 18.2 需求、技术方案与证据的对应关系

## 附录

### 附录 A 需求—模块—测试追踪矩阵

### 附录 B 系统接口索引

附录 B 以当前实现为基线，给出接口族、方向、关键字段、失败语义和 Source of Truth（下称 SoT）。路径均为相应工程内的相对路径；`LongPet:`、`Family:`、`MCU:` 分别指主程序、Family Desktop 和 Motion MCU 工程。正式协议与当前代码有差异时，运行行为以当前代码为准，协议修订应同步跟进。示例中的 `<BASE_URL>`、`<API_KEY>`、`<TOKEN>`、`<DEVICE_ID>` 都是占位符。

#### B.1 接口总览

| ID | 接口族 | 发送方 → 接收方 | 传输/机制 | 主要用途 | SoT |
| --- | --- | --- | --- | --- | --- |
| IF-BOARD-01 | 本地业务请求与状态 | Qt 页面 → AppController → Service | Qt 信号/方法与模型 | 提醒、关怀、设置、通话、语音 | LongPet: `src/app/AppController.cpp`、`src/services/` |
| IF-DATA-01 | 业务持久化 | Service → Repository → SQLite | Qt SQL | 提醒、事件、设置 | LongPet: `src/data/DatabaseManager.cpp`、各 Repository |
| IF-PROC-01 | KWS bridge | KwsProcessAdapter ↔ 独立 bridge | QProcess 标准输入/输出 | 唤醒、暂停确认、恢复、异常退出 | LongPet: `src/platform/KwsProcessAdapter.cpp`、`deploy/kws/` |
| IF-MOTION-01 | Motion UART V2 | MotionService → MCU；MCU → MotionService | ASCII UART，双向 | 运动命令、状态与故障 | MCU: `docs/motion-protocol-v2.md`、`xiao_che/xiao_che.ino`；LongPet: `src/platform/EspMotionProtocol.cpp`、`EspSerialAdapter.cpp` |
| IF-FAMILY-01 | FamilyLink REST | Family Desktop 主进程 ↔ LongPet | HTTP/JSON | 状态、设置、提醒、通话信令、会话签发 | LongPet: `src/app/FamilyLinkController.cpp`；Family: `docs/FAMILY_LINK_API.md` |
| IF-FAMILY-02 | AI 视野流 | LongPet → Family Desktop Renderer | WebSocket，LPMF v1 | JPEG 与人物观测元数据 | LongPet: `src/platform/FamilyVisionStreamAdapter.cpp`、`FamilyVisionProtocol.cpp`；LongPet: `docs/LongPet-Vision-V2.1-Family-AI-View-Report.md` |
| IF-FAMILY-03 | 通话媒体 | LongPet ↔ Family Desktop Renderer | WebSocket，LPMF v1 | 双向 JPEG/PCM、会话控制 | LongPet: `src/platform/VideoCallMediaAdapter.cpp`、`src/model/MediaFrameProtocol.cpp`；Family: `docs/VIDEO_CALL_MEDIA_PROTOCOL.md` |
| IF-FAMILY-04 | 人工远控 | Family Desktop Renderer ↔ MotionService | WebSocket，LPMF v1 Control | 底盘、头部、STOP 和状态 | LongPet: `src/platform/FamilyMotionControlAdapter.cpp`；Family: `docs/FAMILY_LINK_API.md` 第 8 节 |
| IF-FAMILY-05 | 自动视觉运动模式 | Family Desktop 主进程 ↔ FamilyLinkService | HTTP/JSON | HEAD_ONLY、PERSON_FOLLOW 与禁用 | LongPet: `src/app/FamilyLinkController.cpp`；Family: `docs/FAMILY_LINK_API.md` 第 9、12 节 |
| IF-AI-01 | ASR / LLM / TTS | VoiceInteractionService ↔ Provider | Port + HTTP | 语音转写、回答、合成 | LongPet: `src/services/VoiceInteractionPorts.h`、`src/platform/AiProviderFactory.cpp`、各 Provider |
| IF-AI-02 | 当前天气 | WeatherService ↔ QWeatherProvider | Port + HTTPS GET | 当前天气快照 | LongPet: `src/services/WeatherPorts.h`、`src/platform/QWeatherProvider.cpp` |
| IF-VISION-01 | 目标观测 | VisionService → AI 视野/自动控制 | Qt 信号与 `TargetObservation` | 统一人物状态与时效 | LongPet: `src/model/VisionModels.h`、`src/services/VisionService.cpp` |
| IF-DEVICE-01 | 相机/音频/显示/串口 | Adapter ↔ OS 设备 | GStreamer、ALSA、Qt 平台、UART | 平台能力接入 | LongPet: `src/platform/`、`deploy/longpet.service` |
| IF-CONFIG-01 | 配置与模型 | Application/Adapter → 配置/模型文件 | INI、环境变量、文件系统 | Provider、路径、能力开关 | LongPet: `src/app/Application.cpp`、`src/data/*ConfigRepository.cpp`、`deploy/配置说明.md` |

表 B-1 系统接口矩阵。Family Desktop 的早期 `VIDEO_CALL_SIGNALING_REPORT.md` 只描述信令阶段；媒体行为以当前代码和 `VIDEO_CALL_MEDIA_PROTOCOL.md` 为准。FamilyLink 协议中的“后续事件接口”不是当前已实现接口，不列入矩阵。

#### B.2 Motion UART 接口

通道为主控串口 ↔ MCU `Serial1`，115200 baud、8N1、无流控。MCU 接受 CR、LF 或 CRLF 行结束；主控当前以 LF 发送 ASCII 行。命令与状态/诊断共用双向 UART。下表是协议能力，未必表示主程序会主动发送每一种命令。

| Command | 方向 | 允许模式 | 主要参数 | 用途与边界 |
| --- | --- | --- | --- | --- |
| `MODE <mode>` | 主控 → MCU | 模式切换入口 | `SAFE`、`HEAD_ONLY`、`MANUAL`、`FOLLOW` | 切换执行语义；重复当前模式是 no-op |
| `STOP` | 主控 → MCU | 全模式 | 无 | 统一停车；不自动使头部回中 |
| `PING` | 主控 → MCU | 全模式 | 无 | 协议支持的一般链路探测；当前 LongPet Adapter 无发送方法，不续租移动或目标 |
| `STATUS` | 主控 → MCU | 全模式 | 无 | 请求一条 `[STATUS]`；当前 MotionService 周期请求 |
| `MOVE <direction> <speed>` | 主控 → MCU | `MANUAL` | `FORWARD/BACKWARD/ROTATE_LEFT/ROTATE_RIGHT/SHIFT_LEFT/SHIFT_RIGHT`，速度 1—100 | 手动底盘命令；协议有 SHIFT，但当前 LongPet 上层不开放 SHIFT |
| `HEAD <action> [step]` | 主控 → MCU | `MANUAL` | `LEFT/RIGHT`，步长 1—100 μs；或 `CENTER` | 人工头部步进/回中；协议可省步长，主程序发送明确步长 |
| `TARGET <dx> <dy> <area>` | 主控 → MCU | `HEAD_ONLY`、`FOLLOW` | `dx/dy` 为 −4096—4096 px；`area` 为 0—16777216 px² | 人物相对画面中心的目标；`area=0` 表示目标丢失，只控制头部目标语义 |
| `FOLLOW_MOVE <direction> <speed>` / `FOLLOW_MOVE STOP` | 主控 → MCU | `FOLLOW` | `FORWARD/ROTATE_LEFT/ROTATE_RIGHT`、速度 1—100；或 STOP | 独立的跟随底盘意图；不接受后退、平移 |

表 B-2 Motion UART V2 主要命令。MCU 对非法字符、额外字段、未知命令、越界整数及当前模式不允许的命令拒绝整行，拒绝行不刷新超时。主控侧序列化也拒绝其不支持的方向和值。该协议不是每条命令均有单独 ACK；后续 `STATUS`、诊断及链路时效用于确认状态。模式、watchdog 和故障处置以 MCU: `docs/motion-protocol-v2.md` 及第 11 章为准。

| `[STATUS]` 字段 | 主控解释 | 数据失效时的处理 |
| --- | --- | --- |
| `mode`、`motion`、`stop` | 当前 MCU 模式、底盘状态、停车原因 | 不以主控最后发送的命令代替 MCU 报告 |
| `fault`、`target` | 故障锁存、当前是否有有效目标 | 故障或目标丢失时不得继续按旧状态运动 |
| `servo` | 当前舵机脉宽，单位 μs | 只作为反馈，不由页面直接写值 |
| `head_offset` | 可选 V2.3 物理头偏，单位 μs；主控将其规范为负左、正右 | 缺失时人物跟随不可假定头部已对齐 |
| `imu` | IMU 可用性标志 | 不等于自主导航已实现 |

表 B-3 MCU STATUS 的产品级解释。主控解析器允许缺少 `head_offset`，因此消费者还要检查 `headOffsetAvailable`；`uartAvailable` 与 `mcuOnline` 是主控运行期状态，不是 UART 原始 `[STATUS]` 字段。

#### B.3 FamilyLink / Family Desktop 接口

FamilyLink REST 使用 UTF-8 JSON，路径前缀 `/api/v1`。设备默认回环监听；远程监听需配置长期 Bearer Token，请求头为 `Authorization: Bearer <TOKEN>`。家属端由 Electron 主进程 HTTP Adapter 发后续请求，Renderer 经 preload/IPC 调用并只接收连接的 `hasToken` 摘要；但连接弹窗输入 Token 后，成功路径目前未清空 Renderer 本地 state。时间使用 UTC ISO 8601，写操作的 revision 或 `callId` 应以最近设备快照为准。

| Interface | 方向/传输 | 请求或事件与核心字段 | 失败语义 / SoT |
| --- | --- | --- | --- |
| `GET /status` | 家属端 → 设备，HTTP | `apiVersion`、capabilities、device、system、care | 连接失败视为离线；LongPet: `FamilyLinkController.cpp`；Family: `FAMILY_LINK_API.md` |
| `GET /settings`；`PATCH /settings` | 家属端 ↔ 设备，HTTP | `volume`、`brightness`、`petStyle`、`expectedRevision` | 修订冲突 409，能力不可用 503；同上 |
| `GET /reminders`；`POST /reminders` | 家属端 ↔ 设备，HTTP | `items`；草稿的 type、title、timeOfDay、scheduledDate、repeatRule、enabled | 校验失败或能力不可用应显式返回；同上 |
| `PUT /reminders/{id}`；`DELETE /reminders/{id}?expectedRevision=...` | 家属端 ↔ 设备，HTTP | 完整草稿及 `expectedRevision`；删除以查询参数携带版本 | 不匹配 409，不能覆盖新数据；同上 |
| `GET/POST /video-call`；`POST /video-call/actions` | 家属端 ↔ 设备，HTTP | `mode`；`callId`、`expectedRevision`、`action`；快照含 `mediaPort/mediaToken/mediaReady` | 已占用、旧 callId 或 revision 被拒绝；LongPet: `VideoCallService.cpp`、`FamilyLinkController.cpp` |
| `POST /vision-monitor/sessions` | 家属端 → 设备，HTTP | 返回 `sessionId/sessionToken/port/protocolVersion/frameRate/expiresAt` | 单 viewer 忙时 409，未启动 503；LongPet: `FamilyLinkController.cpp`、`FamilyVisionStreamAdapter.cpp` |
| `POST /motion-control/sessions` | 家属端 → 设备，HTTP | 返回 `sessionId/sessionToken/port/protocolVersion/refreshIntervalMs/leaseTimeoutMs/expiresAt` | 已占用 409，服务不可用 503；LongPet: `FamilyLinkController.cpp`、`FamilyMotionControlAdapter.cpp` |
| `GET/PUT /automatic-head-tracking` | 家属端 ↔ 设备，HTTP | 兼容接口；`enabled` 与当前 `active/state` | 不具备能力时 503；LongPet: `FamilyLinkController.cpp` |
| `GET/PUT /automatic-tracking` | 家属端 ↔ 设备，HTTP | `mode=DISABLED/HEAD_ONLY/PERSON_FOLLOW`；返回 followState、distanceClass、targetAgeMs、headOffset 等 | 条件不满足时拒绝模式切换；LongPet: `FamilyLinkController.cpp`；Family: `FAMILY_LINK_API.md` 第 12 节 |

表 B-4 当前 REST 接口。表中路径均在 `/api/v1` 后拼接；准确 JSON 结构和 HTTP 状态以 LongPet 当前控制器实现为准，Family: `docs/FAMILY_LINK_API.md` 为对端联调规范。计划中的 `/api/v1/events` WebSocket 尚未实现。

| 实时接口 | 建立方式与方向 | LPMF 流/Control 内容 | 断开或无效时 |
| --- | --- | --- | --- |
| `/vision-monitor/v1`，通常端口 8789 | HTTP 签发短时会话；Renderer → 设备首帧 `authenticate`；设备 → Renderer | `DeviceVideo(1)` JPEG；`Control(5)` 的 `stream_started`、`vision_target`、`error` | 不认证不开放相机；断开隐藏旧帧和框；SoT: LongPet `FamilyVisionStreamAdapter.cpp`、`FamilyVisionProtocol.cpp` |
| `/media/v1`，通常端口 8788 | 通话快照给出 `mediaPort/mediaToken`；双方 WebSocket | `DeviceVideo(1)`、`FamilyVideo(2)` JPEG；`DeviceAudio(3)`、`FamilyAudio(4)` PCM；`Control(5)` 鉴权及媒体状态 | 旧 callId/Token、媒体失败或断开使通话结束；SoT: LongPet `VideoCallMediaAdapter.cpp`；Family `VIDEO_CALL_MEDIA_PROTOCOL.md` |
| `/motion-control/v1`，通常端口 8790 | HTTP 签发短时会话；Renderer → 设备首帧 `authenticate`；双向状态 | `Control(5)` JSON：`chassis`、`head`、`stop`、`release`；设备返回 `control_started`、`motion_status`、`error` | 断开撤销控制；MOVE 不再刷新则停车；SoT: LongPet `FamilyMotionControlAdapter.cpp`；Family `FAMILY_LINK_API.md` 第 8 节 |

表 B-5 三种 WebSocket 通道。端口可由服务配置或快照决定，客户端按已配置设备 URL 的主机及返回端口推导地址，不把令牌放在 URL。三者复用 `MediaFrameProtocol`：每个 WebSocket Binary Message 为一个 LPMF 帧，24 字节大端帧头依次为 `LPMF` magic(4)、version(1)、streamType(1)、flags(2)、sequence(4)、Unix 微秒时间戳(8)、payloadLength(4)；payload 最大 2 MiB。Control 的 payload 为 UTF-8 JSON。通话媒体的当前设计详见 Family: `docs/VIDEO_CALL_MEDIA_PROTOCOL.md`。该文档约定 `/media/v1`，但当前 `VideoCallMediaAdapter` 只校验会话内 `callId` 与媒体 Token，尚未校验 WebSocket 请求路径；视觉和远控 Adapter 已校验各自路径。AI 视野与远控的具体鉴权字段以对应 Adapter 和测试为准。

视觉与远控首个 Control 消息使用 `type=authenticate`、`protocol_version`、`session_id`、`token`；通话媒体首个 Control 消息使用 `type=authenticate`、`callId`、`token`。视觉 Control 元数据以 `type=vision_target` 携带帧序号、新鲜度、状态与可空 bbox。远控 `chassis` 需 `direction/speed`，`head` 需 `action/step_us`（回中除外），`stop` 无参数；状态反馈以 `motion_status` 携带 `uart_available/mcu_online/fault/mode/motion/updated_at` 等。通话音频为 PCM S16_LE、16 kHz、单声道、20 ms 帧；视频为 JPEG。通话、视觉和远控的短时会话不可互换。

#### B.4 AI Provider 与天气接口

| 能力/实现 | 方法与路径类别 | 请求核心字段 | 响应核心字段 | 超时/错误与 SoT |
| --- | --- | --- | --- | --- |
| OpenAI-compatible ASR | `POST <BASE_URL>/audio/transcriptions`，multipart | WAV `file`、`model`、可选 `language`、`response_format=json` | `text` | session ID 对应的成功/失败信号；LongPet: `OpenAiCompatibleProviders.cpp`、`ProviderHttpClient.cpp` |
| 阿里云 ASR | `POST <BASE_URL>/services/aigc/multimodal-generation/generation` | `model`、含 WAV Data URI 的 `input.messages`、`parameters` | 转写文本 | 与兼容协议不同；LongPet: `AliyunProviders.cpp` |
| OpenAI-compatible LLM | `POST <BASE_URL>/chat/completions` | `model`、`messages`、可选 `tools` 与流式参数 | 文本、SSE delta、tool calls/finish reason | 片段与工具参数校验，取消旧 session；LongPet: `OpenAiCompatibleProviders.cpp` |
| OpenAI-compatible TTS | `POST <BASE_URL>/audio/speech` | `model`、`input`、`voice` | 音频字节 | 失败可保留文字回答；LongPet: `OpenAiCompatibleProviders.cpp` |
| 阿里云 TTS | `POST <BASE_URL>/services/aigc/multimodal-generation/generation` 或 `.../services/audio/tts/SpeechSynthesizer`，按模型系列选择 | `model`、文本及语音参数 | `output.audio.url`，再下载音频字节 | 不与 ASR 共用固定响应解析；LongPet: `AliyunProviders.cpp` |
| 当前天气 | `GET <BASE_URL>/weather/v1/current/{latitude}/{longitude}` | 可选语言；请求头 `X-QW-Api-Key: <API_KEY>` | 条件、温度、湿度等当前天气 JSON | 独立超时/错误码，缓存标记 stale；LongPet: `QWeatherProvider.cpp`、`WeatherService.cpp` |

表 B-6 Provider 接口类别。ASR/LLM/TTS 的 Provider、Base URL、模型与 Key 可分别配置；`AiProviderFactory.cpp` 决定实际实现，不能从配置示例反推正式部署使用哪家供应商。网络、鉴权、限流、超时和无效响应被归入能力错误，不作为成功文本处理。自建 LoongArch AI Server 在 Provider 契约内可替换，但当前不是已交付服务器接口。

#### B.5 Vision / TargetObservation 数据结构

`CameraFrame` 是内部输入，`TargetObservation` 是 `VisionService` 对外的服务级契约，`vision_target` 是家属端网络序列化格式。三者不是同一对象。`PersonDetection.boundingBox` 用原画面像素坐标；`normalizedCenter/normalizedSize` 使用裁剪后的 `[0,1]` 坐标。家属端 `bbox={x,y,w,h}` 也是归一化坐标，但采用左上角加宽高表示，只有可绘制目标才出现。

| Field | 类型 | 含义与单位/范围 | 主要消费者 |
| --- | --- | --- | --- |
| `present`、`fresh` | bool | 是否有目标、观测是否仍在有效时窗；两者需共同判断 | 自动控制、AI 视野 |
| `status` | enum | SEARCHING、DETECTED、TRACKING、CORRECTED、LOST、REACQUIRED | 自动控制、AI 视野 |
| `frameSequence` | uint64 | 对应采集帧序号；网络帧头取低 32 位 | 调试、画面/观测关联 |
| `timestamp`、`publishedAt` | QDateTime | 采集与发布时刻 | 时效判定、遥测 |
| `ageMs` | int64，ms | 观测年龄；需结合当前接收时刻判断 | 自动控制、AI 视野 |
| `sourceSize` | QSize，px | 原画面宽高 | 像素几何转换 |
| `target.boundingBox` | QRectF，px | 原画面中的人物框 | 本机运动策略与调试 |
| `target.normalizedCenter/normalizedSize` | QPointF/QSizeF，0—1 | 相对画面的中心与尺寸 | AI 视野序列化、跟随距离代理 |
| `target.confidence`、`detectorConfidence`、`trackerConfidence` | float | 目标及检测/跟踪置信度；来源不同，不能混作同一阈值 | 策略、诊断与 AI 视野 |
| `trackerName`、`trackedPointCount`、`detectorRan` | string/int/bool | 本次跟踪器和检测器运行信息 | 遥测/诊断 |
| `detectorMs`、`trackerMs`、`diagnostic` | double ms / string | 耗时与诊断，不直接作为控制授权 | 遥测/调试 |
| 网络 `bbox` | JSON object 或 null | `{x,y,w,h}`，均在 `[0,1]`；不可绘制时为 null | Family Desktop Canvas |

表 B-7 目标观测及网络投影的关键字段。网络 `vision_target` 还含 `protocol_version`、`frame_sequence`、`capture_timestamp`、`published_at`、`present`、`fresh`、`state`、`age_ms`、检测/跟踪置信度和遥测字段。服务端在缺失、过期、SEARCHING/LOST 时输出 `bbox:null`；家属端还按收到时间与 `age_ms` 隐藏旧框。AI 视野使用最新 JPEG 与最新有效观测，不保证逐帧严格配对。SoT：LongPet `src/model/VisionModels.h`、`src/model/VisionModels.cpp`、`src/platform/FamilyVisionProtocol.cpp`；Family `src/renderer/vision-monitor-adapter.js`。

#### B.6 本地数据与配置索引

| Item | 用途与实际范围 | 默认/解析规则 | 敏感性及 SoT |
| --- | --- | --- | --- |
| SQLite `schema_meta` | schema 版本；当前 v1 | 随数据库创建 | 非敏感；LongPet: `src/data/DatabaseManager.cpp` |
| SQLite `reminders` | 提醒定义、启用、revision、创建/更新时间 | Repository 维护 | 含个人日程；LongPet: `ReminderRepository.cpp` |
| SQLite `reminder_events` | 提醒计划、完成和状态事件 | 关联提醒 ID | 含个人行为；LongPet: `ReminderRepository.cpp` |
| SQLite `care_events` | 饮水、活动、交互等实际写入事件及来源 | CareService 记录 | 含照护行为；LongPet: `CareEventRepository.cpp` |
| SQLite `settings` | 音量、亮度、宠物风格等键值 | SettingsService 维护 | 一般配置；LongPet: `SettingsRepository.cpp` |
| `LONGPET_DATABASE_PATH` | SQLite 文件路径 | 未覆盖时 Qt `AppLocalDataLocation/longpet.db` | 路径可能暴露部署信息；LongPet: `Application.cpp` |
| AI 配置 `LONGPET_AI_CONFIG` | ASR/LLM/TTS 分项 Provider、Base URL、模型、Key；`history_turns` 等 | Linux 默认 `/etc/longpet/ai.ini`，环境变量可覆盖具体项 | 含密钥；LongPet: `AiConfigRepository.cpp`、`deploy/配置说明.md` |
| 天气配置 `LONGPET_WEATHER_CONFIG` | Host、Key、坐标、刷新与 stale 时限 | Linux 默认 `/etc/longpet/longpet-weather.ini`，环境变量可覆盖 | 含密钥与位置；LongPet: `WeatherConfigRepository.cpp` |
| `LONGPET_FAMILY_LINK_ADDRESS/PORT/TOKEN` | FamilyLink 监听与长期 Bearer | 地址未设时回环，默认端口 8787；远程监听需 Token | Token 敏感；LongPet: `Application.cpp`、`FamilyLinkController.cpp` |
| `LONGPET_VISION_MODEL_PATH` 与视觉开关 | 选择模型文件、启停 Vision | 环境变量优先于 Adapter 默认路径 | 模型文件需版本管理；LongPet: `VisionDetectorFactory.cpp`、`TinyissimoYoloAdapter.cpp` |
| `LONGPET_MOTION_ENABLED/DEVICE` | Motion 开关与 UART 节点 | 默认关闭；启用后由部署指定设备 | 设备访问受系统权限约束；LongPet: `Application.cpp`、`deploy/longpet.service` |
| Qt/音视频设备环境 | `QT_QPA_PLATFORM`、触摸输入、相机和 ALSA 设备选择 | 板端 service 设置，Adapter 读取 | 设备路径不含账号；LongPet: `deploy/longpet.service`、`src/platform/` |
| AI 对话历史、天气快照、通话/视觉/运动状态 | 当前进程或会话内状态 | 重启不从 SQLite 恢复 | 可能含敏感内容；LongPet: 对应 Service/模型 |

表 B-8 本地数据、运行路径与配置。数据库无“AI 长期记忆”或“用户画像”表；训练数据和模型权重是文件资产，非业务 SQLite 实体。板端 service 中的实际路径随部署变化，本表不载入个人目录或真实凭据。

#### B.7 接口错误与降级语义索引

| Interface | 典型失败或过期 | 产品行为 | 恢复/安全边界 |
| --- | --- | --- | --- |
| FamilyLink REST | 请求超时、未鉴权、连接断开 | 标记设备不可达，不把缓存状态伪装为实时在线 | 重连后重新 GET 状态；写入需设备成功响应 |
| 提醒与设置 | `expectedRevision` 不匹配或能力不可用 | 409/503 与明确提示，不静默覆盖/假报已应用 | 刷新最新版本或修复设备能力后重试 |
| AI Provider | 超时、鉴权/限流、无效响应、取消 | 当前在线会话报错，TTS 失败可保留文字；已有离线快捷能力仍独立可用，旧回调按 session ID 丢弃 | 重新发起新会话；不把错误数据写入业务库 |
| 天气 Provider | 网络或响应失败、缓存过期 | 无数据为未知；已有快照标记 stale | 网络恢复补刷，语音引用时说明旧数据时效 |
| AI 视野 | 摄像头/模型不可用、WS 断开、观测不新鲜 | 停止展示旧画面/人物框或标记不可用 | 重新取得会话与新鲜观测，不沿用旧框 |
| 通话 | 媒体权限失败、旧 callId/revision、WS 断开 | 通话失败或结束；只在 `connected && mediaReady` 显示接通 | 释放摄像头/音频/Socket 后重新建会话 |
| 人工远控 | 客户端停止刷新、失焦/断连、UART 或 MCU 状态失效 | STOP 或撤销控制，页面锁定 | 新会话且 MCU 状态有效才可再控制；最终安全以 MCU 为准 |
| Motion UART | 非法命令、写入失败、STATUS 过期/故障 | 不把最后命令当作已执行，退出自动或人工控制 | 检查链路与 MCU 状态；故障复位规则见第 11 章 |
| SQLite | 打开或 schema 迁移失败 | 应用初始化失败，不伪造本地照护数据 | 修复存储/版本后重新启动 |

表 B-9 各接口的失效语义。测试入口为 LongPet `tests/V02Test.cpp`、`tests/VisionV1Test.cpp`、`tests/MotionV1Test.cpp` 和 Family `tests/`；它们证明代码中存在相应校验路径，不应替代另行记录的板端、实机或长期可靠性验收。

### 附录 C 关键配置参数表

### 附录 D 硬件连接与引脚摘要

### 附录 E 第三方软件、库与模型清单

### 附录 F 参考资料
