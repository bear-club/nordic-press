# DN.se 页面模板定义

> 分析日期：2026-04-17
> 来源：https://www.dn.se

---

## 组件主清单

站点中识别到的所有组件，附有唯一 ID 供跨文档引用。

### 导航与头部组件

| ID | 名称 | 说明 |
|----|------|------|
| `CMP-NAV-TOPBAR` | 顶部工具栏/产品链接 | 窄条，包含 E-DN、ARKIVET、KORSORD、KUNDSERVICE、QUIZ、ERBJUDANDEN + Prenumerera/Logga in 按钮 |
| `CMP-NAV-MAIN` | 主导航 | 水平导航栏，包含栏目链接：Nyheter、Sverige、Världen、Ekonomi、Kultur、Sport、Klimatet、Ledare、DN Debatt、Meny，以及搜索和日期显示 |
| `CMP-NAV-SUB` | 子导航 | 随上下文变化的二级导航（如首页显示 "DN Direkt, Politik, Fakta i frågan"；Sverige 栏目显示 "Sthlm, Gbg, Skåne, Norra Sverige"） |
| `CMP-NAV-STICKY` | 吸顶导航（滚动状态） | `CMP-NAV-MAIN` 的精简版本，滚动时出现。Logo 缩小、顶部工具栏隐藏、导航吸顶 |

### 内容卡片组件

| ID | 名称 | 说明 |
|----|------|------|
| `CMP-CARD-HERO` | 头条文章卡片 | 大尺寸焦点文章，全宽图片 + 标题（h2）+ 摘要文字。出现在内容区域顶部 |
| `CMP-CARD-STANDARD` | 标准文章卡片 | 图片（16:9）+ 标题 + 可选摘要。用于主内容列 |
| `CMP-CARD-COMPACT` | 紧凑文章卡片 | 仅标题链接，无图片。用于侧栏和列表 |
| `CMP-CARD-SIDE-THUMB` | 侧缩略图卡片 | 右侧小缩略图 + 左侧标题。用于"最新文章"侧栏和部分列表场景 |
| `CMP-CARD-REVIEW` | 评论卡片 | 图片（16:9）+ 分类标签（如 "MUSIK | RECENSION"）+ 标题 + 时间戳。用于评论轮播 |
| `CMP-CARD-INSANDARE` | 读者来信卡片 | 视觉风格同 `CMP-CARD-REVIEW`，用于读者来信（Insändare） |
| `CMP-CARD-VIDEO` | 视频缩略图卡片 | 视频播放器缩略图 + 播放按钮叠加层 + 时长标签 + 标题。用于视频轮播 |
| `CMP-CARD-GAME` | 游戏卡片 | 图标/插画 + 游戏名称 + 副标题。用于游戏网格区域 |
| `CMP-CARD-QUIZ` | 问答列表项 | 分类标签（如 "QUIZ | NUTIDSTEST"）+ 标题 + 时间戳。用于侧栏问答列表 |
| `CMP-CARD-MOTOR` | 汽车列表项 | 标题 + 日期 + 右对齐小缩略图。用于 Motor 栏目 |

### 区块/版块组件

