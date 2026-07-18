# 🚀 EfficientVLA4AD:


<p align="center">
  <b>Empowering Embodied AI for Autonomous Driving: A Systematic Survey of Efficient VLA Models</b>
</p>

<p align="center">
  <a href="#"><img src="https://img.shields.io/badge/arXiv-Coming%20Soon-b31b1b.svg" alt="arXiv"></a>
  <a href="#"><img src="https://img.shields.io/badge/Target-IEEE%20T--ITS-blue.svg" alt="IEEE T-ITS"></a>
  <img src="https://img.shields.io/badge/Papers-138-green.svg" alt="Papers">
  <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen.svg" alt="PRs Welcome">
</p>

<p align="center">
  A curated, systematically organized reading list accompanying our survey on <b>efficient Vision-Language-Action (VLA) models for autonomous driving (VLA-AD)</b>.
  If you find this repository useful, please consider giving it a ⭐ and citing our paper.
</p>

---
## 📖 About This Survey

End-to-end autonomous driving is rapidly converging with Vision-Language-Action (VLA) models, but real-time, safety-critical deployment exposes a fundamental **triple constraint**: models must be simultaneously **efficient**, **safe**, and **deployable**. This survey systematically reviews **138 papers** spanning architecture design, training, inference, and deployment, organizing the fast-growing VLA-AD literature into a coherent efficiency taxonomy — and is, to our knowledge, the first survey in this space to adopt a **PRISMA-style systematic review methodology**.
![structure](figure001.png)


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
- ⚙️ **Industry/Ref**: 工业实践级优化或重要二次引用

---

## 📊 核心分类论文表格

