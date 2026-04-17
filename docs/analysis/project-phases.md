# DN.se 复刻 — 项目分期计划

> 创建日期：2026-04-17
> 基于对 https://www.dn.se 的站点分析

---

## 分期原则

项目按以下优先级划分阶段：

1. **用户体验核心路径**：典型访客的操作路径是什么？（浏览标题 → 阅读文章 → 栏目导航）
2. **内容丰富度**：补充更多内容类型和栏目，充实站点
3. **增强功能**：互动工具、个性化、多媒体内容
4. **边缘功能**：小众栏目、第三方集成、小型组件

每个阶段产出一个可用、可部署的增量版本。Phase 1-2 严格串行。Phase 0 可与分析/设计工作并行。Phase 3-4 可部分重叠。

---

## Phase 0 — 技术脚手架

**目标**：建立构建工具链、路由、部署流水线和基础布局框架，使 Phase 1 的编码工作可以立即开始。

**预估工期**：1-2 天

### 涉及模板
- 无（仅框架搭建）

### 核心组件
- 基础 HTML 外壳，包含 `<header>`、`<main>`、`<aside>`、`<footer>` 语义结构
- CSS 重置和基础排版设置
- 响应式网格系统（两栏：主内容 + 侧栏）
- 所有页面模板的路由定义

### 涉及交互
- 无

### 各角色交付物

| 角色 | 交付物 |
|------|--------|
| 全栈工程师 | `docs/tech/architecture.md` — 技术栈选型、构建工具配置、目录结构、部署配置 |
| 全栈工程师 | 项目脚手架：package.json、构建配置、开发服务器、基础路由 |
| 全栈工程师 | 基础布局组件（响应���两栏网格） |
| 全栈工程师 | 面向 2 核/2GB 服务器的 CI/CD 流水线搭建 |

### 依赖关系
- 可立即启动，与视觉/内容分析工作并行
- 必须在 Phase 1 编码开始前完成

---

## Phase 1 — 核心骨架

**目标**：访客可以进入首页、看到带图片的标题、点击进入阅读文章、在主要栏目间导航。站点初看之下外观和体验与 DN.se 一致。

**预估工期**：5-7 天

### 涉及模板
- `TPL-HOME`（首页 — 精简版，仅核心区域）
- `TPL-ARTICLE`（文章详情页，含付费墙）
- `TPL-CATEGORY`（栏目页 — 复用首页布局，按栏目过滤）

### 核心组件

| ID | 优先级 | 备注 |
|----|--------|------|
| `CMP-NAV-TOPBAR` | P1 | 产品链接栏，含 Prenumerera/Logga in 按钮 |
| `CMP-NAV-MAIN` | P1 | 水平主导航，包含所有栏目链接 |
| `CMP-NAV-SUB` | P1 | 随上下文变化的子导航 |
| `CMP-NAV-STICKY` | P1 | 导航吸顶滚动行为 |
| `CMP-CARD-HERO` | P1 | 焦点文章卡片（大图 + 标题） |
| `CMP-CARD-STANDARD` | P1 | 标准文章卡片（图片 + 标题 + 摘要） |
| `CMP-CARD-COMPACT` | P1 | 纯文字紧凑文章链接 |
| `CMP-BREAKING-BAR` | P1 | "Just nu:" 突发新闻项 |
| `CMP-SECTION-HEADER` | P1 | 版块分隔标题（红色左边框） |
| `CMP-LATEST-ARTICLES` | P1 | "Senaste artiklarna" 侧栏列表 |
| `CMP-ARTICLE-HEADER` | P1 | 文章页头部（分类 + 标题 + 时间戳） |
| `CMP-ARTICLE-HERO-IMAGE` | P1 | 文章首图 |
| `CMP-ARTICLE-BODY` | P1 | 文章正文内容 |
| `CMP-ARTICLE-BYLINE` | P1 | 作者署名 |
| `CMP-PAYWALL` | P1 | 付费墙（仅视觉效果，无支付集成） |
| `CMP-FOOTER` | P1 | 主页脚（含链接列） |
| `CMP-FOOTER-CREDITS` | P1 | 编辑团队和版权信息 |
| `CMP-AD-BANNER-TOP` | P1 | 广告占位符（空位 + "ANNONS" 标签） |
| `CMP-AD-SIDEBAR` | P1 | 侧栏广告占位符 |

### 涉及交互

| ID | 优先级 | 备注 |
|----|--------|------|
| `INT-STICKY-NAV` | P1 | 滚动时导航吸顶 |
| `INT-PAYWALL` | P1 | 文字渐隐 + 付费墙区块（视觉模拟，无真实认证） |
| `INT-NAV-MAIN-SCROLL` | P1 | 移动端视口下水平滚动 |

