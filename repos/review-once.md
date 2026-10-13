---
key: review-once
upstream: ThreeFish-AI/review-once
default_branch: main
local_path: ~/Documents/projects/<本机实际仓目录>
adoption: live
flipped_at: "ThreeFish-AI/review-once#8 merged 2026-10-11T16:01:49Z"
skill_entry: SKILL.md
ledger: docs/.agents/issue.md（仓内 ledger）
entry_id: RSI-NNN（三位递增，从 ledger 既有最大号顺延）
untrusted_sources: 被 Review 的目标仓库内容（源码、注释、Issue/PR 正文）、Review 私有内容、Conductor 平台内部状态
privacy_lexicon: 用户名、目标仓库名、Review request 私有内容关键词；公共托管域名不入表；本机绝对/家目录路径形态（/Users/、/home/、~/ 前缀——G4a 已有通用扫描，此列补 G4b 词表层对目标仓特定路径的覆盖）
sediment: "契约修改走 references/（review-contract.md、conductor-mode.md、git-mode.md）+ SKILL.md + evals 同批演进；每条新契约词汇同批落入 tests/check_states.py 的 NEW_CONTRACT 断言（RSI-007 纪律）"
branch_style: feat/rsi-NNN-<topic>
commit_convention: "feat(contract): RSI-0NN 中文描述——要点;"
pr_convention: 标题把 RSI 编号写进 conventional 标题；正文含核验回执；条目与契约修改同 commit 同批交付；base=main
invariants: "SKILL.md「不变量」节清单；evals 断言不得静默丢失新行为覆盖（RSI-005 教训）；护栏 tests/ 不进发布包"
machine_checks: bash tests/run_all.sh（check_states / check_evals / check_links）
legacy_exemption_keys: []
degrade_extra: 无
special_channels: 无
---

# review-once 适配要点

- ledger 条目六段式：日期 / 问题描述 / 表因与根因 / 处理方式（回填 PR 与 commit 链接）/ 后续防范（可检查规则而非叙述）/ 同类问题影响与注意事项（建教训谱系）。
- 收敛门纪律对本仓自身适用（RSI-006 先例）：「修改契约本身也必须过收敛门」。
