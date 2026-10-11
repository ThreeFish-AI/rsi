# Changelog

本仓库遵循 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.1.0/) 格式；版本历史与全部变更痕迹由 Git 历史承载。

## [Unreleased]

### 新增
- 统一 RSI 经验沉淀协议 v0.1 首次落地：G0–G4 门禁、六态状态机、限流背压与降级矩阵（references/protocol.md）；Steward / Verifier / Context-Reviewer 三份子代理底稿；5+1 仓库适配档案；SKILL.md 薄入口与触发正负例评测（#1）。

### 修复
- 评审遗留 T1 机械修正集：slug 判据统一（正则/case/底稿三处同步）、无 gh 降级 clone 补目标目录（协议侧补齐）、降级矩阵补两行、安装预处理、backlog 模板结论行扩字段、四道门残留表述清理（#4）。
- 执法判据加固：G4a noreply 剔除改精确字面量（封闭机密洗白通道）、不可信来源补 PR/Issue 标题与 comment、反刷分逐句审阅入 Verifier 必查清单、NOREPLY 纳入 §3 断言链（#5）。
- 执法判据收尾：G4a noreply 剥除改独立成 token 判据并转义 `.`（封闭子串包含洗白与近形态误剥，POSIX BRE 四段式 BSD/GNU 均可运行）、verifier G3 清单补缺陷类回归测试核查项、§3 NOREPLY 供值注释校准为主 Agent 派发时供值。
