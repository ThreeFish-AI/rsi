# rsi

> 统一 RSI（Recursive Self-Improvement）经验沉淀回路 —— Single Source of Truth

把使用 ThreeFish-AI 自研 skill 与规范体系过程中发现的改进经验，经统一协议沉淀回对应维护仓库：**登记 ledger → 隔离 clone → G0–G4 门禁核验 → PR 回流 → PR 后上下文自动审阅与摘要 → 人工决策合并**。

## 为什么

此前 4 个注册仓（preening-substrate、guided-learn、review-once、vibe-video）各自实现了 RSI 机制：`preening-substrate` 与 `guided-learn` 的 rsi-hook 协议是孪生拷贝（机制改进需逐仓修改的 Split-Brain），`review-once` 的 ledger 无运行时 Hook（沉淀全靠人工显式驱动），且每次沉淀后需人工切到目标仓上下文反复 Review-Fix。本仓库把**机制**收归一处（协议、门禁、三份子代理底稿、5+1 适配档案），把**仓内事实**留在各仓（不变量清单、ledger、特殊通道），并以 Context-Reviewer 回路把 PR 后的第一轮上下文审阅自动化。

## 仓库结构

| 路径 | 职责 |
| :--- | :--- |
| [SKILL.md](SKILL.md) | 入口：触发契约摘要、注册仓库路由表（adoption 状态）、最小流程、硬禁令 |
| [references/protocol.md](references/protocol.md) | 统一协议 SSOT：白名单、状态机六态、G0–G4、T1/T2/T3、限流背压、确认与豁免、降级矩阵、PR 模板、失败出路 |
| [references/steward.md](references/steward.md) | Steward 子代理底稿（实施侧） |
| [references/verifier.md](references/verifier.md) | Verifier 子代理底稿（核验侧） |
| [references/context-reviewer.md](references/context-reviewer.md) | Context-Reviewer 子代理底稿（PR 后八镜头审阅、修复白名单内小修、摘要回执） |
| [repos/](repos/) | 适配层：每仓一份档案（upstream、ledger、沉淀格式、分支/commit 约定、不变量**指针**、机器执法命令、adoption 状态等；全部字段见[协议附录B](references/protocol.md#附录b-适配档案字段)） |
| [evals/trigger-evals.json](evals/trigger-evals.json) | 触发边界正负例（改动 SKILL.md description 须同批过评测） |
| [CHANGELOG.md](CHANGELOG.md) | 变更登记（Keep a Changelog 格式；[Unreleased] 同批登记义务见 [repos/rsi.md](repos/rsi.md) pr_convention） |
| LICENSE | MIT License |

## 注册仓库与切换状态

| repo-key | 上游 | adoption |
| :--- | :--- | :--- |
| rsi（自举） | ThreeFish-AI/rsi | live |
| agents.md | ThreeFish-AI/agents.md | live |
| preening-substrate | ThreeFish-AI/preening-substrate | live |
| guided-learn | ThreeFish-AI/guided-learn | live |
| vibe-video | ThreeFish-AI/vibe-video | live |
| review-once | ThreeFish-AI/review-once | live |

`pending` = 该仓切换 PR 合并前，仍按仓内既有 RSI 流程运行；合并后置 `live`，SSOT 原子翻转。切换 PR 已合并、flip PR 未落的窗口内仍为 `pending`，此时按协议直接派发、不退回仓内流程（防环形指引）。

## 安装

```bash
mkdir -p ~/projects ~/.claude/skills ~/.agents/skills
git clone git@github.com:ThreeFish-AI/rsi.git ~/projects/rsi
ln -sfn ~/projects/rsi ~/.claude/skills/rsi   # Claude Code
ln -sfn ~/projects/rsi ~/.agents/skills/rsi   # Codex 等其他 agent CLI
```

目标路径（如 `~/.claude/skills/rsi`）已是实体目录时，先迁移其内容再建 symlink。

单一检出多端共享（symlink 安装，仓库变更后全局实时生效）。

## 使用

在任意项目中使用注册仓库的 skill/规约时，发现其自身缺陷或可沉淀经验 → 直接对 Claude 说（或 Agent 自行识别）→ rsi skill 捕获入账 → 交付后自动走完整回路。授权豁免文法三档：`rsi <repo-key>[@<版本号>]: T1 免确认提交 | 免确认提交 | 关闭`——`T1 免确认提交` 仅 T1 分级免确认；`免确认提交`（裸档，不带 T1 限定）= 该仓全部分级免确认，建议仅短期使用并带版本号；`关闭` 只登记来源①条目、不派发。豁免行按整行精确匹配，仅认用户亲手写入且不被分发覆盖的用户级全局指令文件（sync / 分发机制产物一律不认，详见[协议 §7](references/protocol.md#7-确认与提交)）。

## 约束

零可执行运行时代码（协议级 Hook，宿主通用）；G 门禁只增不减；适配档案只放指针与参数，不变量清单复述即违规；MIT License。
