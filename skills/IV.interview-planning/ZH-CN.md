# 演练计划 (Interview Planning)

## 动机

此技能必须严格跟在 `IV.interview-alignment` 之后使用。它的职责**不是**与用户闲聊出题，它是一个冷酷无情的单纯“计划生成工厂”。负责将策略文档直接转化为可执行的清单。

## 1. 上下文识别与读取 (Context Resolution & Read Strategy)

不要盲目启动。扫描 `docs/interviews/` 目录。

- 如果存在**多个活跃的** `[Company]-[Role]` 公司文件夹，你必须立刻熔断并向用户确认：“当前存在多个活跃的面试流，我们要为哪场面试制定筹备计划？”。
- 一旦锁定了唯一的执行上下文，准确找到并通读对应的战术文档：`docs/interviews/YYYY-MM-DD-[Company]-[Role]/strategy.md`。

## 2. 生成模拟演练任务清单

严格依据刚刚读取到的防守反击策略和盲区，生成相应的模拟考题与知识扫盲点清单。

**保存要求：** `docs/interviews/YYYY-MM-DD-[Company]-[Role]/prep-plan.md`

## 3. 强制的排版格式 (Mandatory Formatting)

这份生成的清单**必须采用标准的 Markdown 任务清单框 `[ ]` 进行输出**，该点不接受妥协。
此外，你**必须**为每道考题打上目标考官子代理的标签 (如 `[Agent: @/interview-peer]`, `[Agent: @/interview-manager]`, `[Agent: @/interview-architect]`, 或 `[Agent: @/interview-hr]`)。

示例格式：

```markdown
# [公司名] [岗位名] 备考实操清单

## 苏格拉底式发问题库 (Mock Questions)
- [ ] **问题 1** [Agent: @/interview-architect]: 告诉我一次你不得不去优化一个慢查询的真实经历。(考察目标：数据库防护战术)
- [ ] **问题 2** [Agent: @/interview-manager]: 你会如何处理不断加塞的临时需求？(考察目标：项目管理排期能力)

## 资料扫盲区 (Knowledge Review)
- [ ] 复习以往重构项目 X 的具体实施细节数据。
```

## 4. 退出与接棒 (Terminal State)

一旦生成完这套清单并保存后，**绝对不要自发开始进入问答模式**。直接停工并对接下一步：

> "为您量身定制的单兵作战演练计划已经写入了对应文件夹的 `prep-plan.md` 中。现在万事俱备，我们可以开启真正的拉练了。正在帮您呼唤 `@[/IV.interview-mocking]` 执行器。"

