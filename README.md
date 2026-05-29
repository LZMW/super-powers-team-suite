# Super Powers Team Suite

> 给 Claude Code 配一支 AI 开发团队——设计审问、代码实现、质量审查全自动完成

---

## 这是什么

一套 Claude Code 的 Agent 团队套件。用 `/` 命令启动协调器，协调器自动调度多位专家 Agent 协作完成任务。不是单个 AI 对话，而是一支有分工、有协作、有质量门控的虚拟开发团队。

覆盖软件开发全流程：从源码分析提取设计智慧，到对新项目进行架构审问和 UX 设计，再到 TDD 开发和质量审查交付。

## 三支团队

**Design-Miner（设计挖掘）**：分析参考项目源码，提取架构模式、UX 工程经验、元方法论。9 位专家并行跑三条分析轨道，输出结构化的设计资产。

**Design-Interrogator（设计审问官）**：从零设计新项目。7 位专家双轨道并行——架构轨道遍历决策树、逐条拷问；UX/UI 轨道研究用户、设计交互、压测视觉、输出裁决。最终编译为开发团队可直接消费的规格文档。

**Dev-Genius（开发天才）**：读取设计规格，按五道门控完成开发。Plan Gate → Architecture Gate → TDD Gate → Verify Gate → Review Gate → Finish Gate，每道门不过不许往下走。写测试、写代码、修 Bug、审查质量，全自动循环。

所有团队共用黑板模式（Blackboard Pattern）进行专家间状态同步，事件总线解耦通信，比链式传递省 50%+ Token。

## 安装

```bash
git clone https://github.com/LZMW/super-powers-team-suite.git ~/.claude/super-powers-team-suite
```

然后在 Claude Code 中用 `/skill-name` 调用对应协调器即可。每个团队的 `agents/` 目录存放 Agent 定义，`skills/` 存放协调器 Skill。

## 赞助

如果这个项目帮到了你，欢迎打赏支持。

<p align="center">
  <img src="donate-qr.jpg" width="260" alt="微信赞赏码">
</p>

## 许可证

AGPL-3.0 —— 自由使用、修改、分发，但修改后的源码必须公开。

---

维护者：Mr.Chen · 版本 v3.2