### 各角色交付物

| 角色 | 交付物 |
|------|--------|
| 视觉还原师 | 设计 Token（颜色、排版、间距） |
| 视觉还原师 | 所有 P1 组件的组件规范 |
| 视觉还原师 | 布局规范（网格比例、断点） |
| 内容工程师 | Article、Section、Author 数据模型 |
| 内容工程师 | Mock 数据：30-50 篇文章（覆盖各栏目）、5+ 位作者 |
| 全栈工程师 | 所有 P1 组件的代码实现 |
| 全栈工程师 | 三个页面模板可运行 |
| 全栈工程师 | 响应式布局在所有断点下正常工作 |

### 依赖关系
- 视觉规范和内容模型必须在全栈实现之前就绪
- 设计 Token 是首个需要的视觉交付物
- Mock 数据可与组件实现并行开发

---

## Phase 2 — 内容体系

**目标**：站点具备完整的导航深度。用户可以浏览专题、搜索文章、查看全站菜单、导航至所有内容栏目。内容生态系统基本完整。

**预估工期**：4-5 天

### 涉及模板
- `TPL-TOPIC`（专题/标签页）
- `TPL-SEARCH`（搜索页）
- `TPL-MENU`（全站菜单页）
- `TPL-DIREKT`（DN Direkt 实时新闻页）

### 核心组件

| ID | 优先级 | 备注 |
|----|--------|------|
| `CMP-TOPIC-HEADER` | P2 | 专题页头部（含关注按钮和描述） |
| `CMP-SEARCH-BOX` | P2 | 搜索输入框 |
| `CMP-SEARCH-FILTERS` | P2 | 搜索排序和过滤控件 |
| `CMP-SEARCH-POPULAR` | P2 | 热门搜索列表 |
| `CMP-SEARCH-ARCHIVE` | P2 | 档案 CTA 侧栏卡片 |
| `CMP-MENU-GRID` | P2 | 五列菜单链接网格 |
| `CMP-MENU-AZ` | P2 | 字母排序站点索引 |
| `CMP-MENU-SIDEBAR` | P2 | 菜单页服务图标侧栏 |
| `CMP-DIREKT-HERO` | P2 | DN Direkt 红色头图横幅 |
| `CMP-DIREKT-TIMELINE` | P2 | 带时间戳的新闻时间线 |
| `CMP-DIREKT-FILTERS` | P2 | 主题流过滤链接 |
| `CMP-DN-DIREKT-FEED` | P2 | 首页 DN Direkt 滚动条 |
| `CMP-CARD-SIDE-THUMB` | P2 | 侧缩略图文章卡片 |
| `CMP-ARTICLE-TOPICS` | P2 | 文章专题标签（带关注开关） |
| `CMP-ARTICLE-RELATED` | P2 | 相关文章区域 |
| `CMP-ARTICLE-TOOLS` | P2 | 打印/分享/纠错工具 |
| `CMP-ARTICLE-QUALITY` | P2 | 新闻品质声明 |
| `CMP-SECTION-HEADER-TOPIC` | P2 | 首页专题版块标题 |
| `CMP-SUBSCRIPTION-PROMO` | P2 | 订阅推广卡片 |
| `CMP-CONTACT-BLOCK` | P2 | 联系信息区块 |
| `CMP-FOOTER-TOOLS` | P2 | 版本切换和 Cookie 管理按钮 |

### 涉及交互

| ID | 优先级 | 备注 |
|----|--------|------|
| `INT-SEARCH` | P2 | 带过滤和结果展示的搜索 |
| `INT-DIREKT-TIMELINE` | P2 | 时间线展示（静态渲染，无实时更新） |
| `INT-TOPIC-FOLLOW` | P2 | 关注按钮切换（仅视觉效果） |
| `INT-NAV-SUB-SCROLL` | P2 | 子导航水平滚动 |
| `INT-BREAKING-NEWS` | P2 | 突发新闻条展示 |

### 各角色交付物

| 角色 | 交付物 |
|------|--------|
| 视觉还原师 | 所有 P2 组件的组件规范 |
| 内容工程师 | Topic、SearchResult、DirektItem 数据模型 |
| 内容工程师 | Mock 数据：专题页、搜索结果、Direkt 新闻流条目 |
| 内容工程师 | 内容分类体系：完整的栏目/专题层级映射 |
| 全栈工程师 | 四个新页面模板 |
| 全栈工程师 | 搜索功能（基于 Mock 数据的客户端搜索） |
| 全栈工程师 | 专题/标签系统 |

