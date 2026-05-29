# Design Interrogator (设计审问官) 团队 v4.0

> **一句话**：双轨道黑板型 + 品味注入 + Pre-Synthesis + 设计挖掘上游集成 + 跨 gen 冲突审查，覆盖架构设计审问和 UX/UI 全流程，统一交付 dev-genius。

## v3.0 核心创新（design-miner 三迭代 + uxui-studio 合并）

| 创新 | 来源 | 说明 |
|------|------|------|
| **双轨道黑板型** | design-miner v3.0 | Track A（架构设计）+ Track B（UX/UI 设计）并行执行，黑板共享状态，收敛于 strategist |
| **上游集成** | 新增 | 自动读取 design-miner 五份分析报告，analyst 和 researcher 以此为起点 |
| **团队合并** | DI + UXUI | 原 design-interrogator (3人) + uxui-studio (5人) → 统一7人团队，消除双协调器冗余 |
| **Pre-Synthesis** | Agent Orchestration | 协调器在 Phase 3 完成后消化全部产出、生成 synthesis-summary.md、构造自包含简报再派发后续 |
| **品味注入** | PCA 基向量 | Phase 1 收集用户设计偏好作为品味向量，注入所有专家 prompt |
| **视角声明** | 品味注入延伸 | 所有专家产出的首段必须声明分析视角，禁止"假装客观" |
| **统一交付** | 合并原 .di/ + .uxs/ | dev-genius 只需读取 `.di/phases/07_documentation/` 一个来源 |
| **writer 吸收** | 角色精简 | 原 DI writer 职责并入 strategist Phase 10 文档编译 |

## 生态系统位置

```
design-miner-team (上游, 9人, 黑板型)
    产出: output/{project}-analysis/ 五份分析报告
    ↓
design-interrogator-team v3.2 (本团队, 7人, 黑板型双轨道)
    产出: .di/phases/07_documentation/ 七份规格文档
    ↓
dev-genius-team (下游, 5人, 黑板型)
    自动读取 .di/phases/07_documentation/INDEX.md 开始开发
```

## 团队架构

```
Phase 0: 上游检测 (design-miner 产出)
Phase 1: 需求沟通 + 品味注入 (Taste Vectors)
    ↓
Phase 2: 流程规划 + Context Map
    ↓
Phase 3a: analyst (源码分析)     ∥ Phase 3b: researcher (用户研究)
    ↓                              ↓
    └────── Phase 4: Pre-Synthesis ───────┘
                    ↓
Phase 5a: interrogator (架构拷问)  Phase 5b: ixd (交互设计)
    ↓                              ↓
    │                           Phase 6b: critic (交互审问)
    │                              ↓
    │                           Phase 7b: ui (视觉设计)
    │                              ↓
    │                           Phase 8b: critic (视觉审问)
    ↓                              ↓
    └──────── Phase 9: strategist (策略裁决) ─────┘
                    ↓
               Phase 10a: strategist (文档编译)
                    ↓
               Phase 10b 🔴: conflict-reviewer (跨 gen 冲突审查)
                    ↓
               Phase 11: 产出验证 + 冲突裁决 + 回退检测
                    ↓
               Phase 12: 综合报告 + 设计偏好捕获
                    ↓
               交付 dev-genius
```

## 专家一览

| # | 代号 | 轨道 | 角色 | 阶段 | 模型 |
|---|------|------|------|------|------|
| 1 | analyst | 架构 | 源码分析师 | Phase 3a | Sonnet |
| 2 | interrogator | 架构 | 架构审问官 | Phase 5a (交互式) | Sonnet |
| 3 | researcher | UX | UX研究员 | Phase 3b | Sonnet |
| 4 | ixd | UX | 交互设计师 | Phase 5b | Sonnet |
| 5 | critic | UX | 设计审问官 | Phase 6b+8b (交互式) | Sonnet |
| 6 | ui | UX | UI设计师 | Phase 7b | Sonnet |
| 7 | strategist | 收敛 | UX策略师+文档编译 | Phase 9+10a | Sonnet |
| 8 | conflict-reviewer | 收敛 | 冲突审查专家 | Phase 10b | Opus |

## 黑板结构

```
{项目}/.di/
├── GENESIS.md                    # Phase 11: 世代日志（追加式，永不覆盖）
├── context-map.md                # Phase 2: 上下文地图
├── design-preferences.md         # Phase 12: 设计偏好记录
├── synthesis-summary.md          # Phase 4: Pre-Synthesis 简报
├── blackboard/
│   ├── INDEX.md                  # Coordinator 全局索引
│   ├── inbox.md                  # 事件总线
│   ├── architecture-analysis.md  # A: Phase 3a analyst
│   ├── interrogation-tree.md     # A: Phase 5a interrogator
│   ├── ux-research.md           # B: Phase 3b researcher
│   ├── interaction-design.md     # B: Phase 5b ixd
│   ├── critique-interaction.md   # B: Phase 6b critic
│   ├── visual-design.md         # B: Phase 7b ui
│   ├── critique-visual.md       # B: Phase 8b critic
│   └── strategy-verdicts.md     # Phase 9 strategist
└── phases/
    └── 07_documentation/         # Phase 10: 交付 dev-genius
        ├── INDEX.md
        ├── ARCHITECTURE_SPEC.md
        ├── UX_SPEC.md
        ├── INTERACTION_SPEC.md
        ├── UI_SPEC.md
        ├── DESIGN_DECISIONS.md
        └── VALIDATION_PLAN.md
```

