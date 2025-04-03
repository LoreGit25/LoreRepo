# LLM Engineer 岗位指南（大语言模型工程方向）

LLM Engineer 是连接前沿模型研究与实际产品落地的关键岗位。这个角色不仅需要深刻理解大语言模型的训练与推理机制，还要具备强大的系统搭建、部署优化和工具链集成能力。

---

## 🎯 岗位定位与价值

- **核心目标**：将研究成果变为稳定、可扩展的模型服务，为对话、生成、搜索、推荐等业务场景提供 LLM 支撑。
- **适合人群**：具有模型工程背景、熟悉 PyTorch 或深度学习框架、能解决大规模训练和部署瓶颈的开发者。
- **岗位优势**：
  - 直接与研究科学家协作，深入理解模型结构
  - 有机会参与千亿级模型训练或高性能推理系统
  - 影响产品体验，技术闭环速度快，成就感高

---

## 🔍 核心职责详解

### 1. 构建训练与微调系统

- 支持 SFT、LoRA、QLoRA 等训练范式
- 构建自定义 DatasetLoader、Tokenizer 预处理器、Trainer 管理器
- 采用 FSDP、DeepSpeed ZeRO、gradient checkpointing 降低显存占用

### 2. 推理系统开发与优化

- 搭建高性能服务（如基于 `vLLM` 的异步推理系统）
- 优化 KV Cache、Token Prefill、Batch Scheduling
- 实现 Token Streaming、并发响应、多会话管理

### 3. 模型压缩与部署

- 使用量化（INT4, INT8）、蒸馏、剪枝减少模型体积
- 支持 Triton Server、ONNX Runtime、TorchScript 推理部署
- 在 GPU、CPU、边缘端部署不同版本模型

### 4. 工程集成与平台化建设

- 将模型封装为 API（FastAPI、gRPC），对接下游系统
- 构建 CI/CD 自动化训练 & 推理部署流程（配合 Docker, K8s）
- 管理模型版本、监控延迟、QPS、失败率、日志

### 5. 应用层能力实现（选修但加分）

- 实现 Function Calling、ReAct Prompt 框架
- 构建 Agent 系统（如 Toolformer, LangChain 应用）
- 支持多轮上下文缓存、记忆管理、用户定制模板

---

## 🛠️ 技能要求拆解

| 技能类别 | 详细要求 |
|----------|----------|
| **深度学习能力** | 熟悉 Transformer 结构、模型训练流程、loss 调试 |
| **分布式训练** | 使用 FSDP / DeepSpeed 训练 >10B 参数模型 |
| **推理系统构建** | 掌握 KV Cache、Beam Search、Speculative Decoding 等推理加速方法 |
| **MLOps 工程** | 熟悉 Docker、Kubernetes、GitOps 流程 |
| **性能优化** | 掌握 profile 工具，能定位 GPU 占用高、内存泄漏等问题 |
| **编程基础** | 精通 Python，了解 CUDA/C++ 为部署优化加分项 |

---

## 🏢 典型雇主与工作特色

| 公司 / 团队 | 岗位亮点 |
|-------------|----------|
| ByteDance Doubao Infra | 支持千亿模型部署，建设训练平台与推理调度系统 |
| Amazon AGI / Alexa | 构建语音助手LLM后端，注重推理效率与多语言支持 |
| Meta GenAI / Infra | 负责 LLaMA 推理服务、LoRA 微调系统与模型管理 |
| 腾讯混元团队 | 多模态 LLM 部署与大规模指令微调任务调度 |
| OpenAI Deployment Team | 支持 GPT API 推理系统，追求稳定性与高并发 |
| 初创公司（如 Modal、Replicate） | 快速交付 LLM 推理/训练托管服务，追求极致性能和简洁开发体验 |

---

## ✅ 求职建议与项目准备

### 简历关键词建议：

- “构建 xxB 模型的多机训练框架，使用 DeepSpeed ZeRO + gradient checkpointing”
- “搭建异步推理系统，使用 vLLM 将 QPS 提升 3 倍”
- “实现微调平台，支持 LoRA + QLoRA + PEFT + ChatTemplate 自动处理”

### 技术面试常见题：

| 类型 | 示例问题 |
|------|----------|
| 微调流程理解 | LoRA 和 Full Finetuning 有哪些差别？QLoRA 的原理是什么？ |
| 推理优化 | 如何提升 token 生成速度？KV Cache 如何工作？ |
| 工程设计 | 如何搭建一个高并发、多模型的推理 API 服务？ |
| Debug 实战 | Loss 不下降可能有哪些原因？显存爆炸怎么处理？ |
| 项目讲解 | 请介绍你构建过的训练/推理/平台系统架构和你做的优化 |

---

## 📚 推荐资源与工具库

### 工程框架

- [DeepSpeed](https://github.com/microsoft/DeepSpeed)：分布式训练加速利器
- [vLLM](https://github.com/vllm-project/vllm)：推理性能极佳，支持连续动态批处理
- [Hugging Face Accelerate](https://huggingface.co/docs/accelerate/index)：快速启动训练，兼容多后端
- [PEFT](https://github.com/huggingface/peft)：高效微调库，支持 LoRA、Prompt Tuning 等

### 项目推荐

- [FastChat](https://github.com/lm-sys/FastChat)：微调 + 推理一体，支持OpenAI格式接口
- [OpenChat](https://github.com/imoneoi/openchat)：指令微调 + RLHF 项目
- [Axolotl](https://github.com/OpenAccess-AI-Collective/axolotl)：全流程 RLHF 支持

### 博客/知识平台

- Hugging Face Engineering Blog（模型部署最佳实践）
- Scale AI Infra Series（真实系统的工程剖析）
- Lightning.ai Engineering Notes（MLOps 框架设计理念）

---

📁 返回上级：[岗位类型与行业.md](../岗位类型与行业.md)
