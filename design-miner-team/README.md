# Design-Miner (设计挖掘) 团队 v5.3

> **一句话**：三轨道并行 + Pre-Synthesis + 品味注入 + Review-Execution 分离 + 增强手艺结构 + 模板完整对齐，从参考项目源码中挖掘架构智慧、UX 模式和跨领域元方法论。

## v5.1 模板对齐（super-team-builder v4.2 blackboard-coordinator-template）

| 创新 | 来源 | 说明 |
|------|------|------|
| **模板框架对齐** | super-team-builder v4.2 | 协调器原则编号对齐模板 7 条标准原则 + 3 条特有创新，Agent 补全设定 7-9（工作风格/服务对象/汇报机制）|
| **调度指令理解** | agent-template.md | 全部 9 个 Agent 新增标准化"调度指令理解"章节，明确协调器触发格式和响应行为 |
| **信息传递机制标准化** | blackboard-template | 全部 Agent 的信息传递机制统一为：黑板读写表 + 下游依赖表 + 事件通知格式 |
| **MCP 工具约束显式化** | agent-template 设定X+1 | methodologist-pragmatist 新增 MCP 工具使用约束章节 |

## v5.0 核心创新（从 agentic-harness-patterns 蒸馏）
| **Pre-Synthesis** | Agent Orchestration Pattern | 协调器读完 Stage 2-3 全部产出，生成自包含简报再派发 Stage 5。贯彻 "Synthesize, don't delegate understanding" |
| **Review-Execution 分离** | Claude Code 蒸馏实践 | Track 1 改为 A(执行)→B(审查) 串行，B 读 A 的 handoff 后针对性批判 |
| **品味注入 (Taste Injection)** | PCA 基向量理论 | Step 1 收集用户设计偏好作为"基向量"，注入所有专家 prompt。客观 = 无用 |
| **自包含 Prompt** | Zero-inheritance 原则 | 每个专家 prompt 是完全独立的文档，Stage 5 专家读 synthesis-summary 而非 5 份原始产出 |
| **验证工作者独立启动** | Fork 模式 | rules-distiller 从零上下文启动，不继承前人假设 |
| **视角声明** | 品味注入延伸 | 所有专家必须声明分析视角，禁止"假装客观" |

## 团队架构

```
Stage 1: 准备 — 需求沟通 + 品味注入 + 黑板规划 + 任务规划
    ↓
Stage 2: A(模式识别) 单独执行
    ↓
Stage 3: B(读A后批判) ∥ D(交互) ∥ E(感知) ∥ F(情感)
    ↓
Stage 4 🔴: Pre-Synthesis (协调器生成 synthesis-summary.md)
    ↓
Stage 5: C(架构抽象) ∥ G(跨域解构) ← 收到自包含简报
    ↓
Stage 6: H(体系构建) → I(原则蒸馏·验证工作者·零上下文)
    ↓
Stage 7: 交付 — 产出验证 + 增量输出 + 下游推荐
```

## 专家一览

| # | 代号 | 轨道 | 角色 | 阶段 | 模型 |
|---|------|------|------|------|------|
| A | pattern-recognizer | 架构 | 模式识别者(执行者) | Stage 2 | Sonnet |
| B | critical-thinker | 架构 | 批判性思考者(审查者) | Stage 3(读A) | Sonnet |
| C | abstraction-modeler | 架构 | 抽象建模者 | Stage 5 | Opus |
| D | interaction-analyzer | UX | 交互反馈分析 | Stage 3 | Sonnet |
| E | perception-analyzer | UX | 信息感知分析 | Stage 3 | Sonnet |
| F | emotion-analyzer | UX | 情感容错分析 | Stage 3 | Sonnet |
| G | deconstructor-patternmaster | 元方法论 | 解构与模式识别 | Stage 5 | Opus |
| H | methodologist-pragmatist | 元方法论 | 体系构建与评判 | Stage 6 | Opus |
| I | rules-distiller | 综合 | 原则蒸馏者 | Stage 6 | Sonnet |

## 黑板结构（v3.0 新增文件）

```
{项目}/.design-miner/
├── GENESIS.md                # Stage 7: 世代日志（追加式，永不覆盖）
└── blackboard/
    ├── context-map.md            # Stage 1: 文件→模块→专家映射表
    ├── synthesis-summary.md      # Stage 4: 预合成简报(Stage 2-3→5)
    ├── pattern-analysis.md       # A(Stage 2): 模式分析(handoff 给 B)
    ├── critical-review.md        # B(Stage 3): 批判审视(基于 A 的 handoff)
    ├── abstract-principles.md    # C(Stage 5): 四段式架构报告(双层级)
    ├── interaction-analysis.md   # D(Stage 3): 交互反馈分析
    ├── perception-analysis.md    # E(Stage 3): 信息感知分析
    ├── emotion-analysis.md       # F(Stage 3): 情感容错分析
    ├── deconstructed-facts.md    # G(Stage 5): 跨域解构+模式识别
    ├── methodology-system.md     # H(Stage 6): 方法论体系
    ├── rules-crosscheck.md       # I(Stage 6): 独立验证+原则印证
    ├── INDEX.md                  # Stage 1: 全局索引（全程维护）
    └── inbox.md                  # 事件总线
```

