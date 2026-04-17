# DN.se 站点地图

> 分析日期：2026-04-17
> 来源：https://www.dn.se

---

## 1. URL 结构概览

DN.se 采用扁平化、基于 slug 的 URL 架构，主要模式如下：

| 模式 | 示例 | 说明 |
|------|------|------|
| `/` | `dn.se/` | 首页（Nyheter，新闻） |
| `/{section}/` | `dn.se/sverige/` | 分类/栏目页 |
| `/{section}/{article-slug}/` | `dn.se/sverige/ricky-insjuknade-pa-ssab-jobbet-radd-for-att-do/` | 文章详情页 |
| `/om/{topic-slug}/` | `dn.se/om/val-2026/` | 专题/标签页 |
| `/av/{author-slug}/` | `dn.se/av/andreas-lindberg/` | 作者页 |
| `/direkt/` | `dn.se/direkt/` | DN Direkt 实时新闻流 |
| `/direkt/{date}/{slug}/` | `dn.se/direkt/2026-04-17/nya-stolder-pa-sjukhus/` | DN Direkt 单条新闻 |
| `/meny/` | `dn.se/meny/` | 全站菜单页 |
| `/sok/` | `dn.se/sok/` | 搜索页 |
| `/brandstudio/{brand}/{slug}/` | `dn.se/brandstudio/clearlii/optikern-manga-tror/` | 赞助内容/原生广告 |
| `/quiz/{category}/{slug}/` | `dn.se/quiz/nutidstest/vecka-16-2026/` | 问答/测验页 |

### 外部域名

| 域名 | 用途 |
|------|------|
| `etidning.dn.se` | 电子报纸（e-DN） |
| `arkivet.dn.se` | 历史档案库（始于 1864 年） |
| `prenumerera.dn.se` | 订阅服务 |
| `erbjudanden.dn.se` | 客户优惠 |
| `konto.bonniernews.se` | 账户管理/客服 |
| `id.bonniernews.se` | 登录/认证 |
| `dngranskar.dn.se` | 调查报道线索提交 |

---

## 2. 导航系统

### 2.1 顶部工具栏（产品链接） `CMP-NAV-TOPBAR`

位于主导航上方的窄条，包含 DN 各产品的快捷链接。

链接项：E-DN | ARKIVET | KORSORD | KUNDSERVICE | QUIZ | ERBJUDANDEN

右侧：**Prenumerera**（红色 CTA 按钮） | **Logga in**（描边按钮）

### 2.2 主导航 `CMP-NAV-MAIN`

位于顶部工具栏下方的水平导航栏，包含主要栏目链接。

导航项（从左到右）：
1. **Nyheter**（新闻）(`/`) — 首页激活时显示红色下划线
2. **Sverige**（瑞典）(`/sverige/`)
3. **Världen**（世界）(`/varlden/`)
4. **Ekonomi**（经济）(`/ekonomi/`)
5. **Kultur**（文化）(`/kultur/`)
6. **Sport**（体育）(`/sport/`)
7. **Klimatet**（气候）(`/om/klimatet/`)
8. **Ledare**（社论）(`/ledare/`)
9. **DN Debatt**（DN 辩论）(`/debatt/`)
10. **Meny**（菜单）(`/meny/`) — 前面有汉堡图标

右侧：**Sök**（搜索图标+文字） | **当前日期**（如 "Fredag 17 apr"）

**激活状态**：当前栏目名称下方显示红色下划线。

### 2.3 子导航 `CMP-NAV-SUB`

位于主导航下方的上下文相关二级导航，内容随当前栏目变化。

| 当前栏目 | 子导航项 |
|---------|---------|
| Nyheter（首页） | DN Direkt, Politik, Fakta i frågan, Vetenskap, Tipsa DN |
| Sverige | Sthlm, Gbg, Skåne, Norra Sverige |
| Världen | [需确认 — 可能有专题相关子导航] |
| Ekonomi | [需确认] |
| Kultur | [需确认] |
| Sport | [需确认] |

### 2.4 页脚 `CMP-FOOTER`

深色背景（接近黑色），四列布局：

**第 1 列 — "Ta del av DN"（了解 DN）**
- DN:s appar, e-DN, Spel, Arkivet, DN Direkt, Insändare, Nyhetsbrev, Följ ämnen och skribenter, Alla ämnen

**第 2 列 — "Kundservice"（客户服务）**
- Bli prenumerant, Kundservice, Min prenumeration, Vanliga frågor, Kontakta kundservice, Kunderbjudanden

**第 3 列 — "Om DN"（关于 DN）**
- Kontakta oss, Tipsa DN, Jobba på DN, Kakpolicy, Upphovsrätt och AI, Personuppgiftspolicy, Annonsera, IAB Sweden Gold Standard, Anmäl störande/felaktig annons, Anmäl brist i digital tillgänglighet

**第 4 列 — "Följ oss"（关注我们）**
- Instagram, Youtube, Facebook, TikTok

**列下方区域：**
- 编辑部成员列表（总编辑、编辑主任、CEO 等）
- "Dagens Nyheter — en del av Bonnier News"
- 组织编号、版权声明
- Rudolf Wall 肖像 + "Dagens Nyheter." 历史沿革说明
- 版本切换按钮：Ändra version | Mobil | Tablet | Hantera kakor

### 2.5 页脚前联系区块 `CMP-CONTACT-BLOCK`

出现在首页页脚上方（位于 `<main>` 内）：
- Livechef（值班主编）: 姓名 + 邮箱
- Redaktör（编辑）: 姓名 + 邮箱
- E-post DN.se: www@dn.se
- Prenumerationer（订阅）: 电话号码
- E-post: kundservice@dn.se
- Nyhetstips（新闻线索）: 电话号码
- DN:s växel（DN 总机）: 电话号码

