# LLM180

准备大模型实习面试时，最容易踩的坑不是完全没听过 PPO、GRPO、RAG、KV cache，而是概念都背过，一被追问“为什么这样设计、工程里哪里会失败、怎么评测、怎么和项目结合”，答案就散了。

LLM180 是一个面向国内 AI 人才计划实习和大模型算法面试的刷题页。页面将内容拆成两套独立题库：180 道大模型八股和 40 道手撕代码题。八股题重点训练在 60 到 90 秒内讲清结论、机制、工程落地和评测风险，代码题则按题目、思路、参考实现、复杂度、测试与易错点组织。

页面是单文件静态应用，无需后端、无需构建，直接打开 `index.html` 即可使用，也可以通过 GitHub Pages 在线刷题。

![Interface screenshot](assets/screenshot.png)

## 刷题页特点

- **Slide 式刷题体验**：每一页只聚焦一道题，左右切换，不做复杂信息工作台。
- **八股与代码分开训练**：顶部可在 `八股训练 180` 和 `手撕代码 40` 间切换，两套题库独立计数和切题。
- **离线代码高亮**：Python 和 SQL 参考实现内置语法高亮，本地直接打开也能区分关键字、字符串、注释和数字。
- **代码默认隐藏**：先完成思路和手写实现，再显示参考代码；切换代码题后会自动重新隐藏。
- **答案不是一句八股**：每题融合面试回答、问题本质、关键机制、详细原理、工程落地、评测风险和来源校准。
- **按真实追问组织**：覆盖“为什么有效”“哪里会失败”“成本怎么解释”“业务怎么落地”“指标怎么设计”等高频追问。
- **本地学习状态**：用 `localStorage` 保存不会、模糊、掌握和错题记录，刷新后仍可继续复盘。
- **适配国内 AI 实习面试**：覆盖腾讯青云、字节 Seed、Kimi、DeepSeek、智谱 GLM、小米 MiMo、美团 LongCat、阿里 Qwen 等方向性准备。

## 内容覆盖

- 后训练/RL：SFT、RLHF、PPO、DPO、GRPO、DAPO、RLVR、reward hacking、KL、entropy collapse
- Agent/RAG：RAG、tool calling、MCP、function calling、memory、harness、多智能体、GUI Agent、自进化
- 推理系统：MHA、KV cache、GQA/MQA、vLLM、PagedAttention、FlashAttention、speculative decoding、长上下文
- 训练系统与数据：显存估算、ZeRO/FSDP/DeepSpeed、LoRA/QLoRA、数据配比、合成数据、benchmark 污染
- 多模态/VLM：LLaVA、CLIP、VQ-VAE、Diffusion、vision tower、视频理解、多模态后训练
- 项目/论文答辩：motivation、cost、ablation、failure case、业务落地、GM 答辩
- 公司专项：腾讯青云、字节 Seed、Kimi、DeepSeek、智谱 GLM、小米 MiMo、美团 LongCat、阿里 Qwen 等
- Coding 八股：40 题，覆盖 MHA、PPO/GAE/DPO/GRPO、Softmax/CE、AdamW、RoPE、RMSNorm、KV cache、FlashAttention、采样器，以及链表、树、动态规划、滑动窗口、SQL 等高频手撕题。每题附 Python/PyTorch/NumPy/SQL 参考代码、复杂度、追问和易错点

## 使用方式

本地直接打开：

```bash
open index.html
```

或者启动任意静态服务器：

```bash
python3 -m http.server 8000
```

然后访问：

```text
http://localhost:8000
```

## 训练方式

- 左右箭头或底部按钮切换题目
- 顶部导航切换主题
- 重要性导航按基础必过、高频核心、进阶追问、项目落地过滤
- 每页融合展示题目、面试回答、问题本质、关键机制、详细原理、工程落地、评测风险和来源校准
- 本地状态通过 `localStorage` 保存，刷新后仍保留掌握状态和错题记录

快捷键：

- `←` / `→`：切换题目
- `1`：不会
- `2`：模糊
- `3`：掌握
- `B`：加入错题

## 来源校准

题库答案使用面经总结发现高频问法，并用论文、官方文档和框架文档校准技术细节。覆盖来源包括：

- InstructGPT / RLHF
- Direct Preference Optimization
- DeepSeekMath / GRPO
- DAPO
- Retrieval-Augmented Generation
- ReAct / Toolformer / MCP
- PagedAttention / vLLM
- FlashAttention
- LoRA / QLoRA
- ZeRO / DeepSpeed
- LLaVA / CLIP / VQ-VAE / DDPM
- Kimi K2、DeepSeek-V3/R1、MiMo、GLM-4.5、Qwen2.5 等公开技术报告

## 文件结构

```text
.
├── index.html
├── README.md
├── talent_plan_internship_interview_50_report.html
└── assets
    └── screenshot.png
```

## 说明

这是面试训练工具，不是论文综述。公开面经只用于总结问法和流程，标准答案优先以论文、官方文档和可复现实现为准。
