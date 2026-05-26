# Super Powers Team Suite — 更新说明

> **发布日期**：2026-05-26
> **版本**：DM v5.3 / DI v3.2 / DV v2.3

---

## 核心变更：三团队编号体系统一

三团队各自的编号前缀**完全去重**，消灭了跨团队混用造成的 AI 幻觉风险。

| 团队 | 旧编号体系 | 新编号体系 | 前缀唯一性 |
|------|-----------|-----------|-----------|
| **DM** (设计挖掘) | `Step 1-5` + `Phase 1a-3` + `.5` 小数 | **Stage 1-7** | ✅ 三团队唯一 |
| **DI** (设计审问) | `Step 0-5` + `Phase 1a-7` + `.5` 小数 | **Phase 0-12** | ✅ 三团队唯一 |
| **DV** (开发实现) | `Step 0-9` + `Gate 1-5` + `.5` 小数 | **Gate 1-6** | ✅ 三团队唯一 |

**关键规则**：三个前缀互不重叠。对话中提到 `Stage` 必指 DM，`Phase` 必指 DI，`Gate` 必指 DV。

---

## 各团队变更详情

### DM：design-miner-team v5.2 → v5.3

```
旧: Step 1→2→3 → Phase 1a→1b → Step 3.5 → Phase 2→3 → Step 4.5→5
新: Stage 1→2→3→4→5→6→7
```

| Stage | 内容 | 类型 |
|-------|------|------|
| Stage 1 | 准备（需求 + 黑板 + 任务规划） | 协调器 |
| Stage 2 | 模式识别（A 单独执行） | 专家 |
| Stage 3 | 多重分析（B ∥ D ∥ E ∥ F） | 专家 |
| Stage 4 | Pre-Synthesis | 协调器 |
| Stage 5 | 深度提炼（C ∥ G） | 专家 |
| Stage 6 | 体系构建（H → I） | 专家 |
| Stage 7 | 交付（验证 + 输出 + 下游推荐） | 协调器 |

其他改动：
- 添加下游声明：design-interrogator-team
- 添加三团队工作流链推荐（DM→DI→DV）
- 任务映射修正：仅架构分析拆为基础（A+B）和完整（A+B+C）
- D/E/F agent 标题补 Stage 3 标注
- 8 个 agent 汇报模板 Phase→Stage 修正

### DI：design-interrogator-team v3.1 → v3.2

```
旧: Step 0→1→2 → Phase 1a∥1b → Step 3.5 → Phase 2a∥2b→3b→4b→5b → Phase 6→7 → Step 4.5→4.6→5→5.5
新: Phase 0→1→2→3a∥3b→4→5a∥5b→6b→7b→8b→9→10→11→12
```

专家 Phase 统一 **+3 偏移**（Phase 0-2 留给协调器准备，Phase 4 留给 Pre-Synthesis）：

| 旧 | 新 | 专家 |
|----|-----|------|
| Phase 1a | Phase 3a | analyst |
| Phase 1b | Phase 3b | researcher |
| Phase 2a | Phase 5a | interrogator |
| Phase 2b | Phase 5b | ixd |
| Phase 3b | Phase 6b | critic（交互审问）|
| Phase 4b | Phase 7b | ui |
| Phase 5b | Phase 8b | critic（视觉审问）|
| Phase 6 | Phase 9 | strategist 裁决 |
| Phase 7 | Phase 10 | strategist 编译 |
| Step 4.5+4.6 | Phase 11 | 产出验证+回退检测 |
| Step 5+5.5 | Phase 12 | 综合报告+偏好捕获 |

其他改动：
- 上游声明强化：DM 引用同步到 Stage 体系
- 黑板结构所有文件补 Phase 标注
- Phase 4（Pre-Synthesis）移至 Phase 3b 和 Phase 5a 之间
- 决策树全用新编号
- README 流程图补 Phase 11/12

### DV：dev-genius-team v2.2 → v2.3

```
旧: Step 0→0.5→1→2 → Gate 1→1.5→2→3 → Step 7 → Gate 4 → Step 4.5 → Gate 5
新: 无编号准备节 → Gate 1→2→3→4→5→6
```

六道门控 Pipeline：

| Gate | 名称 | 专家 |
|------|------|------|
| Gate 1 | Plan Gate | Planner |
| Gate 2 | Architecture Gate | Architect |
| Gate 3 | TDD Gate | Developer |
| Gate 4 | Verify Gate | QA Tester |
| Gate 5 | Review Gate | Analyst |
| Gate 6 | Finish Gate | Coordinator |

其他改动：
- **Step 前缀完全消灭**：上游检测/需求沟通/黑板初始化/局部闭环/产出验证 → 无编号命名节
- 上游引用更新：DI 用 Phase 10，DM 用 Stage 1-7
- 黑板结构补 Gate 标注
- INSTALL.md 同步更新

---

## 推荐工作流链

```
DM (Stage 1-7) → DI (Phase 0-12) → DV (Gate 1-6)
```

| 路径 | 推荐度 | 说明 |
|------|--------|------|
| DM → DI → DV | ⭐⭐⭐ 推荐 | 完整项目链路 |
| DI → DV | ⭐⭐ 可接受 | 无参考项目时跳过 DM |
| DM → DV | ⭐ 不推荐 | 跳过设计审问，缺失关键决策环节 |

---

## 审计结果

两轮全量审计，26 项检查全部通过，零 `.X` 小数残留，三团队编号无重叠。
