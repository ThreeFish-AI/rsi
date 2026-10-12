---
key: vibe-video
upstream: ThreeFish-AI/vibe-video
default_branch: main
local_path: ~/Documents/projects/aurelius/vibe-video
adoption: live
skill_entry: SKILL.md
ledger: docs/.agents/issue.md（仓内 ledger）
entry_id: RSI-NNN（三位递增，从 ledger 既有最大号顺延；刻意不用 ISSUE- 前缀，与上游 negentropy ledger 区分）
untrusted_sources: 视频工作区内容、上游 negentropy Issue 正文；上游教训一律写全 URL 引用
privacy_lexicon: 声音样本生物特征纪律——样本路径与音频绝不进任何 RSI 材料；工作区/集目录名；公共托管域名不入表
sediment: "规格修改走 references/ 与 SKILL.md（按需加载表等量压缩守 8000 字预算）；CHANGELOG [Unreleased] 登记；ledger 条目回填 PR 与 commit 链接；复发不新开编号，原条目追加带日期复盘点"
branch_style: ThreeFish-AI/rsi-NNN-<topic>
commit_convention: "feat(rsi): 中文描述（RSI-0NN）;"
pr_convention: 标题中文 conventional、单条或攒批编号都入标题；描述含 G0–G4 核验回执表（统一协议 §5 格式）；触碰不变量逐项点名；base=main
invariants: "十五条不变量清单（RSI.md 第九节，清单本体留仓内：阶段编号对齐、narration.md 唯一 SSOT、frozen Remotion skeleton、复制不共享边界、SKILL.md 路由壳纪律、建模手册有界等）；每条自带执法测试"
machine_checks: "uv run --no-project --with pytest --with numpy --with pillow --with mutagen --with soundfile python -m pytest tests -q"
legacy_exemption_keys: []
degrade_extra: 拷贝式安装（$T 无 .git）时大声退出，绝不改无版本控制副本；出路=GitHub Issue 草稿或 clone 正式仓迁移条目
special_channels: "RSI.md 保留节——触发分流四象表（视频内容问题走既有 QA 回路不进 RSI）；建模经验分支（第十节：Generator/Reflector/Curator 分权、权重生命周期、压缩阶梯、check_playbook.py 执法）；$T worktree 与候选行交接契约；SKILL.md 描述/路由改动的 evals 新旧对拍（RSI.md §四仓内附加执法资产）"
---

# vibe-video 适配要点

- 切换方式为外科手术拆分：RSI.md（131 行）保留「一、触发与分流」四象表、「十、建模经验分支」全文与仓内特殊节；通用流程（登记纪律通用部分、旧四道门、子代理通用协议、PR 规范通用部分、失败出路、统一降级）上收统一协议，原地改指针。
- 门禁映射：旧 G1–G4 → 统一 G1/G2(a)/G2(b)/G3（见统一协议附录A）；ledger 既有历史条目引用保持可读。
- 建模经验分支是内容侧唯一 RSI 通道：制片中主 Agent 只许向 MODELING-PLAYBOOK 候选区追加一行（+用户/−用户/+主 三种信号），策展与晋升由 fresh-context 子代理攒批处置——该主流程内嵌行为留在仓内，不走统一 PR 回路。
- 主 Agent 自评为弱信号（w=1），不得单独推动条目晋升；删并既有条目 ≥3 条或触发压缩时另起独立核验子代理。
