diff --git a/README.md b/README.md
index 806ccc29b20c0e32277cd8a745a8fc454aa8f1ee..c7d89607454179f73cd53d0ee99fba64d5b3e952 100644
--- a/README.md
+++ b/README.md
@@ -17,130 +17,136 @@ In particular, we focus on the **Data-Strategy-Platform** framework for E2E-AD s
 
 - **Data Layer**: Addressing data collection, coverage, and governance practices.
 - **Strategy Layer**: Exploring imitation learning, reinforcement learning, and generative approaches.
 - **Platform Layer**: Understanding scalable training infrastructures and cloud-edge collaborations.
 
 Each paper in this repository has been selected for its relevance and contribution to the field, and we hope it serves as a valuable resource for anyone working in or learning about autonomous driving technology.
 
 ---
 
 #### Contributions are welcome! Please feel free to submit pull requests or reach out via email to add papers!
 
 Feel free to explore the papers, contribute, and stay updated with the latest trends in this exciting and rapidly advancing field! If you find this repository useful, please consider citing and STARing this list ⭐. Feel free to share this list with others!
 
 ---
 
 
 
 ## 📌 Framework
 
 <div align="center">
 <img src="./assets/Fig_framework.png" width="100%" alt="Framework Overview">
 </div>
 
 
 