| ID | 名称 | 说明 |
|----|------|------|
| `CMP-BREAKING-BAR` | 突发新闻条 | 红色 "Just nu:" 标签 + 标题链接。可堆叠多条。出现在广告下方、主内容上方 |
| `CMP-SECTION-HEADER` | 版块标题 | 红色左边框 + 版块名称 + 可选右箭头。链接到版块页面（如 "DN granskar"、"Insändare"、"Val 2026"） |
| `CMP-SECTION-HEADER-TOPIC` | 专题版块标题 | 同 `CMP-SECTION-HEADER`，用于首页信息流中的专题分组（如 "Kriget i Mellanöstern"、"Kriget i Ukraina"、"USA"） |
| `CMP-LATEST-ARTICLES` | 最新文章侧栏 | "Senaste artiklarna" 标题 + 可滚动的 `CMP-CARD-COMPACT` 列表（含时间戳和分类标签）。右侧栏组件 |
| `CMP-LATEST-CLIPS` | 最新视频侧栏 | "Senaste klippen" 标题 + 带时间戳的视频链接列表。右侧栏组件 |
| `CMP-LATEST-QUIZ` | 最新问答侧栏 | "Senaste quizen" 标题 + 带分类标签和时间戳的问答列表 |
| `CMP-DN-DIREKT-FEED` | DN Direkt 滚动条 | "DN Direkt" 标题 + Föregående/Nästa 导航按钮 + 按时间排列的标题列表 |
| `CMP-SOCIAL-LINKS` | 社交媒体链接区块 | "Följ DN i sociala medier" + Facebook、Instagram、YouTube、TikTok 图标及文字 |
| `CMP-NEWSLETTER-CTA` | 新闻通讯 CTA | "Prenumerera på nyheter" + 链接到新闻通讯页 |
| `CMP-TIPSA-CTA` | 线索提交 CTA | "Tipsa DN:s granskande reportrar" 链接卡片 |
| `CMP-SUBSCRIPTION-PROMO` | 订阅推广卡片 | "Vilken prenumeration passar dig bäst?" + "Välj din läsning" + "Läs mer" 按钮。DN 品牌风格 |
| `CMP-COMICS` | 漫画连载 | "Läs DN:s serier" 标题 + 漫画缩略图行 |
| `CMP-EDN-WIDGET` | e-DN 报纸组件 | "Dagens tidning [日期]" + 报纸封面图片 + "Läs e-DN" 按钮 |
| `CMP-ARCHIVE-CTA` | 档案 CTA | "Sök i DN:s arkiv — från 1864 till i dag" 链接卡片 |
| `CMP-STREAMING-GUIDE` | 流媒体指南 CTA | "DN:S GUIDE — NYA TIPS VARJE VECKA" + "Bästa tipsen för just dina strömningstjänster" 推广 |
| `CMP-GAMES-GRID` | 游戏版块网格 | "Spel — nya utmaningar varje dag" 标题 + `CMP-CARD-GAME` 网格布局 |
| `CMP-NUTIDSORIENTERING` | 时事教育推广 | DN 学校测验项目推广卡片 |
| `CMP-BIKE-CTA` | DN 自行车 CTA | "BESTÄLL DN-CYKELN" 推广卡片 |
| `CMP-CLIMATE-DASHBOARD` | 气候仪表盘 CTA | "KLIMATET JUST NU" + "Fakta: Hur går kampen mot klimathotet?" |
| `CMP-FRAGA-INSIDAN` | Fråga Insidan 侧栏 | "Fråga Insidan" 标题 + 最新生活建议专栏条目列表 |
| `CMP-KROG-COMMISSION` | 餐厅评测卡片 | Krogkommissionen 餐厅评测特色卡片（含图片） |
| `CMP-KALENDARIET` | 活动日历卡片 | "Det bästa att göra i Stockholm just nu" 活动列表卡片 |

### 轮播组件

| ID | 名称 | 说明 |
|----|------|------|
| `CMP-CAROUSEL-REVIEWS` | 评论轮播 | `CMP-CARD-REVIEW` 水平滚动轮播，带 Föregående/Nästa 按钮 |
| `CMP-CAROUSEL-INSANDARE` | 读者来信轮播 | `CMP-CARD-INSANDARE` 水平滚动轮播 |
| `CMP-CAROUSEL-VIDEO` | 视频轮播 | `CMP-CARD-VIDEO` 水平滚动轮播 |

### 广告组件

| ID | 名称 | 说明 |
|----|------|------|
| `CMP-AD-BANNER-TOP` | 顶部横幅广告 | 主内容区上方的大尺寸广告位（导航下方）。标注 "ANNONS" |
| `CMP-AD-SIDEBAR` | 侧栏广告 | 右侧栏广告位。标注 "ANNONS" |
| `CMP-AD-NATIVE` | 原生/赞助文章 | 品牌内容卡片。黄色 "ANNONS" 标签 + "Innehåll från [品牌]" + 标题 + 文字 |
| `CMP-AD-INLINE` | 内嵌广告 | 主内容列中内容块之间插入的广告单元 |

### 文章页组件

