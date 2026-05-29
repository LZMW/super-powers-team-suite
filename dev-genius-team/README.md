# Dev-Genius (开发天才) 团队 v3.1

> **一句话**：黑板型 + 七道强制门控（含 Gate 2b 文档验证）+ F 双阶段源码扫描 + Superpowers + OpenSpec 方法论注入，从设计规格到可交付软件的全自动开发流水线。Architect 和 QA Tester 是每任务必经门控。

## v2.2 核心变化（Architect + QA Tester 强制门控）

| 变化 | 说明 |
|------|------|
| 🔴 **Architect 必经门控** | 从「可选架构环节」升级为 Gate 2，三级响应（完整架构/影响评估/架构签批），协调器定级别 |
| 🔴 **QA Tester 必经门控** | 从「可选验证环节」升级为 Gate 4，验证深度协调器可调，证据门槛不变 |
| 🔴 **stop-on-mismatch** | Developer 发现架构冲突/范围膨胀/设计缺陷立即停止并上报 |
| 🔴 **no-silent-scope-expansion** | Developer 不得默默实现超出批准范围的内容 |
| 🆕 **架构复杂度标注** | Planner 为每个任务标注架构复杂度，指导 Architect 响应级别 |

## v2.0 核心创新（保留）

| 创新 | 来源 | 说明 |
|------|------|------|
| **六道质量门控** | Superpowers + OpenSpec | Plan Gate → Architecture Gate → TDD Gate → Verify Gate → Review Gate → Finish Gate |
| **TDD 铁律** | test-driven-development | RED-GREEN-REFACTOR 循环强制执行，无失败测试先行的代码必须删除重来 |
| **系统化调试** | systematic-debugging | 四阶段调试（根因→模式→假设→修复），禁止猜测式修复 |
| **验证前证据** | verification-before-completion | 每个完成声明必须附带新鲜测试输出，禁止"应该通过"类声明 |
| **规划即代码** | writing-plans | 禁止 TODO/TBD/占位符/模糊描述，每个任务具体到文件路径 |
| **合并前检查** | finishing-a-development-branch | 全部任务+测试+审查通过后才可合并 |
| **v5.0 手艺结构** | super-team-builder | 全部 Agent 按 §1-10 增强手艺结构组织 |
| **上游路径统一** | DI v3.0 合并 | 读取 `.di/phases/07_documentation/` 统一规格文档 |

## 生态系统位置

```
design-miner-team (上游, 分析参考源码)
    ↓
design-interrogator-team (上游, Phase 0-12 统一设计审问)
    产出: .di/phases/07_documentation/ 七份规格文档
    ↓
dev-genius-team v3.1 (本团队, 7人, 黑板型)
    产出: 可交付软件产品
```

## 六道质量门控

```
🚪 Gate 1: Plan Gate (writing-plans)
    Planner → task-queue.md（禁止 TODO/TBD，标注架构复杂度）
    ↓
🚪 Gate 2: Architecture Gate
    Architect → architecture.md（三级响应：完整架构/影响评估/架构签批）
    ↓
🚪 Gate 2b: Doc-Validate Gate
    Doc-Validator → 架构文档与 DI 规格一致性校验 + 接口契约验证 + ADR 追溯
    ↓
🚪 Gate 3: TDD Gate (test-driven-development)
    Developer → RED→GREEN→REFACTOR（无失败测试先行=任务失败）
    ↓
🚪 Gate 4: Verify Gate
    QA Tester → 验收标准逐项验证（新鲜测试输出为证据）
    ↓
🚪 Gate 5: Review Gate (code-review)
    Analyst → Karpathy四原则 + OWASP（Critical 必须修复）
    ↓
🚪 Gate 6: Finish Gate (finishing-a-development-branch)
    Coordinator → 全部任务+测试+审查通过 → 交付
```

## 专家一览

