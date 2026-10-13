# Changelog

本仓库遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/) 格式；版本历史与全部变更痕迹由 Git 历史承载。

## [Unreleased]

### 新增
- 注册 dub（ThreeFish-AI/dub，独立配音 Skill）：新增适配档案 `repos/dub.md`（`adoption: pending`，待 dub 切换 PR 合并后 flip）；SKILL.md 路由表与 description 枚举、README 注册表同步；适配档案与 README 中随清单漂移的计数（vibe-video 的「十五条」、agents 的「六注册仓」、README 的「5+1 适配档案」）改为不含数字的指针式表述；trigger-evals 正负例各增一条（#22）。
- 统一 RSI 经验沉淀协议 v0.1 首次落地：G0–G4 门禁、六态状态机、限流背压与降级矩阵（references/protocol.md）；Steward / Verifier / Context-Reviewer 三份子代理底稿；5+1 仓库适配档案；SKILL.md 薄入口与触发正负例评测（#1）。

### 更改
- 上游仓更名同步：ThreeFish-AI/dub → ThreeFish-AI/vibe-tts（上游改名 PR 已合并），适配档案 git mv `repos/dub.md` → `repos/vibe-tts.md`（frontmatter `key`/`upstream` 同步），SKILL.md description 枚举与路由表、README 注册表、trigger-evals 正负例语料一并迁移，正文指称同步（库模块 `dub_` 前缀 → `vibe_tts_` 前缀）；存量 CHANGELOG 条目、既有 PR/issue URL 与 flipped_at 历史锚点保留原文（GitHub 仓库重定向保活），历史台账不改写（#23）。

