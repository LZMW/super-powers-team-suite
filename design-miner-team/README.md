# Design-Miner (设计挖掘) 团队 v6.2

> **一句话**：三轨道并行 + Pre-Synthesis + 品味注入 + Review-Execution 分离 + 增强手艺结构 + 模板完整对齐 + 汇总专家 J，从参考项目源码中挖掘架构智慧、UX 模式和跨领域元方法论。**v6.2 扩展**：支持技术栈调研、依赖分析、安全审计、代码健康评估等代码相关的泛用调研分析能力。

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
Stage 7a 🔴: J(汇总专家) — 读取全部黑板 → 写入全部产出文档
    ↓
Stage 7b 🔴: 协调器 — 验证 + 阅读学习 + 下游推荐
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
| J | summarizer | 综合 | 汇总专家 | Stage 7a | Opus |

## 黑板结构（v6.0 文件夹组模式）

```
{项目}/.design-miner/
├── GENESIS.md                       # 世代日志（追加式，永不覆盖）
└── blackboard/
    ├── MASTER-INDEX.md              # 跨 gen 总索引（协调器维护）
    ├── inbox.md                     # 事件总线
    ├── context-map.md               # 🟢 低保留，每次 run 重建
    ├── synthesis-summary.md         # 🟢 低保留，每次 run 重建
    │
    ├── pattern-analysis/            # 🟡 A: 模式识别
    │   ├── pattern-INDEX.md
    │   ├── 01-tech-fingerprint.md
    │   ├── 02-design-patterns.md
    │   ├── 03-architecture-patterns.md
    │   ├── 04-solid-analysis.md
    │   └── 05-dependency-topology.md
    │
    ├── critical-review/             # 🟡 B: 批判审视
    │   ├── critical-INDEX.md
    │   ├── 01-executive-summary.md
    │   ├── 02-tradeoff-analysis.md
    │   ├── 03-gaps-and-omissions.md
    │   ├── 04-counterfactual.md
    │   └── 05-tech-debt.md
    │
    ├── abstract-principles/         # 🔴 C: 抽象建模
    │   ├── abstract-INDEX.md
    │   ├── 01-core-design-philosophy.md
    │   ├── 02-design-deconstruction.md
    │   ├── 03-principles/
    │   │   ├── principles-INDEX.md
    │   │   └── principle-01-xxx.md
    │   └── 04-architecture-quotes.md
    │
    ├── interaction-analysis/        # 🟡 D: 交互反馈
    │   ├── interaction-INDEX.md
    │   ├── 01-overview.md
    │   ├── 02-sensation-code-mapping.md
    │   ├── 03-micro-interactions.md
    │   └── 04-interaction-principles.md
    │
    ├── perception-analysis/         # 🟡 E: 信息感知
    │   ├── perception-INDEX.md
    │   ├── 01-info-architecture.md
    │   ├── 02-state-coverage.md
    │   ├── 03-perception-trace.md
    │   └── 04-perception-principles.md
    │
    ├── emotion-analysis/            # 🟡 F: 情感容错
    │   ├── emotion-INDEX.md
    │   ├── 01-vulnerability-scan.md
    │   ├── 02-emotion-temperature.md
    │   ├── 03-error-handling-analysis.md
    │   └── 04-emotion-principles.md
    │
    ├── deconstructed-facts/         # 🟡 G: 跨域解构
    │   ├── deconstructed-INDEX.md
    │   ├── 01-fact-inventory.md
    │   ├── 02-cross-track-patterns.md
    │   ├── 03-mental-models.md
    │   └── 04-classical-connections.md
    │
    ├── methodology-system/          # 🔴 H: 方法论体系
    │   ├── methodology-INDEX.md
    │   ├── 01-core-philosophy.md
    │   ├── 02-principles/
    │   │   ├── principles-INDEX.md
    │   │   └── principle-01-xxx.md
    │   ├── 03-toolkit/
    │   │   ├── toolkit-INDEX.md
    │   │   └── tool-a-xxx.md
    │   ├── 04-anti-patterns.md
    │   └── 05-cross-domain.md
    │
    └── rules-crosscheck/            # 🔴 I: 原则蒸馏
        ├── rules-INDEX.md
        ├── 01-verdict-summary.md
        ├── 02-detailed-verdicts/
        │   ├── verdicts-INDEX.md
        │   └── verdict-01-xxx.md
        ├── 03-statistics.md
        └── 04-rollback-items.md
```

