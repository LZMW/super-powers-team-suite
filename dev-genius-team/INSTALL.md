# Dev-Genius Team v2.3 — 安装说明

## 前置依赖

- **上游团队**：design-interrogator-team — 提供统一设计规格文档（Phase 10 产出）

## 安装步骤

### 1. 安装协调器 Skill

```bash
# Claude Code
mkdir -p ~/.claude/skills/dev-genius-coordinator
cp skills/dev-genius-coordinator/skill.md ~/.claude/skills/dev-genius-coordinator/skill.md
```

### 2. 安装 Agent 配置

```bash
mkdir -p ~/.claude/agents
cp agents/dev-genius-planner.md ~/.claude/agents/
cp agents/dev-genius-architect.md ~/.claude/agents/
cp agents/dev-genius-developer.md ~/.claude/agents/
cp agents/dev-genius-qa-tester.md ~/.claude/agents/
cp agents/dev-genius-analyst.md ~/.claude/agents/
```

### 3. Agent 清单

| 文件 | Agent ID | 门控 |
|------|----------|------|
| `dev-genius-planner.md` | 任务规划师 | 🚪 Gate 1 |
| `dev-genius-architect.md` | 架构实施师 | 🚪 Gate 2 必经 |
| `dev-genius-developer.md` | 开发工程师 | 🚪 Gate 3 |
| `dev-genius-qa-tester.md` | 测试工程师 | 🚪 Gate 4 必经 |
| `dev-genius-analyst.md` | 代码审查师 | 🚪 Gate 5+6 |

### 4. MCP 服务器（可选但推荐）

| MCP Server | 用途 | 使用者 |
|------------|------|--------|
| context7 | 查询框架/库 API 文档 | architect, developer |
| sequential-thinking | 复杂规划/架构决策 | planner, architect |
| vision-server | UI 审查 | analyst |

### 5. 验证安装

```bash
/dev-genius-coordinator 开发项目
```

## 使用流程

```
1. design-interrogator-team 产出 .di/phases/07_documentation/
2. 启动 dev-genius-coordinator
3. 协调器自动检测上游 → 🚪 Gate 1 (Plan) → 🚪 Gate 2 (Arch) → 🚪 Gate 3 (TDD) → 🚪 Gate 4 (Verify) → 🚪 Gate 5 (Review) → 🚪 Gate 6 (Finish)
4. 每道门控通过后才进入下一阶段。Gate 2 (Architect) 和 Gate 4 (QA Tester) 是必经门控，协调器不可随意跳过
5. 推荐 /goal + /loop 实现全自动开发
```

---

**版本**: v2.3
