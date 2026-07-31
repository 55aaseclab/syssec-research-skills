# SysSec Research Skills

[English](README.md) | [简体中文](README.zh-CN.md)

这是一套面向系统安全研究的全生命周期 Skill 系统。不是把几篇论文、几条命
令、几个模板散着堆在一起，而是把系统安全科研拆成可路由、可交接、可复现、
可审计的研究操作系统。

从选题、文献、artifact intake、复现、系统分析、攻击或防御原型、实验评估、
论文写作，到投稿、rebuttal、artifact evaluation、披露与后续维护，整条链
路都在覆盖范围内。

**最新版本：v0.1.3**

**定位**：全生命周期系统安全科研编排系统

**当前原则**：

- 不预设具体项目、实验室、会议或工具链
- 不把猜测写成结论
- 不把一次跑通写成可复现
- 不把论文 claim 当作本地验证结果

---

## 更新日志

### v0.1.3（2026-07-31）

- **新增 workspace homepage workflow schema**：提供
  `workspace-prebuilt-workflows.json`，让 research workspace 首页可自动加
  载这套预置工作流
- **把 literature-review 纳入 homepage 预置工作流**：不再只存在于文档
  和 workflow catalog

### v0.1.2（2026-07-31）

- **新增 literature-review workflow**：把“做某个方向的文献综述/相关工作
  梳理”从 `paper-reproduction` 里分离出来，作为独立主路径
- **更新 Hub 路由触发器**：让 literature review 类型请求可以直接命中预
  设 workflow
- **补示例入口**：新增 `examples/literature-review.md`

### v0.1.1（2026-07-30）

- **补齐正式版本化**：新增 `VERSION`、`CHANGELOG.md` 与 git tag 发布节奏
- **补齐缺失阶段**：新增 `syssec-method-design` 与
  `syssec-post-submission`
- **补齐缺失模板**：把 research artifacts、评估 notes、写作 notes、披
  露 notes 和 post-submission notes 的模板补齐
- **补齐参考层与示例**：为 Hub、Supervisors 和关键阶段新增
  `references/`，并增加 root `examples/`
- **清理悬空引用**：关闭 README、workflow、Supervisor 中提到但仓库里不存
  在的文件或阶段缺口

### v0.1.0（2026-07-30）

- **初始化系统架构**：建立 `1 Hub + 4 Supervisor + 27 Worker` 的三层结构
- **建立协议层**：补齐 preamble、证据规则、复现规则、伦理与披露、降级规
  则、输出格式、handoff 契约、工作流目录、skill 目录
- **覆盖完整生命周期**：从 intake 一直到 post-submission 阶段
- **补齐核心模板**：research brief、threat model、artifact inventory、
  reproduction log、experiment matrix、claim-evidence map 等
- **预设 7 条研究工作流**：覆盖 idea-to-paper、paper-reproduction、
  literature-review、system-attack-study、defense-design-study、
  measurement-study、vuln-to-disclosure

---

## 版本化

这套系统从 `v0.1.1` 开始正式版本化：

- 当前版本以 `VERSION` 为准
- 人类可读变更记录在 `CHANGELOG.md`
- 发布节点通过 git tag 固化

---

## 系统架构

SysSec Research Skills 不是一堆散装研究 prompt，它是一个三层架构的系统
安全科研编排系统：

```text
L0  Hub          syssec-research ───── 系统入口 · 一级路由 · 工作流编排
                  │
L1  Supervisors   ├── syssec-foundation ───── 研究基建中枢
                  │     └─ intake / scope / survey / baseline / artifact-intake
                  │
                  ├── syssec-investigation ── 技术调查中枢
                  │     └─ target-understanding / method-design / reverse /
                  │        static / dynamic / fuzzing / exploit /
                  │        defense-prototype
                  │
                  ├── syssec-validation ───── 验证与评估中枢
                  │     └─ reproduction / experiment-design / evaluation /
                  │        performance / compatibility / statistics /
                  │        threats-validity
                  │
L2  Workers       └── syssec-publication ──── 论文与披露中枢
                        └─ synthesis / write / related-work / figures /
                           submission / rebuttal / disclosure /
                           artifact-eval / post-submission
```

### 三层是什么意思？

| 层级 | 角色 | 做什么 |
|:---|:---|:---|
| **L0 Hub** | `syssec-research` | 系统入口。识别当前研究阶段，选择工作流，路由到对应 Supervisor。 |
| **L1 Supervisor** | 4 个中枢 | 二级路由。接住 Hub 分下来的阶段任务，再派给具体 Worker，负责协同与回收结果。 |
| **L2 Worker** | 29 个执行引擎 | 干活的。每个 Worker 只解决一个明确研究问题，不混阶段，不越权扩写结论。 |

