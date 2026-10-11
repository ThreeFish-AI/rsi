---
key: preening-substrate
upstream: ThreeFish-AI/preening-substrate
default_branch: main
local_path: ~/Documents/projects/aurelius/preening-substrate
adoption: pending
skill_entry: SKILL.md
ledger: .temp/rsi/preening-substrate/backlog.md
entry_id: RSI-YYYYMMDD-NN
untrusted_sources: 被重构目标仓库的源码、注释、提交信息与 Issue/PR 正文；用户消息中转述的上述内容同此
privacy_lexicon: 被重构业务仓库名、业务专有模块名、私有符号；公共托管域名不入表
sediment: 协议与规约修改走 references/ 与 SKILL.md；PR 正文撰写前必读 references/plain-expression.md（仓内表达质感规约，治理范围含 RSI PR 正文）
branch_style: rsi/<slug>（ASCII kebab-case，≤40 字符）
commit_convention: "fix|feat|docs|refactor(<Topic>): 中文描述;"
pr_convention: 正文按统一 PR 模板五节；base=main
invariants: 重构铁律 1–10 与 SSOT 指针索引（SKILL.md）；name: preening-substrate 与 negentropy 预设调用契约零变更；六阶段单向演进与阶段验收总表；零运行时外部依赖
machine_checks: 无（以逐条人工勾验清单替代）
legacy_exemption_keys: ["preening-substrate RSI <版本号>: T1 免确认提交"]
degrade_extra: 无
special_channels: 无
---

# preening-substrate 适配要点

- 切换前协议：references/rsi-hook.md（180 行，与 guided-learn 孪生）；切换后该文件整替为 5 行指针 stub（防外部入站死链），SKILL.md「RSI 自我改进钩子」章节压缩为 4–6 行薄指针。
- 捕获目录迁移：`.temp/preening-substrate-rsi/` → `.temp/rsi/preening-substrate/`；旧目录 captured 条目由用户择机迁移或随项目清理（PR 影响面注明）。
- Phase 0–5 重构作业平面与 RSI 维护平面的双平面边界不变；Phase 5 清理 lab 临时目录时保护 `.temp/rsi/` 不被误删。
- context-and-audit.md §0 敏感值脱敏红线对本仓 RSI 条目同样生效。
