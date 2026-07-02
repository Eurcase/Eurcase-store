# Eurcase 网站项目对话交接记录

日期：2026-06-17  
项目：Eurcase 旅行箱包品牌官网  
本地项目路径：`C:\Users\Administrator\Documents\Codex\2026-06-12\eurcase-eurcase-com`

这份文件用于在更换 Codex 账号后继续项目。新的 Codex 可以先阅读本文件，再阅读 `PROJECT_CONTEXT.md`、`README.md` 和 `IMAGE_MAP.md`，即可接上当前阶段。

## 一句话概况

我们正在为 Eurcase 旅行箱包品牌制作第一阶段官网，参考 ITO / itotravel 的电商品牌官网视觉和手机端结构，目前已经完成本地静态网页、GitHub + Cloudflare Pages 部署流程、首屏两图轮播和基础品牌体系。

## 已确认的第一阶段策略

第一阶段先用免费、轻量、稳定的方式搭建网站：

- 网站代码放在 GitHub 私有仓库
- 使用 Cloudflare Pages 免费版部署
- 域名 `eurcase.com` 是在阿里云购买的
- DNS 可以先继续放在阿里云，后续也可以迁到 Cloudflare
- 所有相关账号建议开启两步验证
- 第一版不接数据库
- 第一版不做真实支付
- 第一版不开放后台

这个阶段的重点是：先把品牌官网做出来，能浏览、能展示、能持续迭代。

## 参考对象

主要参考 ITO / itotravel 官网的电商品牌感：

- 手机端首屏大图
- 顶部促销条
- 简洁导航
- 大图轮播
- 轮播图片上有文字
- 切换图片时先显示图，文字后进入
- 首页有电商产品卡、系列模块、品牌模块

注意：目标不是复制 ITO，而是参考它的结构、节奏和电商感，做成 Eurcase 自己的风格。

## Eurcase 品牌颜色

用户给出的品牌颜色参考：

| 颜色角色 | 色值 | 用途 |
|---|---|---|
| 主品牌色 | `#7F9A8A` 鼠尾草绿 | 品牌识别、系列页、标签 |
| 稳定深色 | `#2F3432` 石墨灰 | 标题、Logo、正文重点 |
| 页面底色 | `#F5F7F4` 旅雾白 | 详情页背景、大面积留白 |
| 生活暖色 | `#D8C7AA` 柔沙米 | 场景页、家庭/旅行氛围 |
| 强调色 | `#E59A45` 旅程橙 | 按钮、重点卖点、促销点缀 |

使用比例：

- 旅雾白 60%
- 石墨灰 20%
- 鼠尾草绿 10%
- 柔沙米 7%
- 旅程橙 3%

这些颜色已经应用在 `src/styles.css` 的 CSS 变量中。

## 产品体系

一级按品类：

- Cases | 旅行箱
- Bags | 旅行包
- Backpacks | 双肩包
- Slings | 随身包
- Essentials | 旅行配件

二级按 Nature Series 自然元素系列：

- WOOD | 原木：实用、多开、快取、有序
- AIR | 空气：轻便、透气、舒适背负
- CLOUD | 轻量系列
- STONE | 防护系列
- WATER | 水：灵活、扩容、可变、多场景

组合示例：

- Eurcase CLOUD Cabin Case | 云感轻量登机箱
- Eurcase STONE Frame Case | 坚固防护铝框箱
- Eurcase WOOD Front-open Case | 原木快取前开箱
- Eurcase WATER Travel Bag | 水系灵活旅行包
- Eurcase AIR Commuter Backpack | 轻装通勤双肩包

## 当前网站文件结构

主要文件：

- `index.html`：首页结构、首屏轮播脚本、页面内容
- `src/styles.css`：全部视觉样式、手机端样式、首屏动效
- `assets/`：网站图片资源
- `IMAGE_MAP.md`：图片命名和用途说明
- `PROJECT_CONTEXT.md`：项目背景、规则、当前决策
- `README.md`：项目基本说明
- `DEPLOYMENT.md`：部署说明
- `outputs/eurcase-github-upload/`：整理好的 GitHub 上传文件夹

本地预览地址通常是：

`http://127.0.0.1:4173/`

为了避免浏览器缓存，常加版本参数，例如：

`http://127.0.0.1:4173/?v=nature-series-20260702`

## GitHub / Cloudflare 部署进度

用户已经：

- 把整理好的网站文件上传到 GitHub 仓库
- 在 Cloudflare Pages 里连接 GitHub
- 完成 Pages 部署
- 绑定或访问到 `eurcase.com`

第一阶段部署方式已经跑通。之后每次更新网站，建议流程是：

1. 本地修改网站文件
2. 本地预览确认
3. 同步到 `outputs/eurcase-github-upload`
4. 上传或提交到 GitHub
5. Cloudflare Pages 自动更新线上网站