**关键规则**：Hub 不直接替代 Worker，Worker 不直接跨组乱跳。研究阶段切换
必须通过显式 handoff 完成。

---

## 工具箱

### 🔀 Hub（系统入口）

| 模块 | 做什么 |
|:---|:---|
| `syssec-research` | 主入口，负责阶段识别、工作流选择、Supervisor 路由、长期研究状态维护 |

### 🏗️ syssec-foundation — 研究基建中枢

| Worker | 做什么 |
|:---|:---|
| `syssec-intake` | 研究 intake。把模糊请求整理成 research brief、study type、deliverable |
| `syssec-scope` | 问题定义与 threat model。明确研究问题、假设、边界、成功标准 |
| `syssec-survey` | 相关工作梳理。分组已有工作、提炼比较维度、识别 gap |
| `syssec-baseline` | baseline 纪律。定义哪些系统、方法、设置必须比较，以及为什么比较公平 |
| `syssec-artifact-intake` | artifact 清点。整理代码、二进制、数据集、trace、环境依赖、缺失项 |

### 🔬 syssec-investigation — 技术调查中枢

| Worker | 做什么 |
|:---|:---|
| `syssec-target-understanding` | 目标系统理解。梳理架构、信任边界、攻击面、观测点 |
| `syssec-method-design` | 方法设计。把 threat model、目标系统理解和预期 claim 收束成可实现、可评估的方法方案 |
| `syssec-reverse` | 逆向分析。面向 binary、firmware、closed component 恢复结构和关键行为 |
| `syssec-static-analysis` | 静态分析。检查源码、配置、调用路径、边界检查、权限变化 |
| `syssec-dynamic-analysis` | 动态分析。用 trace、instrumentation、debugger 观察真实运行行为 |
| `syssec-fuzzing` | 模糊测试。设计 harness、oracle、seed、triage 路线 |
| `syssec-exploit` | PoC/利用验证。判断怀疑点是否真的可达、可触发、可造成影响 |
| `syssec-defense-prototype` | 防御原型。实现或约束化设计一个可被验证的防护机制 |

### 📏 syssec-validation — 验证与评估中枢

| Worker | 做什么 |
|:---|:---|
| `syssec-reproduction` | 复现已有工作。记录 exact/partial reproduction 状态和偏差原因 |
| `syssec-experiment-design` | 实验设计。明确变量、指标、baseline、trial、输出路径 |
| `syssec-evaluation` | 执行评估。跑实验矩阵、汇总原始结果、记录异常与失败 |
| `syssec-performance` | 性能评估。量化 overhead、tail behavior、资源成本和扩展性 |
| `syssec-compatibility` | 兼容性评估。检查 OS、版本、架构、部署模式的适配边界 |
| `syssec-statistics` | 统计解释。处理 variance、significance、underpowered comparison |
| `syssec-threats-validity` | 有效性威胁。梳理 internal / external / construct / measurement 风险 |

### 📝 syssec-publication — 论文与披露中枢

| Worker | 做什么 |
|:---|:---|
| `syssec-synthesis` | claim 收敛。把结果整理成带证据等级的 claim-evidence map |
| `syssec-write` | 论文写作。围绕已验证 claim 组织章节，而不是围绕愿望清单写故事 |
| `syssec-related-work` | 相关工作章节。把 survey 转成技术定位而不是 citation dump |
| `syssec-figures` | 图表规划。让每张图或表都服务一个明确 claim |
| `syssec-submission` | 投稿检查。检查稿件、附录、artifact、伦理和格式完整性 |
| `syssec-rebuttal` | rebuttal 编排。把 reviewer comment 映射到证据、补实验、修文 |
| `syssec-disclosure` | 负责任披露。控制公开边界、受影响版本、沟通时序 |
| `syssec-artifact-eval` | artifact evaluation。准备外部 reviewer 可重放的包和 replay checklist |
| `syssec-post-submission` | 投稿后维护。处理 camera-ready、artifact follow-up、release hygiene、后续维护承诺 |

---

## 工具路径图

### 路由逻辑

#### 一级路由（Hub → Supervisor）