| # | 代号 | 角色 | 门控 | 模型 |
|---|------|------|------|------|
| 1 | planner | 任务规划师 | 🚪 Gate 1 | Sonnet |
| 2 | architect | 架构实施师 | 🚪 Gate 2 必经 | Sonnet |
| 3 | doc-validator | 文档验证师 | 🚪 Gate 2b | Sonnet |
| 4 | developer | 开发工程师 | 🚪 Gate 3 | Sonnet |
| 5 | qa-tester | 测试工程师 | 🚪 Gate 4 必经 | Sonnet |
| 6 | analyst | 代码审查师 | 🚪 Gate 5+6 | Sonnet |
| 7 | codebase-analyst | 源码状态分析师 | 🚪 Gate 0+6（双阶段） | Sonnet |

## 黑板结构

```
{项目}/.dev-genius/blackboard/
├── task-queue.md       # Gate 1 (Planner): 开发任务队列
├── architecture.md     # Gate 2 (Architect): 技术架构
├── code-state.md       # Gate 3 (Developer): 代码状态（含 TDD 证据）
├── test-report.md      # Gate 4 (QA Tester): 测试报告（含验证证据）
├── review-report.md    # Gate 5 (Analyst): 审查报告
├── INDEX.md            # Coordinator 维护
└── inbox.md            # 事件总线
```

## Superpowers + OpenSpec 注入映射

| Agent | 注入技能 | 核心机制 |
|-------|---------|---------|
| **planner** | writing-plans | 禁止 TODO/TBD、任务原子/独立/可验证、自审检查清单、架构复杂度标注 |
| **architect** | — | 三级响应（完整架构/影响评估/架构签批）、架构冲突回退 |
| **doc-validator** | — | 架构文档与 DI 规格一致性校验、接口契约验证、ADR 可追溯性 |
| **developer** | test-driven-development | RED-GREEN-REFACTOR 铁律、无失败测试=删除重来 |
| **developer** | systematic-debugging | 四阶段调试、根因分析先于修复、3+ 失败质疑架构 |
| **developer** | openspec change-implementation | stop-on-mismatch、no-silent-scope-expansion |
| **qa-tester** | verification-before-completion + pr-test-analyzer | 验收标准逐项验证、新鲜测试输出为证据、行为覆盖优先、负面空间映射 |
| **analyst** | code-review + silent-failure-hunter | Karpathy 四原则、OWASP Top 10、静默失败检测、置信度评分、假阳性排除、合并前检查 |
| **coordinator** | subagent-driven-development + openspec | 六道门控串行执行、每道未通过禁止进入下一阶段、文件即真实来源 |

## 设计来源

| 来源 | 贡献 |
|------|------|
| dev-genius-team v2.1 | 黑板模式、事件总线、Dev↔QA 局部闭环、/goal+/loop、五道门控 |
| design-interrogator-team v3.0 | 统一上游规格文档（.di/phases/07_documentation/） |
| Superpowers: writing-plans | 规划方法论、禁止占位符 |
| Superpowers: test-driven-development | RED-GREEN-REFACTOR 铁律 |
| Superpowers: systematic-debugging | 四阶段系统化调试 |
| Superpowers: verification-before-completion | 验证前强制证据 |
| Superpowers: subagent-driven-development | 两阶段审查、每任务审查循环 |
| Superpowers: code-review + finishing | Karpathy 审查 + 合并前检查 |
| OpenSpec: change-implementation | stop-on-mismatch、no-silent-scope-expansion、文件即真实来源 |
| Claude Plugins: code-review | 置信度评分、假阳性排除清单、五维并行审查 |
| Claude Plugins: silent-failure-hunter | 静默失败五大铁律、错误处理五维审查 |
| Claude Plugins: pr-test-analyzer | 行为覆盖优先、负面空间映射、DAMP 原则 |
| super-team-builder v5.0 | 增强手艺结构 |

---

**版本**: v3.1
**更新日期**: 2026-05-29

## 更新日志

### v3.1 (2026-05-29)
- 🆕 **Doc-Validator (L) 专家**：新增 Gate 2b 文档验证门控，Architect 产出后校验架构文档与 DI 规格一致性、接口契约完整性和 ADR 可追溯性
- 🆕 **黑板文件夹扩展**：新增 doc-state/（Doc-Validator 专属），黑板从 7 文件夹扩展到 8 文件夹
- 🆕 **architecture/ 领域分类**：architecture/ 按 style/modules/contracts/decisions/signoffs 领域分类
- 🆕 **task-queue/ 类型分类**：task-queue/ 按 features/bugfixes/refactors/infrastructure/dependencies 类型分类
- 🆕 **Agent 设定7 精修**：4 个 Agent（codebase-analyst/developer/qa-tester/analyst）设定7 升级为子文件清单总表 + 每子文件 mini-模板格式
- 📝 **版本号**：v3.0 → v3.1

