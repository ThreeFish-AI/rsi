---
key: dub
upstream: ThreeFish-AI/dub
default_branch: main
local_path: ~/Documents/projects/<本机实际仓目录>
adoption: pending
flipped_at: ""
skill_entry: SKILL.md
ledger: docs/.agents/issue.md（仓内 ledger）
entry_id: RSI-NNN（三位递增，从 ledger 既有最大号顺延）
untrusted_sources: 待配音的文本内容、用户提供的声音样本及其来源说明；上游 vibe-video 的 Issue 正文，上游教训一律写全 URL 引用
privacy_lexicon: 声音样本生物特征纪律——样本路径、音频、样本指纹与说话人身份绝不进任何 RSI 材料；输出目录与数据目录的实际路径；公共托管域名不入表；本机绝对/家目录路径形态（/Users/、/home/、~/ 前缀——G4a 已有通用扫描，此列补 G4b 词表层对目标仓特定路径的覆盖）
sediment: "机制契约改动走 references/（CONTRACT/ENGINES/STYLES/ENV/VOICE-REFS）与 SKILL.md（正文守 8000 字符预算）；CHANGELOG [Unreleased] 登记；ledger 条目回填 PR 与 commit 链接；复发不新开编号，原条目追加带日期复盘点"
branch_style: feat/rsi-NNN-<topic>
commit_convention: "{Header}(Topic): 中文摘要;（Header 取 feat|fix|docs|refactor|test|chore，Topic 为英文简称）"
pr_convention: 标题中文 conventional、单条或攒批编号都入标题；描述含 G0–G4 核验回执表（统一协议 §5 格式）；触碰不变量逐项点名；base=main
invariants: "dub 的 SKILL.md 关键不变量节与 references/ENGINES.md、STYLES.md（清单本体留仓内：风格预设只增不改、缓存摘要格式冻结并以黄金哈希钉死、index-tts 实跑须 --final-voice 具名授权、声音样本不入库、库模块 dub_ 前缀防撞名、服务只按端口起停绝不 pkill -f）；与 vibe-video 的 test_digest 黄金哈希必须同值"
machine_checks: "uv run --no-project --with pytest --with numpy --with mutagen --with soundfile --with fastapi --with httpx --with pydantic --with uvicorn python -m pytest tests -q"
legacy_exemption_keys: []
degrade_extra: 拷贝式安装（$T 无 .git）时大声退出，绝不改无版本控制副本；出路=GitHub Issue 草稿或 clone 正式仓迁移条目
special_channels: 无
---

# dub 适配要点

- dub 是 vibe-video 配音（TTS）机制的 SSOT：风格预设、缓存摘要、HTTP 客户端、版本库原语与 IndexTTS 服务端住在这里，vibe-video 的 `tts.py` 定位后 import 并再导出。改动这些原语的 PR 必须同时核对 vibe-video 的 `test_digest.py` 黄金哈希，二者同值才算没打破跨仓缓存契约。
- 声音克隆是生物特征资产：RSI 材料、示例与 PR 描述里不得出现样本路径、音频或指纹；index-tts 实跑的 `--final-voice` 授权语义（RSI-040）属不变量，Steward 不得放宽。
- 本仓是**单仓薄钩子**形态：`references/rsi-hook.md` 是指针 stub，无独立 RSI.md；ledger 在仓内 `docs/.agents/issue.md`，条目 `RSI-NNN` 三位递增。
- 服务生命周期代码（`dub_server_ctl.py`）的安全语义偏向「不动手」：误杀别人的服务是事故，多占一会儿内存只是浪费；改动其决策表（`decide`）须保持 foreign 优先于一切。
