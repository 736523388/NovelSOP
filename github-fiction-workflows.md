# GitHub 小说工作流核查

核查日期：2026-09-30。只读查看 README、工作流及许可证页面；未安装、运行或实测项目。仓库中的 SKILL.md 仅为研究材料。以下机制存在于文档，不等于创作效果已获独立验证。

## 1. zhougz520/novel-architect

[项目](https://github.com/zhougz520/novel-architect) 面向中文长篇商业连载，包含 Python 状态工具与 Agent 文学判断。README 声称做过 140 章生产，明确未公开后台、收入和合同数据，因此不能据此判断商业成功。

[章节工作流](https://github.com/zhougz520/novel-architect/blob/master/docs/guides/chapter-workflow.md) 的可借鉴设计：写前读取状态及 writing_task；比较情节候选；正文通过审校后才提交状态。读者承诺记录引入章节、预计兑现窗口和兑现证据，能将“钩子”变成可追踪事项。它还将人物声音、可见收益、状态变化、下一章阅读理由放进写作输入。

[审校规则](https://github.com/zhougz520/novel-architect/blob/master/docs/reference/signals-and-gates.md) 将启发式与模型评审分开，并要求稿件及输入 hash 匹配，避免改稿后沿用旧报告。建议借用版本校验和修稿闭环；具体分数阈值及严格合并策略仍需试验，不能当成番茄平台标准或真实留存率。

[Apache-2.0 LICENSE](https://github.com/zhougz520/novel-architect/blob/master/LICENSE) 实际存在。本轮核查了工作流文档，未对 Python 实现做完整审计。

## 2. hestudy/snowflake-fiction

[项目](https://github.com/hestudy/snowflake-fiction) 将构思、人物深化、场景规划、章节生成、复核及导出拆成独立环节，适合参考文件组织和局部重做。README 提及番茄 8 万字评估准备，属于仓库说法，使用前必须与番茄当期官方规则核对。

[chapter-write](https://github.com/hestudy/snowflake-fiction/blob/main/skills/chapter-write/SKILL.md) 实际要求读取场景规划、人物档案、前章正文和风格文件，缺少前置场景规划时跳过；写后检查冲突、情绪、期待和因果。可借鉴“先备齐上下文再写、失败回到场景设计”的流程。

[opening-check](https://github.com/hestudy/snowflake-fiction/blob/main/skills/opening-check/SKILL.md) 使用了未在该文件提供来源的读者 3 秒决策、前三章流失超过 80%、留存提高 40% 等数字，还要求生成预计留存率。不能把这些数字纳入生产承诺；建议仅保留开篇问题定位及修改建议。每章固定钩子、前三章固定金手指/打脸等，也应按题材调整。

[MIT LICENSE](https://github.com/hestudy/snowflake-fiction/blob/main/LICENSE) 实际存在。

## 3. ZBA-z/novel-writer-agent

[项目 README](https://github.com/ZBA-z/novel-writer-agent) 的正文流程包括细纲、写作、打磨、审查和状态记忆；宣称朱雀检测实测低于 5%，并设定低于 20% 为交付指标。没有在已核查 README 中看到足以独立复核该效果的实验材料。

[核心工作流](https://github.com/ZBA-z/novel-writer-agent/blob/main/SKILL.md) 值得参考的是区分市场事实与假设、角色/伏笔/时间线回写、单章检查与跨章检查分开。需要剔除的硬规则包括固定每 300 字爽点、主线不能超过 400 章、每 30 章必须发现至少 100 个问题。这些规则可能制造机械文本或虚假问题，应改成题材适用的编辑检查及真实缺陷记录。AI 检测数字也不等于质量、原创性或平台认可；不能将模型扮演“检测人格”的输出当成第三方检测实测。

README 写 MIT License，但此次根目录文件列表未见独立 LICENSE；许可证完整性尚未核实，不能把它等同于前两个项目已具备明确许可证文件。参考小说宜只提炼抽象结构，保留来源，避免复用具体表达和独特情节组合。

## 对番茄 SOP 的建议

优先组合：novel-architect 的状态与审校闭环 + snowflake-fiction 的分层规划及独立模块 + 作者实际后台反馈。先用自己的连续章节试验修改时间、矛盾数量和读者反馈，再决定是否采用整个工具。上述 GitHub 项目均不能充当番茄规则的权威来源，也未提供可用于保证收益或推荐量的证据。