### 依赖关系
- Phase 1 必须完成（基础布局和核心组件）
- 搜索可使用客户端过滤 Mock 数据（无需后端搜索引擎）

---

## Phase 3 — 增强功能

**目标**：站点包含多媒体内容、互动功能和丰富的编辑格式。用户可以观看视频、浏览评论、查看轮播、体验 DN.se 完整的编辑丰富度。

**预估工期**：5-7 天

### 涉及模板
- `TPL-AUTHOR`（作者页）[需确认]

### 核心组件

| ID | 优先级 | 备注 |
|----|--------|------|
| `CMP-CAROUSEL-REVIEWS` | P3 | 评论水平轮播 |
| `CMP-CAROUSEL-INSANDARE` | P3 | 读者来信轮播 |
| `CMP-CAROUSEL-VIDEO` | P3 | 视频轮播 |
| `CMP-CARD-REVIEW` | P3 | 评论卡片（含分类标签） |
| `CMP-CARD-INSANDARE` | P3 | 读者来信卡片 |
| `CMP-CARD-VIDEO` | P3 | 视频缩略图卡片 |
| `CMP-AD-NATIVE` | P3 | 赞助/原生内容卡片 |
| `CMP-AD-INLINE` | P3 | 内嵌广告单元 |
| `CMP-FREE-ARTICLE-CTA` | P3 | 免费文章登录提示 |
| `CMP-ARTICLE-SAVE`（`CMP-ARTICLE-ACTIONS` 的一部分） | P3 | 文章收藏切换 |
| `CMP-ARTICLE-SHARE`（`CMP-ARTICLE-ACTIONS` 的一部分） | P3 | 文章分享按钮 |
| `CMP-SOCIAL-LINKS` | P3 | 社交媒体链接区块 |
| `CMP-NEWSLETTER-CTA` | P3 | 新闻通讯注册 CTA |
| `CMP-STREAMING-GUIDE` | P3 | 流媒体指南推广卡片 |
| `CMP-KROG-COMMISSION` | P3 | 餐厅评测卡片 |
| `CMP-KALENDARIET` | P3 | 活动日历卡片 |
| `CMP-FRAGA-INSIDAN` | P3 | 生活建议专栏侧栏 |
| `CMP-LATEST-CLIPS` | P3 | 最新视频侧栏 |
| `CMP-LATEST-QUIZ` | P3 | 最新问答侧栏 |

### 涉及交互

| ID | 优先级 | 备注 |
|----|--------|------|
| `INT-CAROUSEL` | P3 | 带上一组/下一组按钮的水平轮播 |
| `INT-VIDEO-PLAY` | P3 | 视频播放/暂停 |
| `INT-ARTICLE-SAVE` | P3 | 收藏切换（仅视觉状态） |
| `INT-ARTICLE-SHARE` | P3 | 分享对话框 |
| `INT-SUBSCRIPTION-POPUP` | P3 | 移动端订阅弹窗 |
| `INT-LOGIN-TOOLTIP` | P3 | 登录提示气泡 |
| `INT-LAZY-LOAD` | P3 | 图片懒加载（含 CDN 参数） |
| `INT-AD-SLOTS` | P3 | 广告位占位符 |

### 各角色交付物

| 角色 | 交付物 |
|------|--------|
| 视觉还原师 | 轮播、视频播放器、原生广告等的组件规范 |
| 内容工程师 | Video、Review、Insändare 数据模型 |
| 内容工程师 | Mock 数据：视频、评论、读者来信、问答 |
| 全栈工程师 | 轮播组件（可复用于评论、来信、视频） |
| 全栈工程师 | 视频播放器集成（占位符/嵌入） |
| 全栈工程师 | 原生广告卡片样式 |
| 全栈工程师 | 所有侧栏组件 |

### 依赖关系
- Phase 2 必须完成（完整内容体系）
- 轮播是一个可复用的通用组件，供多种卡片类型使用

---

## Phase 4 — 边缘功能与打磨

**目标**：站点包含所有剩余功能：游戏、问答、e-DN 组件、漫画、特色推广卡片及所有小型组件。复刻在功能上基本完整。

**预估工期**：4-6 天

### 涉及模板
- `TPL-GAME`（游戏页 — 填字、数独、问答等）

### 核心组件