| 用户意图 | 路由到 |
|:---|:---|
| 还没想清楚问题、要定 threat model、要梳理文献、要列 baseline、要盘 artifact | `syssec-foundation` |
| 要看系统架构、逆向、静态分析、动态分析、fuzz、做 PoC、做 defense prototype | `syssec-investigation` |
| 要复现、设计实验、跑评估、看性能、做兼容性、做统计、写 threats to validity | `syssec-validation` |
| 要收敛 claim、写论文、做图、准备投稿、写 rebuttal、处理 disclosure 或 artifact eval | `syssec-publication` |

#### 二级路由（Supervisor → Worker）

**syssec-foundation →**

| 意图信号 | Worker |
|:---|:---|
| 需求还很散、目标和交付不清楚 | `syssec-intake` |
| 研究问题、威胁模型、假设、边界 | `syssec-scope` |
| 相关工作、gap、相邻论文 | `syssec-survey` |
| baseline 选择、公平比较 | `syssec-baseline` |
| code / binary / dataset / trace / artifact 清点 | `syssec-artifact-intake` |

**syssec-investigation →**

| 意图信号 | Worker |
|:---|:---|
| 先弄清系统架构和攻击面 | `syssec-target-understanding` |
| 先把方法和 proof obligation 设计清楚 | `syssec-method-design` |
| 没源码，要啃 binary 或 firmware | `syssec-reverse` |
| 有源码，先看静态逻辑 | `syssec-static-analysis` |
| 需要 runtime 证据 | `syssec-dynamic-analysis` |
| 需要自动输入探索 | `syssec-fuzzing` |
| 需要验证 exploitability | `syssec-exploit` |
| 需要实现 mitigation / defense | `syssec-defense-prototype` |

**syssec-validation →**

| 意图信号 | Worker |
|:---|:---|
| 复现别人的 paper 或 artifact | `syssec-reproduction` |
| 先把实验矩阵设计清楚 | `syssec-experiment-design` |
| 开始跑实验和看结果 | `syssec-evaluation` |
| 关注 overhead 和 scalability | `syssec-performance` |
| 关注 OS / arch / deployment support | `syssec-compatibility` |
| 关注 variance 和显著性 | `syssec-statistics` |
| 关注 overclaim 和 validity | `syssec-threats-validity` |

**syssec-publication →**

| 意图信号 | Worker |
|:---|:---|
| 先把 claim 收住 | `syssec-synthesis` |
| 开始写正文 | `syssec-write` |
| 整理 related work | `syssec-related-work` |
| 规划图和表 | `syssec-figures` |
| 准备投稿包 | `syssec-submission` |
| 回 reviewer | `syssec-rebuttal` |
| 管披露边界 | `syssec-disclosure` |
| 准备 artifact eval | `syssec-artifact-eval` |
| 处理 camera-ready 和后续维护 | `syssec-post-submission` |

### 预设工作流

SysSec Research Skills 内置 7 个预设工作流，覆盖系统安全科研中最常见
的主路径：

| # | 工作流 | 适用场景 | 执行链路 |
|:--|:---|:---|:---|
| 1 | **idea-to-paper** | 从研究想法一路做到投稿 | intake → scope → survey → baseline → artifact-intake → method-design → prototype → evaluation → synthesis → writing → submission |
| 2 | **paper-reproduction** | 手上有论文，目标是复现和偏差审计 | intake → survey → artifact-intake → reproduction → experiment-design → evaluation → threats-validity → writing |
| 3 | **literature-review** | 做某个方向的系统安全文献综述、related work map、综述型写作 | intake → scope → survey → baseline → synthesis → related-work → write → submission |
| 4 | **system-attack-study** | 对一个系统做攻击面分析、PoC、评估、写作 | intake → scope → target-understanding → reverse/static → dynamic/fuzzing → exploit → evaluation → synthesis → writing → disclosure |
| 5 | **defense-design-study** | 设计并实现一个 defense，再评估安全性与代价 | intake → scope → survey → baseline → target-understanding → method-design → defense-prototype → evaluation → performance → compatibility → threats-validity → writing |
| 6 | **measurement-study** | 做系统安全测量、分类、趋势或对比研究 | intake → scope → survey → baseline → artifact-intake → experiment-design → evaluation → statistics → synthesis → writing |
| 7 | **vuln-to-disclosure** | 从发现问题一路走到验证、披露与发表边界控制 | intake → scope → target-understanding → static/dynamic → reproduction → exploit/defense → evaluation → disclosure → writing |

### 常见路径

```text
只有一个模糊想法
→ syssec-research
→ syssec-foundation
→ intake → scope → survey

有论文，想复现
→ syssec-research
→ syssec-validation
→ reproduction → experiment-design → evaluation

怀疑系统有洞，想验证
→ syssec-research
→ syssec-investigation
→ target-understanding → static/dynamic → exploit
→ syssec-validation → evaluation
→ syssec-publication → disclosure

结果已经有了，准备写 paper
→ syssec-research
→ syssec-publication
→ synthesis → figures → write → submission
```