### 修复
- 盲审只读纪律补包管理器副作用显式禁令：steward 与 verifier 两份底稿的只读纪律处各补一句——禁止在隔离 clone 内运行包管理器/解释器命令（uv run、npm install、pip install 等生成 .venv、lockfile 等 untracked 副作用文件，.gitignore 豁免不覆盖此类命令），必要的环境准备一律在隔离 clone 之外进行（源自 review-once RSI-013 同源缺口，语义与 review-once#11 同构；#26）。
- vibe-tts 适配档案的「须与 vibe-video 同值」表述改为「黄金哈希测试只住 vibe-tts，vibe-video 经委托继承、不留镜像副本」：vibe-tts 与 vibe-video 的配音测试按被测对象归属拆分，不再要求双仓人工同步（#23）。
- 注册状态 flip 补登：agents.md（#2）、preening-substrate / guided-learn / vibe-video（#3）、review-once（#6）依次置 `live`——`adoption`、SKILL 路由表与 README 注册表同步翻转（#2、#3、#6）。
- dub 注册完成：切换 PR（ThreeFish-AI/dub#1）已合并，适配档案置 `live`，SKILL 路由表与 README 注册表同步翻转（#24）。
- 评审遗留 T1 机械修正集：slug 判据统一（正则/case/底稿三处同步）、无 gh 降级 clone 补目标目录（协议侧补齐）、降级矩阵补两行、安装预处理、backlog 模板结论行扩字段、四道门残留表述清理（#4）。
- 执法判据加固：G4a noreply 剔除改精确字面量（封闭机密洗白通道）、不可信来源补 PR/Issue 标题与 comment、反刷分逐句审阅入 Verifier 必查清单、NOREPLY 纳入 §3 断言链（#5）。
- 执法判据收尾：G4a noreply 剥除改独立成 token 判据并转义 `.`（封闭子串包含洗白与近形态误剥，POSIX BRE 四段式 BSD/GNU 均可运行）、verifier G3 清单补缺陷类回归测试核查项、§3 NOREPLY 供值注释校准为主 Agent 派发时供值（#7）。
- 豁免文法加固：受信载体排除 sync / 分发链产物（豁免行须手写且不被分发覆盖）、整行精确匹配语义与免确认回报强制披露命中行、裸「免确认提交」三档口径统一（README 同步）、legacy 键全字面整行匹配与 `<版本号>` 式样占位注明（#8）。
- 评审 P3 池 T1 快修：report.md 指派主 Agent 呈现报告时同步落盘（§3 目录树 + §7）、README / SKILL description「隔离分支」统一为「隔离 clone」、evals 正例孤立术语 RSID 换为上游现存术语 Diff、README repos/ 行字段摘要改为指向协议附录B、「五仓」补定义注并校准为六注册仓、preening-substrate 档案 invariants 值加双引号修复 YAML 解析（#9）。
- 状态机与时序收口：submitted 补终态转移（合并结案回填 merge sha / 关闭未合并转 rejected）且条目模板状态枚举补「结案」终态显示、跨会话补跑限定 PR 仍 open、切换 PR 不得先于本仓适配档案入 main 合并、flip 时限改两者较晚者起算并于 flip PR 登记切换合并时间（SKILL.md 路由表旧起算点同步对齐）、自举改动按语义分级（不改门禁编号与判据语义的修正按分级表执行且一律 Draft）、回执更新条款指针化至 context-reviewer.md §8（#10）。
- 信任边界收口：§10 无 gh 降级补交接块消费路径（PR 手动创建后依 review-request.md 落盘块派发 Context-Reviewer、无 gh 时回执落 $S-ctx.md 由主 Agent 转述）、evals 触发正例补 rsi 自身与门禁无法判定 / 宿主能力不符两类运行时证据、§3 编号式样注补仓内 ledger 型仓库的双 ledger 并线规则（PR 创建后转写仓内 ledger 沿用仓内编号、.temp backlog 结论行指向仓内条目）（#11）。
- 制度收尾：§6 merge 流程补解冲突提交前冲突标记零残留核验（grep 计数全为 0 且输出贴回执，verifier 基线核验步骤同步抽查最终树）、§5 SSOT 整体迁移对账豁免补「接收仓对应文本」测量面定义（接收文件集合的全部新增行，以骨架后首个含迁移内容 PR 为界）与回执双口径披露、判定以测量面口径为准（#12）。
- 散件 T1 批（第二轮）：vibe 档案正文门禁映射指称去重（与下句映射行重复）、「白名单」三义限定词对齐（协议首处裸用 / context-reviewer §5 定义改称修复白名单 / SKILL.md 正文）、verifier G2 步骤补 (a)/(b) 子编号对齐协议 §5、六适配档案 frontmatter 长值引号化（14 值，附录B 补登记判据）、rsi 档案 commit_convention 补 chore(changelog)、协议 §3 路径约定补 .temp 隔离 clone 路径过滤假绿警示（#13）。
- SKILL.md 硬禁令一句话版对齐协议 §7——「永不 merge」改「不 merge 上游 PR（本地 merge 例外见协议 §7）」（#14）。
- 落盘物补目录树与信任边界、flipped_at 字段化：§3 目录树 pr/ 区补 review-request.md、-ctx.md 与 -ctx.patch 三行（report.md 连接符同步调整）、落盘物信任边界枚举并列补两文件、patch 泛称改「全部 patch」并举例两类；附录B 补登记 flipped_at 字段（切换 PR 链接与合并时间；由 flip PR 填写，未切换仓为空）、§12 可见性锚句改为登记至适配档案 flipped_at 字段（frontmatter）、六适配档案 frontmatter 各补 flipped_at 实测值（#16）。
- T2 收尾簇：修复白名单例外授权成文（主 Agent 显式授权修复白名单外动作，授权与执行在当轮回报及 PR 摘要披露并标注，context-reviewer §5 同步指针）、跨规约提交纪律优先级澄清（隔离 clone 内协议命令优先、宿主 `/commit` 纪律不约束 `$REPO`、pre-commit 不激活以 `machine_checks` 为准，agents.md 档案同步指针）、隔离 clone 终态清理规则（条目终态后经用户确认，未经确认不删除）、§6 冲突标记判据 setext 下划线人工豁免出口、§5 对账豁免增量迁移批次测量面并入累计口径（界桩随批前移）、仓内 ledger 转写载体与时序（主 Agent 追加独立 commit 且先于 Context-Reviewer 派发，L3 双 ledger 判据同步分流）（#15）。
- local_path 脱敏占位与回填 commit 规范式样：六适配档案 local_path 统一为 `~/Documents/projects/<本机实际仓目录>` 脱敏占位（附录B 释义同步补「脱敏占位——公开仓不落本机实际路径，安装时自行替换」）、§8 交接块段末补 CHANGELOG PR 号回填 commit 规范（主 Agent 以 rsi-reviewer noreply 身份追加 commit，标题式样 `chore(changelog): 回填 PR 号（#N）;`，正文含签名块）（#17）。
- flipped_at 一致性判据入勾验清单、§3 树-落盘物双向差集对账配方：附录B flipped_at 行补值式样（`<owner>/<repo>#<N> merged <ISO8601Z>`；rsi 自举仓为 `bootstrap`）、verifier G1 补档案一致性勾验（adoption=live ⇔ flipped_at 非空，pending ⇔ 空）与 $W/ 路径形态集合对 §3 目录树双向差集对账（新落盘物只定义不入树即 FAIL）（#18）。
- §7 授权话术与 §4 例外授权通道分离裁定：确认话术明示覆盖面仅限修复白名单内小项与回路常规动作，修复白名单外动作的例外授权独立依 §4 条款执行（单独披露与 commit 前缀标注，不在本话术扩面）——两通道分离，防确认疲劳稀释例外可见性（#19）。
- 六仓 privacy_lexicon 补本机绝对/家目录路径形态模式（/Users/、/home/、~/ 前缀——G4a 已有通用扫描，此列补 G4b 词表层对目标仓特定路径的覆盖；#17 ctx-review F5 词表层根因封口）（#20）。
- 全量评审修复批（review-once 授权，三路独立评审 48 缺陷归并为 14 簇）：verifier 执法面（G4a 裸 diff 假绿、G1 判据回注协议 §5、落盘物对账白名单化、非文档文件清点、merge 后 BASE 刷新）、扫描脚本加固（邮箱 TLD 大小写、`+++` 行头精确过滤、color.ui 钉扎、LC_ALL=C、词表 16→18、按文件 LOSS 防对冲、词表字面量化防 zsh 静默假绿）、协议断链闭合（agents.md 档案名派生、§9 出路六态落点、fork 配方、回填时序、盲评降级、树补残留行、slug 六处点名、回退检测 branch_style 化、回执「未跑」档收口）、角色边界与输入契约（$W/pr 写边界、NOREPLY 供值、$B 覆盖顺序、改动面白名单承接）、G2(a) 比选链闭合、ctx 底稿流程自洽（轮次语义、新实例派发主体、白名单取值落点、重建配方、越界回滚）、G4b 词表口径显式化与豁免通道（RSI-20261012-50）、豁免文法版本号比对对象、事实与引用修正（README 断言、档案悬空指针、孤儿文献、bootstrap 式样、编辑残留、rsi 档案 sediment 补 README 索引登记）、术语对齐（Hook/ledger/Prompt/修复白名单消歧）、evals 例句上游词汇锚定——其中 guided-learn 档案删「零可执行代码与依赖」（上游无该不变量声明文，勾验指针死链）、vibe-video 档案执法测试表述校准（上游 15 条仅 5 条带执法标记、共 6 处测试引用）均以上游实况为据（#21）。