+
+## 🧪 Experimental Playbook
+
+- [Scene-Adaptive Hierarchical RL Pruning Plan (Autonomous-Driving VLA)](docs/scene_adaptive_hierarchical_rl_experiment_plan.md)
+
+---
+
 ## Table of Contents
 
 - [Survey paper](#survey-paper)
 - [Research Papers](#research-papers) 
   - [Data Layer](#data-layer)
     - [Sources and Scenario Coverage](#Sources-and-Scenario-Coverage)
     - [Supervision and Alignment of Labels](#Supervision-and-Alignment-of-Labels)
     - [Data Valuation and Governance](#Data-Valuation-and-Governance)
   - [Strategy Layer](#strategy-layer)
     - [Imitation Learning](#Imitation-Learning)
     - [Reinforcement Learning](#Reinforcement-Learning)
     - [Diffusion Policy](#Diffusion-Policy)
     - [Multimodal Large Language Model](#Multimodal-Large-Language-Model)
     - [World Model](#World-Model)
   - [Platform Layer](#platform-layer)
     - [Distributed and Parallel Training Platform](#Distributed-and-Parallel-Training-Platform)
     - [Testing and Evaluation Platform](#Testing-and-Evaluation-Platform)
 - [Datasets & Benchmarks](#Datasets-&-Benchmarks)
 - [Other Awesome Lists](#Other-Awesome-Lists)
 - [Citation](#Citation)
 
 
 
 ---
 
 ### **📚Survey Papers**
 #### **AD**
 
 | **Title**                                                    |   **Year**    |    **Categories**     |                         **Project**                          |
 | :----------------------------------------------------------- | :-----------: | :-------------------: | :----------------------------------------------------------: |
 | [End-to-end Autonomous Driving: Challenges and Frontiers](https://ieeexplore.ieee.org/abstract/document/10614862) |  TPAMI 2025   |      End to End       | [Project](https://github.com/OpenDriveLab/End-to-end-Autonomous-Driving) |
 | [A Survey of World Models for Autonomous Driving](https://arxiv.org/abs/2501.11260) |  Arxiv 2025   |      World Model      | [Project](https://github.com/FengZicai/AwesomeWMAD) / [Benchmark](https://github.com/FengZicai/WMAD-Benchmarks) |
 | [Generative AI for Autonomous Driving: Frontiers and Opportunities](https://arxiv.org/abs/2505.08854) |  Arxiv 2025   |     Generative AI     |      [Project](https://github.com/taco-group/GenAI4AD)       |
 | [World models for autonomous driving: An initial survey](https://ieeexplore.ieee.org/abstract/document/10522953/) |   TIV 2024    |      World Model      |                                                              |
 | [Synthetic datasets for autonomous driving: A survey](https://ieeexplore.ieee.org/abstract/document/10313052/) |   TIV 2023    |       Datasets        |                                                              |
 | [Explainable AI for safe and trustworthy autonomous driving: A systematic review](https://ieeexplore.ieee.org/abstract/document/10716567/) |   TITS 2024   |          XAI          |                                                              |
 | [On the Prospects of Incorporating Large Language Models (LLMs) in Automated Planning and Scheduling](https://ojs.aaai.org/index.php/ICAPS/article/view/31503) |  ICAPS 2024   | Large Language Models |  [Project](https://ai4society.github.io/LLM-Planning-Viz/)   |
 | [Prospective role of foundation models in advancing autonomous vehicles](https://spj.science.org/doi/full/10.34133/research.0399) | Research 2024 |   Foundation Models   |                                                              |
 | [Large models for intelligent transportation systems and autonomous vehicles: A survey](https://www.sciencedirect.com/science/article/pii/S1474034624004348) |   AEI 2024    |   Foundation Models   |                                                              |
 | [Vision language models in autonomous driving: A survey and outlook](https://ieeexplore.ieee.org/abstract/document/10531702/) |    IV 2024    |   Foundation Models   |   [Project](https://github.com/ge25nab/Awesome-VLM-AD-ITS)   |
 | [A Survey on Multimodal Large Language Models for Autonomous Driving](https://openaccess.thecvf.com/content/WACV2024W/LLVM-AD/html/Cui_A_Survey_on_Multimodal_Large_Language_Models_for_Autonomous_Driving_WACVW_2024_paper.html) |   WACV 2024   |   Foundation Models   |                                                              |
 | [A survey for foundation models in autonomous driving](https://arxiv.org/abs/2402.01105) |  Arxiv 2024   |   Foundation Models   |                                                              |
 | [Forging Vision Foundation Models for Autonomous Driving: Challenges, Methodologies, and Opportunities](https://arxiv.org/abs/2401.08045) |  Arxiv 2024   |   Foundation Models   |                                                              |
 | [Llm4drive: A survey of large language models for autonomous driving](https://arxiv.org/abs/2311.01043) |  Arxiv 2023   | Large Language Models |  [Project](https://github.com/Thinklab-SJTU/Awesome-LLM4AD)  |
 | [V2X cooperative perception for autonomous driving: Recent advances and challenges](https://arxiv.org/abs/2310.03525) |  Arxiv 2023   |       Datasets        |                                                              |
 | [Learning-based 3D Reconstruction in Autonomous Driving: A Comprehensive Survey](https://arxiv.org/abs/2503.14537) |  Arxiv 2025   |       Datasets        |                                                              |
-|A review on reinforcement learning-based highway autonomous  vehicle control|Machine Learning for Autonomous Vehicle’s  Trajectory Prediction: A comprehensive survey,  Challenges, and Future Research Directions|
 #### **Efficient VLA**
 
-| **Title**                                                    |   **Year**    |    **Categories**     |                         **Project**                          |
-| :----------------------------------------------------------- | :-----------: | :-------------------: | :----------------------------------------------------------: |
-| [A Survey on Efficient Vision-Language-Action Models](https://ieeexplore.ieee.org/abstract/document/10614862) |  Arxiv 2025   |      Efficient VLA General       | [Project](https://github.com/YuZhaoshu/Efficient-VLAs-Survey) |
-| [Efficient Vision-Language-Action Models for Embodied Manipulation: A Systematic Survey](https://arxiv.org/pdf/2510.17111) |   Arxiv 2025   |      Efficient VLA General       | [Project](https://github.com/guanweifan/awesome-efficient-vla) |
-         
-[23] Y. Ma, Z. Song, Y. Zhuang, J. Hao, and I. King, “A survey on
-vision-language-action models for embodied ai,” arXiv preprint
-arXiv:2405.14093, 2024.
-[24] R. Shao, W. Li, L. Zhang, R. Zhang, Z. Liu, R. Chen, and L. Nie,
-“Large vlm-based vision-language-action models for robotic ma
-nipulation: A survey,” arXiv preprint arXiv:2508.13073, 2025.
-[25] T.-Y. Xiang, A.-Q. Jin, X.-H. Zhou, M.-J. Gui, X.-L. Xie, S.-Q. Liu,
-S.-Y. Wang, S.-B. Duan, F.-C. Xie, W.-K. Wang et al., “Parallels
-between vla model post-training and human motor learning:
-Progress, challenges, and trends,” arXiv preprint arXiv:2506.20966,
-2025.
-[26] Y. Zhong, F. Bai, S. Cai, X. Huang, Z. Chen, X. Zhang, Y. Wang,
-S. Guo, T. Guan, K. N. Lui et al., “A survey on vision-language
-action models: An action tokenization perspective,” arXiv preprint
-arXiv:2507.01925, 2025.
-[27] M. U. Din, W. Akram, L. S. Saoud, J. Rosell, and I. Hussain,
-“Vision language action models in robotic manipulation: A sys
-tematic review,” arXiv preprint arXiv:2507.10672, 2025.
-[28] D. Zhang, J. Sun, C. Hu, X. Wu, Z. Yuan, R. Zhou, F. Shen,
-and Q. Zhou, “Pure vision language action (vla) models: A
-comprehensive survey,” arXiv preprint arXiv:2509.19012, 2025.
----
-#### **Efficient LLM/VLN**
-A Review on Edge Large Language Models: Design, Execution, and Application  https://arxiv.org/abs/2410.11845
-On-Device Language Models: A Comprehensive Review
-A Survey on Efficient Inference for Large Language Models
+> ✅ Curated for **EFFICIENT VLA4AD**. Split into **General-Purpose** vs **AD-Specific** works.
+
+##### General-Purpose Efficient VLM/VLA (Non-AD)
+
+| **Title** | **Venue/Year** | **Category** | **Link / Project** |
+| :--- | :---: | :--- | :--- |
+| [DynamicViT: Efficient Vision Transformers with Dynamic Token Sparsification](https://proceedings.neurips.cc/paper/2021/file/747d3443e319a22747fbb873e8b2f9f2-Paper.pdf) | NeurIPS 2021 | Token Pruning (Vision) | Paper |
+| [Zero-Shot Token Pruning through Leveraging of the Attention Graph in Pre-Trained Transformers](https://openaccess.thecvf.com/content/CVPR2024/papers/Wang_Zero-Shot_Token_Pruning_through_Leveraging_of_the_Attention_Graph_CVPR_2024_paper.pdf) | CVPR 2024 | Training-free Token Pruning | Paper |
+| [ATP-LLaVA: Adaptive Token Pruning for Large Vision Language Models](https://openaccess.thecvf.com/content/CVPR2025/papers/Ye_ATP-LLaVA_Adaptive_Token_Pruning_for_Large_Vision_Language_Models_CVPR_2025_paper.pdf) | CVPR 2025 | LVLM Adaptive Pruning | Paper |
+| [LVPruning: Language-Guided Vision Token Pruning](https://aclanthology.org/2025.findings-naacl.242.pdf) | Findings of NAACL 2025 | Language-guided Pruning | Paper |
+| [A Survey on Vision-Language-Action Models for Embodied AI](https://arxiv.org/abs/2405.14093) | arXiv 2024 | VLA Survey (General) | Paper |
+| [A Survey on Vision-Language-Action Models: An Action Tokenization Perspective](https://arxiv.org/abs/2507.01925) | arXiv 2025 | VLA Survey (General) | Paper |
+| [Efficient Vision-Language-Action Models for Embodied Manipulation: A Systematic Survey](https://arxiv.org/abs/2510.17111) | arXiv 2025 | Efficient VLA Survey (General) | [Project](https://github.com/guanweifan/awesome-efficient-vla) |
+
+##### Autonomous-Driving-Specific Efficient VLA / VLM
+
+| **Title** | **Venue/Year** | **Category** | **Link / Project** |
+| :--- | :---: | :--- | :--- |
+| [CoVLA: Comprehensive Vision-Language-Action Dataset for Autonomous Driving](https://openaccess.thecvf.com/content/WACV2025/papers/Arai_CoVLA_Comprehensive_Vision-Language-Action_Dataset_for_Autonomous_Driving_WACV_2025_paper.pdf) | WACV 2025 | AD VLA Dataset/Benchmark | [Project](https://turingmotors.github.io/covla-ad/) |
+| [FastDriveVLA: Efficient End-to-End Driving via Plug-and-Play Reconstruction-based Token Pruning](https://arxiv.org/abs/2507.23318) | arXiv 2025 | AD-specific Token Pruning | Paper |
+| [The Better You Learn, The Smarter You Prune: Towards Efficient Vision-language-action Models via Differentiable Token Pruning (LightVLA)](https://arxiv.org/abs/2509.12594) | arXiv 2025 | AD-specific Differentiable Pruning | Paper |
+| [LatentVLA: Efficient Vision-Language Models for Autonomous Driving via Latent Action Prediction](https://arxiv.org/abs/2601.05611) | arXiv 2026 | AD-efficient VLA | Paper |
+| [FROST-Drive: Scalable and Efficient End-to-End Driving with a Frozen Vision Encoder](https://arxiv.org/abs/2601.03460) | arXiv 2026 | AD-efficient Backbone/Training | Paper |
+| [A Vision-Language-Action Model with Visual Prompt for OFF-Road Autonomous Driving (OFF-EMMA)](https://arxiv.org/abs/2601.03519) | arXiv 2026 | AD-specific VLA Efficiency | Paper |
+
+##### Efficient LLM/VLM Systems (General, optional reference)
+
+| **Title** | **Year** | **Category** | **Link** |
+| :--- | :---: | :--- | :--- |
+| [A Review on Edge Large Language Models: Design, Execution, and Application](https://arxiv.org/abs/2410.11845) | 2024 | Edge LLM Systems | Paper |
+
 ### **📄Research Papers**
 
 ### **Data Layer**
 
 #### **Sources and Scenario Coverage**
 
 | Title                                                        | Abstract                                       | Year       | Project                                                      |
 | ------------------------------------------------------------ | ---------------------------------------------- | ---------- | ------------------------------------------------------------ |
 | [WOD-E2E: Waymo Open Dataset for End-to-End Driving in Challenging Long-tail Scenarios](https://arxiv.org/abs/2510.26125) | <details><summary>Details</summary> </details> | Arxiv 2025 | [Project](https://waymo.com/intl/jp/open/data/e2e/)          |
 | [Simscale: Learning to drive via real-world simulation at scale](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=iizqKUsAAAAJ&sortby=pubdate&citation_for_view=iizqKUsAAAAJ:hC7cP41nSMkC) | <details><summary>Details</summary> </details> | Arxiv 2025 | [Project](https://opendrivelab.com/SimScale/)                |
 | [CoVLA: Comprehensive Vision-Language-Action Dataset for Autonomous Driving](https://openaccess.thecvf.com/content/WACV2025/papers/Arai_CoVLA_Comprehensive_Vision-Language-Action_Dataset_for_Autonomous_Driving_WACV_2025_paper.pdf) | <details><summary>Details</summary> </details> | WACV 2025  | [Project](https://turingmotors.github.io/covla-ad/)          |
 | [Argoverse 2: Next generation datasets for self-driving perception and forecasting](https://arxiv.org/abs/2301.00493) | <details><summary>Details</summary> </details> | Arxiv 2023 | [Project](https://www.argoverse.org/av2.html)                |
 | [WOMD-Reasoning: A Large-Scale Dataset for Interaction Reasoning in Driving](https://arxiv.org/abs/2407.04281) | <details><summary>Details</summary> </details> | ICML 2025  | [Code](https://github.com/yhli123/WOMD-Reasoning) / [Project](https://waymo.com/open/download) |
 | [nuscenes: A multimodal dataset for autonomous driving](http://openaccess.thecvf.com/content_CVPR_2020/html/Caesar_nuScenes_A_Multimodal_Dataset_for_Autonomous_Driving_CVPR_2020_paper.html) | <details><summary>Details</summary> </details> | CVPR 2020  | [Project](https://www.nuscenes.org/)                         |
 | [One million scenes for autonomous driving: Once dataset](https://arxiv.org/abs/2106.11037) | <details><summary>Details</summary> </details> | Arxiv 2021 | [Project](https://once-for-auto-driving.github.io/index.html) |
 | [Scalability in perception for autonomous driving: Waymo open dataset](http://openaccess.thecvf.com/content_CVPR_2020/html/Sun_Scalability_in_Perception_for_Autonomous_Driving_Waymo_Open_Dataset_CVPR_2020_paper.html) | <details><summary>Details</summary> </details> | CVPR 2020  | [Project](http://www. waymo. com/open)                       |
 | [Zenseact open dataset: A large-scale and diverse multimodal dataset for](http://openaccess.thecvf.com/content/ICCV2023/html/Alibeigi_Zenseact_Open_Dataset_A_Large-Scale_and_Diverse_Multimodal_Dataset_for_ICCV_2023_paper.html) | <details><summary>Details</summary> </details> | ICCV 2023  | [Project](zod.zenseact.com)                                  |
 | [Scaling out-of-distribution detection for real-world settings](https://arxiv.org/abs/1911.11132) | <details><summary>Details</summary> </details> | PMLR 2022  | [Code](https://github.com/hendrycks/anomaly-seg)             |
 | [SHIFT: a synthetic driving dataset for continuous multi-task domain adaptation](http://openaccess.thecvf.com/content/CVPR2022/html/Sun_SHIFT_A_Synthetic_Driving_Dataset_for_Continuous_Multi-Task_Domain_Adaptation_CVPR_2022_paper.html) | <details><summary>Details</summary> </details> | CVPR 2022  | [Project](https://www.vis.xyz/shift.)                        |
 | [V2x-vit: Vehicle-to-everything cooperative perception with vision transformer](https://link.springer.com/chapter/10.1007/978-3-031-19842-7_7) | <details><summary>Details</summary> </details> | ECCV 2022  | [Code](https://github.com/DerrickXuNu/v2x-vit)               |
 | [Deepaccident: A motion and accident prediction benchmark for v2x autonomous driving](https://ojs.aaai.org/index.php/AAAI/article/view/28370) | <details><summary>Details</summary> </details> | AAAI 2024  | [Project]()                                                  |
 | [Bdd100k: A diverse driving dataset for heterogeneous multitask learning](http://openaccess.thecvf.com/content_CVPR_2020/html/Yu_BDD100K_A_Diverse_Driving_Dataset_for_Heterogeneous_Multitask_Learning_CVPR_2020_paper.html) | <details><summary>Details</summary> </details> | CVPR 2020  | [Project](https://bair.berkeley.edu/blog/2018/05/30/bdd/)    |
 | [The apolloscape dataset for autonomous driving](https://openaccess.thecvf.com/content_cvpr_2018_workshops/w14/html/Huang_The_ApolloScape_Dataset_CVPR_2018_paper.html?ref=https://githubhelp.com) | <details><summary>Details</summary> </details> | CVPR 2018  | [Prioject](https://apolloscape.auto/)                        |
 | [Tumtraf v2x cooperative perception dataset](http://openaccess.thecvf.com/content/CVPR2024/html/Zimmer_TUMTraf_V2X_Cooperative_Perception_Dataset_CVPR_2024_paper.html) | <details><summary>Details</summary> </details> | CVPR 2024  | [Project](https://tum-traffic-dataset.github.io/tumtraf-v2x/) |
 | [Tumtraf intersection dataset: All you need for urban 3d camera-lidar roadside perception](https://ieeexplore.ieee.org/abstract/document/10422289/) | <details><summary>Details</summary> </details> | ITSC 2023  | [Code](https://innovation-mobility.com/tumtraf-dataset.)     |
