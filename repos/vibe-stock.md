---
key: vibe-stock
upstream: ThreeFish-AI/vibe-stock
default_branch: main
local_path: ~/Documents/projects/<本机实际仓目录>
adoption: pending
flipped_at: ""
skill_entry: SKILL.md
ledger: .temp/rsi/vibe-stock/backlog.md
entry_id: RSI-YYYYMMDD-NN
untrusted_sources: "目标业务仓库内容、行情/新闻等外部数据文本、Issue/PR 正文（含 blueprint 仓库 daily_stock_analysis）"
privacy_lexicon: "用户名、目标业务仓库名以外的私有上下文关键词、本机绝对/家目录路径形态（/Users/、/home/、~/ 前缀）"
sediment: "经验落 SKILL.md 路由壳与 references/ 规约文本、参考实现落 batch/、策略判据只动 strategies/*.yaml；规约句三属性（适用条件/做法/坑位）；产物类经验优先沉淀 SSOT 布局与一致性校验清单"
branch_style: "ThreeFish-AI/rsi-<slug>"
commit_convention: "feat|fix|docs|refactor|chore(changelog): 中文描述;"
pr_convention: "中文标题与正文；功能变更常规 PR、触碰红线不变量或裁决链语义一律 Draft；CHANGELOG 同批登记；base=main"
invariants: "指针→ThreeFish-AI/vibe-stock AGENTS.md：红线四条（不下单/敏感信息零落盘/RiskGuard 只降不升/门禁只收严-selftest 全绿）与『改一处规约须同步全部指针（判表/PIPELINE/README）』SSOT 纪律"
machine_checks: "uv run --no-project scripts/adjudicate.py --selftest && uv run --no-project scripts/diagnose.py --selftest && uv run --no-project scripts/postmortem.py --selftest && uv run --no-project scripts/lens.py --selftest"
legacy_exemption_keys: []
degrade_extra: 无
special_channels: 无
---

# vibe-stock 适配要点

- **金融红线（无条件全局规则）**：任何沉淀经验不得放宽 vibe-stock 红线四条（完整定义见 frontmatter invariants 指针→ThreeFish-AI/vibe-stock AGENTS.md）——带「允许升级 / 放宽判据」语义的候选即拒绝，不进入门禁核验。
- **批量层与裁决链分离**：批量诊股经验落编排层——参考实现落 `batch/`、策略判据只动 `strategies/*.yaml`；编排类经验不触碰 `scripts/` 裁决语义（验票 / 聚合 / RiskGuard 的行为变更须独立条目并过 selftest 破坏性实验）。
- **信号登记以 signals.json 为 SSOT**：信号与登记口径（register_signal、价格口径等）只动登记链 `~/.vibe-stock/signals.json`，报告与后验一律从其派生，不在报告层复制登记事实。
- **批量公平性口径**：批量诊股的中间 tier 运行禁 WebSearch 兜底——单票流程「关键情报块 fetch_failed 可兜底并降置信」的特权不外溢到批量段（防跨标的取证口径不对称污染横向比较）；兜底仅限单票深诊段。
