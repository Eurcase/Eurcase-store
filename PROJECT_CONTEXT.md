# Eurcase Project Context

这个文件用于保存我们在聊天中已经确认的项目背景、设计决定和操作规则。以后继续做 Eurcase 网站时，优先先看这个文件，就能快速接上之前的进度。

## 项目目标

为 Eurcase 旅行箱包品牌制作第一阶段官网。

当前阶段目标不是完整电商系统，而是先做一个稳定、可展示、可持续迭代的品牌官网：

- 展示品牌调性和产品系列
- 支持手机端和桌面端浏览
- 先不接数据库
- 先不做真实支付
- 先不开放后台
- 后续可逐步升级到 Shopify 或其他电商系统

## 当前部署策略

第一阶段采用免费、稳妥的方式：

- 网站代码放 GitHub 私有仓库
- 使用 Cloudflare Pages 免费版部署
- 域名 `eurcase.com` 仍在阿里云购买和管理
- DNS 可以先继续阿里云，后续也可以迁到 Cloudflare
- 所有账号开启两步验证

Cloudflare Pages 设置：

- Framework preset: None
- Build command: 留空
- Build output directory: `/`

上传 GitHub 用的整理文件夹：

`outputs/eurcase-github-upload`

每次本地修改完成后，需要把最新的 `index.html`、`src`、`assets`、说明文档同步到这个文件夹，再上传或提交到 GitHub。

## 品牌参考

主要参考 ITO / itotravel 的电商品牌官网感觉：

- 手机端首屏大图
- 顶部促销条
- 简洁导航
- 大图轮播
- 图片先进入，文字后浮入
- 电商感强，但不过度复杂

Eurcase 不能完全复制 ITO，而是参考它的结构、节奏和电商展示方式，做成 Eurcase 自己的品牌感。

## 品牌颜色

当前使用的 Eurcase 颜色体系：

- 主品牌色：`#7F9A8A` 鼠尾草绿
- 稳定深色：`#2F3432` 石墨灰
- 页面底色：`#F5F7F4` 旅雾白
- 生活暖色：`#D8C7AA` 柔沙米
- 强调色：`#E59A45` 旅程橙

使用比例参考：

- 旅雾白 60%
- 石墨灰 20%
- 鼠尾草绿 10%
- 柔沙米 7%
- 旅程橙 3%

## 产品体系

一级按品类：

- Cases | 旅行箱
- Bags | 旅行包
- Backpacks | 双肩包
- Slings | 随身包
- Essentials | 旅行配件

二级按 Nature Series 自然元素系列：

- WOOD | 原木系列：实用、多开、快取、有序
- AIR | 空气系列：轻便、透气、舒适背负
- CLOUD | 轻量系列
- STONE | 防护系列
- WATER | 水系列：灵活、扩容、可变、多场景

示例命名：

- Eurcase CLOUD Cabin Case | 云感轻量登机箱
- Eurcase STONE Frame Case | 坚固防护铝框箱
- Eurcase WOOD Front-open Case | 原木快取前开箱
- Eurcase WATER Travel Bag | 水系灵活旅行包
- Eurcase AIR Commuter Backpack | 轻装通勤双肩包

自然元素图标资产位于：

`assets/nature-icons-apple-system/`

当前官网系列入口使用彩色 SVG 主版：WOOD、AIR、CLOUD、WATER、STONE。

## 首屏轮播规则

当前首页首屏已经改成轮播：

- 自动轮播：约每 5 秒切换一次
- 手动轮播：图片左右有箭头按钮，可手动上一张 / 下一张
- 切换节奏：旧文字立即消失，图片先切换，新图保持干净画面约 0.7 秒，文字再慢慢浮入

首屏图片命名：

- 首屏1 / Hero 1：`assets/hero-1-access.jpg`
  - 系列：WOOD
  - 文案：Open neat. Move easy.
  - 说明：文件名仍保留 access，是因为图片来自旧 ACCESS 阶段；新体系中归入 WOOD。
- 首屏2 / Hero 2：`assets/hero-2-stone.jpg`
  - 系列：STONE
  - 文案：Built tough. Travel calm.

以后如果说“更换首屏1”，就是替换 `assets/hero-1-access.jpg` 或更新 `index.html` 里的对应引用。

以后如果说“更换首屏2”，就是替换 `assets/hero-2-stone.jpg` 或更新 `index.html` 里的对应引用。

图片映射也记录在：

`IMAGE_MAP.md`

## 当前主要文件

- `index.html`：首页结构和轮播脚本
- `src/styles.css`：全部视觉样式、响应式样式、首屏动效
- `assets/`：网站图片素材
- `IMAGE_MAP.md`：图片命名和用途说明
- `DEPLOYMENT.md`：部署说明
- `README.md`：项目基础说明
- `outputs/eurcase-github-upload/`：用于上传 GitHub 的整理包

## 语言版本

当前首页已加入轻量中英文切换：

- 默认英文
- 顶部导航右侧有 `中文 / EN` 切换按钮
- 手机端顶部也有语言切换按钮
- 点击后主要页面文案会在中文和英文之间切换
- 选择会保存在浏览器本地，下次打开延续上次语言

实现位置：

- 切换按钮：`index.html` 的 header 区域
- 翻译词条和切换逻辑：`index.html` 底部脚本
- 按钮样式：`src/styles.css` 的 `.language-toggle`

## 本地预览

当前本地预览常用地址：

`http://127.0.0.1:4173/`

有时为了避免浏览器缓存，会在后面加版本参数，例如：

`http://127.0.0.1:4173/?v=bilingual-20260702`

## 后续协作方式

之后继续做网站时，可以按这种方式推进：

1. 先确认要修改的模块，比如首屏、产品区、系列区、品牌故事、底部等。
2. 如果换图，先明确图片属于哪个位置，比如“首屏1”“首屏2”“产品卡1”。
3. 图片进入网站前，优先压缩成网页适合的尺寸和体积。
4. 修改完成后，先本地预览。
5. 确认满意后，再同步到 `outputs/eurcase-github-upload`。
6. 最后上传或提交 GitHub，让 Cloudflare Pages 自动更新线上网站。

## 当前建议的下一步

可以继续完善：

- 首页产品卡真实图片
- WOOD / AIR / CLOUD / WATER / STONE 系列模块
- 手机端菜单
- 产品详情页结构
- 品牌故事页
- 联系和批发询盘区
- SEO 标题、描述和社交分享图
