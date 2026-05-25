# Design-Miner 团队安装指南 v5.2

## 安装步骤

### 1. 复制协调器 Skill

```bash
mkdir -p ~/.claude/skills/design-miner-coordinator
cp skills/design-miner-coordinator/skill.md ~/.claude/skills/design-miner-coordinator/skill.md
```

### 2. 复制专家 Agent 配置（9 个）

```bash
mkdir -p ~/.claude/agents
cp agents/design-miner-pattern-recognizer.md ~/.claude/agents/
cp agents/design-miner-critical-thinker.md ~/.claude/agents/
cp agents/design-miner-abstraction-modeler.md ~/.claude/agents/
cp agents/design-miner-interaction-analyzer.md ~/.claude/agents/
cp agents/design-miner-perception-analyzer.md ~/.claude/agents/
cp agents/design-miner-emotion-analyzer.md ~/.claude/agents/
cp agents/design-miner-deconstructor-patternmaster.md ~/.claude/agents/
cp agents/design-miner-methodologist-pragmatist.md ~/.claude/agents/
cp agents/design-miner-rules-distiller.md ~/.claude/agents/
```

### 3. 校验安装

重启 Claude Code 后输入：

```
使用 design-miner 团队全面分析 [项目路径] 的源码设计
```

## 文件清单

| 类型 | 文件 | 目标路径 |
|------|------|----------|
| 协调器 | skill.md | `~/.claude/skills/design-miner-coordinator/skill.md` |
| 专家 A | design-miner-pattern-recognizer.md | `~/.claude/agents/` |
| 专家 B | design-miner-critical-thinker.md | `~/.claude/agents/` |
| 专家 C | design-miner-abstraction-modeler.md | `~/.claude/agents/` |
| 专家 D | design-miner-interaction-analyzer.md | `~/.claude/agents/` |
| 专家 E | design-miner-perception-analyzer.md | `~/.claude/agents/` |
| 专家 F | design-miner-emotion-analyzer.md | `~/.claude/agents/` |
| 专家 G | design-miner-deconstructor-patternmaster.md | `~/.claude/agents/` |
| 专家 H | design-miner-methodologist-pragmatist.md | `~/.claude/agents/` |
| 专家 I | design-miner-rules-distiller.md | `~/.claude/agents/` |

## 模型要求

| 专家 | 模型 | 原因 |
|------|------|------|
| abstraction-modeler | Opus | 深层抽象思考需要最强推理能力 |
| deconstructor-patternmaster | Opus | 跨域类比和心智模型逆向工程 |
| methodologist-pragmatist | Opus | 方法论体系构建需要系统性思维 |
| 其余 6 专家 | Sonnet | 识别/批判/分析类任务，Sonnet 足够 |

## 依赖

- Claude Code（支持 skills 和 agents 配置）
- 无外部 MCP 服务依赖
- 建议为 Opus 模型预留足够的 token 配额