> **v6.0 升级**：从单文件模式升级为文件夹组模式。子索引使用模块前缀命名（如 pattern-INDEX.md），避免同名幻觉。MASTER-INDEX.md 作为跨 gen 总索引。

### 保留分层

| 级别 | 文件夹 | 含义 |
|------|--------|------|
| 🔴 高保留 | methodology-system, abstract-principles, rules-crosscheck | 跨项目可复用原则/方法论，跨 gen 持续累积 |
| 🟡 中保留 | pattern-analysis, critical-review, interaction-analysis, perception-analysis, emotion-analysis, deconstructed-facts | 项目级别分析事实，跨 gen 持续累积 |
| 🟢 低保留 | context-map, synthesis-summary | 临时工作文件，每次 run 重建 |

## 产出（v6.0 文件夹组模式）

```
output/{project}-analysis/
├── 00-综合报告.md                # 索引表（下游 DI 入口）
├── 00-session-log.md             # 会话记录（追加式）
│
├── 01-architecture/              # 架构设计分析
│   ├── architecture-INDEX.md
│   ├── pattern-analysis.md       # A: 模式分析
│   ├── critical-review.md        # B: 批判审视
│   └── abstract-principles.md    # C: 抽象原则提炼
│
├── 02-ux-engineering/            # UX 工程分析
│   ├── ux-INDEX.md
│   ├── interaction-analysis.md   # D: 交互反馈
│   ├── perception-analysis.md    # E: 信息感知
│   └── emotion-analysis.md       # F: 情感容错
│
├── 03-methodology/               # 元方法论萃取
│   ├── methodology-INDEX.md
│   ├── deconstructed-facts.md     # G: 跨域解构
│   └── methodology-system.md      # H: 方法论体系
│
├── 04-rules-crosscheck/          # 原则交叉印证
│   ├── rules-INDEX.md
│   ├── verdict-summary.md        # 裁决汇总表
│   ├── detailed-verdicts.md      # 详细裁决
│   ├── statistics.md             # 统计
│   └── rollback-items.md         # 回退项
│
├── 05-tech-survey/               # 🔴 v6.2 技术调研
│   ├── tech-survey-INDEX.md
│   ├── dependency-report.md      # 依赖版本/许可证/CVE
│   └── tech-comparison.md        # 技术栈选型对比
│
├── 06-code-health/               # 🔴 v6.2 代码健康
│   ├── code-health-INDEX.md
│   ├── tech-debt-quantification.md  # 技术债务量化
│   └── security-audit.md         # 安全审计报告
│
└── 05-{自定义主题}/              # 非标准分类时自动创建
    └── custom-INDEX.md
```

> **v6.0 升级**：按专家来源拆分（01 拆 A/B/C 三个文件），下游按需读取。00-综合报告.md 保留原名确保 DI 向后兼容。

## 下游团队与工作流链

**下游**: design-interrogator-team（设计审问官），读取 DM 产出作为代码证据富化层。

**三团队完整链路**：

```
DM (设计挖掘) → DI (设计审问) → DG (开发实现)
```

| 路径 | 推荐度 | 说明 |
|------|--------|------|
| **DM → DI → DG** | ⭐⭐⭐ 推荐 | 完整项目链路：挖掘→审问→实现 |
| **DI → DG** | ⭐⭐ 可接受 | 无参考项目时跳过 DM |
| **DM → DG** | ⭐ 不推荐 | 跳过设计审问，缺失关键决策环节 |

