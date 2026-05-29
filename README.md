# Super Powers Team Suite

> 给 Claude Code 配一支 AI 开发团队——设计挖掘、设计审问、代码实现全自动完成

---

## 这是什么

一套 Claude Code 的 Agent 团队套件。用协调器 Skill 启动，协调器自动调度多位专家 Agent 协作完成任务。不是单个 AI 对话，而是一支有分工、有协作、有质量门控的虚拟开发团队。

三支团队覆盖软件开发全流程：

```
DM (设计挖掘) → DI (设计审问) → DG (开发实现)
Stage 1-7       Phase 0-12        Gate 0-7
```

所有团队共用**黑板模式（文件夹组 v4.0）**进行专家间状态同步，事件总线解耦通信，INDEX 导航实现按需读取。比链式传递省 50%+ Token。

---

## 三支团队

### DM — Design-Miner（设计挖掘）v6.1

**从参考项目源码中挖掘设计智慧**。10 位专家并行跑三条分析轨道，输出结构化设计资产给 DI 团队。

| 轨道 | 专家 | 产出 |
|------|------|------|
| 架构 | A(模式识别)→B(批判审视)→C(抽象原则) | 15 种 GoF + SOLID + 抽象原则 |
| UX | D(交互)∥E(感知)∥F(情感) | 体感→代码映射 + 状态覆盖 + 情感容错 |
| 元方法论 | G(跨域解构)→H(体系构建)→I(原则蒸馏) | 跨域模式 + 方法论工具箱 + 反模式 |

J(汇总专家) 整合全部黑板为下游可消费的文件夹组产出。

### DI — Design-Interrogator（设计审问官）v4.0

**从零设计新项目**。8 位专家双轨道并行——架构轨道遍历决策树、逐条拷问；UX/UI 轨道研究用户、设计交互、压测视觉。最终 strategist 编译为 DG 可直接消费的规格文档。

K(冲突审查专家) 检测跨 gen 决策不一致——「第一次 run 定 S 弯，第十次改走直线」必被发现。

### DG — Dev-Genius（开发天才）v3.1

**读取 DI 设计规格，按七道门控完成开发**。7 位专家串行执行，每道门不过不许往下走。

```
Gate 0: F(开发前源码扫描)
Gate 1: Planner(任务分解)
Gate 2: Architect(三级响应：完整架构/影响评估/架构签批)
Gate 2b: L(文档校验——Planner↔Architect 一致性)
Gate 3: Developer(TDD: RED→GREEN→REFACTOR)
Gate 4: QA Tester(验收验证，证据驱动)
Gate 5: Analyst(Karpathy四原则 + OWASP审查)
Gate 6: F(开发后重扫描 + 差异报告)
Gate 7: Coordinator(汇总交付)
```

F(源码状态分析师) 是唯一运行两次的专家——Gate 0 拍基准快照，Gate 6 拍结果快照，diff = 净产出。

---

## ⚠️ 安装前必须：MCP 服务器

三支团队依赖以下 MCP 服务器。**请务必在启动团队前安装**，否则专家 Agent 将无法正常工作。

### 必需安装（🔴 核心依赖）

#### 1. CodeGraph — 代码知识图谱

预索引的代码知识图谱，提供跨文件调用链追踪、语义符号搜索、依赖关系分析。

```bash
# 一键安装（推荐）
curl -fsSL https://raw.githubusercontent.com/colbymchenry/codegraph/main/install.sh | sh

# 或 npm
npm i -g @colbymchenry/codegraph

# 初始化项目
cd your-project && codegraph init -i
```

