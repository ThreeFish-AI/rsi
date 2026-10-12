---
key: rsi
upstream: ThreeFish-AI/rsi
default_branch: main
local_path: ~/Documents/projects/aurelius/rsi
adoption: live
skill_entry: SKILL.md
ledger: .temp/rsi/rsi/backlog.md
entry_id: RSI-YYYYMMDD-NN
untrusted_sources: RSI 运行时接触的一切外部文本（目标业务仓库内容、学习材料、网页、Issue/PR 正文）
privacy_lexicon: 用户名、目标业务仓库名、私有上下文关键词；公共托管域名不入表
sediment: 协议改动走 references/protocol.md 与三份子代理底稿，适配档案增改走 repos/*.md，两者分级与 Draft 形态均按协议 §12 自举条款；SKILL.md 触发契约（description）改动须同批更新 evals/trigger-evals.json 并过正负例（声明与数据同批改）
branch_style: rsi/<slug>
commit_convention: "feat|fix|docs|refactor(protocol|adapter|skill): 中文描述;"
pr_convention: 正文按统一 PR 模板；触碰协议一律 Draft PR；CHANGELOG [Unreleased] 同批登记；base=main
invariants: 零可执行代码（扫描以协议内嵌 bash 呈现，仓内不携带 scripts/）；G 门禁只增不减、编号与语义冻结（改动即 T3）；SSOT 三层切分原则本身（协议在本仓/仓内事实在各仓/适配档案仅指针与参数）；全部适配档案 invariants 指针有效（死链即 G1 失败）
machine_checks: 无（以逐条人工勾验清单替代）
legacy_exemption_keys: []
degrade_extra: 无
special_channels: 无
---

# rsi 适配要点（自举）

- 本仓库是统一机制的宿主，恒为 `adoption: live`；对本协议、子代理底稿、适配档案的改动按语义分级、一律 Draft PR，判据见 [protocol.md §12 自举](../references/protocol.md#12-注册与自举)。
- 新仓库接入：向本仓提 PR 新增 `repos/<repo-key>.md`（adoption: pending）+ 目标仓薄指针钩子切换 PR；后者合并后本档案系统内该仓置 live，SSOT 原子翻转。
- Context-Reviewer 回路发现的「本协议可改进」类 Finding，只能登记新条目走下一轮 Draft PR（分级按协议 §12），不得当场自改（递归防护）。