## 调研分析模式（v6.2 新增）

除源码设计挖掘外，同一批专家可直接承担代码相关的泛用调研分析任务——**无需新增专家，复用现有 A-J 能力**：

| 任务类型 | 关键词 | 专家路径 | 产出 |
|----------|--------|----------|------|
| **技术栈调研** | "技术选型"、"依赖分析"、"版本升级" | A（联网查版本/CVE）→ B（替代方案对比） | `05-tech-survey/` |
| **安全审计** | "安全审计"、"CVE扫描"、"漏洞" | A（全局扫描+依赖拓扑）→ B（批判审视）→ F（容错分析+查CVE） | `06-code-health/` |
| **代码健康评估** | "技术债务"、"代码健康"、"复杂度" | A（SOLID+依赖拓扑）→ B（技术债务评估） | `06-code-health/` |
| **依赖生态分析** | "供应链安全"、"许可证"、"过期依赖" | A（技术栈指纹+联网调研） | `05-tech-survey/` |

**联网调研能力**：A (pattern-recognizer) 和 B (critical-thinker) 现可访问 WebSearch/WebFetch，F (emotion-analyzer) 可访问 WebSearch。协调器在调研任务中主动授权联网搜索。

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

### v6.2 (2026-05-30)
- 🆕 **泛用调研分析**：新增技术栈调研、安全审计、代码健康评估、依赖生态分析 4 种任务类型，复用现有 A-J 专家
- 🆕 **联网调研能力**：A/B 新增 WebSearch/WebFetch，F 新增 WebSearch——技术调研时可联网查版本/CVE/替代方案
- 🆕 **新产出文件夹**：`05-tech-survey/`（技术调研）+ `06-code-health/`（代码健康），产出触发时机表同步更新
- 🆕 **快捷执行路径**：仅技术调研（A→B 联网调研）、仅代码健康（A→B 质量审计）
- 📝 **协调器扩展**：任务类型映射表 +4 行、专项聚焦映射 +3 行、MCP 速查表更新

### v6.1 (2026-05-29)
- 🆕 **汇总专家 J (summarizer)**：新增 Opus 级汇总专家，Stage 7a 读取全部黑板 → 写入全部产出文档
- 🔧 **协调器进化**：Stage 7b 不再写产出文档，改为「验证 + 阅读学习 + 交付」
- 🆕 **阅读学习能力**：协调器主动阅读 J 的产出，将项目分析结论加载到上下文，后续工作精准引用
- 🔧 **Stage 7 拆分**：7a (J:汇总) → 7b (协调器:验证+学习+交付)
- 📝 **10 位专家全部就位**：A-I 挖掘 + J 汇总

### v6.0 (2026-05-29)
- 🔴 **文件夹组模式**：黑板从 9 个单文件升级为 9 个文件夹组（子文件 + 子索引 + MASTER-INDEX）
- 🆕 **MASTER-INDEX.md**：新增跨 gen 总索引，协调器全程维护
- 🆕 **子索引前缀命名**：所有子索引使用模块前缀（如 pattern-INDEX.md），避免 LLM 同名幻觉
- 🆕 **保留分层**：🔴 高保留 / 🟡 中保留 / 🟢 低保留，二次运行不删不归档
- 🔧 **gen 按 run 递增**：一次完整 Stage 1-7 = 一个 gen，STALE 状态由子 INDEX 控制
- 🔧 **inbox 事件格式升级**：增加受影响子文件、子索引、gen 编号字段
- 🔧 **Stage 7 验证升级**：从单文件验证改为子 INDEX + 子文件验证

### v5.3 (2026-05-26)
- 🔴 **编号体系统一**：Step/Phase 双前缀 + .5 小数 → 统一 **Stage 1-7**。Stage 是三团队唯一前缀（DI 用 Phase，DG 用 Gate），避免 AI 幻觉
- 🆕 **下游声明**：明确下游为 design-interrogator-team，添加三团队工作流链（DM→DI→DG）推荐路径
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