| ID | 名称 | 说明 |
|----|------|------|
| `CMP-ARTICLE-HEADER` | 文章头部 | 分类标签（链接）+ h1 标题 + 时间戳（更新时间/发布时间） |
| `CMP-ARTICLE-HERO-IMAGE` | 文章主图 | 全宽首图，带图片说明和摄影师署名 |
| `CMP-ARTICLE-BODY` | 文章正文 | 格式化文本内容，包含粗体导语段落（ingress）、正文段落、带说明的行内图片 |
| `CMP-ARTICLE-BYLINE` | 文章署名 | "Text" + 作者姓名（链接到作者页） |
| `CMP-ARTICLE-ACTIONS` | 文章操作栏 | 收藏切换开关 + Dela（分享）按钮 |
| `CMP-ARTICLE-TOPICS` | 文章专题标签 | "Ämnen i artikeln" 标题 + 专题标签（带 "Följ" 关注开关） |
| `CMP-ARTICLE-RELATED` | 相关文章 | "Relaterade artiklar" 标题 + `CMP-CARD-STANDARD` 列表 |
| `CMP-ARTICLE-READ-MORE` | 延伸阅读链接 | "Läs även:" + 文章正文内的行内文章链接 |
| `CMP-ARTICLE-QUALITY` | 新闻品质声明 | "Så här jobbar DN med kvalitetsjournalistik" 文字块 + 链接 |
| `CMP-ARTICLE-TOOLS` | 文章工具 | Dela 按钮 + Skriv ut（打印）+ Rätta artikeln（纠错，通过 mailto） |
| `CMP-PAYWALL` | 付费墙遮罩 | 文字渐隐 + DN Logo + "Är du redan prenumerant, logga in" + 登录按钮 + 含 Klarna 支付的订阅方案 |
| `CMP-FREE-ARTICLE-CTA` | 免费文章登录 CTA | "Få ut mer av DN som inloggad" + 功能列表 + 登录/注册按钮。出现在免费文章中 |

### 页脚组件

| ID | 名称 | 说明 |
|----|------|------|
| `CMP-FOOTER` | 主页脚 | 深色四列页脚，链接分组：Ta del av DN、Kundservice、Om DN、Följ oss |
| `CMP-FOOTER-CREDITS` | 页脚版权信息 | 编辑部成员列表、Bonnier News 品牌、版权声明、Rudolf Wall 肖像 + 历史说明 |
| `CMP-FOOTER-TOOLS` | 页脚工具栏 | "Ändra version" + Mobil + Tablet + Hantera kakor 按钮 |
| `CMP-CONTACT-BLOCK` | 联系信息区块 | 编辑部联系方式（编辑、邮箱、电话）。出现在首页页脚上方 |

### 特殊页面组件

| ID | 名称 | 说明 |
|----|------|------|
| `CMP-SEARCH-BOX` | 搜索输入框 | "Sök artiklar, ämnen och skribenter" 文本输入 + 搜索按钮 |
| `CMP-SEARCH-FILTERS` | 搜索过滤器 | 排序下拉框（Nyast）+ 日期下拉框（När som helst）+ "Sök endast i rubriker" 复选框 |
| `CMP-SEARCH-POPULAR` | 热门搜索 | "Vanliga sökningar:" + 热门搜索链接列表 |
| `CMP-SEARCH-ARCHIVE` | 搜索页档案 CTA | "DN Arkivet" 卡片，建议用户去历史档案搜索 |
| `CMP-MENU-GRID` | 菜单页网格 | 五列分类链接布局：Nyheter、Populärt、Teman、Insändare & Debatt、Underhållning |
| `CMP-MENU-AZ` | A-Z 索引 | 按字母排列的所有栏目和专题列表 |
| `CMP-MENU-SIDEBAR` | 菜单页侧栏 | 服务图标：Kundservice、Prenumerera、Mitt konto、Familjedelning、Kunderbjudanden、Annonsera + Tipsa oss 区域 |
| `CMP-DIREKT-HERO` | DN Direkt 头图 | 红色渐变横幅，"DN DIREKT" 标签 + "Senaste nyheterna" + "Följ DN:s direktrapport här" |
| `CMP-DIREKT-FILTERS` | DN Direkt 子频道 | "Fler direktrapporter" + 主题流链接（Kriget i Ukraina、Krisen i Mellanöstern） |
| `CMP-DIREKT-TIMELINE` | DN Direkt 时间线 | 按时间倒序排列的新闻列表，带红色圆点标记 |
| `CMP-TOPIC-HEADER` | 专题页头部 | 专题名称 + "Följ" 按钮 + 可选图片 + 描述文字 + 文章数量 |