---

## 3. 页面层级结构

```
dn.se/
├── （首页 / Nyheter 新闻）
├── /sverige/               （瑞典新闻）
│   ├── /sthlm/             （斯德哥尔摩）
│   ├── /gbg/               （哥德堡）
│   ├── /skane/             （斯科讷）
│   └── /norra-sverige/     （北瑞典）
├── /varlden/               （世界新闻）
├── /ekonomi/               （经济）
├── /kultur/                （文化）
├── /sport/                 （体育）
├── /om/klimatet/           （气候专题）
├── /ledare/                （社论）
├── /debatt/                （DN 辩论）
├── /insandare/             （读者来信）
├── /direkt/                （DN Direkt — 实时新闻流）
│   ├── /direkt/{date}/{slug}/
│   └── /direkt/mellanostern/  （主题实时流）
├── /insidan/               （Fråga Insidan — 生活建议专栏）
├── /mat-dryck/             （美食与饮品）
├── /vetenskap/             （科学）
├── /motor/                 （汽车）
├── /om/{topic-slug}/       （专题页，如 /om/val-2026/）
├── /av/{author-slug}/      （作者页）
├── /sok/                   （搜索）
├── /meny/                  （全站菜单/站点索引）
├── /nyhetsdygnet/          （全天新闻时间线）
├── /nyhetsbrev/            （新闻通讯订阅）
├── /foljer/                （关注的专题和作者）
├── /om/                    （所有专题 A-Z 索引）
├── /kontakt/               （联系方式）
├── /app/                   （App 下载页）
├── /spel/                  （游戏中心）
├── /korsord/               （填字游戏）
├── /sudoku/                （数独）
├── /quiz/                  （问答中心）
│   ├── /quiz/nutidstest/
│   ├── /quiz/ord-och-sprak/
│   ├── /quiz/ur-historien/
│   ├── /quiz/blandat/
│   └── /quiz/sverige-runt/
├── /dagens-fyra/           （每日四字谜）
├── /minispel/              （迷你游戏）
│   └── /minispel/ordroj/   （猜词游戏）
├── /gissa-platsen/         （猜地点游戏，类似 GeoGuessr）
├── /serier/                （漫画连载）
├── /valkompass/            （选举指南针工具）
├── /ungkompassen/          （青年选举指南针）
├── /kalendariet/           （斯德哥尔摩活动日历）
├── /klimatet-just-nu/      （气候数据仪表盘）
├── /brandstudio/{brand}/{slug}/  （赞助/原生广告内容）
├── /sa-jobbar-dn-med-kvalitetsjournalistik/  （DN 新闻品质说明）
├── /jobba-pa-dn/           （在 DN 工作）
└── 外部站点：
    ├── etidning.dn.se      （电子报纸）
    ├── arkivet.dn.se       （历史档案）
    ├── prenumerera.dn.se   （订阅）
    ├── erbjudanden.dn.se   （优惠）
    └── dngranskar.dn.se    （调查线索提交）
```

---

## 4. 菜单页站点地图（来自 /meny/）

菜单页将站点内容组织为五列：

### Nyheter（新闻）
Ekonomi, Kultur, Sthlm, Gbg, Skåne, Norra Sverige, Sport, Sverige, Världen, Politik, Vetenskap, Motor, DN Direkt

### Populärt（热门）
E-tidningen, Insidan, Hälsa, Dödsannonser, Krogkommissionen, Nyhetsdygnet, Privatekonomi, Psykologi, Nyhetsbrev

### Teman（主题）
DN intervju, Mat & Dryck, Recept, Poddar, Kalendariet, Arkivet

### Insändare & Debatt（读者来信与辩论）
DN Debatt, Insändare, Ledare

### Underhållning（娱乐）
Dagens fyra, Sudoku, Korsord, Minispel, Quiz, Serier, Gissa platsen

### A-Z 索引（列下方）
所有栏目和专题的完整字母排序列表，包含以下条目：
- A,B,C: Alla ämnen, Annonsera, Appar, Böcker, Börsen i dag
- D,E,F: Dagens fyra, Dagens tidning (e-DN), DN Arkivet, DN Debatt, Dryck & vintips, Dödsannonser, E-böcker, Ekonomi, Erbjudanden
- G,H,I: Gissa platsen, Gulddraken, Hitta ord, Insidan, Insändare
- J,K,L: Jobb & Karriär, Kalendariet, Kriget i Ukraina, Kriget Israel-Hamas, Klimatet, Konst & Form, Kontakt, Korsord, Krogkommissionen, Kultur, Kulturdebatt, Kundservice, Kåserier, Ledare, Livsstil
- M,N,O: Mat & Dryck, Minispel, Motor, Musik, Nyhetsbrev
- P,Q: Politik, Prenumerera digitalt, Prenumerera på papperstidningen, Quiz
- R,S,T: Recept & middagstips, Scen, Sport, Sthlm, Sudoku, Sök jobb, Tipsa DN
- U,V: Vetenskap

### 菜单页右侧栏
- Kundservice（客服，带图标）
- Prenumerera（订阅，带图标）
- Mitt konto（我的账户，带图标）
- Familjedelning（家庭共享，带图标）
- Kunderbjudanden（客户优惠，带图标）
- Annonsera（广告投放，带图标）
- "Tipsa oss"（线索提交）区域：Tipsa DN Granskar, Tipsa Nyhetsredaktionen
