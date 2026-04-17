# 项目约定

## 项目目标

1:1 复刻瑞典日报 Dagens Nyheter（DN.se）的前端站点。

## 部署约束

- 服务器：2 核 CPU、2GB 内存
- 日访问量：5 万以内
- 架构决策须在此约束下保证稳定运行

## 多角色协作

本项目使用四个 Agent 角色协作完成站点复刻：

- `/site-analyst` — 站点分析师：负责逆向分析 DN.se 的信息架构、页面模板、交互行为，以及项目分期规划
- `/visual-extractor` — 视觉还原师：负责从 DN.se 提取精确的设计系统和组件视觉规范
- `/content-engineer` — 内容工程师：负责内容数据建模、分类体系梳理和 mock 数据生成
- `/frontend-engineer` — 全栈工程师：负责部署架构设计、像素级前端实现，以及按需后端开发

## 协作流程

```
DN.se 站点
    ↓
[站点分析师] → analysis/site-map, page-templates, interaction-spec, project-phases
    ↓                         ↓                         ↓
[视觉还原师]              [内容工程师]              [全栈 Phase 0]
    ↓                         ↓                         ↓
design/                   content/                  tech/architecture
design-tokens             data-models               tech-notes
component-spec            content-spec              项目脚手架
layout-spec               src/data/
    ↓─────────────────────────↓─────────────────────────↓
                    [全栈工程师 Phase 1+]
                            ↓
                     src/ (前端+后端)

注：视觉还原师与内容工程师大部分并行，内容约束(字符限制等)串行等待视觉规范
注：全栈 Phase 0（架构决策）可与视觉/内容并行推进
```

## 目录约定

```
project/
├── .claude/agents/          — 角色定义文件
├── docs/
│   ├── analysis/            — 站点分析师产出
│   │   ├── site-map.md
│   │   ├── page-templates.md
│   │   ├── interaction-spec.md
│   │   ├── project-phases.md
│   │   └── screenshots/
│   ├── design/              — 视觉还原师产出
│   │   ├── design-tokens.md
│   │   ├── component-spec.md
│   │   ├── layout-spec.md
│   │   └── screenshots/
│   ├── content/             — 内容工程师产出
│   │   ├── data-models.md
│   │   └── content-spec.md
│   └── tech/                — 全栈工程师产出
│       ├── architecture.md
│       └── tech-notes.md
├── src/                     — 源代码
└── src/data/                — Mock 数据文件
```

## ID 命名约定

站点分析师负责为以下实体分配唯一 ID，所有角色统一引用：

| 实体类型 | 前缀 | 示例 |
|---------|------|------|
| 页面模板 | `TPL-` | `TPL-HOME`, `TPL-ARTICLE` |
| 组件 | `CMP-` | `CMP-HERO-CARD`, `CMP-NAV-TOP` |
| 交互行为 | `INT-` | `INT-STICKY-NAV`, `INT-CAROUSEL` |

## 关键规则

- 角色间通过 `docs/` 目录下的文件传递信息，每个角色只写入自己的子目录
- 有分歧时在自己的文档中标注，不要直接修改别人的产出
- 所有产出文档（`docs/` 目录下）的主语言必须是中文；组件 ID（`CMP-`）、模板 ID（`TPL-`）、交互 ID（`INT-`）等标识符及瑞典语原文（导航项、按钮文案）保持原样
- 1:1 复刻项目以"精确还原"为最高优先级，不要擅自优化或改进原站设计
- 各角色按 `docs/analysis/project-phases.md` 的阶段划分安排工作优先级

## 反馈标注与处理

各角色在工作中如发现问题，使用以下标注约定：

| 标注 | 使用者 | 含义 |
|------|--------|------|
| `[需确认]` | 站点分析师 | 无法完整观察的功能，需补充验证 |
| `[补充发现]` | 视觉还原师 | 站点分析师遗漏的组件或区块 |
| `[数据反馈]` | 内容工程师 | 内容结构与站点分析不一致 |
| `[技术反馈]` | 全栈工程师 | 规范无法实现或有性能问题 |
| `[未观察到]` | 视觉还原师 | 无法触发的组件状态 |

**处理流程**：
1. 发现方在自己的文档中添加标注，描述问题和建议
2. 责任方在下次工作时检索自己被引用的文档中是否有新标注
3. 责任方评估后在原标注下方追加 `[已处理]` + 处理说明，或在自己文档中更新
4. 无法达成一致的问题，升级为用户决策
