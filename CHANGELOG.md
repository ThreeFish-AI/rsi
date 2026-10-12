# Changelog

本仓库遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/) 格式；版本历史与全部变更痕迹由 Git 历史承载。

## [Unreleased]

### 新增
- 统一 RSI 经验沉淀协议 v0.1 首次落地：G0–G4 门禁、六态状态机、限流背压与降级矩阵（references/protocol.md）；Steward / Verifier / Context-Reviewer 三份子代理底稿；5+1 仓库适配档案；SKILL.md 薄入口与触发正负例评测（#1）。

### 修复
- 评审遗留 T1 机械修正集：slug 判据统一（正则/case/底稿三处同步）、无 gh 降级 clone 补目标目录（协议侧补齐）、降级矩阵补两行、安装预处理、backlog 模板结论行扩字段、四道门残留表述清理（#4）。
- 执法判据加固：G4a noreply 剔除改精确字面量（封闭机密洗白通道）、不可信来源补 PR/Issue 标题与 comment、反刷分逐句审阅入 Verifier 必查清单、NOREPLY 纳入 §3 断言链（#5）。
- 执法判据收尾：G4a noreply 剥除改独立成 token 判据并转义 `.`（封闭子串包含洗白与近形态误剥，POSIX BRE 四段式 BSD/GNU 均可运行）、verifier G3 清单补缺陷类回归测试核查项、§3 NOREPLY 供值注释校准为主 Agent 派发时供值（#7）。
- 豁免文法加固：受信载体排除 sync / 分发链产物（豁免行须手写且不被分发覆盖）、整行精确匹配语义与免确认回报强制披露命中行、裸「免确认提交」三档口径统一（README 同步）、legacy 键全字面整行匹配与 `<版本号>` 式样占位注明（#8）。
- 评审 P3 池 T1 快修：report.md 指派主 Agent 呈现报告时同步落盘（§3 目录树 + §7）、README / SKILL description「隔离分支」统一为「隔离 clone」、evals 正例孤立术语 RSID 换为上游现存术语 Diff、README repos/ 行字段摘要改为指向协议附录B、「五仓」补定义注并校准为六注册仓、preening-substrate 档案 invariants 值加双引号修复 YAML 解析（#9）。
- 状态机与时序收口：submitted 补终态转移（合并结案回填 merge sha / 关闭未合并转 rejected）且条目模板状态枚举补「结案」终态显示、跨会话补跑限定 PR 仍 open、切换 PR 不得先于本仓适配档案入 main 合并、flip 时限改两者较晚者起算并于 flip PR 登记切换合并时间（SKILL.md 路由表旧起算点同步对齐）、自举改动按语义分级（不改门禁编号与判据语义的修正按分级表执行且一律 Draft）、回执更新条款指针化至 context-reviewer.md §8（#10）。
- 信任边界收口：§10 无 gh 降级补交接块消费路径（PR 手动创建后依 review-request.md 落盘块派发 Context-Reviewer、无 gh 时回执落 $S-ctx.md 由主 Agent 转述）、evals 触发正例补 rsi 自身与门禁无法判定 / 宿主能力不符两类运行时证据、§3 编号式样注补仓内 ledger 型双台账并线规则（PR 创建后转写仓内 ledger 沿用仓内编号、.temp backlog 结论行指向仓内条目）（#11）。
- 制度收尾：§6 merge 流程补解冲突提交前冲突标记零残留核验（grep 计数全为 0 且输出贴回执，verifier 基线核验步骤同步抽查最终树）、§5 SSOT 整体迁移对账豁免补「接收仓对应文本」测量面定义（接收文件集合的全部新增行，以骨架后首个含迁移内容 PR 为界）与回执双口径披露、判定以测量面口径为准（#12）。
- 散件 T1 批（第二轮）：vibe 档案正文门禁映射指称去重（与下句映射行重复）、「白名单」三义限定词对齐（协议首处裸用 / context-reviewer §5 定义改称修复白名单 / SKILL.md 正文）、verifier G2 步骤补 (a)/(b) 子编号对齐协议 §5、六适配档案 frontmatter 长值引号化（14 值，附录B 补登记判据）、rsi 档案 commit_convention 补 chore(changelog)、协议 §3 路径约定补 .temp 隔离 clone 路径过滤假绿警示（#13）。
- 落盘物补目录树与信任边界、flipped_at 字段化：§3 目录树 pr/ 区补 review-request.md 与 -ctx.md 两行（report.md 连接符同步调整）、落盘物信任边界枚举并列补两文件；附录B 补登记 flipped_at 字段（切换 PR 链接与合并时间；由 flip PR 填写，未切换仓为空）、§12 可见性锚句改为登记至适配档案 flipped_at 字段（frontmatter）、六适配档案 frontmatter 各补 flipped_at 实测值（#16）。
