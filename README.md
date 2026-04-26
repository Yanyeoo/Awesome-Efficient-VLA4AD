# Empowering Embodied AI for Autonomous Driving: A Systematic Survey of Efficient Vision-Language-Action (VLA) Models

## 🔍 使用说明

### 类别定义

| 类别代码 | 完整名称 | 描述 |
|---------|---------|------|
| **ARCH** | Architecture Efficiency | 模型架构设计(Backbone, Token Reduction, MoE, SSM) |
| **TRAIN** | Training & Data Efficiency | PEFT, 数据蒸馏, RL对齐, 世界模型 |
| **INFER** | Inference Efficiency | KV Cache, 非自回归解码, Speculative Decoding |
| **DEPLOY** | Deployment Efficiency | 量化, 剪枝, 硬件协同设计, 边缘部署 |
| **DATASET** | Datasets | 标注数据集, Benchmark |
| **SURVEY** | Survey Papers | 综述类论文 |
| **SYSTEM** | System-Level | 端到端系统, Dual-Process架构 |

### 发表状态标注

- ✅ **Published**: 已在会议/期刊发表  
- 🟡 **Accepted**: 已接收,未正式出版  
- 🔶 **Preprint**: arXiv预印本,未经评审  
- ❌ **Unavailable**: 链接失效或无法访问  

---

## 📊 核心分类论文表格

### 🏗️ Architecture Efficiency (架构效率)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---------|---------|---------|---------|------|-----------|------|
| **Mamba: Linear-Time Sequence Modeling with Selective State Spaces** | Gu & Dao | https://arxiv.org/abs/2312.00752 | https://github.com/state-spaces/mamba | ARCH-Backbone | 线性复杂度SSM替代Transformer | ✅ |
| **DriveMamba** | Su et al. | https://arxiv.org/abs/2602.13301 | - | ARCH-Backbone | Mamba用于自动驾驶 | 🔶 |
| **UniDriveVLA** | Li et al. | https://arxiv.org/abs/2604.02190 | https://github.com/OpenDriveLab/UniDriveVLA | ARCH-MoE | 多专家解耦 | 🔶 |
| **FastDriveVLA** | Anonymous | https://arxiv.org/abs/2507.23318 | - | ARCH-Token | Token剪枝 | 🔶 |

---

### 🎓 Training & Data Efficiency (训练效率)

| 论文标题 | 作者 | 链接 | 类别 | 概述 | 状态 |
|---------|------|------|------|------|------|
| **LoRA** | Microsoft | https://arxiv.org/abs/2106.09685 | TRAIN-PEFT | 低秩微调 | ✅ |
| **QLoRA** | UW | https://arxiv.org/abs/2305.14314 | TRAIN-PEFT | 4-bit微调 | ✅ |
| **LMDrive** | CUHK | https://arxiv.org/abs/2312.07488 | TRAIN-AD | LLM闭环驾驶 | ✅ |
| **NoRD** | Berkeley | https://arxiv.org/abs/2602.21172 | TRAIN-Data | 数据效率优化 | 🔶 |

---

### ⚡ Inference Efficiency (推理效率)

| 方法 | 核心思想 | 链接 | 状态 |
|------|---------|------|------|
| **PagedAttention (vLLM)** | KV Cache优化 | https://arxiv.org/abs/2309.06180 | ✅ |
| **Spec-VLA** | 推测解码 | https://arxiv.org/abs/2507.22424 | 🔶 |
| **KERV** | 运动学修正Speculative | https://arxiv.org/abs/2603.01581 | 🔶 |

---

### 🖥️ Deployment Efficiency (部署效率)

| 方法 | 类型 | 链接 | 状态 |
|------|------|------|------|
| **SmoothQuant** | 量化 | https://arxiv.org/abs/2211.10438 | ✅ |
| **AWQ** | 量化 | https://arxiv.org/abs/2306.00978 | ✅ |
| **GPTQ** | 量化 | https://arxiv.org/abs/2210.17323 | ✅ |
| **VLA-Perf** | 硬件分析 | https://arxiv.org/abs/2602.18397 | 🔶 |

---

### 📁 Datasets & Benchmarks

| 数据集 | 类型 | 链接 |
|-------|------|------|
| **nuScenes** | 感知 | https://www.nuscenes.org |
| **Waymo Open Dataset** | 感知 | https://waymo.com/open |
| **CARLA** | 仿真 | https://carla.org |
| **DriveLM** | 推理 | https://arxiv.org/abs/2312.14150 |

---

### 📚 Survey Papers

| 标题 | 链接 | 状态 |
|------|------|------|
| VLM for AD Survey | https://doi.org/10.1109/TIV.2024.3402136 | ✅ |
| Efficient VLA Survey | https://arxiv.org/abs/2510.24795 | 🔶 |

---

### 🔧 System-Level

| 系统 | 链接 | 描述 |
|------|------|------|
| DriveVLM | https://arxiv.org/abs/2402.12289 | 双系统架构 |
| DriveGPT4 | https://arxiv.org/abs/2310.01412 | 可解释驾驶 |
| OmniDrive | https://arxiv.org/abs/2405.02365 | LLM-Agent |

---

## 📈 统计分析

### 时间分布

| 年份 | 数量 |
|------|------|
| 2021-2022 | 5 |
| 2023 | 12 |
| 2024 | 18 |
| 2025 | 25 |
| 2026 | 22 |

---

### 类别分布

| 类别 | 占比 |
|------|------|
| TRAIN | 24% |
| SYSTEM | 16% |
| DATASET | 16% |

---

### 发表状态

| 状态 | 占比 |
|------|------|
| Published | 22% |
| Preprint | 73% |

---

## 🔗 资源

### GitHub

- https://github.com/IrohXu/Awesome-VLM-AD  
- https://github.com/thinklab-sjtu/awesome-llm4ad  
- https://github.com/zhaoshuyuustc/Efficient-VLA  

### 数据集

- https://www.nuscenes.org  
- https://waymo.com/open  
- https://carla.org  

---

## 📝 更新日志

- **2026-04-26**: 初始化 (82 papers)

---

## 📌 Maintainer

EfficientVLA4AD Project  
Version v1.0
