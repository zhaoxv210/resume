# 赵德明

**C#/.NET 全栈开发工程师（桌面端 + 后端）**

【手机号】 | 【个人邮箱】 | 【城市】 | GitHub: zhaoxv210

---

## 个人概述

1.5 年 VOIP 语音批发/国际路由计费系统开发经验，独立负责一套综合运维平台的端到端交付。桌面端（WinForms + WebView2）第一贡献者，累计非 merge 提交 1859 次；后端（ASP.NET Core 8 + Quartz）承担定时作业、话单采集与质量分析模块，非 merge 提交 195 次。熟悉多数据源（SQL Server / MySQL / PostgreSQL）跨库同步、Quartz 作业治理、NPOI Excel 导出、OA/E9 SOAP 工作流集成，近期完成 AI 助手与 NOC 排障技能包落地。

---

## 技术栈

- **语言与框架：** C# · .NET Framework 4.8 WinForms · ASP.NET Core 8 Web API · EF Core 8（SqlServer / Pomelo MySQL / Npgsql）· Quartz 3.14 Extensions.Hosting
- **前端与桌面：** WebView2（HTML/JS/CSS 混合界面）· AdvancedDataGridView · ReportViewer · 全局异常兜底与 CrashLog
- **办公与集成：** NPOI 2.5.6 · SSH.NET · Exchange EWS · OA / E9 Workflow SOAP · HtmlAgilityPack
- **AI 与语音：** Microsoft.Extensions.AI + OpenAI · ONNX Runtime · Whisper.net · 自定义 Agent Skill 技能包
- **日志与监控：** log4net · Job 独立日志（按类名分组、48h 自动清理）· Job 维度内存监控与告警
- **部署与发布：** ClickOnce + FTP 分发（版本号 ~4.8k）· Windows 服务自托管 · Swashbuckle Swagger

---

## 项目经历

### SynthesisTool —— 综合运维平台桌面管理工具（.NET Framework 4.8 WinForms）
*2025.05 – 至今 | 桌面端第一贡献者（非 merge 1859 次）*

- **运营商产品与路由配置体系（从零搭建）：** 实现运营商产品分组、号码长度与显示规则配置、路由重指（含超长校验），通过定时任务处理"未来生效的路由切换"；后期将分组级不通判定、无网关行置灰与跳转约束收敛为可核对口径，减少误操作。
- **问题看板（WebView2 动态可配置）：** 自主设计并实现看板模块，混线问题按当天数据展示，支持一键发起到 OA 的处理流程；后续清理被 WebView2 取代的废弃 WinForms 控件，完成从原生控件到内嵌页面的架构迁移。
- **连接质量分析（ConnectionAnalysis）：** 新增后拨号延迟（PDD）指标统计与展示；修复交叉查询与分组模式下排序混乱问题；在 SQL Server 严格 GROUP BY 下用 MAX 包裹字段做兼容，完成 ASR / ACD / 分组多维度口径对齐。
- **CDR 质量与风险分析：** 优化根因检测逻辑，重点提升"客户切流"场景识别准确度——区分线路故障与客户侧流量迁移，避免误判导致的错误处置；配合阈值告警机制输出可执行结论。
- **AI 智能助手与 NOC 排障技能包：** 在桌面端新增 AI 助手模块，将任务管理与对话结合；编写 VOIP NOC 排障技能包，使"某路由 ASR 低"等问题可按标准流程自动分析，而非仅翻译错误码。
- **轮选价格管理与自动变价：** 实现轮选变价定时任务与每周一自动解锁任务，补上 JOB 监控维度，解决变价作业执行情况不可观测的问题。
- **客户单指与费率申请 OA 打通：** 客户单指申请页支持按国家 code 反查运营商并反选；费率核查页同时比对待变表、费率变更表与轮选表；修复 OA 工作流单据解析逻辑，审批数据自动落库。

### SynthesisServer —— 综合运维平台后端 API 服务（ASP.NET Core 8）
*2025.06 – 至今 | 非 merge 提交 195 次（全仓第 4）*

- **IDR / IVR / CDR 话单数据采集与跨库同步：** 新增 IDR 数据采集任务、IVR 自动拉取（带翻译）、CDR 拉取至 SQL Server 定时任务，以及采集文件的删除与重跑管理；处理 SQL Server / MySQL / PostgreSQL 三数据源之间的数据搬运与一致性。
- **运营商 A→Z 自动化测试作业（OperatorTestJob）：** 支持按目的地方向批量拨测并回收结果，增加断电/异常后的重试续跑能力；引入"锁定操作人"机制避免多人并发触发同一测试任务造成冲突，逐轮收紧测试量与正显规则的边界条件。
- **Quartz 作业基建治理：** 参与 30+ 个定时作业的开发与维护，包括动态实例化与手动触发、按 Job 类名分组的独立日志（48h 自动清理）、Job 维度内存监控与告警；移除已注释的 CDR 同步到 SQL Server 的死任务配置。

---

## 量化产出

| 指标 | 数据 |
|---|---|
| 在职周期 | 2025.05.20 – 至今（约 17 个月） |
| 总提交 | 2620 次（桌面端 2333 / 后端 287），非 merge 2055 次 |
| 代码量级 | 约 +24.2 万行 / −10.9 万行（剔除 bin/obj/publish 与依赖噪音） |
| 桌面端排名 | 第一贡献者（非 merge 1859 次，第二名 1016 次） |
| 峰值产出 | 单月 223 次提交（2025.11） |
| 发布频次 | 桌面端 ClickOnce 累计约 600 次发版，版本号 ~4.8k |

---

## 说明

本简历内容依据两个内部仓库（SynthesisServer / SynthesisTool）的完整 git 提交记录整理，已做脱敏处理：不含运营商与客户端名称、内部表名、路由编号、内网地址与内部域名。如需核验具体实现，可约时间现场演示代码结构。