Cloudflare Pages 设置：

- Framework preset: None
- Build command: 留空
- Build output directory: `/`

## 首屏轮播当前状态

首页首屏已经完成两张图轮播：

### 首屏1

- 名称：首屏1 / Hero 1
- 文件：`assets/hero-1-access.jpg`
- 系列：WOOD
- 文案：`Open neat. Move easy.`
- 中文含义：原木、快取、前开、有序收纳
- 备注：文件名仍保留 `access`，因为它来自旧 ACCESS 阶段；当前展示归入 WOOD。

### 首屏2

- 名称：首屏2 / Hero 2
- 文件：`assets/hero-2-stone.jpg`
- 系列：STONE
- 文案：`Built tough. Travel calm.`
- 中文含义：坚固、防护、安全感

### 轮播交互

现在首屏支持：

- 自动轮播：大约每 5 秒切换一次
- 手动轮播：图片左右有圆形箭头按钮，可以上一张 / 下一张
- 切换动效：上一张图的文字立即消失，图片先切换，新图保持干净画面约 0.7 秒，然后新文字慢慢浮入

这个动效是用户明确要求的，方向是接近 ITO 那种“先看图，文字后出现”的感觉。

## 已处理过的首屏图片

用户提供过两张主要首屏图：

1. WOOD 系列图  
   最终网页文件：`assets/hero-1-access.jpg`  
   说明：已压缩为网页适用版本，约 261KB。

2. STONE 系列图  
   最终网页文件：`assets/hero-2-stone.jpg`  
   说明：已压缩为网页适用版本，约 185KB。

之后如果用户说“更换首屏1”，就是替换或更新 `assets/hero-1-access.jpg`。

之后如果用户说“更换首屏2”，就是替换或更新 `assets/hero-2-stone.jpg`。

## 用户偏好的协作方式

用户希望：

- 一步一步指导，不要太技术化
- 能解释为什么这么做
- 本地先能浏览，再考虑部署
- 做完一版后同步到上传 GitHub 的文件夹
- 文件命名要清楚，比如“首屏1”“首屏2”
- 手机端展示很重要，要经常检查手机端
- 视觉上更接近 ITO 那种成熟电商品牌官网

和用户沟通时，建议用中文，少说复杂术语。如果必须说技术词，要顺手解释。

## 当前可继续做的下一步

建议接下来继续完善这些模块：

1. 首页产品卡真实图片
2. WOOD / AIR / CLOUD / WATER / STONE 系列模块
3. 手机端菜单展开效果
4. 产品详情页结构
5. 品牌故事区
6. 批发询盘 / 联系表单区
7. SEO 标题、描述和社交分享图
8. 更完整的图片命名规则，例如“产品卡1”“系列图1”“品牌故事图1”

## 2026-07-02 系列体系更新

用户提供了新的品牌核心文档：

`C:\Users\Administrator\Desktop\Eurcase资产\01_品牌核心\Eurcase欧优品牌核心与系列体系_含自然元素图标系统_同源预览版.docx`

根据该文档，网页系列体系从旧的功能命名表达，切换到 Nature Series 自然元素体系：

- WOOD | 原木：实用、多开、快取、有序
- AIR | 空气：轻便、透气、舒适背负
- CLOUD | 云：轻量、省力、柔和移动
- WATER | 水：灵活、扩容、可变、多场景
- STONE | 石头：坚固、防护、稳定、长途安心

对应调整：

- 原 ACCESS 前开快取逻辑，归入 WOOD。
- 原 FLOW 灵活扩容逻辑，归入 WATER。
- 首屏1仍使用 `assets/hero-1-access.jpg`，但页面展示为 WOOD Series。
- 首屏2仍使用 `assets/hero-2-stone.jpg`，展示为 STONE Series。
- 自然元素图标已复制到 `assets/nature-icons-apple-system/`。

继续做页面时，应优先使用 WOOD / AIR / CLOUD / WATER / STONE 这套系列语言。

## 给新 Codex 的接续提示

如果换了 Codex 账号，可以这样开始：

```text
请先阅读当前项目里的 CHAT_HANDOFF_2026-06-17.md、PROJECT_CONTEXT.md、IMAGE_MAP.md 和 README.md。
我们正在做 Eurcase 旅行箱包官网，当前已经完成 ITO 风格的首页基础版和首屏两图轮播。
请先不要重做项目，先基于现有 index.html 和 src/styles.css 继续迭代。
每次改完后先本地预览，再同步到 outputs/eurcase-github-upload。
```

## 重要提醒

不要从零重做。当前项目已经有可用基础，继续在现有文件上迭代即可。

不要直接用超大原图放进网页。图片进入网站前要压缩成网页适合的大小。

不要只看桌面端。这个项目的手机端体验很重要，很多参考来自 ITO 手机端页面。

不要忘记同步上传文件夹：`outputs/eurcase-github-upload`。
