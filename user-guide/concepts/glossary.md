# 术语表

全书措辞以本页为准。每个术语 = 一句话定义 + 在哪一章详细了解。

## 会话与轮次

| 术语 | 定义 | 详见 |
|---|---|---|
| 会话（Session） | 一份完整的 AI 协作对话，时间线上的卡片单位 | [时间线浏览](../guides/timeline.md) |
| 轮次（Turn） | 会话中的一来一回（用户输入 + AI 回复），卡片上按序排列 | [时间线浏览](../guides/timeline.md) |
| Part | 超长会话被自动拆分成的段落，以堆叠卡片展示，可散开查看 | [时间线浏览](../guides/timeline.md) |
| 会话速览 | 时间线右侧的目录列：不展开卡片即可浏览每轮理解的目标 | [时间线浏览](../guides/timeline.md) |
| 原文视图 | 某一轮对话的完整原文阅读界面 | [时间线浏览](../guides/timeline.md) |

## AI 理解层

| 术语 | 定义 | 详见 |
|---|---|---|
| Turn 理解 | AI 为单轮对话生成的结构化要点（目标 / 过程 / 成果） | [理解与摘要](../guides/understand-and-summary.md) |
| 叙事摘要 | AI 为整个会话生成的四节叙事：背景与目标 / 过程脉络 / 关键决策与转折 / 最终成果 | [理解与摘要](../guides/understand-and-summary.md) |
| 完成清单 | 摘要的清单式形态，逐条列出会话完成的事项 | [理解与摘要](../guides/understand-and-summary.md) |
| Session 问答 | 基于整个会话上下文向 AI 提问 | [问答与翻译](../guides/qa-and-translate.md) |
| 翻译 / 解读 | 原文视图中对选中段落的段落级批注：翻译 = 中英对照，解读 = AI 讲解 | [问答与翻译](../guides/qa-and-translate.md) |

## 项目与代码

| 术语 | 定义 | 详见 |
|---|---|---|
| 项目 | 会话的组织单位；一个项目对应一个代码库 | [项目与归档](../guides/projects.md) |
| 代码文件夹 | 项目确认的代码根目录，代码树的扫描起点 | [项目与归档](../guides/projects.md) |
| 代码树 | 项目文件结构的树形视图 | [代码树与注解](../guides/code-tree.md) |
| AI 注解 | AI 为文件/目录生成的 1~3 句说明 | [代码树与注解](../guides/code-tree.md) |
| 影响关联 | 对话轮次与代码文件之间的关联；对话中直接出现的路径为「显式」，由摘要内容匹配的为「AI 推断」 | [影响关联与溯源](../guides/impact-links.md) |
| 历史路径 | 对话中提到过、但代码树中找不到的路径 | [影响关联与溯源](../guides/impact-links.md) |
| 补挂关联 | 为存量会话批量补齐影响关联的操作 | [影响关联与溯源](../guides/impact-links.md) |
| 数据流边 | 从 import 语句解析出的文件间上下游关系 | [数据流与解读](../guides/dataflow.md) |
| Flowchart | 以某个文件为中心的三层上下游关系图 | [数据流与解读](../guides/dataflow.md) |
| 中观描述 | AI 对焦点节点邻域图景的角色描述 | [数据流与解读](../guides/dataflow.md) |
| Flow 解释 | AI 对两个节点之间数据如何流动的解释 | [数据流与解读](../guides/dataflow.md) |
| worktree | 同一仓库的多个工作目录，项目视图按 worktree 分组展示分支与改动 | [数据流与解读](../guides/dataflow.md) |

## 进度与复盘

| 术语 | 定义 | 详见 |
|---|---|---|
| DevPlan 清单 | 从计划文档导入的结构化任务清单 | [DevPlan 计划清单](../guides/devplan.md) |
| 判定留痕 | AI 判定任务进度时记录的对话依据 | [DevPlan 计划清单](../guides/devplan.md) |
| Debug 复盘 | 对 debug 会话的 AI 复盘：根因分析 / 排查过程 / 修复策略 / 教训总结 | [Debug 复盘](../guides/debug-retro.md) |

## 导入与授权

| 术语 | 定义 | 详见 |
|---|---|---|
| 监测文件夹 | 设置中登记的目录，出现新的导出文件即自动导入 | [导入与整理](../guides/import-and-organize.md) |
| 实时监测 | 对 Kimi / Qwen 进行中会话的自动同步（设置中的「Wire 会话」即此类实时数据） | [开启实时监测](../getting-started/live-monitor.md) |
| 归档 | 项目的「藏起来但不删」：全局隐藏其会话，数据保留，可恢复 | [项目与归档](../guides/projects.md) |
| 授权码 | 离线验证的激活凭证：永久码长期使用，延期码按天数续期 | [试用与激活](../getting-started/trial-and-activate.md) |
| 账号 | 一份授权码对应的独立数据空间；切换账号即切换数据 | [授权与账号](../guides/license-account.md) |
