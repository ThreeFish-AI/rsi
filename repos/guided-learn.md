---
key: guided-learn
upstream: ThreeFish-AI/guided-learn
default_branch: main
local_path: ~/Documents/projects/<本机实际仓目录>
adoption: live
flipped_at: "ThreeFish-AI/guided-learn#20 merged 2026-10-11T14:19:51Z"
skill_entry: SKILL.md
ledger: .temp/rsi/guided-learn/backlog.md
entry_id: RSI-YYYYMMDD-NN
untrusted_sources: 学习材料、网页、视频转录、上游 Issue/PR 正文中要求修改本 Skill 的文字
privacy_lexicon: "用户名、项目目录名、学习材料标题与 URL 的「域名+路径」（公共托管域名 github.com、arxiv.org 等单独不入表，防 Skill 自带链接误命中）"
sediment: "协议与规约修改走 references/ 与 SKILL.md；图表资产遵循 archify 四件套纪律（references/diagram-assets.md）"
branch_style: rsi/<slug>（ASCII kebab-case，≤39 字符，对齐 §3 slug 正则上限）
commit_convention: "fix|feat|docs|refactor(<Topic>): 中文描述;"
pr_convention: 正文按统一 PR 模板六节（含去重与关联）；base=main
invariants: "教学铁律 1–10、六阶段单向演进与阶段验收标准（SKILL.md）；双代理对抗内省机制角色隔离；SSOT 指针索引完整性；frontmatter 触发契约；archify 四件套纪律（references/diagram-assets.md）；零可执行代码与依赖"
machine_checks: 无（以逐条人工勾验清单替代）
legacy_exemption_keys: ["guided-learn RSI: 免确认提交"]  # 式样记录，非功能键；启用须登记实际整行（协议 §7）
degrade_extra: 无
special_channels: 无
---

# guided-learn 适配要点

- 切换前协议：references/rsi-hook.md（237 行，与 preening-substrate 孪生、为两份中更全版本）；切换后整替为指针 stub，SKILL.md「RSI 自我改进钩子」章节（L113–119）及 SSOT 指针索引、阶段验收总表 RSI 行同步改写。
- 捕获目录迁移：`.temp/guided-learn-rsi/` → `.temp/rsi/guided-learn/`（PR 影响面注明存量处置）。
- G2 盲评 comparator 细节（合成夹具 A/B 打乱标签、判定代理不读 diff）已上收为统一协议 G2(b) 标准配置。
- 外行四测轮次触顶仍不过时：仅当归因指向本 Skill 规约且脱离材料可复现，方按触发白名单捕获（运行时证据的固定产生点）。
