# 超级力量团队开发者套装

> Super Powers Team Developer Suite — 从设计挖掘到代码交付的完整 AI Agent 协作系统

## 概述

本套装包含三支专业 AI Agent 团队，覆盖软件开发的**设计挖掘 → 设计审问 → 开发实现**全流程。每支团队采用**黑板模式（Blackboard Pattern）+ 事件总线（Event Bus）**进行多专家协作，实现高效、低 Token 消耗的复杂任务执行。

```
design-miner-team          design-interrogator-team        dev-genius-team
  (设计挖掘)      ──→         (设计审问官)        ──→        (开发天才)
 源码分析+UX工程               架构拷问+UX设计                  TDD开发+质量门控
 9位专家 × 3轨道              7位专家 × 双轨道               5位专家 × 5道门控
```

## 团队详情

### 1. Design-Miner Team（设计挖掘）

从参考项目源码中多维度提取设计智慧——架构模式、UX工程、元方法论。

- **9 位专家**：模式识别者 → 批判性思考者 ∥ 交互/感知/情感分析者 → 抽象建模者 ∥ 跨域解构者 → 体系构建者 → 原则蒸馏者
- **3 个分析轨道**：架构分析 · UX 工程分析 · 元方法论萃取
- **独特创新**：Pre-Synthesis 预合成、品味注入（Taste Injection）、Review-Execution 分离

### 2. Design-Interrogator Team（设计审问官）

对新项目进行无死角设计拷问和 UX/UI 设计，输出可直接开发的完整设计规格。

- **7 位专家**：源码分析师 + 架构审问官（交互式多轮）∥ UX研究员 + 交互设计师 + 设计审问官 + UI设计师 → 策略裁决+文档编译
- **双轨道并行**：架构轨道（拷问式决策树遍历）+ UX/UI 轨道（设计→审问→裁决→编译）
- **独特创新**：上游富化（design-miner 代码证据交叉印证）、回退原则（GENESIS.md 世代日志）、设计偏好 reflect 式捕获

### 3. Dev-Genius Team（开发天才）

读取 DI 团队的设计规格，按五道质量门控完成 TDD 开发并交付。

- **5 位专家**：任务规划师 → 架构实施师 → 开发工程师 ↔ QA测试工程师 → 代码审查师
- **5 道质量门控**：Plan Gate → TDD Gate → Verify Gate → Review Gate → Finish Gate
- **独特创新**：TDD RED-GREEN-REFACTOR 铁律、系统化调试四阶段、verification-before-completion 证据驱动、/goal + /loop 自主循环、两阶段审查（规格符合性 → 代码质量）

## 架构设计

### 黑板模式（Blackboard Pattern）

所有团队采用黑板模式进行专家协作：
- **共享工作区**：每个专家维护专属黑板模块，全局可读
- **事件总线**：发布-订阅异步通信，解耦专家间依赖
- **局部闭环**：预定义专家对可直接反馈（如 Dev↔QA Bug 修复）
- **Token 优化**：共享状态替代链式传递，降低 50%+ Token 消耗

### 技术栈

- **平台**：Claude Code（Agent SDK）
- **专家模型**：Claude Sonnet（执行层）/ Claude Opus（架构和决策层）
- **MCP 工具**：Context7（文档查询）、Vision Server（图像分析）、Web Search Prime（网页搜索）、Sequential Thinking（深度推理）

## 快速开始

1. 将本仓库克隆到 `~/.claude/` 目录下
2. 各团队的 `agents/` 目录中的 `.md` 文件即为 Agent 配置
3. 各团队的 `skills/<team>-coordinator/skill.md` 即为协调器 Skill
4. 在 Claude Code 中通过 `/skill-name` 调用协调器

## 🍜 投喂作者

如果这个项目帮到了你，欢迎请我喝杯咖啡~

![投喂作者](donate-qr.jpg)

## 许可证

**GNU Affero General Public License v3.0 (AGPL-3.0)**

本软件包采用 AGPL-3.0 许可证。这意味着：

- ✅ 你可以自由使用、修改、分发本软件
- ✅ 你可以将本软件用于商业用途
- ⚠️ **如果你修改了本软件并通过网络提供服务，你必须公开修改后的源代码**
- ⚠️ **衍生作品也必须以 AGPL-3.0 许可开源**
- ⚠️ 分发本软件时必须附带完整的源代码和许可证声明

这是最严格的开源许可证之一，旨在确保软件及其所有衍生版本永远保持开源。

完整许可证文本见 [LICENSE](./LICENSE) 文件。

---

**维护者**：Mr.Chen  
**版本**：v3.2
