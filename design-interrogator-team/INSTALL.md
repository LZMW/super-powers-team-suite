# Design Interrogator Team v3.1 — 安装说明

## 前置依赖

- **上游团队**（推荐）：[design-miner-team](../design-miner-team/) — 提供参考项目分析报告
- **下游团队**：[dev-genius-team](../dev-genius-team/) — 消费设计规格文档

## 安装步骤

### 1. 安装协调器 Skill

```bash
# Claude Code
mkdir -p ~/.claude/skills/design-interrogator-coordinator
cp skills/design-interrogator-coordinator/skill.md ~/.claude/skills/design-interrogator-coordinator/skill.md

# Codex
mkdir -p ~/.agents/skills/design-interrogator-coordinator
cp skills/design-interrogator-coordinator/skill.md ~/.agents/skills/design-interrogator-coordinator/skill.md
```

### 2. 安装 Agent 配置

```bash
# Claude Code
mkdir -p ~/.claude/agents
cp agents/design-interrogator-analyst.md ~/.claude/agents/
cp agents/design-interrogator-interrogator.md ~/.claude/agents/
cp agents/design-interrogator-researcher.md ~/.claude/agents/
cp agents/design-interrogator-ixd.md ~/.claude/agents/
cp agents/design-interrogator-critic.md ~/.claude/agents/
cp agents/design-interrogator-ui.md ~/.claude/agents/
cp agents/design-interrogator-strategist.md ~/.claude/agents/
```

### 3. Agent 清单

| 文件 | Agent ID | 轨道 |
|------|----------|------|
| `design-interrogator-analyst.md` | 源码分析师 | 架构 |
| `design-interrogator-interrogator.md` | 架构审问官 | 架构 |
| `design-interrogator-researcher.md` | UX研究员 | UX |
| `design-interrogator-ixd.md` | 交互设计师 | UX |
| `design-interrogator-critic.md` | 设计审问官 | UX |
| `design-interrogator-ui.md` | UI设计师 | UX |
| `design-interrogator-strategist.md` | UX策略师+文档编译 | 收敛 |

### 4. MCP 服务器（可选但推荐）

| MCP Server | 用途 | 使用者 |
|------------|------|--------|
| context7 | 查询框架/库文档 | analyst, interrogator |
| web-search-prime | 竞品调研 | researcher |
| web-reader | 读取行业报告 | researcher |
| vision-server | 分析参考设计图 | ixd, ui |

### 5. 验证安装

```bash
# 启动协调器
/design-interrogator-coordinator

# 自然语言触发
"帮我做个完整的产品设计"
"拷问我关于微服务架构的设计"
"审问这个交互设计方案"
```

## 使用流程

```
1. (可选) 先运行 design-miner-team 分析参考项目
2. 启动 design-interrogator-coordinator
3. 协调器自动检测上游 → 收集需求+品味 → 派发双轨道专家
4. Track A (架构) 和 Track B (UX) 并行执行
5. strategist 裁决争议 → 编译统一规格文档
6. 交付 .di/phases/07_documentation/ 给 dev-genius
```

## 权限配置

如需减少权限提示，可在项目 `.claude/settings.json` 中添加：

```json
{
  "permissions": {
    "allow": [
      "Read(**)",
      "Write(**)",
      "Glob(**)",
      "Grep(**)",
      "Bash(git:*)",
      "Bash(ls:*)"
    ]
  }
}
```

---

**版本**: v3.1