| ID | 优先级 | 备注 |
|----|--------|------|
| `CMP-GAMES-GRID` | P4 | 游戏版块（游戏卡片网格） |
| `CMP-CARD-GAME` | P4 | 单个游戏卡片 |
| `CMP-CARD-QUIZ` | P4 | 问答列表项卡片 |
| `CMP-CARD-MOTOR` | P4 | 汽车栏目列表项 |
| `CMP-COMICS` | P4 | 漫画连载区域 |
| `CMP-EDN-WIDGET` | P4 | e-DN 报纸预览组件 |
| `CMP-ARCHIVE-CTA` | P4 | 档案搜索 CTA |
| `CMP-NUTIDSORIENTERING` | P4 | 学校测验推广 |
| `CMP-BIKE-CTA` | P4 | DN 自行车推广 |
| `CMP-CLIMATE-DASHBOARD` | P4 | 气候数据仪表盘 CTA |
| `CMP-TIPSA-CTA` | P4 | 线索提交 CTA 卡片 |

### 涉及交互

| ID | 优先级 | 备注 |
|----|--------|------|
| `INT-COOKIE-CONSENT` | P4 | Cookie 管理对话框 |
| `INT-VERSION-TOGGLE` | P4 | 移动/平板版本切换 |

### 各角色交付物

| 角色 | 交付物 |
|------|--------|
| 视觉还原师 | 游戏、漫画、e-DN 组件的组件规范 |
| 内容工程师 | Mock 数据：问答题目、游戏占位内容 |
| 全栈工程师 | 游戏版块网格布局 |
| 全栈工程师 | e-DN 组件（含报纸预览图） |
| 全栈工程师 | 所有剩余推广/CTA 卡片 |
| 全栈工程师 | Cookie 同意集成 |
| 全栈工程师 | 最终打磨和跨浏览器测试 |

### 依赖关系
- Phase 3 应基本完成
- 游戏页可能使用占位内容/iframe 嵌入，而非完全重建
- 漫画区域可使用静态图片

---

## 阶段依赖关系图

```
Phase 0（脚手架）
    |
    v
Phase 1（核心骨架）──────────────────> Phase 2（内容体系）
                                            |
                                            v
                                      Phase 3（增强功能）
                                            |
                                            v
                                      Phase 4（边缘功能）
```

**阶段内并行工作：**

```
Phase 0:
  [全栈：脚手架搭建] ─────────────────────>

Phase 1:
  [视觉：设计 Token + P1 组件规范] ──>
  [内容：数据模型 + Mock 数据] ──>
                                    [全栈：P1 实现] ──>

Phase 2:
  [视觉：P2 组件规范] ──>
  [内容：P2 模型 + 数据] ──>
                           [全栈：P2 实现] ──>

Phase 3:
  [视觉：P3 组件规范] ──>
  [内容：P3 数据] ──>
                      [全栈：P3 实现] ──>

Phase 4:
  [所有角色：最终组件 + 打磨] ──>
```

---

## 各阶段实体统计

| 阶段 | 模板 | 组件 | 交互 |
|------|------|------|------|
| 0 | 0 | 0（仅框架） | 0 |
| 1 | 3（TPL-HOME、TPL-ARTICLE、TPL-CATEGORY） | 18 | 3 |
| 2 | 4（TPL-TOPIC、TPL-SEARCH、TPL-MENU、TPL-DIREKT） | 21 | 5 |
| 3 | 1（TPL-AUTHOR） | 19 | 8 |
| 4 | 1（TPL-GAME） | 11 | 2 |
| **合计** | **9** | **69** | **18** |

---

## 风险提示

1. **服务器约束（2 核、2GB 内存）**：必须使用轻量级技术栈。重度 Node.js SSR 渲染可能存在风险。建议考虑静态生成或轻量级服务端渲染方案。

2. **付费墙集成**：DN.se 实际使用 Klarna + Bonnier News 认证体系。我们的复刻将仅在视觉上模拟付费墙，不集成真实支付/认证。

3. **DN Direkt 实时流**：实时更新需要 WebSocket 或轮询基础设施。Phase 2 使用静态 Mock 数据，实时更新可作为后续增强。

4. **游戏/互动工具**：填字游戏、数独、问答引擎都是复杂的独立应用。建议嵌入占位内容或链接到外部资源，而非完全重建。

5. **广告系统**：真实广告使用复杂的 Header Bidding 和广告服务器集成。我们的复刻使用静态 "ANNONS" 占位广告位。

6. **移动端版本**：DN.se 在所有断点下似乎提供相同的响应式页面（非独立移动站点），但移动端会强势弹出订阅弹窗。该弹窗为模态对话框，可能干扰 UX 测试。

7. **图片 CDN**：DN.se 使用 `static.bonniernews.se` 及其复杂的图片变换参数。我们的复刻需要使用本地图片配合 CSS 响应式尺寸方案。