---

## 模板定义

### TPL-HOME — 首页

**URL**：`/`
**布局**：两栏（主内容列约 70% + 右侧栏约 30%），穿插全宽区域。

**主内容列内容区域（从上到下）：**

1. `CMP-AD-BANNER-TOP` — 顶部广告横幅
2. `CMP-BREAKING-BAR` — 1-2 条突发新闻，"Just nu:" 标签
3. `CMP-SECTION-HEADER`（"DN granskar"）+ `CMP-CARD-HERO` — 焦点调查报道
4. "Tipsa DN:s granskande reportrar" 链接
5. `CMP-CARD-STANDARD` x 2 — 更多头条新闻
6. `CMP-DN-DIREKT-FEED` — 实时新闻滚动条，带上一条/下一条按钮
7. `CMP-AD-NATIVE` — 赞助内容卡片
8. `CMP-SECTION-HEADER`（"Fråga Insidan"）+ `CMP-CARD-HERO` — 生活建议专栏焦点
9. `CMP-CARD-STANDARD` — 文章卡片
10. `CMP-CAROUSEL-VIDEO` — 视频轮播（桌面端可见 5 项）
11. `CMP-CARD-STANDARD` — 文章卡片
12. `CMP-AD-NATIVE` — 赞助内容
13. `CMP-CARD-STANDARD` — 文章卡片
14. `CMP-SECTION-HEADER`（"Val 2026"）+ `CMP-CARD-STANDARD` x 3 — 选举专题文章组
15. `CMP-CAROUSEL-REVIEWS` — "Senaste recensionerna" 评论轮播
16. 更多 `CMP-CARD-STANDARD` 卡片 — 混合编辑内容
17. `CMP-SECTION-HEADER`（"Insändare"）+ `CMP-CAROUSEL-INSANDARE` — 读者来信轮播
18. `CMP-AD-NATIVE` — 赞助内容
19. `CMP-SECTION-HEADER-TOPIC`（"USA"）+ 文章组
20. `CMP-SECTION-HEADER`（"Val 2026"）+ Valkompassen 推广卡片
21. 更多 `CMP-CARD-STANDARD` 卡片
22. `CMP-SECTION-HEADER-TOPIC`（"Kriget i Mellanöstern"）+ 文章组
23. `CMP-CARD-STANDARD`（DN Debatt）
24. `CMP-CARD-STANDARD` x 2 — 更多文章
25. `CMP-SECTION-HEADER-TOPIC`（"Kriget i Ukraina"）+ 文章组
26. `CMP-SECTION-HEADER`（"Mat & Dryck"）+ `CMP-CARD-HERO` + 相关文章
27. `CMP-CARD-STANDARD`（Quiz 推广）
28. `CMP-GAMES-GRID` — 游戏版块
29. `CMP-CONTACT-BLOCK` — 编辑部联系信息

**右侧栏（随内容滚动，非吸顶）：**

1. `CMP-AD-SIDEBAR` — 广告位
2. `CMP-LATEST-ARTICLES` — "Senaste artiklarna"（约 20 项）+ "Alla nyheter" 链接
3. `CMP-CARD-STANDARD`（Kåseri/专栏特写，含图片）
4. `CMP-SUBSCRIPTION-PROMO` — 订阅 CTA
5. `CMP-AD-SIDEBAR` — 广告位
6. `CMP-CARD-GAME`（"Gissa platsen" 推广）
7. `CMP-AD-SIDEBAR` — 广告位
8. `CMP-SOCIAL-LINKS`
9. `CMP-NEWSLETTER-CTA`
10. `CMP-TIPSA-CTA`
11. `CMP-LATEST-QUIZ`
12. `CMP-STREAMING-GUIDE`
13. `CMP-FRAGA-INSIDAN`（侧栏版本）
14. `CMP-KROG-COMMISSION`
15. `CMP-AD-SIDEBAR`
16. `CMP-KALENDARIET`
17. Motor 栏目列表项（`CMP-CARD-MOTOR` x 3）
18. `CMP-NUTIDSORIENTERING`
19. `CMP-BIKE-CTA`
20. `CMP-CLIMATE-DASHBOARD`
21. `CMP-AD-SIDEBAR`
22. `CMP-COMICS`
23. `CMP-EDN-WIDGET`
24. `CMP-ARCHIVE-CTA`
25. `CMP-LATEST-CLIPS`
26. `CMP-CARD-GAME`（"Gissa platsen" 推广 #2）

