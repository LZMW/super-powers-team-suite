# Dev-Genius (开发天才) 团队 v2.0

> **一句话**：黑板型 + 五道质量门控 + Superpowers 方法论注入，从设计规格到可交付软件的全自动开发流水线。

## v2.0 核心创新（Superpowers 技能注入）

| 创新 | 来源 | 说明 |
|------|------|------|
| **五道质量门控** | Superpowers 全流程 | Plan Gate → TDD Gate → Verify Gate → Review Gate → Finish Gate，每道不可跳过 |
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
design-interrogator-team v3.0 (上游, 统一设计审问)
    产出: .di/phases/07_documentation/ 七份规格文档
    ↓
dev-genius-team v2.0 (本团队, 5人, 黑板型)
    产出: 可交付软件产品
```

## 五道质量门控

```
🚪 Gate 1: Plan Gate (writing-plans)
    Planner → task-queue.md（禁止 TODO/TBD）
    ↓
🚪 Gate 2: TDD Gate (test-driven-development)
    Developer → RED→GREEN→REFACTOR（无失败测试先行=任务失败）
    ↓
🚪 Gate 3: Verify Gate (verification-before-completion)
    QA Tester → 验收标准逐项验证（有测试输出为证据）
    ↓
🚪 Gate 4: Review Gate (code-review)
    Analyst → Karpathy四原则 + OWASP（Critical 必须修复）
    ↓
🚪 Gate 5: Finish Gate (finishing-a-development-branch)
    Coordinator → 全部任务+测试+审查通过 → 交付
```

## 专家一览

| # | 代号 | 角色 | 门控 | 模型 |
|---|------|------|------|------|
| 1 | planner | 任务规划师 | 🚪 Gate 1 | Sonnet |
| 2 | architect | 架构实施师 | — | Sonnet |
| 3 | developer | 开发工程师 | 🚪 Gate 2 | Sonnet |
| 4 | qa-tester | 测试工程师 | 🚪 Gate 3 | Sonnet |
| 5 | analyst | 代码审查师 | 🚪 Gate 4+5 | Sonnet |

## 黑板结构

```
{项目}/.dev-genius/blackboard/
├── task-queue.md       # Planner: 开发任务队列
├── architecture.md     # Architect: 技术架构
├── code-state.md       # Developer: 代码状态（含 TDD 证据）
├── test-report.md      # QA Tester: 测试报告（含验证证据）
├── review-report.md    # Analyst: 审查报告
├── INDEX.md            # Coordinator 维护
└── inbox.md            # 事件总线
```

## Superpowers 注入映射

| Agent | 注入技能 | 核心机制 |
|-------|---------|---------|
| **planner** | writing-plans | 禁止 TODO/TBD、任务原子/独立/可验证、自审检查清单 |
| **developer** | test-driven-development | RED-GREEN-REFACTOR 铁律、无失败测试=删除重来 |
| **developer** | systematic-debugging | 四阶段调试、根因分析先于修复、3+ 失败质疑架构 |
| **qa-tester** | verification-before-completion | 验证前运行命令+读取输出、禁止"应该通过" |
| **analyst** | code-review + finishing | Karpathy 四原则、OWASP Top 10、合并前检查清单 |
| **coordinator** | executing-plans | 五道门控串行执行、每道未通过禁止进入下一阶段 |

## 设计来源

| 来源 | 贡献 |
|------|------|
| dev-genius-team v1.1 | 黑板模式、事件总线、Dev↔QA 局部闭环、/goal+/loop |
| design-interrogator-team v3.0 | 统一上游规格文档（.di/phases/07_documentation/） |
| Superpowers: writing-plans | 规划方法论、禁止占位符 |
| Superpowers: test-driven-development | RED-GREEN-REFACTOR 铁律 |
| Superpowers: systematic-debugging | 四阶段系统化调试 |
| Superpowers: verification-before-completion | 验证前强制证据 |
| Superpowers: code-review + finishing | Karpathy 审查 + 合并前检查 |
| super-team-builder v5.0 | 增强手艺结构 |

---

**版本**: v2.0
**更新日期**: 2026-05-23

## 更新日志

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