> 仓库：[github.com/colbymchenry/codegraph](https://github.com/colbymchenry/codegraph)
> 备用（Rust 版）：[github.com/grahambrooks/symgraph](https://github.com/grahambrooks/symgraph)

Claude Code 配置（`~/.claude.json` 或 `claude mcp add`）：
```json
{
  "mcpServers": {
    "codegraph": {
      "type": "stdio",
      "command": "codegraph",
      "args": ["serve", "--mcp"]
    }
  }
}
```

CodeGraph 工具（10 个）：`codegraph_search`, `codegraph_context`, `codegraph_callers`, `codegraph_callees`, `codegraph_impact`, `codegraph_node`, `codegraph_explore`, `codegraph_files`, `codegraph_status`, `codegraph_trace`

适用团队：DM（全部 9 位分析专家）、DG（F 源码分析师、Architect）

---

### 推荐安装（🟡 显著提升质量）

#### 2. Context7 — 实时文档查询

获取最新版本的库/框架文档和代码示例，避免 LLM 用过期 API 生成代码。

```bash
claude mcp add context7 -- npx -y @upstash/context7-mcp
```

> 仓库：[github.com/upstash/context7](https://github.com/upstash/context7) · npm: [`@upstash/context7-mcp`](https://www.npmjs.com/package/@upstash/context7-mcp)

工具：`resolve-library-id`, `query-docs`

适用团队：DI（analyst、interrogator）、DG（Architect）

#### 3. Sequential Thinking — 结构化推理

动态逐步推理，支持思路修正、分支探索、假设验证。

```bash
claude mcp add sequential-thinking -- npx -y @modelcontextprotocol/server-sequential-thinking
```

> 仓库：[github.com/modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) · npm: [`@modelcontextprotocol/server-sequential-thinking`](https://www.npmjs.com/package/@modelcontextprotocol/server-sequential-thinking)

工具：`sequentialthinking`

适用团队：DG（Architect——架构决策推理）

---

### 可选安装（🟢 锦上添花）

#### 4. Web Search Prime — 联网搜索

智谱 AI 提供的联网搜索 MCP 服务（HTTP 方式，非 npm 包）。

```bash
claude mcp add -s user -t http web-search-prime \
  https://open.bigmodel.cn/api/mcp/web_search_prime/mcp/ \
  --header "Authorization: Bearer 你的智谱API密钥"
```

> 平台：[open.bigmodel.cn](https://open.bigmodel.cn) · 需注册智谱 AI 获取 API Key

工具：`webSearchPrime`

适用团队：DI（researcher——竞品调研）

#### 5. Web Reader — 网页内容抓取

将任何网页转为干净的 Markdown 供 LLM 阅读，支持多引擎+批量抓取。

```bash
npm install -g mcp-web-reader
claude mcp add web-reader -- mcp-web-reader
```

> 仓库：[github.com/Gracker/mcp-web-reader](https://github.com/Gracker/mcp-web-reader) · npm: [`mcp-web-reader`](https://www.npmjs.com/package/mcp-web-reader)
> 轻量替代：[github.com/agenticbuildingblocks/markfetch](https://github.com/agenticbuildingblocks/markfetch) — 零配置，无需 API Key

工具：`webReader`, `fetch_url`, `fetch_multiple_urls`

适用团队：DI（researcher——竞品页面分析）

#### 6. Vision Server — 图像分析

分析截图、设计稿、图表，支持 OCR 文字提取和多模型。

```bash
claude mcp add vision -- npx -y @haisto/vision-mcp
```

> 仓库：[github.com/haisto/vision-mcp](https://github.com/haisto/vision-mcp) · npm: [`@haisto/vision-mcp`](https://www.npmjs.com/package/@haisto/vision-mcp)
> 离线替代：[github.com/hydroCoderClaud/mcp-hydrocoder-vision](https://github.com/hydroCoderClaud/mcp-hydrocoder-vision) — LM Studio + Qwen3 VL，100% 本地

工具：`analyze_image`, `chat_vision`, `get_status`

适用团队：DI（ixd、ui——分析参考设计图）

---

## 安装

```bash
git clone https://github.com/LZMW/super-powers-team-suite.git
cd super-powers-team-suite
```

### 本机用户级安装

将协调器 Skills 和 Agent 配置复制到 Claude Code 用户目录：

```bash
# Skills（协调器入口）
cp -r skills/design-miner-coordinator ~/.claude/skills/
cp -r skills/design-interrogator-coordinator ~/.claude/skills/
cp -r skills/dev-genius-coordinator ~/.claude/skills/

# Agents（专家配置）
cp agents/*.md ~/.claude/agents/
```

安装后在 Claude Code 中直接输入自然语言即可触发，或使用 `/design-miner-coordinator`、`/design-interrogator-coordinator`、`/dev-genius-coordinator`。

### 推荐权限配置（减少弹窗）

在 `~/.claude/settings.json` 中添加以下权限以允许 MCP 工具调用：

```json
{
  "permissions": {
    "allow": [
      "mcp__codegraph__codegraph_search",
      "mcp__codegraph__codegraph_context",
      "mcp__codegraph__codegraph_callers",
      "mcp__codegraph__codegraph_callees",
      "mcp__codegraph__codegraph_impact",
      "mcp__codegraph__codegraph_node",
      "mcp__codegraph__codegraph_explore",
      "mcp__codegraph__codegraph_files",
      "mcp__codegraph__codegraph_status",
      "mcp__codegraph__codegraph_trace",
      "mcp__context7__resolve-library-id",
      "mcp__context7__query-docs",
      "mcp__sequential-thinking__sequentialThinking",
      "mcp__web-search-prime__webSearchPrime",
      "mcp__web-reader__webReader",
      "mcp__vision-server__analyze_image",
      "mcp__vision-server__chat_vision",
      "mcp__vision-server__get_status"
    ]
  }
}
```

---

## 赞助

如果这个项目帮到了你，欢迎打赏支持。

<p align="center">
  <img src="donate-qr.jpg" width="260" alt="微信赞赏码">
</p>

## 许可证

AGPL-3.0 —— 自由使用、修改、分发，但修改后的源码必须公开。

---

维护者：Mr.Chen · 版本 v4.0 · 更新日期 2026-05-29
