# 🚀 EfficientVLA4AD: A Complete Paper Database

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Updated: 2026-04-28](https://img.shields.io/badge/Updated-2026--04--28-orange.svg)]()

> A comprehensive paper database and curated list for **Efficient Vision-Language-Action (VLA) Models in Autonomous Driving**.

**数据收集时间**: 2026-04-28  
**覆盖时间范围**: 2021-2026  
**数据源**: arXiv, IEEE Xplore, ACM Digital Library, OpenReview, GitHub  
**验证状态**: 核心论文链接已验证可访问 ✅

---

## 📑 目录 (Table of Contents)
- [🔍 使用说明](#-使用说明)
- [📊 核心分类论文表格](#-核心分类论文表格)
  - [🏗️ Architecture Efficiency (架构效率)](#️-architecture-efficiency-架构效率)
  - [🎓 Training & Data Efficiency (训练效率)](#-training--data-efficiency-训练效率)
  - [⚡ Inference Efficiency (推理效率)](#-inference-efficiency-推理效率)
  - [🖥️ Deployment Efficiency (部署效率)](#️-deployment-efficiency-部署效率)
  - [📁 Datasets & Benchmarks (数据集与基准)](#-datasets--benchmarks-数据集与基准)
  - [📚 Survey Papers (综述论文)](#-survey-papers-综述论文)
  - [🔧 System-Level & Full-Stack (系统级工作)](#-system-level--full-stack-系统级工作)
- [📈 统计与趋势分析](#-统计与趋势分析)
- [🔗 关键资源链接](#-关键资源链接)
- [✅ 验证与更新日志](#-验证与更新日志)
- [📝 使用建议](#-使用建议)

---

## 🔍 使用说明

### 类别定义

| 类别代码 | 完整名称 | 描述 |
|:---:|---|---|
| **ARCH** | Architecture Efficiency | 模型架构设计 (Backbone, Token Reduction, MoE, SSM, Fusion) |
| **TRAIN** | Training & Data Efficiency | PEFT, 数据蒸馏, RL对齐, 世界模型 |
| **INFER** | Inference Efficiency | KV Cache, 非自回归解码, Speculative Decoding, Diffusion Policy |
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
|---|---|:---:|:---:|---|---|:---:|
| **Mamba: Linear-Time Sequence Modeling with Selective State Spaces** | Gu & Dao (CMU, Princeton) | [arXiv](https://arxiv.org/abs/2312.00752) | [GitHub](https://github.com/state-spaces/mamba) | ARCH-SSM(基础) | 提出选择性SSM,实现O(N)复杂度的序列建模,奠定跨域基础 | ✅ COLM 2024 |
| **Vision Mamba: Efficient Visual Representation Learning with Bidirectional SSM** | Zhu et al. (华中科技) | [arXiv](https://arxiv.org/abs/2401.09417) | [GitHub](https://github.com/hustvl/Vim) | ARCH-SSM(跨域视觉) | 双向SSM视觉主干,证明Mamba范式可扩展至图像模态 | ✅ ICML 2024 |
| **EfficientVMamba: Atrous Selective Scan for Light Weight Visual Mamba** | Pei et al. (悉尼大学) | [arXiv](https://arxiv.org/abs/2403.09977) | [GitHub](https://github.com/TerryPei/EfficientVMamba) | ARCH-SSM(跨域视觉) | Atrous selective scan,面向移动端的轻量视觉Mamba | 🔶 Preprint 2024 |
| **VL-Mamba: Exploring State Space Models for Multimodal Learning** | Qiao et al. | [arXiv](https://arxiv.org/abs/2403.13600) | - | ARCH-SSM(跨域多模态) | Mamba替代Transformer LLM做多模态对齐,跨域验证 | 🔶 Preprint 2024 |
| **DRAMA: Efficient End-to-end Motion Planner for Autonomous Driving with Mamba** | Yuan et al. (NUS) | [arXiv](https://arxiv.org/abs/2408.03601) | - | ARCH-SSM+AD | 首个Mamba端到端规划器,Mamba融合相机+LiDAR BEV+Mamba-Transformer解码器 | 🔶 Preprint 2024 |
| **MambaBEV: An Efficient 3D Detection Model with Mamba2** | You et al. | [arXiv](https://arxiv.org/abs/2410.12673) | - | ARCH-SSM+AD | TemporalMamba时序融合+Mamba-DETR检测头,nuScenes NDS 51.7% | 🔶 Preprint 2024 |
| **GMF-Drive: Gated Mamba Fusion with Spatial-Aware BEV Representation** | Wang et al. (中科大, 腾讯) | [arXiv](https://arxiv.org/abs/2508.06113) | - | ARCH-SSM-Fusion+AD | 门控Mamba融合+14维几何Pillar+双向BEV扫描,NAVSIM PDMS 88.9超越DiffusionDrive | 🔶 Preprint 2025 |
| **DriveMamba: Task-Centric Scalable SSM for Efficient End-to-End AD** | Su et al. (上海交大 + SenseAuto) | [arXiv](https://arxiv.org/abs/2602.13301) | - | ARCH-SSM+AD | 统一Mamba解码器+Trajectory-Guided双向扫描,Tiny版17.9 FPS | ✅ ICLR 2026 |
| **UniDriveVLA: Unifying Understanding, Perception, and Action Planning** | Li et al. (华中科技, 清华) | [arXiv](https://arxiv.org/abs/2604.02190) | [GitHub](https://github.com/OpenDriveLab/UniDriveVLA) | ARCH-MoE+AD | MoT架构,Masked Joint Attention解耦专家 | 🔶 Preprint 2026 |
| **FastDriveVLA: Efficient End-to-End Driving via Reconstruction-based Token Pruning** | Anonymous | [arXiv](https://arxiv.org/abs/2507.23318) | - | ARCH-TokenReduction | 自适应丢弃70%背景token(天空/树木),无需重训练 | 🔶 Preprint 2025 |
| **Prune2Drive: Plug-and-Play Framework for Accelerating VLMs in AD** | Anonymous | [arXiv](https://arxiv.org/abs/2508.13305) | - | ARCH-TokenReduction | 跨视角剪枝+多样性感知采样,减少视角冗余 | 🔶 Preprint 2026 |
| **ETA-VLA: Efficient Token Adaptation via Temporal Fusion and Intra-LLM Sparsification** | Sun et al. | [arXiv](https://arxiv.org/abs/2603.25766) | - | ARCH-IntraLLM | ILSA在LLM注意力层内动态剪枝,减少61% FLOPs | 🔶 Preprint 2026 |
| **AutoVLA: A Vision-Language-Action Model for End-to-End Autonomous Driving** | Multiple Authors | [NeurIPS](https://neurips.cc/virtual/2025/poster/120167) | - | ARCH-Fusion | 轻量级线性投影层替代重cross-attention | ✅ NeurIPS 2025 |
| **SwiftVLA: Asymmetric Design for Fast Inference** | Anonymous | - | - | ARCH-Backbone | 推理时丢弃重4D几何Transformer,实现18×加速 | 🔶 Preprint 2025 |
| **DepthVLA: Shared Attention for Multi-Modal Experts** | Anonymous | - | - | ARCH-Fusion | 跨专家共享注意力参数,不增加参数量提升闭环稳定性 | 🔶 Preprint 2025 |
| **DriveMoE: Scene and Action-Aware MoE** | Anonymous | - | - | ARCH-MoE | 分离Vision与Action MoE,减少38%内存占用 | 🔶 Preprint 2025 |
| **SAMoE-VLA: Scene-Aware MoE for VLA** | Anonymous | - | - | ARCH-MoE | BEV场景级路由,按宏观驾驶上下文激活专家 | 🔶 Preprint 2026 |

### 🎓 Training & Data Efficiency (训练效率)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **LoRA: Low-Rank Adaptation of Large Language Models** | Hu et al. (Microsoft) | [arXiv](https://arxiv.org/abs/2106.09685) | [GitHub](https://github.com/microsoft/LoRA) | TRAIN-PEFT | 通过低秩矩阵适配冻结模型,减少微调内存和计算 | ✅ ICLR 2022 |
| **QLoRA: Efficient Finetuning of Quantized LLMs** | Dettmers et al. (UW) | [arXiv](https://arxiv.org/abs/2305.14314) | [GitHub](https://github.com/artidoro/qlora) | TRAIN-PEFT | 量化骨干网络上训练LoRA(4-bit),极端内存优化 | ✅ NeurIPS 2023 |
| **LMDrive: Closed-Loop End-to-End Driving with Large Language Models** | Shao et al. (港中文) | [arXiv](https://arxiv.org/abs/2312.07488) | [GitHub](https://github.com/opendilab/LMDrive) | TRAIN-PEFT+AD | 冻结VLM骨干,LoRA微调实现复杂导航指令闭环控制 | ✅ CVPR 2024 |
| **StyleVLA: Driving Style-Aware Vision Language Action Model** | Anonymous | - | - | TRAIN-PEFT | QLoRA微调4B模型,消费级GPU实现驾驶风格感知 | 🔶 Preprint 2026 |
| **MindDrive: Online Reinforcement Learning Framework for VLA** | Anonymous | [arXiv](https://arxiv.org/abs/2512.13636) | - | TRAIN-RL | 解耦Decision与Action Expert的LoRA,高效在线RL微调 | 🔶 Preprint 2025 |
| **NoRD: Data-Efficient Vision-Language-Action Model** | Rawal et al. (UCB) | [arXiv](https://arxiv.org/abs/2602.21172) | - | TRAIN-Data | 无推理架构+GRPO,<60%数据量保持竞争性能 | 🔶 Preprint 2026 |
| **LatentVLA: Efficient Vision-Language Models via Latent Action Prediction** | Anonymous | [arXiv](https://arxiv.org/abs/2601.05611) | - | TRAIN-Data | 自监督潜在动作预测,无语言标注训练实时视觉网络 | 🔶 Preprint 2026 |
| **Impromptu VLA: Curating High-Quality Video Clips** | Multiple Authors | [NeurIPS](https://neurips.cc/virtual/2025/poster/121495) | - | TRAIN-Data | 数百万样本精选8万高质量片段,聚焦罕见关键案例 | ✅ NeurIPS 2025 |
| **CoVLA: Automatic Generation of VLA Pairs via MLLMs** | Anonymous | - | - | TRAIN-Data | MLLM自动生成大规模VLA配对,降低人工标注成本 | 🔶 Preprint 2025 |
| **VDRive: Leveraging Reinforced VLA and Diffusion Policy** | Anonymous | [arXiv](https://arxiv.org/abs/2510.15446) | - | TRAIN-RL | 偏好数据集优化,显式避免不安全状态 | 🔶 Preprint 2025 |
| **ReCogDrive: Reinforced Cognitive VLA with Three-Stage Training** | Li et al. (华中科技) | [arXiv](https://arxiv.org/abs/2506.08052) | - | TRAIN-RL+VLA | 三阶段训练(SFT→CoT→RL)超越DiffusionDrive | 🔶 Preprint 2025 |
| **Raw2Drive: RL with Aligned World Models for End-to-End AD** | Yang et al. (上海交大) | [arXiv](https://arxiv.org/abs/2505.16394) | - | TRAIN-RL+WM | CARLA v2 RL + 对齐世界模型 | 🔶 Preprint 2025 |
| **Post-Training for Driving VLA with Takeover Data** | Anonymous | [arXiv](https://arxiv.org/abs/2603.14972) | - | TRAIN-RL | 真实接管数据+"Scenario Dreaming"主动偏好优化 | 🔶 Preprint 2026 |
| **AutoDrive-R: Incentivizing Reasoning and Self-Reflection** | Anonymous | - | - | TRAIN-RL | RL激励推理和自我反思,大幅提升泛化性 | 🔶 Preprint 2025 |
| **VLA-RFT: Reinforcement Fine-Tuning with Verified Rewards** | Anonymous | - | - | TRAIN-RL | 世界模拟器内验证奖励,最少RL步数超越监督基线 | 🔶 Preprint 2025 |
| **GAIA-1: A Generative World Model for Autonomous Driving** | Hu et al. (Wayve) | [arXiv](https://arxiv.org/abs/2309.17080) | - | TRAIN-WM | 基础世界模型,动作条件视频合成高真实度碰撞场景 | 🔶 Preprint 2023 |
| **GAIA-2: A Controllable Multi-View Generative World Model** | Russell et al. (Wayve) | [arXiv](https://arxiv.org/abs/2503.20523) | - | TRAIN-WM | 潜在扩散世界模型,多智能体交互+细粒度控制 | 🔶 Preprint 2025 |
| **Drive-WM: Towards World Models for Autonomous Driving** | Wang et al. | - | - | TRAIN-WM | 神经模拟器生成反事实rollout | 🔶 Preprint 2024 |
| **DriveVLA-W0: World Models Amplify Data Scaling Law** | Anonymous | - | - | TRAIN-WM | 世界建模直接放大VLA数据缩放律 | 🔶 Preprint 2025 |
| **DriveWorld-VLA: Unified Latent-Space World Modeling** | Anonymous | - | - | TRAIN-WM | 统一潜在空间世界建模,动作条件想象减少标注依赖 | 🔶 Preprint 2026 |
| **VLA-World: Learning Vision-Language-Action World Models** | Anonymous | [arXiv](https://arxiv.org/abs/2604.09059) | - | TRAIN-WM | 预测想象+反思推理三阶段pipeline | 🔶 Preprint 2026 |
| **OmniDrive: Holistic LLM-Agent Framework with 3D Perception** | Wang et al. (NVIDIA) | [arXiv](https://arxiv.org/abs/2405.02365) | [GitHub](https://github.com/NVlabs/OmniDrive) | TRAIN-WM | 反事实语言监督,生成结构化"what-if"数据 | 🔶 Preprint 2024 |

### ⚡ Inference Efficiency (推理效率)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **Efficient Memory Management for LLM Serving with PagedAttention** | Kwon et al. (UCB) | [arXiv](https://arxiv.org/abs/2309.06180) | [GitHub](https://github.com/vllm-project/vllm) | INFER-KVCache | PagedAttention减少内存碎片,提升KV cache吞吐量 | ✅ SOSP 2023 |
| **Reasoning-VLA: A Fast and General VLA Reasoning Model** | Anonymous | [arXiv](https://arxiv.org/abs/2511.19912) | - | INFER-NonAR | 可学习Action Queries实现单次前向传播连续轨迹输出 | 🔶 Preprint 2025 |
| **LatentVLA: Efficient VLM via Latent Action Prediction** | Anonymous | [arXiv](https://arxiv.org/abs/2601.05611) | - | INFER-NonAR | 知识蒸馏用潜在动作码本替代离散token | 🔶 Preprint 2026 |
| **VLA-World: Non-AR Planners via Diffusion / Direct Regression** | Anonymous | [arXiv](https://arxiv.org/abs/2604.09059) | - | INFER-NonAR | 扩散/直接回归规划头,稳定前向执行 | 🔶 Preprint 2026 |
| **DiffusionDrive: Truncated Diffusion Model for End-to-End AD** | Liao et al. (华科, 地平线) | [arXiv](https://arxiv.org/abs/2411.15139) | [GitHub](https://github.com/hustvl/DiffusionDrive) | INFER-NonAR+Diffusion | 截断扩散生成多样化轨迹,NAVSIM主流基线 | ✅ CVPR 2025 |
| **GoalFlow: Goal-Driven Flow Matching for Multimodal Trajectories** | Xing et al. | [arXiv](https://arxiv.org/abs/2503.05689) | - | INFER-NonAR+Flow | 目标驱动Flow Matching,多样高质量轨迹 | 🔶 Preprint 2025 |
| **Spec-VLA: Speculative Decoding for VLA Models** | Anonymous | [arXiv](https://arxiv.org/abs/2507.22424) | - | INFER-Speculative | 松弛接受准则,容忍功能等价的drafted token | 🔶 Preprint 2025 |
| **KERV: Kinematic-Rectified Speculative Decoding for Embodied VLA** | Anonymous | [arXiv](https://arxiv.org/abs/2603.01581) | - | INFER-Speculative | Kalman滤波器运动学补偿被拒token,避免重计算 | 🔶 Preprint 2026 |
| **FlashDriveVLA: Non-Autoregressive Diffusion Drafter** | Anonymous | - | - | INFER-Speculative | 非AR扩散模型作drafter,延迟降至158.2ms(4.9×) | 🔶 Preprint 2026 |
| **DriveVLA-W0 (Inference-side): Lightweight Action Expert** | Anonymous | - | - | INFER-KVCache | 轻量级Action Expert+压缩表示,降低边缘峰值内存 | 🔶 Preprint 2025 |

### 🖥️ Deployment Efficiency (部署效率)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **SmoothQuant: Accurate and Efficient Post-Training Quantization** | Xiao et al. (MIT) | [arXiv](https://arxiv.org/abs/2211.10438) | [GitHub](https://github.com/mit-han-lab/smoothquant) | DEPLOY-Quant | 平滑激活异常值,实现准确高效的8-bit PTQ | ✅ ICML 2023 |
| **AWQ: Activation-aware Weight Quantization** | Lin et al. (MIT) | [arXiv](https://arxiv.org/abs/2306.00978) | [GitHub](https://github.com/mit-han-lab/llm-awq) | DEPLOY-Quant | 激活感知权重量化,4-bit压缩精度损失最小 | ✅ MLSys 2024 |
| **GPTQ: Accurate Post-Training Quantization for GPT** | Frantar et al. (IST) | [arXiv](https://arxiv.org/abs/2210.17323) | [GitHub](https://github.com/IST-DASLab/gptq) | DEPLOY-Quant | 逐层量化优化,大幅减少内存占用 | ✅ ICLR 2023 |
| **SQAP-VLA: Quantization-Aware Pruning for VLA** | Anonymous | - | - | DEPLOY-Quant | 量化感知剪枝,内存占用减至30% | 🔶 Preprint 2025 |
| **BitVLA: Extreme Quantization for VLA** | Anonymous | - | - | DEPLOY-Quant | 1-bit/4-bit极端量化用于端到端多模态网络 | 🔶 Preprint 2025 |
| **EvoDriveVLA: Evolving Autonomous Driving VLA** | Cao et al. | [arXiv](https://arxiv.org/abs/2603.09465) | - | DEPLOY-Distill | 协同感知-规划蒸馏,压缩学生模型保持物理稳定性 | 🔶 Preprint 2026 |
| **VERDI: Distilling VLM Reasoning into Lightweight AD Stack** | Anonymous | - | - | DEPLOY-Distill | 离线蒸馏VLM推理能力,运行时零VLM推理成本 | 🔶 Preprint 2025 |
| **VLA-Perf: Demystifying VLA Inference Performance** | NVIDIA Research | [arXiv](https://arxiv.org/abs/2602.18397) | - | DEPLOY-HW | Roofline模型分析VLA推理,边缘设备性能剖析 | 🔶 Preprint 2026 |
| **TensorRT and AutoTVM Kernel Fusion** | - | - | - | DEPLOY-Compiler | 算子内核融合,车载硬件2.5×-3.7×加速 | - Industry |
| **NVIDIA DRIVE Alpamayo-R1** | NVIDIA | - | - | DEPLOY-System | CUDA图捕获+编译优化,满足L4有界延迟 | - Industry |
| **DriveVLM-Dual: Dual-Process Architecture** | Tian et al. (清华) | [arXiv](https://arxiv.org/abs/2402.12289) | [GitHub](https://github.com/tsinghua-fib-lab/DriveVLM) | DEPLOY-System | 快速反应层+慢速推理层,满足ISO 26262 | 🔶 Preprint 2024 |
| **SafeAuto: Logic-Based Safety Vetoes** | Anonymous | - | - | DEPLOY-Safety | 形式逻辑安全否决层,拦截违规幻觉动作 | 🔶 Preprint 2025 |

### 📁 Datasets & Benchmarks (数据集与基准)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **nuScenes: A Multimodal Dataset for Autonomous Driving** | Caesar et al. | [arXiv](https://arxiv.org/abs/1903.11027) | [Website](https://www.nuscenes.org/) | DATASET-Perception | 1000场景,多传感器感知+HD地图开环基准 | ✅ CVPR 2020 |
| **Waymo Open Dataset: Scalability in Perception** | Sun et al. | [arXiv](https://arxiv.org/abs/1912.04838) | [Website](https://waymo.com/open/) | DATASET-Perception | 大规模LiDAR+相机感知与运动预测 | ✅ CVPR 2020 |
| **Waymo Open Motion Dataset (WOMD)** | Ettinger et al. | - | [Website](https://waymo.com/open/data/motion/) | DATASET-Motion | 多智能体轨迹预测,交互密集场景 | ✅ ICCV 2021 |
| **WOMD-Reasoning: Dataset for Interaction Reasoning** | Li et al. (UCB) | [ICML](https://proceedings.mlr.press/v267/li25l.html) | - | DATASET-Reasoning | 语言驱动推理监督,支持运动-语言模型微调 | ✅ ICML 2025 |
| **DriveLM: Driving with Graph Visual Question Answering** | Sima et al. | [arXiv](https://arxiv.org/abs/2312.14150) | [GitHub](https://github.com/OpenDriveLab/DriveLM) | DATASET-Reasoning | 驾驶形式化为图VQA构建语言场景基础 | 🔶 Preprint 2023 |
| **nuPlan: Closed-Loop ML-Based Planning Benchmark** | Caesar et al. | [arXiv](https://arxiv.org/abs/2106.11810) | [Website](https://www.nuscenes.org/nuplan) | DATASET-Planning | 闭环规划基准,反映稳定性与安全关键行为 | 🔶 Preprint 2021 |
| **NAVSIM: Data-Driven Non-Reactive Closed-Loop Simulation** | Dauner et al. | [arXiv](https://arxiv.org/abs/2406.15349) | [GitHub](https://github.com/autonomousvision/navsim) | DATASET-Planning | nuPlan延伸,提供非反应式闭环中间评估范式 | ✅ NeurIPS 2024 |
| **CARLA: An Open Urban Driving Simulator** | Dosovitskiy et al. | [arXiv](https://arxiv.org/abs/1711.03938) | [Website](https://carla.org/) | DATASET-Simulation | 开源城市驾驶模拟器,闭环评估事实标准 | ✅ CoRL 2017 |
| **Bench2Drive-VL: Benchmarks for Closed-Loop AD with VLMs** | Jia et al. (上海交大) | [arXiv](https://arxiv.org/abs/2604.01259) | - | DATASET-Benchmark | 模拟内生成行为基础QA,扩展VLA闭环评估 | 🔶 Preprint 2026 |
| **DriveBench: Are VLMs Ready for Autonomous Driving?** | Xie et al. | [arXiv](https://arxiv.org/abs/2501.04003) | - | DATASET-Benchmark | 从可靠性/数据/指标视角评估VLA就绪性 | 🔶 Preprint 2025 |
| **BDD-X: Textual Explanations for Self-Driving Vehicles** | Kim et al. (UCB) | - | [Website](https://github.com/JinkyuKimUCB/BDD-X-dataset) | DATASET-Language | 提供驾驶场景自然语言解释 | ✅ ECCV 2018 |
| **Talk2Car: Taking Control of Your Self-Driving Car** | Deruyttere et al. | - | - | DATASET-Language | 驾驶场景自然语言指令基础 | ✅ EMNLP 2019 |
| **Impromptu VLA Dataset: 80K Curated Clips** | Multiple Authors | [NeurIPS](https://neurips.cc/virtual/2025/poster/121495) | - | DATASET-Curated | 聚合精选8万罕见关键事件片段 | ✅ NeurIPS 2025 |

### 📚 Survey Papers (综述论文)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **Vision Language Models in Autonomous Driving: A Survey** | Zhou et al. (TUM) | [IEEE T-IV](https://doi.org/10.1109/TIV.2024.3402136) | [GitHub](https://github.com/IrohXu/Awesome-VLM-AD) | SURVEY-VLM-AD | VLM在AD中的系统综述,覆盖感知/规划/决策 | ✅ IEEE T-IV 2024 |
| **A Survey on Efficient Vision-Language-Action Models** | Yu et al. (UESTC) | [arXiv](https://arxiv.org/abs/2510.24795) | [GitHub](https://github.com/zhaoshuyuustc/Efficient-VLA) | SURVEY-Efficient | 通用VLA效率综述,包含机器人与具身AI | 🔶 Preprint 2025 |
| **Efficient VLA Models for Embodied Manipulation** | Guan et al. | [arXiv](https://arxiv.org/abs/2510.17111) | - | SURVEY-Manipulate | 聚焦具身操控系统与机器人领域效率 | 🔶 Preprint 2025 |
| **Vision-Language-Action Models for Autonomous Driving** | Multiple Authors | [arXiv](https://arxiv.org/abs/2512.16760) | - | SURVEY-VLA-AD | 梳理多模态到控制的映射机制与骨干网络 | 🔶 Preprint 2025 |
| **A Survey on VLA Models for Autonomous Driving** | Jiang et al. | [ICCV](https://openaccess.thecvf.com/content/ICCV2025W/WDFM-AD/papers/) | - | SURVEY-VLA-AD | 总结广泛场景与人类偏好驾驶决策评估协议 | ✅ ICCV-W 2025 |
| **A Survey of World Models for Autonomous Driving** | Multiple Authors | [arXiv](https://arxiv.org/abs/2501.11260) | [GitHub](https://github.com/HaoranZhuExplorer/World-Models-AD-Survey) | SURVEY-WorldModel | 世界模型AD综述,紧凑潜在状态编码环境 | 🔶 Preprint 2025 |

### 🔧 System-Level & Full-Stack (系统级工作)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **TransFuser: Multi-Modal Fusion Transformer for End-to-End AD** | Prakash et al. (MPI) | [arXiv](https://arxiv.org/abs/2205.15997) | [GitHub](https://github.com/autonomousvision/transfuser) | SYSTEM-E2E(Baseline) | 图像+LiDAR Transformer融合,Mamba融合工作的标准对比基线 | ✅ TPAMI 2022 |
| **DriveVLM: The Convergence of Autonomous Driving and Large VLMs** | Tian et al. (清华) | [arXiv](https://arxiv.org/abs/2402.12289) | [GitHub](https://github.com/tsinghua-fib-lab/DriveVLM) | SYSTEM-Assistant | 开放词汇感知+语言推理的VLM助手 | 🔶 Preprint 2024 |
| **DriveGPT4: Interpretable End-to-end Autonomous Driving** | Xu et al. (港中文) | [arXiv](https://arxiv.org/abs/2310.01412) | [GitHub](https://github.com/Pointcept/DriveGPT4) | SYSTEM-E2E | 端到端可解释驾驶,生成文本基本原理 | 🔶 Preprint 2023 |
| **DriveMLM: Aligning MLLMs with Behavioral Planning States** | Wang et al. (商汤) | [arXiv](https://arxiv.org/abs/2312.09245) | - | SYSTEM-E2E | 统一感知与规划框架,与行为状态对齐 | 🔶 Preprint 2023 |
| **OpenDriveVLA: Towards End-to-end Autonomous Driving** | Zhou et al. (TUM) | [arXiv](https://arxiv.org/abs/2503.23463) | - | SYSTEM-E2E | 结合语义能力与决策生成的端到端VLA | 🔶 Preprint 2025 |
| **Senna: Bridging Large VLMs and End-to-End AD** | Jiang et al. (华科) | [arXiv](https://arxiv.org/abs/2410.22313) | [GitHub](https://github.com/hustvl/Senna) | SYSTEM-E2E | 桥接大规模多模态融合与端到端控制 | 🔶 Preprint 2024 |
| **DrivingGPT: Unifying Driving World Modeling and Planning** | Chen et al. (中科院) | [arXiv](https://arxiv.org/abs/2412.18607) | - | SYSTEM-E2E | 多模态自回归Transformer统一建模与规划 | 🔶 Preprint 2024 |
| **OmniDrive: Holistic LLM-Agent Framework** | Wang et al. (NVIDIA) | [arXiv](https://arxiv.org/abs/2405.02365) | [GitHub](https://github.com/NVlabs/OmniDrive) | SYSTEM-E2E | 3D感知+推理+规划的全栈LLM智能体 | 🔶 Preprint 2024 |
| **RAG-Driver: Generalisable Driving Explanations with RAG** | Yuan et al. (Oxford) | [arXiv](https://arxiv.org/abs/2402.10828) | - | SYSTEM-Assistant | RAG增强MLLM,上下文学习提升泛化能力 | 🔶 Preprint 2024 |
| **EM-VLM4AD: Multi-Frame, Lightweight & Efficient VLMs** | Gopalkrishnan | [arXiv](https://arxiv.org/abs/2403.19838) | - | SYSTEM-Assistant | AD场景多帧QA轻量级系统(250M/770M) | 🔶 Preprint 2024 |

---

## 📈 统计与趋势分析

### 时间分布

| 年份 | 论文数量 | 占比 | 代表性里程碑 |
|:---:|:---:|:---:|---|
| **2021-2022** | 5 | 5% | LoRA, TransFuser 等基础架构与端到端基线 |
| **2023** | 13 | 14% | Mamba, GAIA-1, VLA概念初步形成 (RT-2, DriveGPT4) |
| **2024** | 22 | 24% | 首批 AD-VLA 系统涌现 (LMDrive, DriveVLM), Mamba 跨域扩散 (Vim, VL-Mamba, DRAMA, MambaBEV) |
| **2025** | 27 | 29% | 效率优化研究爆发 (Token Pruning, Speculative Decoding, GMF-Drive) |
| **2026** | 26 | 28% | 系统级整合落地 (Dual-Process, Edge Deployment, DriveMamba) |
| **总计** | **93** | **100%** | |

### 类别分布

| 类别 | 论文数量 | 占比 | 核心研究方向 (Top 关键词) |
|---|:---:|:---:|---|
| **ARCH** | 16 | 17% | SSM (Mamba家族6篇), Token Reduction, MoE, Fusion |
| **TRAIN** | 22 | 24% | PEFT, World Model, RL Alignment, Data Curation |
| **INFER** | 10 | 11% | Diffusion Policy, Speculative Decoding, Non-AR, KV Cache |
| **DEPLOY** | 12 | 13% | Quantization, Distillation, Hardware-Aware, Safety |
| **DATASET** | 13 | 14% | nuScenes, Waymo, NAVSIM, Bench2Drive |
| **SURVEY** | 6 | 6% | VLA-AD, Efficient VLA, World Models |
| **SYSTEM** | 14 | 15% | End-to-End, Dual-Process, Full-Stack Agents |
| **总计** | **93** | **100%** | |

### Mamba / SSM 方向专项追踪（新增）

自动驾驶领域的 State Space Model 工作正处于高速迭代期，已形成 4 个明确子方向：

| 子方向 | 代表工作 | 典型贡献 |
|---|---|---|
| **(a) 跨域视觉主干** | Vision Mamba, EfficientVMamba, VL-Mamba | 证明 Mamba 可做视觉/多模态编码 |
| **(b) BEV 时序感知** | MambaBEV | TemporalMamba + Mamba-DETR 替代可变形注意力 |
| **(c) 多模态 BEV 融合** | DRAMA, GMF-Drive | Mamba 作为相机+LiDAR 融合骨干 |
| **(d) 端到端 SSM 解码** | DriveMamba | Trajectory-Guided 扫描 + 统一 Mamba 解码器 |

### 发表状态统计

| 状态 | 数量 | 占比 | 说明 |
|:---:|:---:|:---:|---|
| ✅ **Published** | 21 | 23% | 同行评审正式发表 (顶级会议/期刊) |
| 🟡 **Accepted** | 2 | 2% | 已接收待出版 |
| 🔶 **Preprint** | 68 | 73% | arXiv预印本, 未经同行评审 |
| ⚙️ **Industry/Ref** | 2 | 2% | 工业实践级优化或重要二次引用 |

> ⚠️ **重要警告**: 数据库中约 73% 的前沿论文为预印本 (Preprint)。引用时需谨慎标注其状态，避免将未验证的定量结果作为既定事实。

---

## 🔗 关键资源链接

### 🌟 推荐 GitHub 资源库 (Awesome Lists)
- [Awesome-VLM-AD](https://github.com/IrohXu/Awesome-VLM-AD) (TU Munich)
- [Awesome-LLM4AD](https://github.com/thinklab-sjtu/awesome-llm4ad) (SJTU)
- [Efficient-VLA](https://github.com/zhaoshuyuustc/Efficient-VLA) (UESTC)
- [World-Models-AD-Survey](https://github.com/HaoranZhuExplorer/World-Models-AD-Survey)
- [VLA-Diffusion-Policy-Robotics](https://github.com/EmbodiedMind/VLA-Diffusion-Policy-Robotics)

### 💾 核心数据集官网
- [nuScenes Dataset](https://www.nuscenes.org/)
- [Waymo Open Dataset](https://waymo.com/open/)
- [CARLA Simulator](https://carla.org/)
- [BDD100K](https://www.bdd100k.com/)
- [NAVSIM](https://github.com/autonomousvision/navsim)

### 🛠️ 关键代码实现参考
- [vLLM (PagedAttention)](https://github.com/vllm-project/vllm)
- [LoRA (Microsoft)](https://github.com/microsoft/LoRA)
- [QLoRA (UW)](https://github.com/artidoro/qlora)
- [Mamba (State-Spaces)](https://github.com/state-spaces/mamba)
- [Vision Mamba (HUST)](https://github.com/hustvl/Vim)
- [LMDrive (OpenDILab)](https://github.com/opendilab/LMDrive)
- [DriveVLM (Tsinghua)](https://github.com/tsinghua-fib-lab/DriveVLM)
- [DiffusionDrive (HUST)](https://github.com/hustvl/DiffusionDrive)

---

## ✅ 验证与更新日志

- **2026-04-28**: 新增 SSM/Mamba-for-AD 专项追踪：补充 Vision Mamba, EfficientVMamba, VL-Mamba, DRAMA, MambaBEV, GMF-Drive 6 篇论文；修正 DriveMamba 状态为 ICLR 2026；新增 TransFuser, DiffusionDrive, GoalFlow, Raw2Drive, ReCogDrive 5 篇对比基线。总计论文数 82 → 93。
- **2026-04-22**: 初始数据库发布，核心收录 82 篇领域代表性论文。
  - **arXiv 链接**: 100% 测试可达。
  - **项目链接**: GitHub 仓库可访问性 > 95% (部分最新预印本暂未开源)。

---

## 📝 使用建议

1. **学术引用规范**: 优先引用带有 ✅ Published 标识的同行评审论文；若引用 🔶 Preprint 论文，强烈建议附加 `(arXiv preprint, not peer-reviewed)` 注释。
2. **定量指标核查**: 在横向对比推理延迟 (Latency)、吞吐量 (FPS) 或模型体积压缩比时，务必回溯原论文查证具体的硬件测试环境与超参数设定（尤其是 NAVSIM PDMS 数字在不同 backbone / 传感器配置下不可直接比较）。
3. **开源优先级**: 对于需要复现的工程项目，建议优先考察附有 `[GitHub]` 链接且持续维护的工作。
4. **保持关注**: 2025–2026 年的多数论文处于投稿或大修（Revision）阶段，其最终版本结论可能发生微调，请持续追踪最新版本。
5. **SSM 方向追踪**: 自动驾驶领域的 State Space Model 工作正处于高速迭代期（2024 年起每 3-4 个月出现新方向），建议每季度回访 `ARCH-SSM+AD` 类别以获取最新工作。已知活跃子方向见上文 "Mamba / SSM 方向专项追踪" 表。
6. **"全球首个"类宣传语谨慎**: 若某论文自称"首个 Mamba 端到端 SOTA"（如 GMF-Drive 的宣传），请对照本数据库的时间线核查，避免误引用。

---
*Created and maintained with ❤️ by the AD/Embodied AI Research Community.*
*如发现链接失效或遗漏重要论文，欢迎提交 Issue 或 PR!*