**主内容+侧栏下方（全宽）：**
- `CMP-FOOTER`
- `CMP-FOOTER-CREDITS`
- `CMP-FOOTER-TOOLS`

---

### TPL-CATEGORY — 分类/栏目页

**URL**：`/sverige/`、`/varlden/`、`/ekonomi/`、`/kultur/`、`/sport/`、`/ledare/`、`/debatt/`、`/insandare/`

**布局**：与 TPL-HOME 相同的两栏布局。

**与首页的区别：**
- `CMP-NAV-MAIN` 高亮当前栏目（红色下划线）
- `CMP-NAV-SUB` 显示栏目专属子导航（如 Sverige 显示 "Sthlm, Gbg, Skåne, Norra Sverige"）
- 内容按对应栏目过滤
- 使用相同的组件类型，但内容针对栏目主题精选
- 右侧栏结构与首页类似

**备注**：分类页布局与首页几乎完全一致，复用了相同的信息流式布局，内容由编辑精选。

---

### TPL-ARTICLE — 文章详情页

**URL**：`/{section}/{article-slug}/`

**布局**：单列居中（最大宽度受限，比首页主内容列窄）。无侧栏。

**内容区域（从上到下）：**

1. `CMP-NAV-TOPBAR` + `CMP-NAV-MAIN` + `CMP-NAV-SUB` — 全局导航（同其他页面）
2. `CMP-AD-BANNER-TOP` — 顶部广告
3. `CMP-ARTICLE-HEADER` — 分类标签（红色、大写、可点击）+ h1 标题 + 时间戳
4. `CMP-ARTICLE-HERO-IMAGE` — 全宽首图（含图片说明和署名）
5. **导语段落（ingress）** — 粗体衬线字体，字号大于正文
6. `CMP-PAYWALL` — [付费文章] 渐隐效果 + DN Logo + 登录提示 + 含 Klarna 的订阅方案
7. 或 `CMP-ARTICLE-BODY` — [免费/可访问文章] 完整文章文本：
   - 正文段落
   - 带说明的行内图片
   - `CMP-ARTICLE-READ-MORE` — "Läs även:" 延伸阅读链接
8. `CMP-ARTICLE-TOPICS` — 专题标签（带关注开关）
9. `CMP-ARTICLE-BYLINE` — 作者署名（可点击）
10. `CMP-ARTICLE-QUALITY` — DN 新闻品质声明
11. `CMP-ARTICLE-TOOLS` — Dela / Skriv ut / Rätta artikeln
12. `CMP-ARTICLE-RELATED` — 3 篇相关文章卡片
13. `CMP-FOOTER` + `CMP-FOOTER-CREDITS` + `CMP-FOOTER-TOOLS`

**右侧区域：**
- `CMP-AD-SIDEBAR` — 吸顶广告（跟随滚动）

**付费墙行为：**
- 付费文章显示 1-2 段导语后文字渐隐
- `CMP-PAYWALL` 出现，包含 DN Logo、登录选项和订阅方案
- 订阅方案集成 Klarna 支付
- 免费文章则内嵌显示 `CMP-FREE-ARTICLE-CTA`，提示用户登录以获取更多功能

---

### TPL-TOPIC — 专题/标签页

**URL**：`/om/{topic-slug}/`

**布局**：单列居中（无侧栏，宽度与文章页类似）。

**内容区域：**

1. 全局导航
2. `CMP-AD-BANNER-TOP`
3. `CMP-TOPIC-HEADER` — 专题名称（h1）+ "Följ" 按钮（红色）+ 可选插图/图片 + 描述段落 + 文章数量（如 "234 artiklar"）
4. 按时间倒序排列的文章列表 — 每项使用 `CMP-CARD-SIDE-THUMB` 样式（标题 + 摘要 + 右对齐图片）
5. `CMP-FOOTER`

