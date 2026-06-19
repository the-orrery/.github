---
description: "the-orrery 工具命名规约:三线分类(天文/文书/植物)+ 名册 + 立规 + 决策日志;贴切优先于主题纯度,新工具命名或重命名按此定名。"
keywords: [the-orrery, 命名规约, naming-convention, tool-naming, registrar, gnomon, 贴切优先, 套件命名]
kind: spec
code: [the-orrery/profile/README.md]
---

# the-orrery 命名规约

套件工具名走「**evocative 单词、贴切优先、三线并存**」——不是单一天文主题。新工具命名或重命名按本规约定名;名册随套件演进就地更新(本篇是活契约,非冻结 ADR)。

## 1. 三线分类法

| 线 | 隐喻 | 成员 |
|---|---|---|
| 天文 / 导航 / 指引 | 天体、航海仪器、灯塔 | orrery(伞), crux(南十字座 + 「关键点」双关), sextant, lodestar, pharos, gnomon |
| 文书 / 记录(clerk's office) | 案卷、誊写、登记册 | docket, scribe, registrar |
| 植物 / 生长 | 根茎网、种子 | rhizome, seed |
| 外来经典概念(标志性,离主题但保留) | — | memex(Bush 1945), rhizome(德勒兹;同时归植物线) |

memex / rhizome 是套件里最好记的两个名,不因主题不纯而改。

## 2. 名册

| 名字 | 线 | 职责 | 层 |
|---|---|---|---|
| orrery | 天文 | 套件 umbrella(org 名 the-orrery) | — |
| crux | 天文 | LLM-facing 统一入口,git 式 dispatch | 收口 |
| rhizome | 植物 | 去中心 KB authoring CLI + 内容仓 | 内容 |
| memex | 外来 | 在 rhizome 上的混合检索引擎 | 引擎 |
| docket | 文书 | local-first PM CLI | 内容 |
| seed | 植物 | Python 仓脚手架(Copier + uv) | 写作 / 脚手架 |
| doc-skills | 描述式 | doc-write / doc-xray 写作 skills 包 | 写作 |
| sextant | 天文 | local-first 投资推理 CLI | 垂直应用 |
| scribe | 文书 | 离线语音听写 | 垂直应用 |
| pharos | 天文 | 本机健康 / 告警 ledger(东西「跑得好不好」) | 治理·可观测 |
| registrar | 文书 | 工作区资源 registry + 生命周期 / 归属门禁控制面(东西「存不存在、归谁、能不能安全删」) | 治理·可观测 |
| gnomon | 天文 | 每次调用的 telemetry 度量核心(共享库) | 底座 |

### 不在发布命名范围内
- **gnomon**(原 orrery-telemetry):rename 已完成(2026-06-19)—— 远端 `the-orrery/gnomon`、tag `v0.3.0`、7 个 dependent 已迁移测试通过。现为 registry 正式成员(见上表),此条仅留迁移留痕。
- **rerank-bench**:临时、不开源、召回层评测工具。保持描述式,不进套件命名、不改名。
- **lodestar**:对外可见性 / 作品集 KB 内容线(无 CLI),不是发布工具;名字虽属天文线,但归属是内容仓不是工具。

## 3. 立规

1. **贴切优先于主题纯度**。名字先精确描述职责,再谈主题归属;三线并存合法,不强行收成单一天文主题(那要改 docket / scribe,且 memex / rhizome 不能动)。
2. **现有 headline 名冻结**:crux / rhizome / memex / docket / seed / sextant / scribe / pharos 不再改名。
3. **子件默认描述式**:非 headline 的子件 / skills 包(doc-skills、rerank-bench)保持描述式名,除非有真贴切的单词才升级。
4. **控制面工具要和动词子命令读得通**:名字 + action 子命令要自然(`registrar relocate / closeout` ✓)。
5. **天文线已满(6+),新增谨慎**:再加天文名前先确认它没有「只覆盖语义一半」(ephemeris 教训)。

## 4. 决策日志(一次性拍板,留因由)

**2026-06-19**

- **registrar 采纳 / ephemeris 否决**(工作区控制面)。registrar 语义全覆盖 registry + 归属 + finalizer 门禁 + 注销,且与动词子命令搭配自然(`registrar closeout` ✓);ephemeris(天体位置表)主题最押韵 orrery,但只描述工具的 `status` / 观测半边,`ephemeris closeout` 读不通,且天文线已满。落文书线,与 docket / scribe 成「clerk's office」三件套,顺带补平命名分布(原天文 5、文书 2)。
- **gnomon 采纳**(orrery-telemetry 升级名)。日晷投影杆 = 负责「度量」的元件:天文仪器线、语义精确(每次调用的度量核心)。代价 = 丢「orrery- 命名空间」的归属信号,但 memex / crux 同样无前缀照样归属清楚,代价小。
- **rerank-bench 移出命名范围**。临时、不开源、召回层评测工具,保持描述式。
- **主题策略拍板**:保持「贴切优先、三线并存」,现有 headline 名一个不动。

## 5. 待办

- [x] **orrery-telemetry → gnomon 机械改名**(2026-06-19 完成):仓+包改名、远端 repo rename、tag `v0.3.0`、7 dependent(crux/docket/memex/pharos/ali-sls/almanac/ali-ops)的 pyproject+import+`uv lock` 迁移、测试全通过、ops/docs 引用更新。
- [ ] **suite 级 ADR 归属**:`rhizome/decisions/adr-033`(orrery-telemetry schema)、`adr-034`(.github ruff canonical config)是套件级决策却住在 rhizome。若以本 the-orrery 源为套件决策 canonical 家,考虑迁来;否则保持现状(轻微分叉)。先记着,待 principal 定。
- [ ] **workbench doc 文件名**:`eridanus-ops/docs/local-agent-workbench-registry-v0.md` 可改 `registrar-v0.md`,但有下游设计文档反向链接,改名要同步修链接,暂缓。
