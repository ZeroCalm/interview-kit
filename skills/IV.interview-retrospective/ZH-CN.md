# 面试复盘总结 (Interview Retrospective)

## 动机

这是整条流水线的收宫组件。在 `IV.interview-mocking` 穷尽了清单考题，或由用户强行终止 (`/wrapup`) 时使用，目的是把之前的受苦推演转化为高密度的复习精华。

## 1. 考官视角引入与资料整合 (Persona Ingestion & Cross-Reference)

在动笔执笔之前，你必须**强制询问用户两个关键信息**（如果用户还没提供的话）：

1. 真实面试的**录音转写文本（Transcript）**或面经原声记录。
2. **考官的身份 (Persona)**：这次对线的考官是同级开发 (Peer)、直属主管 (Manager)、架构师 (Architect) 还是 HR？

一旦确认身份，你必须在后台静默加载该角色专属的考核标准体系（位于 `.agents/agents/interview-[role].md` 中）。这是为了防止“拿架构师的标尺去打分 HR 面试”的低级错误。

拿到日志并加载判别法则后，读取当前活跃的 `docs/interviews/YYYY-MM-DD-[Company]-[Role]/` 目录，并通读这三份核心文档：

1. `resume-snapshot.md`（查看用户当时究竟在简历上如何标榜自己）
2. `strategy.md`（原始防御战略）
3. `prep-plan.md`（预演的题目列表）

将真实的面试表现与当初的简历快照进行对比碰撞，评估是否是失真的简历部分导向了灾难性的连环追问。然后比对策略资料，评估真实战场上的执行偏差（The Delta）。

## 2. 复盘落盘与导师级深度诊断 (Pedagogical Diagnosis)

生成最终的复盘复习册。你不能只是像个记账员一样罗列错误。你必须扮演顶级大厂的技术导师，使用以下心法对逐字稿进行诊断：

**保存要求：** `docs/interviews/YYYY-MM-DD-[Company]-[Role]/review.md`

必须严格采用下列段落格式呈现：

1. **背景与战况 (Context & Execution)**: 目标战、涉及公司、预定角色，以及真实面试的体感是否与预想一致。
2. **战术执行度复查 (Strategy vs Reality)**: 对照 `strategy.md`，候选人是成功把问题 Pivot（转移）到了自己的防御阵地，还是毫无准备地被对方拖死，掉进了盲区？
3. **行为心理学与简历引火侧写 (Behavioral & Resume Assessment)**: 一针见血地点出转写稿中暴露的防备心 (Defensiveness) 或掩饰性废话 (Rambling)。指出具体是哪一句话让面试官失去了耐心。并狠狠指出，这场灾难性的连环追问究竟是由 `resume-snapshot.md` 里的哪一行“过度吹牛”引发的。
4. **病灶归因溯源 (Root-Cause Analysis)**: 对于每一次技术回答的翻车，指出其底层的“心智模型缺失”。（例如：“你连这道题都答不出，说明你根本没想过微前端沙箱的 CSS 污染穿透原理，只是背了概念。”）
5. **刻意练习清单与简历降级通牒 (Actionable Study Plan & Resume Revision)**: 一份 `[ ]` 任务清单。针对暴露的盲点，布置**确切的 15 分钟级的代码验证任务**（严禁给出“建议回去好好复习深入浅出XX”的废话）。并且，必须强制下达简历相应高危描述的“剔除/降维修改”指令。

## 3. 彻底了结 (Terminal State)

这份浓缩战书写入硬盘妥当之后，正式告知用户全套闭环流程顺利完结，系统休眠。在此处绝对不要再自作主张唤起其他多余技能。