## 关键设计原则

1. **Synthesize, don't delegate understanding** — 协调器消化 Phase 3 产出后构造自包含简报
2. **客观 = 无用** — 有品味向量的分析才有优先级和方向
3. **Handoff 即 API** — 黑板模块是 Agent 之间的通信接口
4. **双轨道并行，单节点收敛** — Track A/B 独立执行，strategist 统一裁决
5. **先建协调机制，再开始干活** — context-map.md 在分析前就位
6. **上游消费，下游友好** — 自动读取 design-miner，统一交付 dev-genius

## 设计来源

| 来源 | 贡献 |
|------|------|
| design-miner-team v3.0 | 黑板模式、Pre-Synthesis、品味注入、视角声明、三层手艺结构 |
| design-interrogator-team v1.2 | 架构分析+拷问+文档三阶段流水线、交互式多轮延续、回退机制 |
| uxui-studio-team v2.0 | UX七阶段流水线、Critic多轮审问、Strategist裁决+编译 |
| dev-genius-team v1.1 | 下游消费接口（.di/phases/07_documentation/） |
| keli-wen: Agent Orchestration | Pre-Synthesis、自包含Prompt、Review-Execution分离 |
| keli-wen: Context Engineering | context-map.md、Zero-inheritance、渐进披露 |
| keli-wen: 蒸馏实践 | PCA品味注入、Handoff即API、基向量理论 |
| grill-me 模式 | 一次一问、决策树深度优先、代码库优先、分支完成标准 |
| openspec 模式 | 工件状态模型、分层审问协议、scope guardrails、严重程度分级 |
| super-team-builder v5.0 | 增强手艺结构、18项验证矩阵 |

---

**版本**: v3.2
**更新日期**: 2026-05-26

## 更新日志

### v4.0 (2026-05-29)
- 🔴 **文件夹组模式**：黑板 8 单文件 → 8 文件夹组 + MASTER-INDEX + GENESIS 正式启用
- 🔴 **产出文件夹组**：phases/07_documentation/ 7 单文件 → 7 文件夹组 + 增量累积 + 00-CONFLICT_LOG
- 🆕 **冲突审查专家 K (conflict-reviewer)**：Phase 10b 跨 gen 决策一致性审查，三层标记（文件头红幅+文件名前缀+CONFLICT_LOG）
- 🆕 **Phase 10 拆分**：10a (strategist 编译) → 10b (K 冲突审查) → 11 (验证+裁决) → 12 (报告)
- 🔧 **Phase 0 上游适配**：DM v6.1 文件夹组路径更新
- 🔧 **gen/GENESIS 机制**：正式启用，按 run 递增，子 INDEX 追踪 gen 状态
- 📝 **8 位专家全部就位**：7 原专家 + K (conflict-reviewer)

### v3.2 (2026-05-26)
- 🔴 **编号统一**：Step/Phase 双前缀 + .5 小数 → 统一 **Phase 0-12**。Phase 是三团队唯一前缀（DM=Stage，DG=Gate），避免 AI 幻觉
- 🔴 **专家 Phase 重编号**：+3 偏移（Phase 1a→3a, 2a→5a, 6→9, 7→10 等），Phase 0-2 预留给协调器准备活动
- 🆕 **上游声明强化**：上游 DM 引用同步到 Stage 体系，添加三团队工作流链推荐

### v3.1 (2026-05-24)
- 🆕 **Interrogator 决策节点状态模型**：五状态（pending/active/resolved/deferred/superseded）+ 分支完成标准
- 🆕 **Interrogator 代码库优先协议**：Glob→Grep→Read 搜索后才向用户提问
- 🆕 **Critic 分层审问协议**：五层依序进行（可用性→可访问性→一致性→边界→可行性）
- 🆕 **Critic 反对意见严重程度分级**：critical/major/minor/suggestion
- 🆕 **Critic Scope Guardrails**：交互/视觉审问范围防线 + 禁止泛泛而谈

### v3.0 (2026-05-23)
- 🔴 **团队合并**：design-interrogator (v1.2) + uxui-studio (v2.0) → 统一双轨道黑板型团队
- 🔴 **架构重构**：流水线型→黑板型双轨道（Track A: 架构设计 ∥ Track B: UX/UI设计）
- 🆕 **上游集成**：自动检测和读取 design-miner 产出
- 🆕 **品味注入**：品味向量收集和注入全部专家
- 🆕 **Pre-Synthesis**：合成简报
- 🆕 **视角声明**：所有专家产出首段声明分析视角
- 🆕 **v5.0 增强手艺结构**：7个专家全部按 §8.8 重构
- 🔄 **角色合并**：writer 职责并入 strategist Phase 7
- 🔄 **输出统一**：`.di/` + `.uxs/` → 统一 `.di/` 目录，dev-genius 单一来源读取
- 📝 **专家阵容**：3+5=7 (analyst + researcher + interrogator + ixd + critic + ui + strategist)

### v1.2 (2026-05-22)
- 生态系统衔接 + 回退机制 + Karpathy 四原则嵌入

### v1.1
- 修复延续对话 subagent_type bug + 交互延续原则