### 🏗️ Architecture Efficiency (架构效率)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **Mamba: Linear-Time Sequence Modeling with Selective State Spaces** | Gu & Dao (CMU, Princeton) | [arXiv](https://arxiv.org/abs/2312.00752) | [GitHub](https://github.com/state-spaces/mamba) | ARCH-SSM(基础) | 提出选择性SSM,实现O(N)复杂度的序列建模,奠定跨域基础 | ✅ COLM 2024 |
| **Vision Mamba: Efficient Visual Representation Learning with Bidirectional SSM** | Zhu et al. (华中科技) | [arXiv](https://arxiv.org/abs/2401.09417) | [GitHub](https://github.com/hustvl/Vim) | ARCH-SSM(跨域视觉) | 双向SSM视觉主干,证明Mamba范式可扩展至图像模态 | ✅ ICML 2024 |
| **EfficientVMamba: Atrous Selective Scan for Light Weight Visual Mamba** | Pei et al. (悉尼大学) | [arXiv](https://arxiv.org/abs/2403.09977) | [GitHub](https://github.com/TerryPei/EfficientVMamba) | ARCH-SSM(跨域视觉) | Atrous selective scan,面向移动端的轻量视觉Mamba | 🔶 Preprint 2024 |
| **VL-Mamba: Exploring State Space Models for Multimodal Learning** | Qiao et al. | [arXiv](https://arxiv.org/abs/2403.13600) | - | ARCH-SSM(跨域多模态) | Mamba替代Transformer LLM做多模态对齐,跨域验证 | 🔶 Preprint 2024 |
| **Perceiver IO: A General Architecture for Structured Inputs & Outputs** | Jaegle et al. | [arXiv](https://arxiv.org/abs/2107.14795) | - | ARCH-LatentBottleneck | 提出固定大小的潜在瓶颈，实现可扩展的结构化多模态融合 | ✅ ICLR 2022 |
| **EfficientFormer: Vision Transformers at MobileNet Speed** | Li et al. | - | - | ARCH-VisionEncoder | 面向移动端的视觉主干优化，以实际设备延迟而非纯FLOPs为导向 | ✅ NeurIPS 2022 |
| **MambaBEV: An Efficient 3D Detection Model with Mamba2** | You et al. | [arXiv](https://arxiv.org/abs/2410.12673) | - | ARCH-SSM+AD | TemporalMamba时序融合+Mamba-DETR检测头,nuScenes NDS 51.7% | 🔶 Preprint 2024 |
| **DRAMA: Efficient End-to-end Motion Planner for Autonomous Driving with Mamba** | Yuan et al. (NUS) | [arXiv](https://arxiv.org/abs/2408.03601) | - | ARCH-SSM+AD | 首个Mamba端到端规划器,Mamba融合相机+LiDAR BEV+Mamba-Transformer解码器 | 🔶 Preprint 2024 |
| **GMF-Drive: Gated Mamba Fusion with Spatial-Aware BEV Representation** | Wang et al. (中科大, 腾讯) | [arXiv](https://arxiv.org/abs/2508.06113) | - | ARCH-SSM-Fusion+AD | 门控Mamba融合+14维几何Pillar+双向BEV扫描,NAVSIM PDMS 88.9超越DiffusionDrive | 🔶 Preprint 2025 |
| **DriveMamba: Task-Centric Scalable SSM for Efficient End-to-End AD** | Su et al. (上海交大 + SenseAuto) | [arXiv](https://arxiv.org/abs/2602.13301) | - | ARCH-SSM+AD | 统一Mamba解码器+Trajectory-Guided双向扫描,Tiny版17.9 FPS | ✅ ICLR 2026 |
| **TokenLearner: Adaptive Space-Time Tokenization for Videos** | Ryoo et al. | - | - | ARCH-TokenReduction | 学习紧凑的token选择，奠定视觉流摘要与压缩基础 | ✅ NeurIPS 2021 |
| **Token Merging: Your ViT But Faster (ToMe)** | Bolya et al. | - | - | ARCH-TokenReduction | 动态合并冗余视觉token，无需重训练的即插即用机制 | ✅ ICLR 2023 |
| **FastV: Plug-and-Play Inference Acceleration for Large Vision-Language Models** | Chen et al. | - | - | ARCH-TokenReduction | 发现多模态模型深层视觉注意力极其稀疏，提出即插即用早期剪枝 | ✅ ECCV 2024 |
| **LLaVA-PruMerge: Adaptive Token Reduction for Efficient Large Multimodal Models** | Shang et al. | [arXiv](https://arxiv.org/abs/2403.15388) | - | ARCH-TokenReduction | 自适应联合剪枝与合并，实现~14倍高度压缩 | ✅ ICCV 2025 |
| **FastDriveVLA: Efficient End-to-End Driving via Reconstruction-based Token Pruning** | Anonymous | [arXiv](https://arxiv.org/abs/2507.23318) | - | ARCH-TokenReduction | 自适应丢弃70%背景token(天空/树木),无需重训练 | 🔶 Preprint 2025 |
| **Prune2Drive: Plug-and-Play Framework for Accelerating VLMs in AD** | Anonymous | [arXiv](https://arxiv.org/abs/2508.13305) | - | ARCH-TokenReduction | 跨视角剪枝+多样性感知采样,减少视角冗余 | 🔶 Preprint 2026 |
| **VLA-Pruner: Joint Spatio-Temporal Token Selection for VLA Models** | Anonymous | - | - | ARCH-TokenReduction | 时空联合裁剪，保留对当前机动范围最相关的token特征 | 🔶 Preprint 2025 |
| **AutoVLA: A Vision-Language-Action Model for End-to-End Autonomous Driving** | Multiple Authors | [NeurIPS](https://neurips.cc/virtual/2025/poster/120167) | - | ARCH-Fusion | 轻量级线性投影层替代重cross-attention | ✅ NeurIPS 2025 |
| **Outrageously Large Neural Networks: The Sparsely-Gated Mixture-of-Experts Layer** | Shazeer et al. | - | - | ARCH-MoE | 提出可训练的门控混合专家层，奠定条件计算基础 | ✅ ICLR 2017 |
| **Switch Transformers: Scaling to Trillion Parameter Models** | Fedus et al. | - | - | ARCH-MoE | Top-1路由简化大规模稀疏训练，建立生产级MoE范式 | ✅ JMLR 2022 |
| **ST-MoE: Designing Stable and Transferable Sparse Expert Models** | Zoph et al. | [arXiv](https://arxiv.org/abs/2202.08906) | - | ARCH-MoE | 揭示专家路由不稳定性与延迟抖动风险，提供稳定设计规范 | 🔶 Preprint 2022 |
| **UniDriveVLA: Unifying Understanding, Perception, and Action Planning** | Li et al. (华中科技, 清华) | [arXiv](https://arxiv.org/abs/2604.02190) | [GitHub](https://github.com/OpenDriveLab/UniDriveVLA) | ARCH-MoE+AD | MoT架构,Masked Joint Attention解耦专家 | 🔶 Preprint 2026 |
| **DriveMoE: Scene and Action-Aware MoE** | Anonymous | - | - | ARCH-MoE | 分离Vision与Action MoE,减少38%内存占用 | 🔶 Preprint 2025 |
| **SAMoE-VLA: Scene-Aware MoE for VLA** | Anonymous | - | - | ARCH-MoE | BEV场景级路由,按宏观驾驶上下文激活专家 | 🔶 Preprint 2026 |
| **BranchyNet: Fast Inference via Early Exiting from Deep Neural Networks** | Teerapittayanon et al. | - | - | ARCH-IntraModel | 浅层辅助分类器早退机制的基础性先驱工作 | ✅ ICPR 2016 |
| **SkipNet: Learning Dynamic Routing in Convolutional Networks** | Wang et al. | - | - | ARCH-IntraModel | 逐层门控条件执行，将早退逻辑扩展至跳层机制 | ✅ ECCV 2018 |
| **Depth-Adaptive Transformer** | Elbayad et al. | [arXiv](https://arxiv.org/abs/1910.10073) | - | ARCH-IntraModel | 依赖输入难度的动态深度与早退分配机制 | ✅ ICLR 2020 |
| **DynamicViT: Efficient Vision Transformers with Dynamic Token Sparsification** | Rao et al. | - | - | ARCH-IntraModel | 视觉Transformer内的动态token稀疏化与抛弃机制 | ✅ NeurIPS 2021 |
| **ETA-VLA: Efficient Token Adaptation via Temporal Fusion and Intra-LLM Sparsification** | Sun et al. | [arXiv](https://arxiv.org/abs/2603.25766) | - | ARCH-IntraLLM | ILSA在LLM注意力层内动态剪枝,减少61% FLOPs | 🔶 Preprint 2026 |
| **DeeAD: Dynamic Depth Modulation for Efficient AD Vision-Language-Action Models** | Anonymous | - | - | ARCH-IntraModel | 基于动作轨迹收敛性的动态早退，桥接架构与调度逻辑 | 🔶 Preprint 2025 |
| **SwiftVLA: Asymmetric Design for Fast Inference** | Anonymous | - | - | ARCH-Backbone | 推理时丢弃重4D几何Transformer,实现18×加速 | 🔶 Preprint 2025 |
| **DepthVLA: Shared Attention for Multi-Modal Experts** | Anonymous | - | - | ARCH-Fusion | 跨专家共享注意力参数,不增加参数量提升闭环稳定性 | 🔶 Preprint 2025 |

### 🎓 Training & Data Efficiency (训练效率)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **LoRA: Low-Rank Adaptation of Large Language Models** | Hu et al. (Microsoft) | [arXiv](https://arxiv.org/abs/2106.09685) | [GitHub](https://github.com/microsoft/LoRA) | TRAIN-PEFT | 通过低秩矩阵适配冻结模型,减少微调内存和计算 | ✅ ICLR 2022 |
| **QLoRA: Efficient Finetuning of Quantized LLMs** | Dettmers et al. (UW) | [arXiv](https://arxiv.org/abs/2305.14314) | [GitHub](https://github.com/artidoro/qlora) | TRAIN-PEFT | 量化骨干网络上训练LoRA(4-bit),极端内存优化 | ✅ NeurIPS 2023 |
| **LMDrive: Closed-Loop End-to-End Driving with Large Language Models** | Shao et al. (港中文) | [arXiv](https://arxiv.org/abs/2312.07488) | [GitHub](https://github.com/opendilab/LMDrive) | TRAIN-PEFT+AD | 冻结VLM骨干,LoRA微调实现复杂导航指令闭环控制 | ✅ CVPR 2024 |
| **Adaptive Capacity Allocation for Vision Language Action Fine-tuning (LoRA-SP)** | Kim et al. | [arXiv](https://arxiv.org/abs/2603.07404) | - | TRAIN-PEFT | 针对VLA微调提出SVD参数化与能量路由，揭示VLA需要高内在秩(r≈128) | ✅ ICRA 2026 |
| **MindDrive: Online Reinforcement Learning Framework for VLA** | Fu et al. | [arXiv](https://arxiv.org/abs/2512.13636) | - | TRAIN-RL | 解耦Decision与Action Expert的LoRA,高效在线RL微调 | 🔶 Preprint 2025 |
| **StyleVLA: Driving Style-Aware Vision Language Action Model** | Gao et al. | [arXiv](https://arxiv.org/abs/2603.09482) | - | TRAIN-PEFT | QLoRA微调4B模型,消费级GPU实现驾驶风格感知 | 🔶 Preprint 2026 |
| **NoRD: Data-Efficient Vision-Language-Action Model** | Rawal et al. (UCB) | [arXiv](https://arxiv.org/abs/2602.21172) | - | TRAIN-Data | 无推理架构+GRPO,<60%数据量保持竞争性能 | ✅ CVPR 2026 |
| **FLARE: Learning Future-Aware Latent Representations from VLMs** | Xie et al. | [arXiv](https://arxiv.org/abs/2601.05611) | - | TRAIN-Data | 自监督潜在动作预测,无语言标注训练实时视觉网络 | 🔶 Preprint 2026 |
| **Impromptu VLA: Curating High-Quality Video Clips** | Chi et al. | [arXiv](https://arxiv.org/abs/2505.23757) | - | TRAIN-Data | 数百万样本精选8万高质量片段,聚焦罕见关键案例 | 🔶 Preprint 2025 |
| **CoVLA: Automatic Generation of VLA Pairs via MLLMs** | Arai et al. | [arXiv](https://arxiv.org/abs/2408.10845) | - | TRAIN-Data | MLLM自动生成大规模VLA配对,降低人工标注成本 | 🔶 Preprint 2024 |
| **Direct Preference Optimization (DPO)** | Rafailov et al. | [arXiv](https://arxiv.org/abs/2305.18290) | - | TRAIN-RL | 无显式奖励模型的偏好优化基础，转化为监督分类 | 🔶 Preprint 2023 |
| **DeepSeekMath (GRPO)** | Shao et al. | [arXiv](https://arxiv.org/abs/2402.03300) | - | TRAIN-RL | Group-Relative Policy Optimization基础，通过组内归一化稳定奖励估计 | 🔶 Preprint 2024 |
| **VDRive: Leveraging Reinforced VLA and Diffusion Policy** | Guo et al. | [arXiv](https://arxiv.org/abs/2510.15446) | - | TRAIN-RL | Actor-critic RL微调+扩散动作头，SOTA Bench2Drive | 🔶 Preprint 2025 |
| **TakeVLA: Post-Training for Driving VLA with Takeover Data** | Gao et al. | [arXiv](https://arxiv.org/abs/2603.14972) | - | TRAIN-RL | 接管前语言监督+"Scenario Dreaming"主动偏好优化 | 🔶 Preprint 2026 |
| **AutoDrive-R²: Incentivizing Reasoning and Self-Reflection** | Yuan et al. | [arXiv](https://arxiv.org/abs/2509.01944) | - | TRAIN-RL | 结合物理先验奖励的GRPO，大幅提升泛化性 | 🔶 Preprint 2025 |
| **VLA-RFT: Reinforcement Fine-Tuning with Verified Rewards** | Li et al. | [arXiv](https://arxiv.org/abs/2510.00406) | - | TRAIN-RL | 世界模拟器内验证密集奖励,最少RL步数超越监督基线 | 🔶 Preprint 2025 |
| **GAIA-1: A Generative World Model for Autonomous Driving** | Hu et al. (Wayve) | [arXiv](https://arxiv.org/abs/2309.17080) | - | TRAIN-WM | 基础原生世界模型,动作条件视频合成离散token流 | 🔶 Preprint 2023 |
| **Drive-WM: Towards World Models for Autonomous Driving** | Wang et al. | [arXiv](https://arxiv.org/abs/2311.17918) | - | TRAIN-WM | 神经模拟器生成多视角反事实rollout，并与规划耦合 | ✅ CVPR 2024 |
| **DriveVLA-W0: World Models Amplify Data Scaling Law** | Li et al. | [arXiv](https://arxiv.org/abs/2510.12796) | - | TRAIN-WM | 世界建模目标直接放大VLA数据缩放律曲线 | 🔶 Preprint 2025 |
| **DriveWorld-VLA: Unified Latent-Space World Modeling** | Jia et al. | [arXiv](https://arxiv.org/abs/2602.06521) | - | TRAIN-WM | 统一潜在空间世界建模,特征级别想象减少像素级幻觉 | 🔶 Preprint 2026 |
| **VLA-World: Learning Vision-Language-Action World Models** | Wang et al. | [arXiv](https://arxiv.org/abs/2604.09059) | - | TRAIN-WM | act→imagine→reflect的闭环修正推理三阶段pipeline | ✅ CVPR 2026 |
| **OmniDrive: Holistic LLM-Agent Framework with 3D Perception** | Wang et al. (NVIDIA) | [arXiv](https://arxiv.org/abs/2405.01533) | [GitHub](https://github.com/NVlabs/OmniDrive) | TRAIN-WM | 离线反事实语言监督,生成结构化"what-if"注释 | 🔶 Preprint 2024 |
| **PhyGenesis: Toward Physically Consistent Driving Video World Models** | Zhou et al. | [arXiv](https://arxiv.org/abs/2603.24506) | - | TRAIN-WM | 挑战性轨迹下物理一致性的视频生成，致力于缓解世界模型幻觉 | 🔶 Preprint 2026 |

### ⚡ Inference Efficiency (推理效率)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **Efficient Memory Management for LLM Serving with PagedAttention** | Kwon et al. (UCB) | [arXiv](https://arxiv.org/abs/2309.06180) | [GitHub](https://github.com/vllm-project/vllm) | INFER-KVCache | PagedAttention减少内存碎片,多视角VLA部署的核心内存基建 | ✅ SOSP 2023 |
| **DriveVLA-W0 (Inference-side): Lightweight Action Expert** | Li et al. | [arXiv](https://arxiv.org/abs/2510.12796) | - | INFER-KVCache | 轻量级Action Expert从沉重的世界模型骨干中解耦，限制部署期峰值内存 | 🔶 Preprint 2025 |
| **Reasoning-VLA: A Fast and General VLA Reasoning Model** | Zhang et al. | [arXiv](https://arxiv.org/abs/2511.19912) | - | INFER-NonAR | AD原生非自回归：可学习Action Queries实现单次前向传播连续轨迹输出 | 🔶 Preprint 2025 |
| **Fast Inference from Transformers via Speculative Decoding** | Leviathan et al. | - | - | INFER-Speculative | 基础的草稿-验证投机解码机制，定义了精确分布等效性保证 | ✅ ICML 2023 |
| **Accelerating LLM Decoding with Speculative Sampling** | Chen et al. | [arXiv](https://arxiv.org/abs/2302.01318) | - | INFER-Speculative | 在大规模(70B)模型上验证并行的投机采样基础架构 | 🔶 Preprint 2023 |
| **Spec-VLA: Speculative Decoding for VLA Models** | Wang et al. | - | - | INFER-Speculative | 机器人领域先驱：放宽接受准则,在动作空间内容忍功能等价token | ✅ EMNLP 2025 |
| **KERV: Kinematic-Rectified Speculative Decoding for Embodied VLA** | Zheng et al. | - | - | INFER-Speculative | Kalman滤波器运动学补偿被拒的草稿token,将物理先验注入验证循环 | ✅ DAC 2026 |

### 🖥️ Deployment Efficiency (部署效率)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **Distilling the Knowledge in a Neural Network** | Hinton et al. | [arXiv](https://arxiv.org/abs/1503.02531) | - | DEPLOY-Distill | 知识蒸馏的奠基性工作，支持将大模型能力迁移至轻量学生模型 | 🔶 Preprint 2015 |
| **Searching for MobileNetV3** | Howard et al. | - | - | DEPLOY-HW | 面向移动端与边缘硬件CPU的硬件感知架构搜索(NAS)基础 | ✅ ICCV 2019 |
| **SQAP-VLA: Quantization-Aware Pruning for VLA** | Fang et al. | [arXiv](https://arxiv.org/abs/2509.09090) | - | DEPLOY-Quant | 无需重训练的量化感知剪枝协同设计，转移至具身VLA加速 | 🔶 Preprint 2025 |
| **BitVLA: 1-bit Vision-Language-Action Models** | Wang et al. | [arXiv](https://arxiv.org/abs/2506.07530) | - | DEPLOY-Quant | 极端1-bit VLA预训练目标+量化蒸馏视觉编码器，11×内存下降 | 🔶 Preprint 2025 |
| **EvoDriveVLA: Evolving Autonomous Driving VLA** | Cao et al. | [arXiv](https://arxiv.org/abs/2603.09465) | - | DEPLOY-Distill | 协同感知-规划蒸馏,压缩同族学生模型并保持长期物理稳定性 | 🔶 Preprint 2026 |
| **VERDI: Distilling VLM Reasoning into Lightweight AD Stack** | Feng et al. | [arXiv](https://arxiv.org/abs/2505.15925) | - | DEPLOY-Distill | 跨族蒸馏：离线提取VLM推理至模块化AD中，运行时零VLM开销 | 🔶 Preprint 2025 |
| **NVIDIA DRIVE Alpamayo-R1** | NVIDIA | [arXiv](https://arxiv.org/abs/2511.00088) | - | DEPLOY-System | VLA车载部署的工业级存在证明(0.5-7B)，验证闭环长尾安全容限 | ⚙️ Industry 2025 |
| **DriveVLM-Dual: Dual-Process Architecture** | Tian et al. (清华) | [arXiv](https://arxiv.org/abs/2402.12289) | [GitHub](https://github.com/tsinghua-fib-lab/DriveVLM) | DEPLOY-System | 快速反应层+慢速推理层,通过解耦界定延迟上限(实车部署验证) | 🔶 Preprint 2024 |
| **SafeAuto: Knowledge-Enhanced Safe Autonomous Driving** | Zhang et al. | [arXiv](https://arxiv.org/abs/2503.00211) | - | DEPLOY-Safety | 形式化马尔可夫逻辑网络安全验证+多模态RAG，内嵌于训练流程 | 🔶 Preprint 2025 |

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
| **Impromptu VLA Dataset: 80K Curated Clips** | Chi et al. | [arXiv](https://arxiv.org/abs/2505.23757) | - | DATASET-Curated | 聚合精选8万罕见关键事件片段 | 🔶 Preprint 2025 |

### 📚 Survey Papers (综述论文)

| 论文标题 | 作者/机构 | 论文链接 | 项目链接 | 类别 | 一句话概况 | 状态 |
|---|---|:---:|:---:|---|---|:---:|
| **Vision Language Models in Autonomous Driving: A Survey** | Zhou et al. (TUM) | [IEEE T-IV](https://doi.org/10.1109/TIV.2024.3402136) | [GitHub](https://github.com/IrohXu/Awesome-VLM-AD) | SURVEY-VLM-AD | VLM在AD中的系统综述,覆盖感知/规划/决策 | ✅ IEEE T-IV 2024 |
| **A Survey on Efficient Vision-Language-Action Models** | Yu et al. (UESTC) | [arXiv](https://arxiv.org/abs/2510.24795) | [GitHub](https://github.com/zhaoshuyuustc/Efficient-VLA) | SURVEY-Efficient | 通用VLA效率综述,包含机器人与具身AI | 🔶 Preprint 2025 |
| **Efficient VLA Models for Embodied Manipulation** | Guan et al. | [arXiv](https://arxiv.org/abs/2510.17111) | - | SURVEY-Manipulate | 聚焦具身操控系统与机器人领域效率 | 🔶 Preprint 2025 |

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
| **OmniDrive: Holistic LLM-Agent Framework** | Wang et al. (NVIDIA) | [arXiv](https://arxiv.org/abs/2405.01533) | [GitHub](https://github.com/NVlabs/OmniDrive) | SYSTEM-E2E | 3D感知+推理+规划的全栈LLM智能体 | 🔶 Preprint 2024 |
| **RAG-Driver: Generalisable Driving Explanations with RAG** | Yuan et al. (Oxford) | [arXiv](https://arxiv.org/abs/2402.10828) | - | SYSTEM-Assistant | RAG增强MLLM,上下文学习提升泛化能力 | 🔶 Preprint 2024 |
| **EM-VLM4AD: Multi-Frame, Lightweight & Efficient VLMs** | Gopalkrishnan | [arXiv](https://arxiv.org/abs/2403.19838) | - | SYSTEM-Assistant | AD场景多帧QA轻量级系统(250M/770M) | 🔶 Preprint 2024 |

---

## 📈 统计与趋势分析

### 时间分布

| 年份 | 论文数量 | 占比 | 代表性里程碑 |
|:---:|:---:|:---:|---|
| **2015-2020** | 6 | 5% | 跨域效率根基 (NAS, KD, Early-Exit, 稀疏MoE) 奠定效率原语 |
| **2021-2022** | 11 | 10% | LoRA, TransFuser, 动态Token削减与多模态潜在融合等端到端基线 |
| **2023** | 17 | 15% | Mamba, GAIA-1, VLA概念初步形成 (RT-2, DriveGPT4), Speculative Decoding 出现 |
| **2024** | 25 | 22% | 首批 AD-VLA 系统涌现 (LMDrive, DriveVLM), Mamba 跨域扩散与世界模型爆发 |
| **2025** | 27 | 24% | 效率优化研究爆发 (Token Pruning, Speculative Decoding, GMF-Drive), 部署系统落地 |
| **2026** | 28 | 24% | 闭环对齐与量化落地 (Online-RL, LoRA-SP, 极端1-bit量化, 安全边界验证) |
| **总计** | **114** | **100%** | |

### 类别分布

| 类别 | 论文数量 | 占比 | 核心研究方向 (Top 关键词) |
|---|:---:|:---:|---|
| **ARCH** | 29 | 25% | SSM (Mamba家族), Token Reduction, MoE, Intra-Model Sparsity (早退/跳层) |
| **TRAIN** | 26 | 23% | PEFT (LoRA/SP), World Model, RL Alignment (GRPO/DPO), Data Curation |
| **INFER** | 12 | 11% | Diffusion Policy, Speculative Decoding (草稿-验证), Non-AR, KV Cache |
| **DEPLOY** | 14 | 12% | Quantization (1-bit), Distillation, Hardware-Aware (NAS), Safety (CBF/Logic) |
| **DATASET** | 13 | 11% | nuScenes, Waymo, NAVSIM, Bench2Drive |
| **SURVEY** | 6 | 5% | VLA-AD, Efficient VLA, World Models |
| **SYSTEM** | 14 | 13% | End-to-End, Dual-Process, Full-Stack Agents |
| **总计** | **114** | **100%** | |

### Mamba / SSM 方向专项追踪

自动驾驶领域的 State Space Model 工作正处于高速迭代期，已形成明确子方向：

| 子方向 | 代表工作 | 典型贡献 |
|---|---|---|
| **(a) 跨域视觉主干** | Vision Mamba, EfficientVMamba, VL-Mamba | 证明 Mamba 可做视觉/多模态编码 |
| **(b) BEV 时序感知** | MambaBEV | TemporalMamba + Mamba-DETR 替代可变形注意力 |
| **(c) 多模态 BEV 融合** | DRAMA, GMF-Drive | Mamba 作为相机+LiDAR 融合骨干 |
| **(d) 端到端 SSM 解码** | DriveMamba | Trajectory-Guided 扫描 + 统一 Mamba 解码器 |

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

- **2026-04-29**: 根据 IEEE 综述文献 (Empowering Embodied AI for Autonomous Driving...) 与引用库进行了重大扩展，补齐了跨领域的效率奠基工作 (Cross-domain Roots)，全面打通数据流向。新增 **21 篇** 跨域及核心演进文献：涵盖早退/架构搜索 (BranchyNet, MobileNetV3)、稀疏MoE架构 (Sparsely-Gated MoE, Switch Transformers, ST-MoE)、Token压缩先驱 (TokenLearner, ToMe, FastV, LLaVA-PruMerge)、动态深度与投机解码 (Depth-Adaptive Transformer, Leviathan, Chen)、RL对齐与微调 (DPO, GRPO, LoRA-SP)、量化蒸馏 (Hinton) 等。整体数据覆盖年份从 2021 前推至 2015。总论文库容量达到 114 篇。
- **2026-04-28**: 新增 SSM/Mamba-for-AD 专项追踪：补充 Vision Mamba, EfficientVMamba, VL-Mamba, DRAMA, MambaBEV, GMF-Drive 6 篇论文；修正 DriveMamba 状态为 ICLR 2026；新增 TransFuser, DiffusionDrive, GoalFlow, Raw2Drive, ReCogDrive 5 篇对比基线。总计论文数 82 → 93。
- **2026-04-22**: 初始数据库发布，核心收录 82 篇领域代表性论文。

---

## 📝 使用建议

1. **学术引用规范**: 优先引用带有 ✅ Published 标识的同行评审论文；若引用 🔶 Preprint 论文，强烈建议附加 `(arXiv preprint, not peer-reviewed)` 注释。
2. **定量指标核查**: 在横向对比推理延迟 (Latency)、吞吐量 (FPS) 或模型体积压缩比时，务必回溯原论文查证具体的硬件测试环境与超参数设定（尤其是 NAVSIM PDMS 数字在不同 backbone / 传感器配置下不可直接比较）。
3. **开源优先级**: 对于需要复现的工程项目，建议优先考察附有 `[GitHub]` 链接且持续维护的工作。
4. **保持关注**: 2025–2026 年的多数论文处于投稿或大修（Revision）阶段，其最终版本结论可能发生微调，请持续追踪最新版本。
5. **SSM 方向追踪**: 自动驾驶领域的 State Space Model 工作正处于高速迭代期（2024 年起每 3-4 个月出现新方向），建议每季度回访 `ARCH-SSM+AD` 类别以获取最新工作。已知活跃子方向见上文 "Mamba / SSM 方向专项追踪" 表。
6. **"全球首个"类宣传语谨慎**: 若某论文自称"首个 Mamba 端到端 SOTA"（如 GMF-Drive 的宣传），请对照本数据库的时间线核查，避免误引用。
7. **效率与长尾验证评估**: 当采用或对比列表中的压缩与裁剪技术时，建议高度关注论文是否执行了独立的长尾场景安全测试，并区分“基于平均帧准确度的性能评估”与“极端环境（如$p95/p99$延迟毛刺）的闭环容错能力”。

---
*Created and maintained with ❤️ by the AD/Embodied AI Research Community.*
*如发现链接失效或遗漏重要论文，欢迎提交 Issue 或 PR!*
