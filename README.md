# ARC Paper Watch

公开论文精选：视频、三维与具身、智能体、多模态检索、评测及训练推理。每篇附可折叠中文简介与一手来源。

**80 篇论文** · [在线阅读（支持快捷键）](https://ripemangobox.github.io/arc-paper-watch/) · [下载离线阅读器 ZIP](https://ripemangobox.github.io/arc-paper-watch/research-paper-watch.zip) · [唯一数据源](data/papers.json) · [导入与任务接入](docs/INTEGRATION.md)
收录腾讯 ARC 官方 academic 列表中录用年份为 2024 年及以后的全部 80 篇（2024：33，2025：21，2026：26）；首次公开日期可能早于 2024。已读摘要与引言 78 篇；ViewWeaver、Chinese Title Generation 两篇因引言未取得，仅保留待补占位与暂定优先级。研究目标：视频生成核心难题、实时交互 Avatar、世界模型、Agent 规划与记忆。

阅读优先级依据视频生成核心难题、实时交互 Avatar、世界模型、Agent 规划与记忆：**P0 必读 → P1 重点 → P2 选读 → P3 暂缓**。这是课题相关性排序，不是论文质量排名。每篇说明推荐理由；常规阅读范围为 abs + intro。


在线阅读页直接支持搜索、分类、E 全部展开、C 全部收起。离线 ZIP 解压后双击 index.html，无需安装或启动服务器。GitHub README 不运行自定义脚本：可点击简介，或 Tab 聚焦后按 Enter / 空格展开收起；E / C 请使用在线阅读页。

日期为论文首次公开日期；空链接表示尚未核实。简介中的局限包含基于公开证据的阅读边界，不代表作者自述的缺陷。

## 目录

- [视频生成基础](#视频生成基础) · 9
- [交互长视频](#交互长视频) · 1
- [具身与世界模型](#具身与世界模型) · 2
- [交互 Avatar](#交互-avatar) · 1
- [智能体与上下文](#智能体与上下文) · 7
- [多模态检索](#多模态检索) · 3
- [评测与可靠性](#评测与可靠性) · 4
- [训练与推理效率](#训练与推理效率) · 4
- [多模态架构与综述](#多模态架构与综述) · 5
- [三维生成与重建](#三维生成与重建) · 15
- [图像生成与编辑](#图像生成与编辑) · 10
- [视频理解与推理](#视频理解与推理) · 10
- [语音与音频](#语音与音频) · 6
- [视觉感知](#视觉感知) · 3

## 视频生成基础

+ [CubeComposer: Spatio-Temporal Autoregressive 4K 360deg Video Generation from Perspective Video](<https://arxiv.org/abs/2603.04291>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/CubeComposer.svg?style=social&label=Star)](<https://github.com/TencentARC/CubeComposer>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2603.04291>)
  <br>2026-03-04 · 上下文管理 / 全景视频 / 视频生成 / 高分辨率

  **[CVPR 2026](<https://openaccess.thecvf.com/content/CVPR2026/html/Li_CubeComposer_Spatio-Temporal_Autoregressive_4K_360deg_Video_Generation_from_Perspective_Video_CVPR_2026_paper.html>)** · **P1 重点** · 摘要与引言
  适合研究视频空间扩展、上下文管理与计算成本。

  <details>
  <summary>brief</summary>

  - **问题**：全注意力限制全景视频原生分辨率，后超分容易放大误差。
  - **方法**：按覆盖率安排立方体各面及时窗生成，结合稀疏上下文注意力和接缝处理。
  - **价值**：以较低峰值显存生成原生高分辨率全景视频。
  - **局限**：可利用输入未来片段，不应直接视为完全因果的实时世界模型。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2603.04291">[2]</a> · <a href="https://arxiv.org/pdf/2603.04291">[3]</a> · <a href="https://github.com/TencentARC/CubeComposer">[4]</a> · <a href="https://openaccess.thecvf.com/content/CVPR2026/html/Li_CubeComposer_Spatio-Temporal_Autoregressive_4K_360deg_Video_Generation_from_Perspective_Video_CVPR_2026_paper.html">[5]</a>
  核验：2026-10-13

  </details>

+ [GenCompositor: Generative Video Compositing with Diffusion Transformer](<https://arxiv.org/abs/2509.02460>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/GenCompositor.svg?style=social&label=Star)](<https://github.com/TencentARC/GenCompositor>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2509.02460>)
  <br>2025-09-02 · 视频合成 / 视频生成 / 运动控制

  **[ICLR 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  直接关联视频可控性、主体保持及对象与背景交互。

  <details>
  <summary>brief</summary>

  - **问题**：视频合成需同时保持背景、前景身份运动和用户指定布局。
  - **方法**：以背景保留分支、全注意力融合和扩展旋转位置编码注入动态前景。
  - **价值**：支持按轨迹与尺度组合视频，减少人工合成步骤。
  - **局限**：依赖前景素材和控制条件，视觉协调不代表物理正确性。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2509.02460">[2]</a> · <a href="https://arxiv.org/pdf/2509.02460">[3]</a> · <a href="https://github.com/TencentARC/GenCompositor">[4]</a>
  核验：2026-10-13

  </details>

+ [ToonComposer: Streamlining Cartoon Production with Generative Post-Keyframing](<https://arxiv.org/abs/2508.10881>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/ToonComposer.svg?style=social&label=Star)](<https://github.com/TencentARC/ToonComposer>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2508.10881>)
  <br>2025-08-14 · 动画 / 稀疏控制 / 视频生成

  **[ICLR 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  关注稀疏控制与时序先验保护，可借鉴 Avatar 动画生成。

  <details>
  <summary>brief</summary>

  - **问题**：分开补帧与上色容易累积误差，密集草图又增加人工负担。
  - **方法**：统一关键帧后生成，以稀疏草图注入和空间低秩适配保留运动先验。
  - **价值**：少量草图与彩色参考即可控制动画及局部运动。
  - **局限**：面向卡通域和片段生产，尚不直接满足在线低延迟交互。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2508.10881">[2]</a> · <a href="https://arxiv.org/pdf/2508.10881">[3]</a> · <a href="https://github.com/TencentARC/ToonComposer">[4]</a>
  核验：2026-10-13

  </details>

+ [TrajectoryCrafter: Redirecting Camera Trajectory for Monocular Videos via Diffusion Models](<https://arxiv.org/abs/2503.05638>)<br>
  [![Star](https://img.shields.io/github/stars/TrajectoryCrafter/TrajectoryCrafter.svg?style=social&label=Star)](<https://github.com/TrajectoryCrafter/TrajectoryCrafter>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2503.05638>)
  <br>2025-03-07 · 几何一致性 / 相机控制 / 视频生成

  **[ICCV 2025 &#91;Oral&#93;](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  相机可控性和动态场景保持是视频生成核心控制问题。

  <details>
  <summary>brief</summary>

  - **问题**：单目动态视频改换相机路径时，遮挡补全与几何变换容易混淆。
  - **方法**：分离确定性点云重投影与生成补全，以双流条件融合源视频。
  - **价值**：通过双重投影构造训练数据，减少同步多视角视频依赖。
  - **局限**：质量依赖深度与重投影，未观测区域仍是推测性生成。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2503.05638">[2]</a> · <a href="https://arxiv.org/pdf/2503.05638">[3]</a> · <a href="https://github.com/TrajectoryCrafter/TrajectoryCrafter">[4]</a>
  核验：2026-10-13

  </details>

+ [DiTCtrl: Exploring Attention Control in Multi-Modal Diffusion Transformer for Tuning-Free Multi-Prompt Longer Video Generation](<https://arxiv.org/abs/2412.18597>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/DiTCtrl.svg?style=social&label=Star)](<https://github.com/TencentARC/DiTCtrl>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2412.18597>)
  <br>2024-12-24 · 多提示 / 视频生成 / 长时一致性

  **[CVPR 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  多事件视频的主体保持和提示切换是长视频控制的重要基线。

  <details>
  <summary>brief</summary>

  - **问题**：逐提示生成片段会产生身份断裂与不自然过渡。
  - **方法**：分析多模态扩散注意力，通过掩码引导的键值共享和潜变量混合连接片段。
  - **价值**：无需额外训练即可支持多提示连续视频，并提供转场评测。
  - **局限**：离线片段协调不等同于实时输入响应，控制依赖原模型能力。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2412.18597">[2]</a> · <a href="https://arxiv.org/pdf/2412.18597">[3]</a> · <a href="https://github.com/TencentARC/DiTCtrl">[4]</a>
  核验：2026-10-13

  </details>

+ [MiraData: A Large-Scale Video Dataset with Long Durations and Structured Captions](<https://arxiv.org/abs/2407.06358>)<br>
  [![Star](https://img.shields.io/github/stars/mira-space/MiraData.svg?style=social&label=Star)](<https://github.com/mira-space/MiraData>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2407.06358>)
  <br>2024-07-08 · 数据集 / 视频生成 / 评测 / 长时一致性

  **[NeurIPS 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  长视频数据与运动评测直接支撑视频生成核心问题研究。

  <details>
  <summary>brief</summary>

  - **问题**：公开视频常过短、运动弱且描述粗略，限制长视频生成训练。
  - **方法**：筛选语义连续长片段并生成结构化描述，补充三维一致性和轨迹运动指标。
  - **价值**：提供面向长时与强运动生成的数据及评测管线。
  - **局限**：自动描述和代理几何指标存在误差，不能等价于物理正确性评测。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2407.06358">[2]</a> · <a href="https://arxiv.org/pdf/2407.06358">[3]</a> · <a href="https://github.com/mira-space/MiraData">[4]</a>
  核验：2026-10-13

  </details>

+ [ReVideo: Remake a Video with Motion and Content Control](<https://arxiv.org/abs/2405.13865>)<br>
  [![Star](https://img.shields.io/github/stars/MC-E/ReVideo.svg?style=social&label=Star)](<https://github.com/MC-E/ReVideo>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2405.13865>)
  <br>2024-05-22 · 条件解耦 / 视频编辑 / 运动控制

  **[NeurIPS 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  内容与运动解耦是可控视频和 Avatar 的核心设计问题。

  <details>
  <summary>brief</summary>

  - **问题**：局部视频编辑中，密集内容条件会压过稀疏轨迹控制。
  - **方法**：分三阶段解耦训练，以时空自适应融合整合首帧编辑和轨迹条件。
  - **价值**：支持保持内容改运动、保持运动改内容及多区域编辑。
  - **局限**：轨迹依赖人工指定，未直接保证物理合理或实时反馈。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2405.13865">[2]</a> · <a href="https://arxiv.org/pdf/2405.13865">[3]</a> · <a href="https://github.com/MC-E/ReVideo">[4]</a>
  核验：2026-10-13

  </details>

+ [DynVideo-E: Harnessing Dynamic NeRF for Large-Scale Motion- and View-Change Human-Centric Video Editing](<https://arxiv.org/abs/2310.10624>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2310.10624>)
  <br>2023-10-16 · Avatar / 动态三维 / 视频编辑

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  显式动态三维表示如何维持人体视频一致性，适合 Avatar 背景阅读。

  <details>
  <summary>brief</summary>

  - **问题**：大动作和大视角变化使逐帧及二维图集编辑难维持长期一致。
  - **方法**：在动态辐射场中编辑主体与背景，用多视角多姿态蒸馏约束传播。
  - **价值**：将编辑沿形变场传到整个视频并支持新视角。
  - **局限**：依赖逐场景训练及人体姿态结构，距离实时通用交互仍有成本差距。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2310.10624">[2]</a> · <a href="https://arxiv.org/pdf/2310.10624">[3]</a>
  核验：2026-10-13

  </details>

+ [Mono2Stereo: A Benchmark and Empirical Study for Stereo Conversion](<https://arxiv.org/abs/2503.22262>)<br>
  [![Star](https://img.shields.io/github/stars/song2yu/Mono2Stereo.svg?style=social&label=Star)](<https://github.com/song2yu/Mono2Stereo>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2503.22262>)
  <br>2025-03-28 · 立体转换 / 视频生成 / 评测

  **[CVPR 2025](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  补充多视角一致性和感知评价，主要用于立体内容生产。

  <details>
  <summary>brief</summary>

  - **问题**：单目转立体容易在图像质量与有效视差之间失衡。
  - **方法**：构建立体数据集，以双条件和边缘一致性训练模型，并设计视差指标。
  - **价值**：将立体感与整体画质分开衡量。
  - **局限**：立体视差评估不能替代完整三维一致性或长时动态验证。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2503.22262">[2]</a> · <a href="https://arxiv.org/pdf/2503.22262">[3]</a> · <a href="https://github.com/song2yu/Mono2Stereo">[4]</a>
  核验：2026-10-13

  </details>


## 交互长视频

+ [Rolling Forcing: Autoregressive Long Video Diffusion in Real Time](<https://arxiv.org/abs/2509.25161>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/RollingForcing.svg?style=social&label=Star)](<https://github.com/TencentARC/RollingForcing>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2509.25161>)
  <br>2025-09-29 · 世界模型 / 实时交互 / 视频生成 / 长时一致性

  **[ICLR 2026](<https://proceedings.iclr.cc/paper_files/paper/2026/hash/935151cc6cb5d8b6816133b75233775a-Abstract-Conference.html>)** · **P0 必读** · 摘要与引言
  直接研究实时长视频的误差累积与长期一致性，是主线必读。

  <details>
  <summary>brief</summary>

  - **问题**：严格逐帧自回归会不断放大历史误差，远端关键帧规划又阻碍流式输出。
  - **方法**：滚动窗口联合去噪，以初始帧缓存作锚点并在自生成历史上蒸馏。
  - **价值**：兼顾流式输出与多分钟视频一致性。
  - **局限**：窗口内放松因果约束，吞吐提升仍需结合首帧延迟和交互条件评估。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2509.25161">[2]</a> · <a href="https://arxiv.org/pdf/2509.25161">[3]</a> · <a href="https://github.com/TencentARC/RollingForcing">[4]</a> · <a href="https://proceedings.iclr.cc/paper_files/paper/2026/hash/935151cc6cb5d8b6816133b75233775a-Abstract-Conference.html">[5]</a>
  核验：2026-10-13

  </details>


## 具身与世界模型

+ [VerseCrafter: Dynamic Realistic Video World Model with 4D Geometric Control](<https://arxiv.org/abs/2601.05138>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/VerseCrafter.svg?style=social&label=Star)](<https://github.com/TencentARC/VerseCrafter>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2601.05138>)
  <br>2026-01-08 · 4D控制 / 世界模型 / 多对象 / 视频生成

  **[CVPR 2026](<https://openaccess.thecvf.com/content/CVPR2026/html/Zheng_VerseCrafter_Dynamic_Realistic_Video_World_Model_with_4D_Geometric_Control_CVPR_2026_paper.html>)** · **P0 必读** · 摘要与引言
  直接对应世界模型的可编辑状态、相机与多对象联合控制。

  <details>
  <summary>brief</summary>

  - **问题**：二维控制难在大视角变化下统一约束相机和多个对象运动。
  - **方法**：以背景点云及对象三维高斯轨迹表达状态，渲染控制图驱动视频模型。
  - **价值**：提供统一世界坐标中的可编辑视频生成接口。
  - **局限**：轨迹由外部给定，控制忠实度不等于模型自主预测物理动力学。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2601.05138">[2]</a> · <a href="https://arxiv.org/pdf/2601.05138">[3]</a> · <a href="https://github.com/TencentARC/VerseCrafter">[4]</a> · <a href="https://openaccess.thecvf.com/content/CVPR2026/html/Zheng_VerseCrafter_Dynamic_Realistic_Video_World_Model_with_4D_Geometric_Control_CVPR_2026_paper.html">[5]</a>
  核验：2026-10-13

  </details>

+ [Moto: Latent Motion Token as the Bridging Language for Learning Robot Manipulation from Videos](<https://arxiv.org/abs/2412.04445>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/Moto.svg?style=social&label=Star)](<https://github.com/TencentARC/Moto>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2412.04445>)
  <br>2024-12-05 · 世界模型 / 机器人 / 潜在动作 / 视频预训练

  **[ICCV 2025 &#91;Oral&#93;](<https://arc.tencent.com/academic>)** · **P0 必读** · 摘要与引言
  连接视频运动预训练与动作执行，是世界模型和规划交叉的重点。

  <details>
  <summary>brief</summary>

  - **问题**：无动作标注视频丰富，却缺少能迁移到机器人控制的预训练表示。
  - **方法**：将相邻帧变化离散化为运动标记，自回归预训练后与真实动作联合微调。
  - **价值**：从视频学习运动先验并迁移到操作策略。
  - **局限**：潜在运动并非天然可执行动作，迁移仍需机器人动作标注。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2412.04445">[2]</a> · <a href="https://arxiv.org/pdf/2412.04445">[3]</a> · <a href="https://github.com/TencentARC/Moto">[4]</a>
  核验：2026-10-13

  </details>


## 交互 Avatar

+ [DreamAvatar: Text-and-Shape Guided 3D Human Avatar Generation via Diffusion Models](<https://arxiv.org/abs/2304.00916>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2304.00916>)
  <br>2023-04-03 · 3D生成 / Avatar / 姿态控制

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  三维 Avatar 的形状先验和可动画表示值得作为基础阅读。

  <details>
  <summary>brief</summary>

  - **问题**：通用文本三维生成难保证人体关节结构和细致外观。
  - **方法**：用人体形状先验约束标准及姿态双空间，以形变场连接并强化头部监督。
  - **价值**：生成姿态可控且纹理更完整的人体资产。
  - **局限**：依赖参数化人体先验与优化过程，不是实时对话驱动的 Avatar 系统。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2304.00916">[2]</a> · <a href="https://arxiv.org/pdf/2304.00916">[3]</a>
  核验：2026-10-13

  </details>


## 智能体与上下文

+ [EgoPlan-Bench2: A Benchmark for Multimodal Large Language Model Planning in Real-World Scenarios](<https://arxiv.org/abs/2412.04447>)<br>
  [![Star](https://img.shields.io/github/stars/qiulu66/EgoPlan-Bench2.svg?style=social&label=Star)](<https://github.com/qiulu66/EgoPlan-Bench2>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2412.04447>)
  <br>2024-12-05 · Agent / 第一视角 / 规划 / 评测

  **[IJCV 2026](<https://arc.tencent.com/academic>)** · **P0 必读** · 摘要与引言
  直接对应基于视频历史和当前状态的 Agent 下一步规划。

  <details>
  <summary>brief</summary>

  - **问题**：静态识别不足以判断真实任务下一步应执行的动作。
  - **方法**：结合目标、任务进度视频和当前观察构造跨场景规划题。
  - **价值**：排除单模态捷径，检验时序进展与物体交互理解。
  - **局限**：仍是离线选项决策，不能直接证明闭环执行成功率。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2412.04447">[2]</a> · <a href="https://arxiv.org/pdf/2412.04447">[3]</a> · <a href="https://github.com/qiulu66/EgoPlan-Bench2">[4]</a>
  核验：2026-10-13

  </details>

+ [Before Thinking, Learn to Decide: Proactive Routing for Efficient Visual Reasoning](<https://arxiv.org/abs/2606.30217>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2606.30217>)
  <br>2026-06-29 · Agent / 推理路由 / 效率

  **[ECCV 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  关注推理前的预算分配，适合低延迟交互 Agent。

  <details>
  <summary>brief</summary>

  - **问题**：按难度路由问题容易忽略目标模型是否真正能解。
  - **方法**：先预测自身及目标模型可解性，再以强化学习训练路由决策。
  - **价值**：将计算预算投向值得调用强模型的问题。
  - **局限**：依赖配对模型的能力监督，模型变化后需重新校准。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2606.30217">[2]</a> · <a href="https://arxiv.org/pdf/2606.30217">[3]</a>
  核验：2026-10-13

  </details>

+ [MMhops-R1: Multimodal Multi-hop Reasoning](<https://arxiv.org/abs/2512.13573>)<br>
  [![Star](https://img.shields.io/github/stars/taoszhang/MMhops-R1.svg?style=social&label=Star)](<https://github.com/taoszhang/MMhops-R1>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2512.13573>)
  <br>2025-12-15 · Agent / 多跳检索 / 强化学习

  **[AAAI 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  动态选择图像、文本检索与停止时机，可借鉴 Agent 规划。

  <details>
  <summary>brief</summary>

  - **问题**：固定检索链难解决需要跨图像及外部知识的多跳问题。
  - **方法**：构造桥接和比较任务，以强化学习选择图像检索、文本检索或回答。
  - **价值**：让推理路径与检索深度随问题变化。
  - **局限**：知识问答环境较封闭，未验证持续交互中的记忆维护。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2512.13573">[2]</a> · <a href="https://arxiv.org/pdf/2512.13573">[3]</a> · <a href="https://github.com/taoszhang/MMhops-R1">[4]</a>
  核验：2026-10-13

  </details>

+ [LoRA-Gen: Specializing Large Language Model via Online LoRA Generation](<https://arxiv.org/abs/2506.11638>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2506.11638>)
  <br>2025-06-13 · Agent / LoRA / 上下文压缩 / 端侧

  **[ICML 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  将任务上下文压进参数，适合研究低延迟 Agent 与记忆压缩。

  <details>
  <summary>brief</summary>

  - **问题**：小模型任务适配与长系统提示带来训练及推理成本。
  - **方法**：云端模型按任务描述组合低秩专家，生成可合并到端侧模型的参数。
  - **价值**：缩短推理上下文并支持未见任务的快速适配。
  - **局限**：需要预先训练生成器，压缩静态任务提示不同于持续更新情景记忆。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2506.11638">[2]</a> · <a href="https://arxiv.org/pdf/2506.11638">[3]</a>
  核验：2026-10-13

  </details>

+ [mR$^2$AG: Multimodal Retrieval-Reflection-Augmented Generation for Knowledge-Based VQA](<https://arxiv.org/abs/2411.15041>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2411.15041>)
  <br>2024-11-22 · Agent / RAG / 检索决策

  **[TMM 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  Agent 检索决策与证据定位，可借鉴记忆读取策略。

  <details>
  <summary>brief</summary>

  - **问题**：视觉问答中无必要的检索会引入噪声，相关知识也难定位。
  - **方法**：用反思标记决定是否检索，并选择证据段落进行回答。
  - **价值**：把检索时机与证据使用纳入同一模型训练。
  - **局限**：主要面向百科知识问答，尚不等同于长期交互记忆。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2411.15041">[2]</a> · <a href="https://arxiv.org/pdf/2411.15041">[3]</a>
  核验：2026-10-13

  </details>

+ [Cached Transformers: Improving Transformers with Differentiable Memory Cache](<https://arxiv.org/abs/2312.12742>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2312.12742>)
  <br>2023-12-20 · 记忆机制 / 递归缓存 / 长上下文

  **[AAAI 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  可微递归缓存为 Agent 和视频模型的压缩记忆提供基础。

  <details>
  <summary>brief</summary>

  - **问题**：扩大注意力范围会增加计算和存储，完整历史缓存难以扩展。
  - **方法**：用重置门与更新门压缩历史表示，让注意力同时访问缓存与当前标记。
  - **价值**：以有限缓存建模长依赖，并适用于语言和视觉骨干。
  - **局限**：压缩记忆可能遗失可精确回溯的信息，尚未验证长期 Agent 任务。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2312.12742">[2]</a> · <a href="https://arxiv.org/pdf/2312.12742">[3]</a>
  核验：2026-10-13

  </details>

+ [EgoPlan-Bench: Benchmarking Multimodal Large Language Models for Human-Level Planning](<https://arxiv.org/abs/2312.06722>)<br>
  [![Star](https://img.shields.io/github/stars/ChenYi99/EgoPlan.svg?style=social&label=Star)](<https://github.com/ChenYi99/EgoPlan>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2312.06722>)
  <br>2023-12-11 · Agent / 规划 / 视频理解

  **[IJCV 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  先理解第一视角规划任务设计，再读 EgoPlan-Bench2。

  <details>
  <summary>brief</summary>

  - **问题**：日常长任务规划需要结合目标、已完成步骤与当前观察。
  - **方法**：建立第一视角多模态规划评测及相应指令训练数据。
  - **价值**：将视觉状态与动作序列纳入下一步决策。
  - **局限**：场景覆盖较集中，离线规划表现不等于真实机器人执行能力。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2312.06722">[2]</a> · <a href="https://arxiv.org/pdf/2312.06722">[3]</a> · <a href="https://github.com/ChenYi99/EgoPlan">[4]</a>
  核验：2026-10-13

  </details>


## 多模态检索

+ [Mamba-3VL: Taming State Space Model for 3D Vision Language Learning](<https://openaccess.thecvf.com/content/ICCV2025/papers/Wang_Mamba-3VL_Taming_State_Space_Model_for_3D_Vision_Language_Learning_ICCV_2025_paper.pdf>)<br>
  [![Star](https://img.shields.io/github/stars/wangyuan123ac/Mamba-3VL.svg?style=social&label=Star)](<https://github.com/wangyuan123ac/Mamba-3VL>) [![Paper](https://img.shields.io/badge/Paper-b31b1b.svg)](<https://openaccess.thecvf.com/content/ICCV2025/papers/Wang_Mamba-3VL_Taming_State_Space_Model_for_3D_Vision_Language_Learning_ICCV_2025_paper.pdf>)
  <br>日期待核实 · Agent / 状态空间模型 / 空间推理

  **[ICCV 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  线性复杂度的三维关系建模可补充空间 Agent 状态处理。

  <details>
  <summary>brief</summary>

  - **问题**：三维点云转序列会破坏空间关系，全注意力又成本较高。
  - **方法**：用近邻与远邻扫描、通道融合及实例位置适配增强状态空间模型。
  - **价值**：高效统一三维定位、分割与问答任务。
  - **局限**：主要验证已建模场景理解，开放动态世界中的持续状态更新仍待验证。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://github.com/wangyuan123ac/Mamba-3VL">[2]</a> · <a href="https://openaccess.thecvf.com/content/ICCV2025/papers/Wang_Mamba-3VL_Taming_State_Space_Model_for_3D_Vision_Language_Learning_ICCV_2025_paper.pdf">[3]</a>
  核验：2026-10-13

  </details>

+ [DOGR: Towards Versatile Visual Document Grounding and Referring](<https://arxiv.org/abs/2411.17125>)<br>
  [![Star](https://img.shields.io/github/stars/zyinan99/DOGR.svg?style=social&label=Star)](<https://github.com/zyinan99/DOGR>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2411.17125>)
  <br>2024-11-26 · Agent / 文档理解 / 视觉定位

  **[ICCV 2025](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  可作为文档型 Agent 的精确证据定位基础。

  <details>
  <summary>brief</summary>

  - **问题**：密集文档中的定位与指代能力受低质量标注和单一任务限制。
  - **方法**：构建多粒度解析与对话指令数据，统一文本定位和区域理解。
  - **价值**：支持可回溯到具体位置的文档问答并提供系统评测。
  - **局限**：重点是静态文档感知，规划与长期记忆需其他模块补充。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2411.17125">[2]</a> · <a href="https://arxiv.org/pdf/2411.17125">[3]</a> · <a href="https://github.com/zyinan99/DOGR">[4]</a>
  核验：2026-10-13

  </details>

+ [How to Make Cross Encoder a Good Teacher for Efficient Image-Text Retrieval?](<https://arxiv.org/abs/2407.07479>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2407.07479>)
  <br>2024-07-10 · 多模态 / 检索 / 蒸馏

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  可借鉴到多模态记忆检索器蒸馏，主线相关度为间接。

  <details>
  <summary>brief</summary>

  - **问题**：交叉编码器准确但慢，其分数分布又不适合直接蒸馏给双编码器。
  - **方法**：仅对难负例的相对次序做对比排序蒸馏，忽略无效负例间的次序。
  - **价值**：以兼容原训练目标的方式提升高效图文检索。
  - **局限**：验证集中在图文匹配，长期记忆读写与时间关系需另行设计。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2407.07479">[2]</a> · <a href="https://arxiv.org/pdf/2407.07479">[3]</a>
  核验：2026-10-13

  </details>


## 评测与可靠性

+ [MindOmni: Unleashing Reasoning Generation in Vision Language Models with RGPO](<https://arxiv.org/abs/2505.13031>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/MindOmni.svg?style=social&label=Star)](<https://github.com/TencentARC/MindOmni>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2505.13031>)
  <br>2025-05-19 · 强化学习 / 生成规划 / 统一生成理解

  **[NeurIPS 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  推理计划与生成反馈联合优化可借鉴到视频规划生成。

  <details>
  <summary>brief</summary>

  - **问题**：固定文本编码难处理需要知识、数学或视觉推理的生成指令。
  - **方法**：先统一理解生成并进行思维链监督，再用图文一致性奖励优化推理。
  - **价值**：将显式推理与细粒度生成编辑结合。
  - **局限**：主要面向图像，奖励一致性不足以保证长时视频中的因果正确。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2505.13031">[2]</a> · <a href="https://arxiv.org/pdf/2505.13031">[3]</a> · <a href="https://github.com/TencentARC/MindOmni">[4]</a>
  核验：2026-10-13

  </details>

+ [Grpo-care: Consistency-aware reinforcement learning for multimodal reasoning](<https://aclanthology.org/2026.findings-acl.210.pdf>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/GRPO-CARE.svg?style=social&label=Star)](<https://github.com/TencentARC/GRPO-CARE>) [![Paper](https://img.shields.io/badge/Paper-b31b1b.svg)](<https://aclanthology.org/2026.findings-acl.210.pdf>)
  <br>日期待核实 · Agent / 强化学习 / 规划

  **[Findings of ACL 2026](<https://aclanthology.org/2026.findings-acl.210>)** · **P1 重点** · 摘要与引言
  规划奖励与分布外泛化相关，适合 Agent 后训练。

  <details>
  <summary>brief</summary>

  - **问题**：结果奖励可能鼓励答案正确但推理不可靠的策略。
  - **方法**：以参考模型构造组内似然一致性奖励，并建立分层泛化评测。
  - **价值**：把正确性与推理一致性共同纳入策略优化。
  - **局限**：似然一致性是代理信号，不保证推理具有真实因果依据。

  来源：<a href="https://aclanthology.org/2026.findings-acl.210">[1]</a> · <a href="https://aclanthology.org/2026.findings-acl.210.pdf">[2]</a> · <a href="https://arc.tencent.com/academic">[3]</a> · <a href="https://github.com/TencentARC/GRPO-CARE">[4]</a>
  核验：2026-10-13

  </details>

+ [SEED-Bench-2: Benchmarking Multimodal Large Language Models](<https://arxiv.org/abs/2311.17092>)<br>
  [![Star](https://img.shields.io/github/stars/AILab-CVC/SEED-Bench.svg?style=social&label=Star)](<https://github.com/AILab-CVC/SEED-Bench>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2311.17092>)
  <br>2023-11-28 · 多模态 / 统一生成理解 / 评测

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  可作为多模态能力分层评测背景，主线更需长时与交互指标。

  <details>
  <summary>brief</summary>

  - **问题**：只测单张图文理解无法覆盖交错输入及图文输出能力。
  - **方法**：按输入输出模态划分层级，构建跨图像、视频和生成任务的人工核验选择题。
  - **价值**：提供可复现的分维度能力诊断。
  - **局限**：选择题不能充分衡量开放生成质量，也未直接评价闭环交互。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2311.17092">[2]</a> · <a href="https://arxiv.org/pdf/2311.17092">[3]</a> · <a href="https://github.com/AILab-CVC/SEED-Bench">[4]</a>
  核验：2026-10-13

  </details>

+ [Visionmath: Vision-form mathematical problem-solving](<https://openaccess.thecvf.com/content/ICCV2025/papers/Ma_VisionMath_Vision-Form_Mathematical_Problem-Solving_ICCV_2025_paper.pdf>)<br>
  [![Paper](https://img.shields.io/badge/Paper-b31b1b.svg)](<https://openaccess.thecvf.com/content/ICCV2025/papers/Ma_VisionMath_Vision-Form_Mathematical_Problem-Solving_ICCV_2025_paper.pdf>)
  <br>日期待核实 · 数学 / 数据集 / 视觉推理

  **[ICCV 2025](<https://arc.tencent.com/academic>)** · **P3 暂缓** · 摘要与引言
  主要是视觉数学解题，和当前视频、Avatar、记忆主线较远。

  <details>
  <summary>brief</summary>

  - **问题**：将题干与图形合在一张图中后，现有模型的解题准确性下降。
  - **方法**：分阶段学习文字识别、图形理解和联合推理，并利用教学视频补充图形知识。
  - **价值**：建立中英双语视觉题目训练与评测体系。
  - **局限**：数学截图场景较专门，不能直接代表动态世界推理。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://openaccess.thecvf.com/content/ICCV2025/papers/Ma_VisionMath_Vision-Form_Mathematical_Problem-Solving_ICCV_2025_paper.pdf">[2]</a>
  核验：2026-10-13

  </details>


## 训练与推理效率

+ [ATP-LLaVA: Adaptive Token Pruning for Large Vision Language Models](<https://arxiv.org/abs/2412.00447>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2412.00447>)
  <br>2024-11-30 · Agent / 推理效率 / 视觉压缩

  **[CVPR 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  自适应算力分配可用于实时视觉 Agent 的感知加速。

  <details>
  <summary>brief</summary>

  - **问题**：固定视觉剪枝率无法适配不同层和任务的信息需求。
  - **方法**：依据跨模态冗余与空间信息学习逐层、逐样本剪枝阈值。
  - **价值**：在降低视觉标记开销时保留细粒度理解能力。
  - **局限**：需要训练剪枝模块，极小目标和复杂空间关系仍可能损失信息。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2412.00447">[2]</a> · <a href="https://arxiv.org/pdf/2412.00447">[3]</a>
  核验：2026-10-13

  </details>

+ [VoCo-LLaMA: Towards Vision Compression with Large Language Models](<https://arxiv.org/abs/2406.12275>)<br>
  [![Star](https://img.shields.io/github/stars/Yxxxb/VoCo-LLaMA.svg?style=social&label=Star)](<https://github.com/Yxxxb/VoCo-LLaMA>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2406.12275>)
  <br>2024-06-18 · Agent / 上下文压缩 / 视频记忆

  **[CVPR 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  视觉缓存压缩与重复查询直接关联 Agent 的视频记忆。

  <details>
  <summary>brief</summary>

  - **问题**：视频帧的视觉标记占满上下文，外部压缩又容易丢失任务信息。
  - **方法**：在语言模型内引入压缩标记并蒸馏理解路径，逐帧压缩后建模时序。
  - **价值**：压缩表示可缓存复用，扩大同等上下文内的视频覆盖。
  - **局限**：极高压缩仍损失细节，缓存表示不包含主动记忆更新策略。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2406.12275">[2]</a> · <a href="https://arxiv.org/pdf/2406.12275">[3]</a> · <a href="https://github.com/Yxxxb/VoCo-LLaMA">[4]</a>
  核验：2026-10-13

  </details>

+ [Rethinking the Objectives of Vector-Quantized Tokenizers for Image Synthesis](<https://arxiv.org/abs/2212.03185>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/BasicVQ-GEN.svg?style=social&label=Star)](<https://github.com/TencentARC/BasicVQ-GEN>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2212.03185>)
  <br>2022-12-06 · 生成建模 / 表示学习 / 视觉标记

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  重建质量不等于生成可学性，是视频和世界模型 tokenizer 的关键视角。

  <details>
  <summary>brief</summary>

  - **问题**：提升量化编码器重建保真度未必提升后续生成质量。
  - **方法**：先强化语义压缩，再冻结编码器与码本、单独增强解码器细节恢复。
  - **价值**：把潜表示的可预测性和像素细节恢复分开优化。
  - **局限**：证据主要来自图像，视频运动信息与时序压缩仍需额外验证。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2212.03185">[2]</a> · <a href="https://arxiv.org/pdf/2212.03185">[3]</a> · <a href="https://github.com/TencentARC/BasicVQ-GEN">[4]</a>
  核验：2026-10-13

  </details>

+ [LLaMA Pro: Progressive LLaMA with Block Expansion](<https://arxiv.org/abs/2401.02415>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/LLaMA-Pro.svg?style=social&label=Star)](<https://github.com/TencentARC/LLaMA-Pro>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2401.02415>)
  <br>2024-01-04 · Agent / 持续学习 / 模型扩展

  **[ACL 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  持续能力扩展可补充 Agent 学习，和情景记忆不是同一问题。

  <details>
  <summary>brief</summary>

  - **问题**：领域继续预训练容易覆盖语言模型原有通用能力。
  - **方法**：插入恒等初始化的 Transformer 块，仅以领域语料训练新增模块。
  - **价值**：在注入代码和数学能力时缓解遗忘。
  - **局限**：增加参数与推理深度，不能替代可检索和更新的外部记忆。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2401.02415">[2]</a> · <a href="https://arxiv.org/pdf/2401.02415">[3]</a> · <a href="https://github.com/TencentARC/LLaMA-Pro">[4]</a>
  核验：2026-10-13

  </details>


## 多模态架构与综述

+ [Semantic Generative Tuning for Unified Multimodal Models](<https://arxiv.org/abs/2605.18714>)<br>
  [![Star](https://img.shields.io/github/stars/song2yu/SGT.svg?style=social&label=Star)](<https://github.com/song2yu/SGT>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2605.18714>)
  <br>2026-05-18 · 统一生成理解 / 表示学习

  **[ECCV 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  理解与生成共享语义表示，可为世界模型表示设计提供思路。

  <details>
  <summary>brief</summary>

  - **问题**：统一模型共享结构后，像素生成目标仍难学习抽象语义。
  - **方法**：引入高层语义生成任务，调节统一模型的表示与注意力。
  - **价值**：改善理解能力并增强布局控制，为任务统一提供训练视角。
  - **局限**：重点仍是图像任务，未验证时序动力学与闭环控制。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2605.18714">[2]</a> · <a href="https://arxiv.org/pdf/2605.18714">[3]</a> · <a href="https://github.com/song2yu/SGT">[4]</a>
  核验：2026-10-13

  </details>

+ [Making LLaMA SEE and Draw with SEED Tokenizer](<https://arxiv.org/abs/2310.01218>)<br>
  [![Star](https://img.shields.io/github/stars/AILab-CVC/SEED.svg?style=social&label=Star)](<https://github.com/AILab-CVC/SEED>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2310.01218>)
  <br>2023-10-02 · 统一生成理解 / 自回归 / 视觉标记

  **[ICLR 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  统一多模态离散表示是世界模型与交互生成的重要背景。

  <details>
  <summary>brief</summary>

  - **问题**：低层视觉标记与语言语义错位，难统一图文理解和生成。
  - **方法**：以因果查询模块生成高层离散视觉编码，再进行交错图文下一标记训练。
  - **价值**：使语言模型在多轮上下文中同时理解与生成图像。
  - **局限**：视觉解码依赖扩散模块，原始方案未解决实时长视频动力学。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2310.01218">[2]</a> · <a href="https://arxiv.org/pdf/2310.01218">[3]</a> · <a href="https://github.com/AILab-CVC/SEED">[4]</a>
  核验：2026-10-13

  </details>

+ [HaploVL: A Single-Transformer Baseline for Multi-Modal Understanding](<https://arxiv.org/abs/2503.14694>)<br>
  [![Star](https://img.shields.io/github/stars/Tencent/HaploVLM.svg?style=social&label=Star)](<https://github.com/Tencent/HaploVLM>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2503.14694>)
  <br>2025-03-12 · 多模态 / 早期融合 / 训练效率

  **[ICML 2025](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  补充多模态骨干设计，近期优先于主线的价值有限。

  <details>
  <summary>brief</summary>

  - **问题**：独立视觉编码器容易压缩掉文本任务需要的细粒度信息。
  - **方法**：在单一 Transformer 中早期融合图文，并继承视觉与语言预训练知识。
  - **价值**：减少原生多模态训练成本并改善细粒度理解。
  - **局限**：主要验证视觉问答，未专门建模视频时序或 Agent 记忆。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2503.14694">[2]</a> · <a href="https://arxiv.org/pdf/2503.14694">[3]</a> · <a href="https://github.com/Tencent/HaploVLM">[4]</a>
  核验：2026-10-13

  </details>

+ [GrootVL: Tree Topology is All You Need in State Space Model](<https://arxiv.org/abs/2406.02395>)<br>
  [![Star](https://img.shields.io/github/stars/EasonXiao-888/GrootVL.svg?style=social&label=Star)](<https://github.com/EasonXiao-888/GrootVL>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2406.02395>)
  <br>2024-06-04 · 状态空间模型 / 表示学习 / 长依赖

  **[NeurIPS 2024 &#91;Spotlight&#93;](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  输入自适应记忆传播拓扑可作模型结构背景。

  <details>
  <summary>brief</summary>

  - **问题**：固定序列扫描破坏图像邻接关系，也限制长距离特征传播。
  - **方法**：根据特征构造树拓扑，并用动态规划在线性复杂度内聚合树上信息。
  - **价值**：兼顾较长依赖与计算效率，扩展到视觉和语言任务。
  - **局限**：结构实验不直接证明长期情景记忆或在线规划收益。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2406.02395">[2]</a> · <a href="https://arxiv.org/pdf/2406.02395">[3]</a> · <a href="https://github.com/EasonXiao-888/GrootVL">[4]</a>
  核验：2026-10-13

  </details>

+ [ViT-Lens: Towards Omni-modal Representations](<https://arxiv.org/abs/2311.16081>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/ViT-Lens.svg?style=social&label=Star)](<https://github.com/TencentARC/ViT-Lens>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2311.16081>)
  <br>2023-11-27 · 多模态 / 表示学习 / 适配器

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  跨模态感知适配可补充具身 Agent 输入设计。

  <details>
  <summary>brief</summary>

  - **问题**：稀缺传感模态缺少足量训练数据，难复用大模型能力。
  - **方法**：用模态专属映射接入冻结视觉骨干，并对齐已有共享语义空间。
  - **价值**：支持点云、深度、音频等模态接入理解与生成模型。
  - **局限**：语义对齐不保证保留精确物理量或时间动力学。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2311.16081">[2]</a> · <a href="https://arxiv.org/pdf/2311.16081">[3]</a> · <a href="https://github.com/TencentARC/ViT-Lens">[4]</a>
  核验：2026-10-13

  </details>


## 三维生成与重建

+ [Pixal3D: Pixel-Aligned 3D Generation from Images](<https://arxiv.org/abs/2605.10922>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/Pixal3D.svg?style=social&label=Star)](<https://github.com/TencentARC/Pixal3D>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2605.10922>)
  <br>2026-05-11 · 3D / 几何一致性 / 条件生成

  **[SIGGRAPH 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  显式像素与三维对应可借鉴到可控世界模型的状态表示。

  <details>
  <summary>brief</summary>

  - **问题**：图像条件三维生成的隐式对应容易丢失细节并偏离输入。
  - **方法**：把多尺度像素特征沿射线反投影到体素空间，显式约束生成。
  - **价值**：统一单视图与多视图条件，并支持分对象场景组合。
  - **局限**：不可见部分仍依赖生成先验，未处理动态场景的因果演化。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2605.10922">[2]</a> · <a href="https://arxiv.org/pdf/2605.10922">[3]</a> · <a href="https://github.com/TencentARC/Pixal3D">[4]</a>
  核验：2026-10-13

  </details>

+ [Sculpt4D: Generating 4D Shapes via Sparse-Attention Diffusion Transformers](<https://arxiv.org/abs/2604.21592>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/Sculpt4D.svg?style=social&label=Star)](<https://github.com/TencentARC/Sculpt4D>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2604.21592>)
  <br>2026-04-23 · 4D / Avatar / 时序一致性

  **[CVPR 2026](<https://openaccess.thecvf.com/content/CVPR2026/html/Yin_Sculpt4D_Generating_4D_Shapes_via_Sparse-Attention_Diffusion_Transformers_CVPR_2026_paper.html>)** · **P1 重点** · 摘要与引言
  时间一致的 4D 表示可用于 Avatar 资产及动态场景。

  <details>
  <summary>brief</summary>

  - **问题**：逐帧生成三维形状容易出现跨时间身份与几何漂移。
  - **方法**：以首帧为锚点，结合时间衰减稀疏注意力扩展三维模型。
  - **价值**：在降低计算量的同时维持动态形状对应关系。
  - **局限**：从视频重建动态资产，不直接学习动作条件的环境动力学。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2604.21592">[2]</a> · <a href="https://arxiv.org/pdf/2604.21592">[3]</a> · <a href="https://github.com/TencentARC/Sculpt4D">[4]</a> · <a href="https://openaccess.thecvf.com/content/CVPR2026/html/Yin_Sculpt4D_Generating_4D_Shapes_via_Sparse-Attention_Diffusion_Transformers_CVPR_2026_paper.html">[5]</a>
  核验：2026-10-13

  </details>

+ [Track4World: Feedforward World-centric Dense 3D Tracking of All Pixels](<https://arxiv.org/abs/2603.02573>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/Track4World.svg?style=social&label=Star)](<https://github.com/TencentARC/Track4World>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2603.02573>)
  <br>2026-03-03 · 4D / 三维跟踪 / 世界模型

  **[ECCV 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  为世界模型提供全局坐标中的动态状态和运动监督。

  <details>
  <summary>brief</summary>

  - **问题**：稀疏首帧跟踪无法覆盖后续新像素，逐点稠密跟踪又昂贵。
  - **方法**：预测任意帧对的二维与三维场景流，以稀疏相关更新恢复稠密轨迹。
  - **价值**：将单目视频转为世界坐标中的全像素动态表示。
  - **局限**：依赖整段视频的全局上下文，在线因果处理仍需额外设计。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2603.02573">[2]</a> · <a href="https://arxiv.org/pdf/2603.02573">[3]</a> · <a href="https://github.com/TencentARC/Track4World">[4]</a>
  核验：2026-10-13

  </details>

+ [MotionCrafter: Dense Geometry and Motion Reconstruction with a 4D VAE](<https://arxiv.org/abs/2602.08961>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/MotionCrafter.svg?style=social&label=Star)](<https://github.com/TencentARC/MotionCrafter>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2602.08961>)
  <br>2026-02-09 · 4D / 世界模型 / 表示学习

  **[CVPR 2026](<https://openaccess.thecvf.com/content/CVPR2026/html/Zhu_MotionCrafter_Dense_Geometry_and_Motion_Reconstruction_with_a_4D_VAE_CVPR_2026_paper.html>)** · **P1 重点** · 摘要与引言
  联合几何与运动的潜变量表示适合世界模型状态设计。

  <details>
  <summary>brief</summary>

  - **问题**：单目动态重建将几何与运动分开预测，难保持全局对应。
  - **方法**：用专门训练的四维变分编码器联合压缩世界坐标点图与场景流。
  - **价值**：迁移视频生成先验，无需逐场景后优化即可恢复动态结构。
  - **局限**：任务是从已观测视频重建，尚未学习动作驱动的未来状态转移。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2602.08961">[2]</a> · <a href="https://arxiv.org/pdf/2602.08961">[3]</a> · <a href="https://github.com/TencentARC/MotionCrafter">[4]</a> · <a href="https://openaccess.thecvf.com/content/CVPR2026/html/Zhu_MotionCrafter_Dense_Geometry_and_Motion_Reconstruction_with_a_4D_VAE_CVPR_2026_paper.html">[5]</a>
  核验：2026-10-13

  </details>

+ [NormalCrafter: Learning Temporally Consistent Normals from Video Diffusion Priors](<https://arxiv.org/abs/2504.11427>)<br>
  [![Star](https://img.shields.io/github/stars/Binyr/NormalCrafter.svg?style=social&label=Star)](<https://github.com/Binyr/NormalCrafter>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2504.11427>)
  <br>2025-04-15 · 时序一致性 / 法线估计 / 视频理解

  **[ICCV 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  表面法线可辅助视频物理外观、重光照与几何一致性研究。

  <details>
  <summary>brief</summary>

  - **问题**：图像法线模型逐帧使用会闪烁，视频先验又容易过度平滑细节。
  - **方法**：用语义特征正则增强结构，并分阶段进行潜空间和像素空间训练。
  - **价值**：兼顾长时上下文与局部表面细节。
  - **局限**：输出局部几何属性，不能单独形成完整可交互的世界状态。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2504.11427">[2]</a> · <a href="https://arxiv.org/pdf/2504.11427">[3]</a> · <a href="https://github.com/Binyr/NormalCrafter">[4]</a>
  核验：2026-10-13

  </details>

+ [GeometryCrafter: Consistent Geometry Estimation for Open-world Videos with Diffusion Priors](<https://arxiv.org/abs/2504.01016>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/GeometryCrafter.svg?style=social&label=Star)](<https://github.com/TencentARC/GeometryCrafter>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2504.01016>)
  <br>2025-04-01 · 世界模型 / 几何重建 / 时序一致性

  **[ICCV 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  补齐从时间一致深度到可重建三维点图的表示路径。

  <details>
  <summary>brief</summary>

  - **问题**：有界深度编码丢失远处几何，逐帧预测又缺乏时间稳定性。
  - **方法**：以对数深度和视场分解点图，双编码器保留几何信息并迁移视频扩散先验。
  - **价值**：恢复连贯点图并支持重建与相机参数估计。
  - **局限**：估计仍依赖单目先验，几何正确性受输入与数据分布限制。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2504.01016">[2]</a> · <a href="https://arxiv.org/pdf/2504.01016">[3]</a> · <a href="https://github.com/TencentARC/GeometryCrafter">[4]</a>
  核验：2026-10-13

  </details>

+ [FreeSplatter: Pose-free Gaussian Splatting for Sparse-view 3D Reconstruction](<https://arxiv.org/abs/2412.09573>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/FreeSplatter.svg?style=social&label=Star)](<https://github.com/TencentARC/FreeSplatter>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2412.09573>)
  <br>2024-12-12 · 3D / 位姿估计 / 高斯表示

  **[ICCV 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  世界模型几何初始化和多视角融合的实用基础。

  <details>
  <summary>brief</summary>

  - **问题**：稀疏图像重建常依赖难以准确获得的相机标定。
  - **方法**：直接预测统一坐标中的像素对齐高斯，再用标准求解器恢复相机参数。
  - **价值**：兼顾快速新视角渲染与位姿估计，简化生成资产管线。
  - **局限**：以静态对象和场景为主，不能直接处理长期动态交互。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2412.09573">[2]</a> · <a href="https://arxiv.org/pdf/2412.09573">[3]</a> · <a href="https://github.com/TencentARC/FreeSplatter">[4]</a>
  核验：2026-10-13

  </details>

+ [NVComposer: Boosting Generative Novel View Synthesis with Multiple Sparse and Unposed Images](<https://arxiv.org/abs/2412.03517>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/NVComposer.svg?style=social&label=Star)](<https://github.com/TencentARC/NVComposer>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2412.03517>)
  <br>2024-12-04 · 几何一致性 / 新视角 / 视频生成

  **[CVPR 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  弱位姿条件下的多视角生成与几何蒸馏关联世界模型。

  <details>
  <summary>brief</summary>

  - **问题**：少量视图重叠不足时，外部位姿对齐错误会破坏新视角生成。
  - **方法**：联合扩散图像与位姿，训练时蒸馏立体模型的几何特征。
  - **价值**：推理无需独立预重建即可利用多个未标定位图像。
  - **局限**：生成合理的新视图不保证真实几何，尚未建模动作条件动态。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2412.03517">[2]</a> · <a href="https://arxiv.org/pdf/2412.03517">[3]</a> · <a href="https://github.com/TencentARC/NVComposer">[4]</a>
  核验：2026-10-13

  </details>

+ [OREO: Fidelity Alignment in 3D Generation via On-the-fly Rendering-Editing Optimization](<https://arxiv.org/abs/2609.29788>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2609.29788>)
  <br>2026-09-24 · 3D / 后训练 / 蒸馏

  **[ECCV 2026](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  可参考生成模型自采样后训练，但主题偏三维资产外观。

  <details>
  <summary>brief</summary>

  - **问题**：三维数据外观多样性不足，生成资产缺少细节和真实感。
  - **方法**：循环渲染当前模型输出，以保结构图像编辑构造正样本并对比蒸馏。
  - **价值**：利用二维先验动态改善三维生成器外观。
  - **局限**：编辑伪目标仍可能引入偏差，主要验证静态资产视觉质量。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2609.29788">[2]</a> · <a href="https://arxiv.org/pdf/2609.29788">[3]</a>
  核验：2026-10-13

  </details>

+ [MeshWeaver: Sparse-Voxel-Guided Surface Weaving for Autoregressive Mesh Generation](<https://arxiv.org/abs/2606.04688>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2606.04688>)
  <br>2026-06-03 · 3D / 网格生成 / 资产

  **[CVPR 2026](<https://openaccess.thecvf.com/content/CVPR2026/html/Xu_MeshWeaver_Sparse-Voxel-Guided_Surface_Weaving_for_Autoregressive_Mesh_Generation_CVPR_2026_paper.html>)** · **P2 选读** · 摘要与引言
  可补充世界模型和 Avatar 的几何资产管线。

  <details>
  <summary>brief</summary>

  - **问题**：已知表面几何仍难高效生成结构合理的网格拓扑。
  - **方法**：以稀疏体素条件和分层支架建模，按顶点自回归生成网格。
  - **价值**：改善几何对齐和网格结构生成效率。
  - **局限**：依赖输入表面，未涉及动态交互或环境状态转移。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2606.04688">[2]</a> · <a href="https://arxiv.org/pdf/2606.04688">[3]</a> · <a href="https://openaccess.thecvf.com/content/CVPR2026/html/Xu_MeshWeaver_Sparse-Voxel-Guided_Surface_Weaving_for_Autoregressive_Mesh_Generation_CVPR_2026_paper.html">[4]</a>
  核验：2026-10-13

  </details>

+ [DI-PCG: Diffusion-based Efficient Inverse Procedural Content Generation for High-quality 3D Asset Creation](<https://arxiv.org/abs/2412.15200>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/DI-PCG.svg?style=social&label=Star)](<https://github.com/TencentARC/DI-PCG>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2412.15200>)
  <br>2024-12-19 · 3D / 条件扩散 / 程序化生成

  **[CVPR 2025](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  程序化资产生成可为世界模型构造可编辑训练环境。

  <details>
  <summary>brief</summary>

  - **问题**：程序化建模参数难手调，传统逆向搜索需要大量采样。
  - **方法**：直接对生成器参数进行条件扩散，以图像特征引导参数恢复。
  - **价值**：用小模型快速生成可编辑资产，并可自生成训练数据。
  - **局限**：表达范围受预设程序生成器限制，不能覆盖任意开放世界结构。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2412.15200">[2]</a> · <a href="https://arxiv.org/pdf/2412.15200">[3]</a> · <a href="https://github.com/TencentARC/DI-PCG">[4]</a>
  核验：2026-10-13

  </details>

+ [Mani-GS: Gaussian Splatting Manipulation with Triangular Mesh](<https://arxiv.org/abs/2405.17811>)<br>
  [![Star](https://img.shields.io/github/stars/gaoxiangjun/Mani-GS.svg?style=social&label=Star)](<https://github.com/gaoxiangjun/Mani-GS>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2405.17811>)
  <br>2024-05-28 · 3D / 可编辑资产 / 高斯表示

  **[CVPR 2025](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  Avatar 几何编辑和渲染可参考，优先级低于生成与交互模型。

  <details>
  <summary>brief</summary>

  - **问题**：高斯场景渲染快速，但大形变和局部编辑难保持质量。
  - **方法**：在三角形局部坐标中绑定高斯，随代理网格形变自适应调整属性。
  - **价值**：复用网格编辑与仿真工具，同时容忍不精确的代理表面。
  - **局限**：需要已有重建与网格，动作来源和动态物理仍由外部提供。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2405.17811">[2]</a> · <a href="https://arxiv.org/pdf/2405.17811">[3]</a> · <a href="https://github.com/gaoxiangjun/Mani-GS">[4]</a>
  核验：2026-10-13

  </details>

+ [Sparse3D: Distilling Multiview-Consistent Diffusion for Object Reconstruction from Sparse Views](<https://arxiv.org/abs/2308.14078>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2308.14078>)
  <br>2023-08-27 · 3D / 多视角一致性 / 蒸馏

  **[AAAI 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  多视角约束与生成先验结合，可作为世界模型几何背景。

  <details>
  <summary>brief</summary>

  - **问题**：极少视图下的重建难兼顾新视角质量、几何一致性和细节。
  - **方法**：以极线特征控制图像扩散，再用类别分数蒸馏优化辐射场。
  - **价值**：增强未见类别的稀疏重建并减少过平滑。
  - **局限**：需要已知位姿及逐对象优化，生成的遮挡区域仍可能偏离真实形状。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2308.14078">[2]</a> · <a href="https://arxiv.org/pdf/2308.14078">[3]</a>
  核验：2026-10-13

  </details>

+ [SparseGNV: Generating Novel Views of Indoor Scenes with Sparse Input Views](<https://arxiv.org/abs/2305.07024>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2305.07024>)
  <br>2023-05-11 · 3D / 场景表示 / 新视角

  **[AAAI 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  早期显式几何与生成上下文结合方案，适合作为背景阅读。

  <details>
  <summary>brief</summary>

  - **问题**：稀疏室内视图缺少覆盖，直接重建或二维补全难保持一致。
  - **方法**：用神经点云渲染提供结构上下文，再自回归生成新视角图像标记。
  - **价值**：联合几何约束与跨场景生成先验。
  - **局限**：依赖静态室内场景及几何输入，未建模动态状态转移。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2305.07024">[2]</a> · <a href="https://arxiv.org/pdf/2305.07024">[3]</a>
  核验：2026-10-13

  </details>

+ [ViewWeaver: Geometry-Grounded Generative Rendering for 3D-Aware Image Customization](<https://doi.org/10.1145/3799902.3811059>)<br>
  [![Paper](https://img.shields.io/badge/Paper-b31b1b.svg)](<https://doi.org/10.1145/3799902.3811059>)
  <br>日期待核实 · 三维感知 / 图像定制 / 待补引言

  **[SIGGRAPH 2026](<https://arc.tencent.com/academic>)** · **P2 选读** · 待补引言
  暂定：三维一致图像定制可供世界模型参考；尚未取得引言，需补读后确认。

  <details>
  <summary>brief</summary>

  - **问题**：该工作关注三维感知的图像定制；此条目前仅完成身份与录用信息核验。
  - **方法**：尚未取得可读引言，不据摘要编写方法分析。
  - **价值**：保留官方收录记录，供后续补齐阅读与比较。
  - **局限**：当前优先级仅为主题相关性的暂定判断，不属于完成摘要与引言阅读的导读。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://doi.org/10.1145/3799902.3811059">[2]</a>
  核验：2026-10-13

  </details>


## 图像生成与编辑

+ [Taming Rectified Flow for Inversion and Editing](<https://arxiv.org/abs/2411.04746>)<br>
  [![Star](https://img.shields.io/github/stars/wangjiangshan0725/RF-Solver-Edit.svg?style=social&label=Star)](<https://github.com/wangjiangshan0725/RF-Solver-Edit>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2411.04746>)
  <br>2024-11-07 · 流匹配 / 视频生成 / 视频编辑

  **[ICML 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  理解流匹配采样误差与视频编辑中的结构保持。

  <details>
  <summary>brief</summary>

  - **问题**：流模型反演的数值误差会逐步累积，导致重建和编辑偏离源内容。
  - **方法**：用高阶展开改进常微分方程求解，再共享反演注意力特征进行编辑。
  - **价值**：无需训练即可增强图像与视频的结构保真。
  - **局限**：改进的是采样和反演误差，不直接解决跨视频时间的自回归漂移。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2411.04746">[2]</a> · <a href="https://arxiv.org/pdf/2411.04746">[3]</a> · <a href="https://github.com/wangjiangshan0725/RF-Solver-Edit">[4]</a>
  核验：2026-10-13

  </details>

+ [PhotoMaker: Customizing Realistic Human Photos via Stacked ID Embedding](<https://arxiv.org/abs/2312.04461>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2312.04461>)
  <br>2023-12-07 · Avatar / 个性化生成 / 主体一致性

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  Avatar 身份保持和参考条件设计的基础方法。

  <details>
  <summary>brief</summary>

  - **问题**：快速个性化生成难同时保留身份、变化姿态并遵循文字。
  - **方法**：堆叠多张参考身份嵌入替换类别词，并构造跨视角身份训练数据。
  - **价值**：无需逐身份微调即可生成多样人物图像。
  - **局限**：静态身份保持不保证长视频中表情、动作与身份的稳定解耦。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2312.04461">[2]</a> · <a href="https://arxiv.org/pdf/2312.04461">[3]</a>
  核验：2026-10-13

  </details>

+ [T2I-Adapter: Learning Adapters to Dig out More Controllable Ability for Text-to-Image Diffusion Models](<https://arxiv.org/abs/2302.08453>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/T2I-Adapter.svg?style=social&label=Star)](<https://github.com/TencentARC/T2I-Adapter>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2302.08453>)
  <br>2023-02-16 · 图像生成 / 条件控制 / 适配器

  **[AAAI 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  轻量条件控制是视频与 Avatar 控制分支的重要基础。

  <details>
  <summary>brief</summary>

  - **问题**：仅靠文字难准确控制生成结果的结构、颜色和姿态。
  - **方法**：冻结生成骨干，用轻量适配器对齐外部控制信号与内部多尺度特征。
  - **价值**：不同条件可组合，并能迁移到同源定制模型。
  - **局限**：原始验证在静态图像，视频扩展仍需处理时序及条件冲突。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2302.08453">[2]</a> · <a href="https://arxiv.org/pdf/2302.08453">[3]</a> · <a href="https://github.com/TencentARC/T2I-Adapter">[4]</a>
  核验：2026-10-13

  </details>

+ [IC-Custom: Diverse Image Customization via In-Context Learning](<https://arxiv.org/abs/2507.01926>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/IC-Custom.svg?style=social&label=Star)](<https://github.com/TencentARC/IC-Custom>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2507.01926>)
  <br>2025-07-02 · 主体一致性 / 图像生成 / 条件控制

  **[ICLR 2026](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  主体身份控制可作为 Avatar 外观定制的补充阅读。

  <details>
  <summary>brief</summary>

  - **问题**：图像定制常将指定区域编辑和自由生成分开，难统一身份控制。
  - **方法**：拼接参考与目标图像，以任务标记和边界位置编码区分条件及掩码。
  - **价值**：一个框架兼容不同位置约束，并增强身份保持。
  - **局限**：主要验证静态图像，时间维度的身份与动作一致性尚未覆盖。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2507.01926">[2]</a> · <a href="https://arxiv.org/pdf/2507.01926">[3]</a> · <a href="https://github.com/TencentARC/IC-Custom">[4]</a>
  核验：2026-10-13

  </details>

+ [BrushEdit: All-In-One Image Inpainting and Editing](<https://arxiv.org/abs/2412.10316>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/BrushEdit.svg?style=social&label=Star)](<https://github.com/TencentARC/BrushEdit>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2412.10316>)
  <br>2024-12-13 · Agent / 交互控制 / 图像编辑

  **[TPAMI 2026](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  可参考可解释的视觉编辑 Agent 流程，主线相关度次于视频。

  <details>
  <summary>brief</summary>

  - **问题**：图像编辑指令难同时转成可靠区域定位和生成条件。
  - **方法**：多模态模型拆解编辑任务，再用掩码与 BrushNet 完成局部重绘。
  - **价值**：支持用户检查与修正中间控制信息。
  - **局限**：编辑质量依赖定位和掩码，尚未覆盖实时连续视频交互。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2412.10316">[2]</a> · <a href="https://arxiv.org/pdf/2412.10316">[3]</a> · <a href="https://github.com/TencentARC/BrushEdit">[4]</a>
  核验：2026-10-13

  </details>

+ [SphereDiffusion: Spherical Geometry-Aware Distortion Resilient Diffusion Model](<https://arxiv.org/abs/2403.10044>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2403.10044>)
  <br>2024-03-15 · 全景生成 / 几何约束 / 图像生成

  **[AAAI 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  全景空间连续性设计可补充沉浸式世界内容生成。

  <details>
  <summary>brief</summary>

  - **问题**：平面扩散先验难处理球面畸变，容易错配语义并产生接缝。
  - **方法**：注入对象语义与可变形特征，通过球面旋转训练和去噪增强几何一致性。
  - **价值**：提高分割条件下的可控全景图像质量。
  - **局限**：主要验证静态室内全景，未涵盖动态视频和自由平移视角。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2403.10044">[2]</a> · <a href="https://arxiv.org/pdf/2403.10044">[3]</a>
  核验：2026-10-13

  </details>

+ [BrushNet: A Plug-and-Play Image Inpainting Model with Decomposed Dual-Branch Diffusion](<https://arxiv.org/abs/2403.06976>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/BrushNet.svg?style=social&label=Star)](<https://github.com/TencentARC/BrushNet>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2403.06976>)
  <br>2024-03-11 · 图像补全 / 扩散模型 / 条件控制

  **[ECCV 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  视频补全和编辑分支的基础设计，可按实现需要选读。

  <details>
  <summary>brief</summary>

  - **问题**：将受损图像与噪声早期混合会削弱像素约束并增加学习负担。
  - **方法**：分离纯图像条件分支与生成分支，逐层注入特征并进行模糊边界融合。
  - **价值**：增强区域保留和文本一致性，支持可插拔补全。
  - **局限**：原始方法面向静态图像，时间一致性需额外建模。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2403.06976">[2]</a> · <a href="https://arxiv.org/pdf/2403.06976">[3]</a> · <a href="https://github.com/TencentARC/BrushNet">[4]</a>
  核验：2026-10-13

  </details>

+ [DiffEditor: Boosting Accuracy and Flexibility on Diffusion-based Image Editing](<https://arxiv.org/abs/2402.02583>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2402.02583>)
  <br>2024-02-04 · 交互控制 / 图像编辑 / 扩散采样

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  局部随机性与保真度权衡可启发交互生成控制。

  <details>
  <summary>brief</summary>

  - **问题**：确定性编辑难生成源图中不存在的细节，复杂操作又容易产生伪影。
  - **方法**：结合图像提示、局部随机采样、区域分数引导和回溯式采样。
  - **价值**：兼顾内容保持与移动、拖拽和跨图粘贴的灵活性。
  - **局限**：主要是单图编辑，扩展到视频还需显式处理跨帧一致性。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2402.02583">[2]</a> · <a href="https://arxiv.org/pdf/2402.02583">[3]</a>
  核验：2026-10-13

  </details>

+ [SmartEdit: Exploring Complex Instruction-based Image Editing with Multimodal Large Language Models](<https://arxiv.org/abs/2312.06739>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/SmartEdit.svg?style=social&label=Star)](<https://github.com/TencentARC/SmartEdit>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2312.06739>)
  <br>2023-12-11 · 图像编辑 / 多模态推理 / 指令控制

  **[CVPR 2024 &#91;Highlight&#93;](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  复杂视觉指令到生成控制的桥接可作为基础阅读。

  <details>
  <summary>brief</summary>

  - **问题**：简单文本编码难定位具有属性关系或常识约束的编辑对象。
  - **方法**：引入多模态语言模型与双向交互，再用感知数据和少量复杂编辑数据训练。
  - **价值**：提升复杂指令理解并提供专门评测集。
  - **局限**：仍是静态编辑，无法据此推断视频身份保持或实时交互能力。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2312.06739">[2]</a> · <a href="https://arxiv.org/pdf/2312.06739">[3]</a> · <a href="https://github.com/TencentARC/SmartEdit">[4]</a>
  核验：2026-10-13

  </details>

+ [CustomNet: Zero-shot Object Customization with Variable-Viewpoints in Text-to-Image Diffusion Models](<https://arxiv.org/abs/2310.19784>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/CustomNet.svg?style=social&label=Star)](<https://github.com/TencentARC/CustomNet>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2310.19784>)
  <br>2023-10-30 · 主体一致性 / 图像生成 / 视角控制

  **[ACM MM 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  主体身份与视角解耦可补充 Avatar 外观控制。

  <details>
  <summary>brief</summary>

  - **问题**：对象定制常保留身份却复制原姿态，或改变姿态后丢失细节。
  - **方法**：引入三维新视角先验，分别控制对象位置、视角及文本或图像背景。
  - **价值**：无需测试时优化即可完成多条件对象定制。
  - **局限**：主要生成静态图像，时序稳定性和物理交互尚未纳入。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2310.19784">[2]</a> · <a href="https://arxiv.org/pdf/2310.19784">[3]</a> · <a href="https://github.com/TencentARC/CustomNet">[4]</a>
  核验：2026-10-13

  </details>


## 视频理解与推理

+ [OmniScript: Towards Audio-Visual Script Generation for Long-Form Cinematic Video](<https://arxiv.org/abs/2604.11102>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/OmniScript.svg?style=social&label=Star)](<https://github.com/TencentARC/OmniScript>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2604.11102>)
  <br>2026-04-13 · 事件记忆 / 多模态 / 视频理解

  **[ECCV 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  结构化视频事件记录可借鉴为 Agent 的情景记忆。

  <details>
  <summary>brief</summary>

  - **问题**：长视频脚本需要同步描述动作、对白、情绪与事件时间。
  - **方法**：以分层脚本监督和分段奖励训练音视频模型生成带时间戳记录。
  - **价值**：提供可用于检索与叙事分析的结构化视频表示。
  - **局限**：任务是视频转脚本，长输出成本及时间标注质量仍构成约束。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2604.11102">[2]</a> · <a href="https://arxiv.org/pdf/2604.11102">[3]</a> · <a href="https://github.com/TencentARC/OmniScript">[4]</a>
  核验：2026-10-13

  </details>

+ [Learning to Reason in 4D: Dynamic Spatial Understanding for Vision Language Models](<https://arxiv.org/abs/2512.20557>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/DSR_Suite.svg?style=social&label=Star)](<https://github.com/TencentARC/DSR_Suite>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2512.20557>)
  <br>2025-12-23 · 4D / 空间推理 / 视频理解

  **[CVPR 2026](<https://openaccess.thecvf.com/content/CVPR2026/html/Zhou_Learning_to_Reason_in_4D_Dynamic_Spatial_Understanding_for_Vision_CVPR_2026_paper.html>)** · **P1 重点** · 摘要与引言
  将动态几何压缩成可查询状态，关联世界模型与空间规划。

  <details>
  <summary>brief</summary>

  - **问题**：视频模型缺乏稳定的动态三维状态，直接加入几何又容易干扰语义。
  - **方法**：自动构造空间推理数据，以问题引导的双级模块筛选几何信息。
  - **价值**：改善动态空间推理并控制通用能力损失。
  - **局限**：依赖重建伪标注，选择题结果不能替代闭环规划验证。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2512.20557">[2]</a> · <a href="https://arxiv.org/pdf/2512.20557">[3]</a> · <a href="https://github.com/TencentARC/DSR_Suite">[4]</a> · <a href="https://openaccess.thecvf.com/content/CVPR2026/html/Zhou_Learning_to_Reason_in_4D_Dynamic_Spatial_Understanding_for_Vision_CVPR_2026_paper.html">[5]</a>
  核验：2026-10-13

  </details>

+ [TimeLens: Rethinking Video Temporal Grounding with Multimodal LLMs](<https://arxiv.org/abs/2512.14698>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/TimeLens.svg?style=social&label=Star)](<https://github.com/TencentARC/TimeLens>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2512.14698>)
  <br>2025-12-16 · 时间定位 / 视频理解 / 评测

  **[CVPR 2026](<https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_TimeLens_Rethinking_Video_Temporal_Grounding_with_Multimodal_LLMs_CVPR_2026_paper.html>)** · **P1 重点** · 摘要与引言
  事件时间定位是视频 Agent 记忆检索及生成评测的基础。

  <details>
  <summary>brief</summary>

  - **问题**：时间定位基准中的模糊查询与错误时间戳会误导模型排名。
  - **方法**：重标评测和训练集，比较时间编码、无思考强化学习及采样策略。
  - **价值**：建立更可靠的时间感知训练与评估基线。
  - **局限**：针对事件定位，不能直接推断复杂因果规划或长期记忆能力。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2512.14698">[2]</a> · <a href="https://arxiv.org/pdf/2512.14698">[3]</a> · <a href="https://github.com/TencentARC/TimeLens">[4]</a> · <a href="https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_TimeLens_Rethinking_Video_Temporal_Grounding_with_Multimodal_LLMs_CVPR_2026_paper.html">[5]</a>
  核验：2026-10-13

  </details>

+ [Video-Holmes: Can MLLM Think Like Holmes for Complex Video Reasoning?](<https://arxiv.org/abs/2505.21374>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/Video-Holmes.svg?style=social&label=Star)](<https://github.com/TencentARC/Video-Holmes>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2505.21374>)
  <br>2025-05-27 · 视频理解 / 评测 / 长时记忆

  **[ECCV 2026](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  用跨片段因果推理检验视频 Agent 的记忆与理解。

  <details>
  <summary>brief</summary>

  - **问题**：视频模型识别局部内容后仍难整合跨片段线索。
  - **方法**：从悬疑电影构造七类推理任务，要求关联证据解释事件。
  - **价值**：将感知与长程因果推理能力分开诊断。
  - **局限**：电影选择题具有叙事先验，不能直接代表在线交互能力。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2505.21374">[2]</a> · <a href="https://arxiv.org/pdf/2505.21374">[3]</a> · <a href="https://github.com/TencentARC/Video-Holmes">[4]</a>
  核验：2026-10-13

  </details>

+ [E.T. Bench: Towards Open-Ended Event-Level Video-Language Understanding](<https://arxiv.org/abs/2409.18111>)<br>
  [![Star](https://img.shields.io/github/stars/PolyU-ChenLab/ETBench.svg?style=social&label=Star)](<https://github.com/PolyU-ChenLab/ETBench>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2409.18111>)
  <br>2024-09-26 · 情景记忆 / 时间定位 / 视频理解 / 评测

  **[NeurIPS 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  事件定位、情景记忆与开放回答适合视频 Agent 评价。

  <details>
  <summary>brief</summary>

  - **问题**：粗粒度视频问答难发现事件级定位和时间理解缺陷。
  - **方法**：构建多域多事件任务，并用嵌入匹配预测时间戳及配套指令数据。
  - **价值**：同时诊断指代、定位、密集描述和复杂事件理解。
  - **局限**：离线评测不直接覆盖持续输入、记忆淘汰及交互延迟。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2409.18111">[2]</a> · <a href="https://arxiv.org/pdf/2409.18111">[3]</a> · <a href="https://github.com/PolyU-ChenLab/ETBench">[4]</a>
  核验：2026-10-13

  </details>

+ [SynopGround: A Large-Scale Dataset for Multi-Paragraph Video Grounding from TV Dramas and Synopses](<https://arxiv.org/abs/2408.01669>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2408.01669>)
  <br>2024-08-03 · 时间定位 / 视频理解 / 长时记忆

  **[ACM MM 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  长叙事与多段查询定位，可用于视频记忆检索和事件规划评价。

  <details>
  <summary>brief</summary>

  - **问题**：短查询和短片段评测难覆盖复杂叙事，且容易对应多个相似时刻。
  - **方法**：以电视剧及人工梗概构建多段定位数据，用局部与全局推理联合对齐。
  - **价值**：检验长上下文中抽象情节和具体事件的关联。
  - **局限**：影视梗概具有强叙事结构，向在线第一视角任务迁移需验证。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2408.01669">[2]</a> · <a href="https://arxiv.org/pdf/2408.01669">[3]</a>
  核验：2026-10-13

  </details>

+ [EA-VTR: Event-Aware Video-Text Retrieval](<https://arxiv.org/abs/2407.07478>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2407.07478>)
  <br>2024-07-10 · 事件记忆 / 检索 / 视频理解

  **[ECCV 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  事件内容与顺序表征适合视频 Agent 记忆检索。

  <details>
  <summary>brief</summary>

  - **问题**：全局视频对比学习忽略细节事件和事件之间的时间关系。
  - **方法**：补充帧级描述并合成事件转场，同时训练帧级内容与视频级时序对齐。
  - **价值**：保持高效检索并增强多事件理解。
  - **局限**：单帧近似短事件和拼接转场存在偏差，不保证真实因果理解。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2407.07478">[2]</a> · <a href="https://arxiv.org/pdf/2407.07478">[3]</a>
  核验：2026-10-13

  </details>

+ [ST-LLM: Large Language Models Are Effective Temporal Learners](<https://arxiv.org/abs/2404.00308>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/ST-LLM.svg?style=social&label=Star)](<https://github.com/TencentARC/ST-LLM>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2404.00308>)
  <br>2024-03-30 · 上下文压缩 / 时间建模 / 视频理解

  **[ECCV 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  直接时空序列建模是视频 Agent 感知的重要基础对照。

  <details>
  <summary>brief</summary>

  - **问题**：时间平均池化抹掉运动顺序，额外视频模块又增加训练成本。
  - **方法**：将时空标记直接交给语言模型，以动态掩码和全局局部输入控制开销。
  - **价值**：利用语言模型序列能力改善运动相关理解。
  - **局限**：长视频仍依赖压缩采样，未提供持续可更新的外部记忆。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2404.00308">[2]</a> · <a href="https://arxiv.org/pdf/2404.00308">[3]</a> · <a href="https://github.com/TencentARC/ST-LLM">[4]</a>
  核验：2026-10-13

  </details>

+ [BT-Adapter: Video Conversation is Feasible Without Video Instruction Tuning](<https://arxiv.org/abs/2309.15785>)<br>
  [![Star](https://img.shields.io/github/stars/farewellthree/BT-Adapter.svg?style=social&label=Star)](<https://github.com/farewellthree/BT-Adapter>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2309.15785>)
  <br>2023-09-27 · 视频理解 / 训练效率 / 适配器

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  低成本引入时间建模，适合视频 Agent 感知骨干选型。

  <details>
  <summary>brief</summary>

  - **问题**：图像对话模型缺乏时序能力，而完整视频微调成本较高。
  - **方法**：冻结图像编码器，训练旁路时空适配器与非对称掩码对齐任务。
  - **价值**：可接入共享视觉编码器的对话模型，减少视频指令数据依赖。
  - **局限**：依赖兼容的图像编码器，未专门解决长时记忆与在线响应。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2309.15785">[2]</a> · <a href="https://arxiv.org/pdf/2309.15785">[3]</a> · <a href="https://github.com/farewellthree/BT-Adapter">[4]</a>
  核验：2026-10-13

  </details>

+ [Chinese Title Generation for Short Videos: Dataset, Metric and Algorithm](<https://doi.org/10.1109/TPAMI.2024.3365739>)<br>
  [![Paper](https://img.shields.io/badge/Paper-b31b1b.svg)](<https://doi.org/10.1109/TPAMI.2024.3365739>)
  <br>日期待核实 · 中文数据集 / 待补引言 / 视频标题

  **[TPAMI 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 待补引言
  暂定：视频标题与吸引力评测属于内容理解支线；引言尚未取得，暂缓方法判断。

  <details>
  <summary>brief</summary>

  - **问题**：该工作研究中文短视频标题生成；此条目前仅完成身份与期刊信息核验。
  - **方法**：尚未取得期刊版引言，不以早期会议稿替代阅读。
  - **价值**：保留官方收录记录，便于补齐期刊版阅读。
  - **局限**：当前优先级仅为主题相关性的暂定判断，未对方法、实验及版本增量作结论。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://doi.org/10.1109/TPAMI.2024.3365739">[2]</a>
  核验：2026-10-13

  </details>


## 语音与音频

+ [AudioStory: Generating Long-Form Narrative Audio with Large Language Models](<https://arxiv.org/abs/2508.20088>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC/AudioStory.svg?style=social&label=Star)](<https://github.com/TencentARC/AudioStory>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2508.20088>)
  <br>2025-08-27 · 叙事规划 / 长时一致性 / 音频生成

  **[CVPR 2026](<https://openaccess.thecvf.com/content/CVPR2026/html/Guo_AudioStory_Generating_Long-Form_Narrative_Audio_with_Large_Language_Models_CVPR_2026_paper.html>)** · **P1 重点** · 摘要与引言
  分层事件规划及跨段状态传递可迁移到长视频和 Avatar 音频。

  <details>
  <summary>brief</summary>

  - **问题**：短音频生成器难把复杂叙事分解成连贯的长时声音事件。
  - **方法**：由语言模型规划分段，以语义和残差桥接标记分别传递内容及跨事件声学信息。
  - **价值**：联合优化理解与生成，支持叙事音频和视频配音。
  - **局限**：分段叙事生成不等同于可打断的实时对话音频。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2508.20088">[2]</a> · <a href="https://arxiv.org/pdf/2508.20088">[3]</a> · <a href="https://github.com/TencentARC/AudioStory">[4]</a> · <a href="https://openaccess.thecvf.com/content/CVPR2026/html/Guo_AudioStory_Generating_Long-Form_Narrative_Audio_with_Large_Language_Models_CVPR_2026_paper.html">[5]</a>
  核验：2026-10-13

  </details>

+ [AFL-Net: Integrating Audio, Facial, and Lip Modalities with a Two-step Cross-attention for Robust Speaker Diarization in the Wild](<https://arxiv.org/abs/2312.05730>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2312.05730>)
  <br>2023-12-10 · Avatar / 说话人分离 / 音视频理解

  **[INTERSPEECH 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  多说话人归属与模态缺失处理可用于交互 Avatar 感知。

  <details>
  <summary>brief</summary>

  - **问题**：真实视频中画外音、噪声与遮挡使说话人分段归属困难。
  - **方法**：融合声音、面部和唇动，通过两步交叉注意力及视觉随机遮蔽训练。
  - **价值**：利用互补模态提高身份区分并适应缺失视觉输入。
  - **局限**：是说话人日志任务，未直接实现轮次决策或生成端同步。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2312.05730">[2]</a> · <a href="https://arxiv.org/pdf/2312.05730">[3]</a>
  核验：2026-10-13

  </details>

+ [Neural Concatenative Singing Voice Conversion: Rethinking Concatenation-Based Approach for One-Shot Singing Voice Conversion](<https://arxiv.org/abs/2312.04919>)<br>
  [![Star](https://img.shields.io/github/stars/thuhcsi/NeuCoSVC.svg?style=social&label=Star)](<https://github.com/thuhcsi/NeuCoSVC>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2312.04919>)
  <br>2023-12-08 · Avatar / 语音转换 / 音色控制

  **[ICASSP 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  声音身份保持可补充 Avatar 语音方向，重点仍是歌声转换。

  <details>
  <summary>brief</summary>

  - **问题**：内容与音色解耦不充分会让转换歌声残留原歌手特征。
  - **方法**：从目标录音检索相近自监督特征，再结合显式音高、响度和谐波滤波合成。
  - **价值**：利用参考特征减少音色泄漏并保持旋律。
  - **局限**：表现依赖参考片段的覆盖，未验证完整实时对话链路。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2312.04919">[2]</a> · <a href="https://arxiv.org/pdf/2312.04919">[3]</a> · <a href="https://github.com/thuhcsi/NeuCoSVC">[4]</a>
  核验：2026-10-13

  </details>

+ [Unified Pretraining Target Based Video-music Retrieval With Music Rhythm And Video Optical Flow Information](<https://arxiv.org/abs/2309.09421>)<br>
  [![Star](https://img.shields.io/github/stars/TencentARC-QQ/UT-CMVMR.svg?style=social&label=Star)](<https://github.com/TencentARC-QQ/UT-CMVMR>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2309.09421>)
  <br>2023-09-18 · 检索 / 节奏 / 音视频对齐

  **[ICASSP 2024](<https://arc.tencent.com/academic>)** · **P2 选读** · 摘要与引言
  节奏与运动对齐可为音视频联合生成提供评价思路。

  <details>
  <summary>brief</summary>

  - **问题**：视频与音乐独立预训练目标不一致，全局平均特征又丢失节奏对应。
  - **方法**：统一预训练标签，以片段特征结合音乐节奏和视频光流进行跨模态匹配。
  - **价值**：增强配乐检索的语义及时间相关性。
  - **局限**：任务是检索已有音乐，未直接生成或实现细粒度音画同步。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2309.09421">[2]</a> · <a href="https://arxiv.org/pdf/2309.09421">[3]</a> · <a href="https://github.com/TencentARC-QQ/UT-CMVMR">[4]</a>
  核验：2026-10-13

  </details>

+ [HumTrans: A Novel Open-Source Dataset for Humming Melody Transcription and Beyond](<https://arxiv.org/abs/2309.09623>)<br>
  [![Star](https://img.shields.io/github/stars/shansongliu/HumTrans.svg?style=social&label=Star)](<https://github.com/shansongliu/HumTrans>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2309.09623>)
  <br>2023-09-18 · 数据集 / 音乐转录 / 音频

  **[ICASSP 2024](<https://arc.tencent.com/academic>)** · **P3 暂缓** · 摘要与引言
  面向哼唱转录数据，当前可暂缓。

  <details>
  <summary>brief</summary>

  - **问题**：哼唱音高不稳定且公开标注数据稀缺，限制自动转谱研究。
  - **方法**：让具备音乐经验的参与者跟随乐谱与旋律录制，构建配套音频和转录基线。
  - **价值**：提供较大规模的公开哼唱研究资源。
  - **局限**：参与者和录制方式较受控，不能代表所有自然随意哼唱。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2309.09623">[2]</a> · <a href="https://arxiv.org/pdf/2309.09623">[3]</a> · <a href="https://github.com/shansongliu/HumTrans">[4]</a>
  核验：2026-10-13

  </details>

+ [Music Understanding LLaMA: Advancing Text-to-Music Generation with Question Answering and Captioning](<https://arxiv.org/abs/2308.11276>)<br>
  [![Star](https://img.shields.io/github/stars/crypto-code/MU-LLaMA.svg?style=social&label=Star)](<https://github.com/crypto-code/MU-LLaMA>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2308.11276>)
  <br>2023-08-22 · 数据构建 / 音乐 / 音频理解

  **[ICASSP 2024](<https://arc.tencent.com/academic>)** · **P3 暂缓** · 摘要与引言
  音乐标注管线可作数据工程参考，与核心研究目标较远。

  <details>
  <summary>brief</summary>

  - **问题**：开放音乐文本对稀缺，通用音频问答模型又缺少音乐知识。
  - **方法**：连接音乐编码器与语言模型，用已有描述和标签构造问答训练集。
  - **价值**：通过音乐问答自动生成多种形式的描述。
  - **局限**：文本伪标注可能传播错误，工作本身并非音乐或视频生成器。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2308.11276">[2]</a> · <a href="https://arxiv.org/pdf/2308.11276">[3]</a> · <a href="https://github.com/crypto-code/MU-LLaMA">[4]</a>
  核验：2026-10-13

  </details>


## 视觉感知

+ [UniPixel: Unified Object Referring and Segmentation for Pixel-Level Visual Reasoning](<https://arxiv.org/abs/2509.18094>)<br>
  [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2509.18094>)
  <br>2025-09-22 · Agent / 分割 / 对象记忆 / 视频理解

  **[NeurIPS 2025](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  对象级记忆库可直接借鉴到视频 Agent 的状态追踪。

  <details>
  <summary>brief</summary>

  - **问题**：整体视频问答难对用户指定对象进行定位、跟踪并持续推理。
  - **方法**：统一指代与分割表示，用对象记忆库保存时空信息并按需更新。
  - **价值**：在同一模型中支持视觉提示、掩码输出和对象关系问答。
  - **局限**：记忆主要服务当前输入中的对象，跨会话持久记忆尚未验证。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2509.18094">[2]</a> · <a href="https://arxiv.org/pdf/2509.18094">[3]</a>
  核验：2026-10-13

  </details>

+ [DepthCrafter: Generating Consistent Long Depth Sequences for Open-world Videos](<https://arxiv.org/abs/2409.02095>)<br>
  [![Star](https://img.shields.io/github/stars/Tencent/DepthCrafter.svg?style=social&label=Star)](<https://github.com/Tencent/DepthCrafter>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2409.02095>)
  <br>2024-09-03 · 时序一致性 / 深度估计 / 视频理解

  **[CVPR 2025 &#91;Highlight&#93;](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  长时稳定深度可用于世界模型几何监督与视频控制。

  <details>
  <summary>brief</summary>

  - **问题**：逐帧深度预测会闪烁，依赖相机位姿的优化又难适配开放视频。
  - **方法**：分阶段融合真实与合成数据训练视频扩散模型，并重叠拼接长序列。
  - **价值**：利用生成先验获得细节丰富且时间一致的深度。
  - **局限**：单目尺度仍存在歧义，分段稳定性不等同于长期全局几何正确。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2409.02095">[2]</a> · <a href="https://arxiv.org/pdf/2409.02095">[3]</a> · <a href="https://github.com/Tencent/DepthCrafter">[4]</a>
  核验：2026-10-13

  </details>

+ [YOLO-World: Real-Time Open-Vocabulary Object Detection](<https://arxiv.org/abs/2401.17270>)<br>
  [![Star](https://img.shields.io/github/stars/AILab-CVC/YOLO-World.svg?style=social&label=Star)](<https://github.com/AILab-CVC/YOLO-World>) [![arXiv](https://img.shields.io/badge/arXiv-b31b1b.svg)](<https://arxiv.org/abs/2401.17270>)
  <br>2024-01-30 · Agent / 实时感知 / 目标检测

  **[CVPR 2024](<https://arc.tencent.com/academic>)** · **P1 重点** · 摘要与引言
  适合实时交互 Agent 的开放词汇感知前端。

  <details>
  <summary>brief</summary>

  - **问题**：固定类别检测器无法覆盖开放场景，开放词汇模型又常过于昂贵。
  - **方法**：用区域文本对比预训练和可重参数化图文融合，离线编码用户词汇。
  - **价值**：减少在线文本编码成本，兼顾开放类别与检测效率。
  - **局限**：预编码词汇变化时需更新，检测结果本身不含对象记忆或规划。

  来源：<a href="https://arc.tencent.com/academic">[1]</a> · <a href="https://arxiv.org/abs/2401.17270">[2]</a> · <a href="https://arxiv.org/pdf/2401.17270">[3]</a> · <a href="https://github.com/AILab-CVC/YOLO-World">[4]</a>
  核验：2026-10-13

  </details>

## 维护

Python 3.9+，无第三方依赖。

```bash
python3 scripts/paper_watch.py validate
python3 scripts/paper_watch.py build --check
python3 -m unittest discover -s tests -v
node --test tests/reader.test.cjs
```

数据和源码公开；不收录 PDF、私人笔记、实验记录或会话原文。本仓库以 gh-pages 静态分支部署阅读页及离线 ZIP；修改 main 后需同步更新静态分支，详见 [维护说明](docs/INTEGRATION.md)。

组织形式参考 [Awesome-Video-Diffusion](https://github.com/showlab/Awesome-Video-Diffusion)。摘要为本项目独立撰写；论文、模型和源码的使用条件以各原始发布方为准。