---

### TPL-SEARCH — 搜索页

**URL**：`/sok/`

**布局**：两栏（主内容 + 较窄侧栏）。

**内容区域：**

1. 全局导航（无子导航）
2. 页面标题："Sök"（h1）
3. `CMP-SEARCH-BOX` — 全宽文本输入框 + 搜索图标按钮
4. `CMP-SEARCH-FILTERS` — 排序（Nyast）+ 日期（När som helst）+ "Sök endast i rubriker" 复选框
5. `CMP-SEARCH-POPULAR` — "Vanliga sökningar:" + 热门搜索链接（Quiz、Dagens fyra、Sudoku、Korsord、Strömmat med Wenno、Alex Schulman、Hanna Hellquist、Serier、Dödsannonser、Dagens tidning (e-DN)、Kundservice）
6. **右侧栏**：`CMP-SEARCH-ARCHIVE` — "DN Arkivet" 卡片，链接到历史档案

---

### TPL-MENU — 全站菜单页

**URL**：`/meny/`

**布局**：两区域（主网格 + 右侧栏）。

**内容区域：**

1. 全局导航
2. `CMP-MENU-GRID` — 五列链接网格（Nyheter、Populärt、Teman、Insändare & Debatt、Underhållning）
3. 提示文字："Hittar du inte vad du letar efter? Pröva 'Från A-Ö' eller Sök."
4. `CMP-MENU-AZ` — 按字母排列的所有栏目/专题索引
5. **右侧栏**：`CMP-MENU-SIDEBAR` — 服务图标（Kundservice、Prenumerera、Mitt konto、Familjedelning、Kunderbjudanden、Annonsera）+ Tipsa oss 区域
6. `CMP-FOOTER`

---

### TPL-DIREKT — DN Direkt 页面

**URL**：`/direkt/`

**布局**：单列居中。

**内容区域：**

1. 全局导航 + 子导航
2. `CMP-AD-BANNER-TOP`
3. `CMP-DIREKT-HERO` — 红色渐变横幅，"DN DIREKT" 标签和副标题
4. `CMP-DIREKT-FILTERS` — "Fler direktrapporter" 链接（Kriget i Ukraina、Krisen i Mellanöstern）
5. `CMP-DIREKT-TIMELINE` — 按时间倒序排列的新闻列表，每项包含：
   - 红色圆点标记
   - 时间戳标签（HH:MM）
   - "UPPDATERAD HH:MM" 更新标签（如有更新）
   - 标题（h2）
   - 分享按钮
6. `CMP-FOOTER`

---

### TPL-AUTHOR — 作者页

**URL**：`/av/{author-slug}/`
**布局**：[需确认] 可能是该作者文章的列表页。

---

### TPL-GAME — 游戏页

**URL**：`/korsord/`、`/sudoku/`、`/quiz/`、`/dagens-fyra/`、`/gissa-platsen/`、`/minispel/`
**布局**：[需确认] 可能是标准页面外壳内嵌入的游戏/互动组件。

---

## 响应式行为总结

### 桌面端（>= 1024px）
- 完整两栏布局（主内容 + 侧栏）
- 完整水平导航，所有项目可见
- 子导航可见
- 顶部工具栏产品链接可见

### 平板端（768px - 1023px）
- 导航保持水平（所有项目可见，必要时可水平滚动）
- 两栏布局保持但更窄
- 顶部工具栏产品链接保持可见
- 子导航保持可见
- 整体结构与桌面端一致，仅比例压缩

### 移动端（< 768px）
- 导航项变为可水平滚动（不转换为汉堡菜单）
- 布局变为单列 — 右侧栏内容移到主内容下方或隐藏
- 顶部工具栏产品链接可能水平滚动
- 文章卡片垂直堆叠，全宽显示
- 轮播变为可触摸滑动
- 首次访问时出现订阅弹窗叠加层
- 视频轮播可见项数可能减少

**关键发现**：DN.se 在任何断点下都**不使用汉堡菜单**。导航在移动端也保持为可水平滚动的导航栏。导航中的 "Meny" 链接指向全站菜单页（`/meny/`），而非打开下拉菜单。