### v2.3 (2026-05-26)
- 🔴 **编号体系统一**：消除 Step 前缀 + .5 小数，Gate 1-6 纯整数。Gate 是三团队唯一前缀（DM=Stage，DI=Phase）
- 🔴 **Gate 重编号**：Gate 1.5→2（顺延：TDD→3, Verify→4, Review→5, Finish→6）。六道门控 Pipeline 保持完整
- 🆕 **上游引用同步**：DI 引用更新为 Phase 10 产出，DM 引用更新为 Stage 1-7
- 🆕 **工作流链推荐**：DM(Stage)→DI(Phase)→DG(Gate)，三团队编号前缀无重叠
- 📝 **版本更新**：README v2.2→v2.3，协调器 v2.2→v2.3

### v2.2.1 (2026-05-24)
- 🆕 **Analyst 静默失败检测**（借鉴 claude-plugins-official silent-failure-hunter）：五铁律 + 六项检查清单
- 🆕 **Analyst 置信度评分**（借鉴 claude-plugins-official code-review）：0-100 双维度评分，仅报告 ≥75 问题
- 🆕 **Analyst 假阳性排除清单**（借鉴 claude-plugins-official code-review）：七类不报告的情况
- 🆕 **QA Tester 行为覆盖优先**（借鉴 claude-plugins-official pr-test-analyzer）：测试行为而非实现
- 🆕 **QA Tester 负面空间映射**（借鉴 claude-plugins-official pr-test-analyzer）：先列清单再对照检查
- 🆕 **QA Tester Bug 分级锚点**：P0-P3 每级附具体示例

### v2.2 (2026-05-24)
- 🔴 **Architect 强制门控**：从「可选架构环节」升级为 Gate 1.5，三级响应（完整架构/影响评估/架构签批），每任务必经
- 🔴 **QA Tester 必经门控**：从「可选验证环节」升级为 Gate 3，证据门槛升级（新鲜测试输出），验证深度协调器可调
- 🔴 **stop-on-mismatch**：Developer 发现架构冲突/范围膨胀/设计缺陷立即停止并上报
- 🔴 **no-silent-scope-expansion**：Developer 不得默默实现超出批准范围的内容
- 🆕 **架构复杂度标注**：Planner 为每个任务标注架构复杂度，指导 Architect 响应级别
- 🆕 **架构冲突回退机制**：ARCH_CONFLICT 事件 + Gate 1.5 重新评估流程
- 🆕 **SCOPE_EXPANSION 事件**：Developer 发现范围膨胀时上报
- 📝 **任务类型映射表重写**：所有路径强制包含 Architect + QA Tester，旧的可跳过模式废除
- 📝 **五道门控→六道门控**：Gate 1.5 Architecture Gate 加入流程

### v2.0 (2026-05-23)
- 🔴 **五道质量门控**：Plan → TDD → Verify → Review → Finish
- 🔴 **Superpowers 注入**：writing-plans + TDD + systematic-debugging + verification + code-review + finishing
- 🔴 **TDD 铁律**：Developer 强制执行 RED-GREEN-REFACTOR
- 🔴 **验证证据强制**：QA Tester 每个声明必须有测试输出
- 🔴 **v5.0 手艺结构**：全部 5 个 Agent 按 §1-10 重构
- 🆕 **上游路径统一**：`.di/phases/03_documentation/` → `.di/phases/07_documentation/`
- 🆕 **合并前检查**：Analyst 含 finishing 清单
- 📝 **旧引用清理**：uxui-studio 引用全部替换为统一 DI 团队

### v1.1 (2026-05-21)
- 多源上游衔接 + Karpathy 四原则嵌入 + Planner 多源读取

### v1.0 (2026-05-15)
- 初始版本：黑板型架构，5 位专家，/goal + /loop 集成