### 跨组协同

模块之间默认按研究阶段协同，而不是各写各的：

- `foundation` 把 threat model、baseline、artifact inventory 准备好，再
  交给 `investigation`
- `investigation` 只负责建立技术事实和原型，不直接替 `validation` 宣布
  “已经证明”
- `validation` 把结果、代价、适配边界、validity 风险梳理清楚，再交给
  `publication`
- `publication` 只能消费已建立的证据，不能为了一篇好看的 paper 倒推结论

---

## 研究状态产物

这套系统默认维护一组长期研究产物，作为跨阶段的数据总线：

| 产物 | 作用 |
|:---|:---|
| `research-brief.md` | 记录研究目标、study type、deliverable、约束 |
| `questions-and-hypotheses.md` | 记录研究问题、假设、成功标准 |
| `threat-model.md` | 记录 adversary、资产、边界、假设、non-goals |
| `related-work-map.md` | 记录相关工作分组、比较维度、gap |
| `baseline-matrix.md` | 记录必须比较的 baseline 和比较公平性 |
| `artifact-inventory.md` | 记录代码、binary、dataset、trace、依赖、缺失项 |
| `reproduction-log.md` | 记录复现步骤、环境、偏差和未验证 claim |
| `system-notes.md` | 记录架构、组件、信任边界、攻击面 |
| `attack-surface-map.md` | 记录入口、边界、关键接口、可观察点 |
| `method-design.md` | 记录方法机制、proof obligation、实验绑定关系 |
| `prototype-notes.md` | 记录 PoC 或 defense prototype 的实现边界与失败尝试 |
| `experiment-matrix.md` | 记录变量、指标、baseline、trial 设计 |
| `findings-log.md` | 记录观察、证据等级、后续动作 |
| `results-summary.md` | 汇总实验结果和异常 |
| `performance-notes.md` | 记录 overhead、tail behavior、扩展性和资源成本 |
| `compatibility-notes.md` | 记录平台支持、部署边界和不兼容点 |
| `validity-notes.md` | 记录 internal / external / construct / measurement 风险 |
| `claim-evidence-map.md` | 把 claim 和证据源一一绑定 |
| `paper-outline.md` | 组织论文结构和章节骨架 |
| `figures-plan.md` | 记录图表、表格、caption 和所服务的 claim |
| `submission-checklist.md` | 检查稿件、artifact、伦理和格式 |
| `rebuttal-notes.md` | 记录 reviewer 问题、响应策略和补实验计划 |
| `disclosure-log.md` | 记录披露边界、版本、沟通时序 |
| `post-submission-notes.md` | 记录 camera-ready、artifact follow-up 和维护动作 |

对应模板放在 `templates/`。

---

## 协议层

所有 skill 在真正干活前，都要先加载 `_system/` 协议层：

| 文件 | 作用 |
|:---|:---|
| `preamble.md` | 先判当前研究阶段，再决定动作 |
| `evidence-rules.md` | 区分 verified、derived、inference、hypothesis、external claim |
| `reproducibility-rules.md` | 强制记录环境、命令、输入、输出、版本 |
| `ethics-and-disclosure.md` | 控制 live target、敏感数据、披露边界 |
| `degradation-rules.md` | 没有源码、artifact、权限、硬件时如何降级推进 |
| `output-format.md` | 强制把已证实和待验证分开写 |
| `handoff-contract.md` | 统一 DONE / NEEDS_CONTEXT / BLOCKED / OUT_OF_SCOPE 回交 |
| `workflow-catalog.md` | 预设工作流目录 |
| `skill-directory.md` | 全部 skill 的职责映射 |

---

## 参考层与示例

除了协议层，这套系统还补了两层辅助内容：

- `references/`
  放 Hub、Supervisors 和关键阶段的工作参考与 checklist
- `examples/`
  放常见研究路径的最小示例，帮助快速进入正确工作流

---

## 这套系统不预设什么

- 不预设你一定有源码
- 不预设你一定有 artifact 包
- 不预设论文 claim 一定能复现
- 不预设你一定能碰真实目标
- 不预设你只能做 exploit 研究，防御、测量、复现、写作都在覆盖范围
- 不预设固定会议、固定工具链、固定实验室流程

它唯一预设的是：系统安全科研必须把证据、边界、复现性和披露纪律说清楚。