## 产出

```
output/{project}-analysis/
├── 00-综合报告.md           # 含品味向量回顾 + 视角局限性声明
├── 01-架构设计分析.md       # A+B+C 整合
├── 02-UX工程分析.md         # D+E+F 整合
├── 03-元方法论萃取.md       # G+H 整合
└── 04-原则交叉印证.md       # I 独立产出(验证工作者视角)
```

## 下游团队与工作流链

**下游**: design-interrogator-team（设计审问官），读取 DM 产出作为代码证据富化层。

**三团队完整链路**：

```
DM (设计挖掘) → DI (设计审问) → DV (开发实现)
```

| 路径 | 推荐度 | 说明 |
|------|--------|------|
| **DM → DI → DV** | ⭐⭐⭐ 推荐 | 完整项目链路：挖掘→审问→实现 |
| **DI → DV** | ⭐⭐ 可接受 | 无参考项目时跳过 DM |
| **DM → DV** | ⭐ 不推荐 | 跳过设计审问，缺失关键决策环节 |

## 关键设计原则

1. **Synthesize, don't delegate understanding** — 协调器消化 5 份产出给下游 1 份摘要
2. **客观 = 无用** — 有视角的分析才有优先级和方向
3. **Handoff 即 API** — 黑板模块是 Agent 之间的通信接口
4. **Verification starts fresh** — 验证者从零上下文启动，不被前人假设蒙蔽
5. **先建协调机制，再开始干活** — context-map.md 在分析前就位

## 设计来源

| 来源 | 贡献 |
|------|------|
| keli-wen: Agent Orchestration Pattern | Pre-Synthesis、自包含Prompt、Review-Execution分离、验证工作者 |
| keli-wen: Context Engineering | 三级渐进披露、context-map.md、Zero-inheritance、Isolate |
| keli-wen: 蒸馏实践记录 | PCA品味注入、Handoff即API、基向量理论 |
| 提示词1/2 | 架构三专家+四段式报告 |
| 提示词3/4 | UX三专家+体感到代码映射 |
| 提示词5/6 | 元方法论萃取+反模式+跨域应用 |
| CLAUDE.md | 行为准则 |
| openspec 模式 | Scope Guardrails、常见故障模式 |

## 更新日志

### v5.3 (2026-05-26)
- 🔴 **编号体系统一**：Step/Phase 双前缀 + .5 小数 → 统一 **Stage 1-7**。Stage 是三团队唯一前缀（DI 用 Phase，DV 用 Gate），避免 AI 幻觉
- 🆕 **下游声明**：明确下游为 design-interrogator-team，添加三团队工作流链（DM→DI→DV）推荐路径
- 🔧 **任务映射修正**：仅架构分析拆为基础（A+B）和完整（A+B+C），与流程图一致
- 📝 **版本更新**：README v5.2→v5.3，协调器 v5.2→v5.3

### v5.2 (2026-05-25)
- 🔴 **增量累积输出**：产出文档从「完整流程最后一次性生成」改为「每轨道完成后立即追加」。部分流程也能留下记录，永不覆盖已有内容
- 🆕 **D/E/F Scope Guardrails**：三 UX 专家各自明确范围防线，发现非本领域问题时标注但不展开，防止产出重叠
- 🆕 **协调器常见故障模式**：新增 5 条故障条目（UX 重叠、Pre-Synthesis 偏侧、过度抽象、部分流程产出丢失、产出文档被覆盖）

### v5.1 (2026-05-23)
- 🔴 **模板对齐**：协调器原则编号对齐黑板型模板 7 条标准原则 + 3 条特有创新（Pre-Synthesis/自包含Prompt/分层输出）
- 🔴 **Agent 补全**：全部 9 个 Agent 新增设定 7-9（工作风格/服务对象/特殊情况汇报机制）+ 调度指令理解章节
- 🔴 **信息传递标准化**：全部 Agent 的信息传递机制统一为表格化格式（黑板读写/下游依赖/事件通知）
- 🔴 **MCP 约束**：methodologist-pragmatist 新增显式 MCP 工具使用约束章节
- 📝 **版本更新**：README v5.0→v5.1

### v5.0 (2026-05-23)
- 🔴 **结构对齐**：A/B/C/G/H/I 六个 Agent 从旧"核心设定"升级到 v5.0 增强手艺结构（身份根基+手艺工具箱+分析范围+工作方法论+产出格式+质量自检），与 D/E/F 形成统一格式
- 🔴 **协调器补全**：新增 §2 任务类型映射表/MCP能力速查表/局部闭环配置表、§4 事件类型表+标准化inbox格式、§5 MCP三级授权独立章节（分级判断流程+授权格式模板）、§10 检查清单、§11 故障排查（10条目）
- 🔴 **产出验证强化**：产出验证从一句话扩展为三阶段详细流程（Read验证→重试+警告→协调器兜底写入）
- 📝 **版本更新**：README v3.0→v5.0，更新一句话描述

### v3.0 (2026-05-22)
- 初始发布：Pre-Synthesis、Review-Execution分离、品味注入、自包含Prompt、验证工作者独立启动、视角声明
