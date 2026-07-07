# WebForward 资源导航系统

WebForward 是一个面向技术调研、内容聚合与知识管理场景的轻量级外链资源导航系统。项目定位于帮助开发者、技术内容运营者以及研究型团队高效组织、分类展示和快速检索分散于多个内容源的技术文章与参考链接。系统不依赖外部数据库，所有资源以结构化文本配置方式管理，支持静态站点生成或直接部署于任何支持 HTTPS 的 Web 服务器。

目标用户包括需要维护技术周报的编辑团队、需要统一入口查阅多站点技术博客的研发小组、以及希望将零散收藏夹转化为可共享知识库的个人开发者。项目核心价值在于将碎片化链接转化为具备可维护性、可扩展性与可读性的资源目录，降低知识资产流失风险。

## 功能概览

- 多源链接统一入库：支持将不同域名、不同路径格式的技术文章链接纳入同一套资源索引体系，自动解析来源域名与文章编号。

- 分类标签与全文检索：每条资源可附带多个分类标签，内置前端全文检索能力，支持按标题关键词、来源域名或文章编号快速定位目标链接。

- 批量导入与去重校验：提供脚本工具支持从 CSV 或纯文本列表批量导入链接，导入时自动检测重复 URL 并生成冲突报告。

- 静态页面生成引擎：基于模板引擎将资源配置文件渲染为完整的 HTML 目录页，生成结果可直接部署至 Nginx、Apache 或对象存储服务。

- 资源状态监控：集成链接可达性检测模块，定时对已收录链接发起 HEAD 请求，标记异常链接并生成健康度报表。

- 访问统计与热度排序：记录资源被点击的次数，支持按热度、入库时间或字母顺序对资源列表进行动态排序。

- 响应式目录视图：前端界面适配桌面端与移动端，提供列表视图与卡片视图两种展示模式，满足不同场景下的浏览习惯。

## 应用场景

技术团队内部知识库建设：研发团队可将日常踩坑记录、性能优化案例、第三方库评测文章等分散于个人书签或即时通讯群组中的链接，统一录入 WebForward 系统，形成团队共享的技术参考库。新成员入职时可快速通过该系统了解团队常用的技术栈资料与最佳实践参考。

技术社区内容聚合与周报生成：社区运营人员可将投稿链接、社区精华帖、外部技术博客更新等资源批量导入系统，利用分类标签功能按主题（如前端工程化、云原生基础设施、数据库调优）分组，每周自动生成带摘要的周报页面，减少人工整理成本。

个人开发者知识管理：独立开发者可将长期积累的 API 文档、开源项目地址、解决方案文章等链接集中管理，通过前端检索功能替代浏览器书签的有限层级结构，实现跨设备访问与定期整理归档。

## 快速开始

以下步骤帮助您在本地环境快速启动 WebForward 服务。

```bash
# 克隆代码仓库
git clone https://github.com/webforward/webforward.git
cd webforward

# 安装依赖（基于 Node.js 22 LTS）
npm install

# 构建静态资源目录
npm run build

# 启动开发服务器，默认监听 3000 端口
npm start
```

启动后，打开浏览器访问 http://localhost:3000 即可查看资源导航首页。系统默认加载示例资源数据，您可以通过编辑 `data/resources.json` 文件替换为自有链接列表，修改后刷新页面即可生效。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Node.js | 22.x LTS 或更高 | 运行时环境，用于执行构建脚本与开发服务器 |
| npm | 10.x 或更高 | 包管理器，用于安装项目依赖 |
| Git | 2.40 或更高 | 版本控制工具，用于克隆仓库及后续更新 |
| 操作系统 | Linux / macOS / Windows | 跨平台支持，Windows 下建议使用 WSL2 或 PowerShell 7 |
| 浏览器 | 支持 ES2022 的现代浏览器 | 前端界面运行环境，推荐 Chrome 120+ / Firefox 121+ |
| 磁盘空间 | 至少 200 MB | 包含源代码、依赖包及生成的静态文件 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 入门指南 | docs/quick-start.md | 如何快速上手部署资源导航站？如何进行首次资源导入？ |
| 配置手册 | docs/configuration.md | 资源文件格式如何定义？分类标签体系如何设计？自定义页面标题与描述的方法？ |
| 开发者指南 | docs/development.md | 如何扩展前端视图组件？如何新增链接检测策略？如何参与项目二次开发？ |
| 运维参考 | docs/operations.md | 如何将系统部署至生产环境？如何配置定时检测任务？如何备份资源数据？ |

## 资源列表

- http://http://www.read.usuhx.com/Article/5382.shtml
- http://http://www.read.usuhx.com/Article/3598110.shtml
- http://http://www.mobile.xqnqq.com/Article/5369.shtml
- http://http://www.read.usuhx.com/Article/792869.shtml
- http://http://www.mobile.xqnqq.com/Article/097705.shtml
- http://http://www.mobile.xqnqq.com/Article/87546.shtml
- http://http://www.read.usuhx.com/Article/962987.shtml
- http://http://www.mobile.xqnqq.com/Article/28287.shtml
- http://http://www.read.usuhx.com/Article/56994.shtml
- http://http://www.read.usuhx.com/Article/592694.shtml
- http://http://www.read.usuhx.com/Article/6571.shtml
- http://http://www.mobile.xqnqq.com/Article/563125.shtml
- http://http://www.mobile.xqnqq.com/Article/8053151.shtml
- http://http://www.mobile.xqnqq.com/Article/1224.shtml
- http://http://www.mobile.xqnqq.com/Article/165423.shtml
- http://http://www.mobile.xqnqq.com/Article/1913919.shtml
- http://http://www.mobile.xqnqq.com/Article/23264.shtml
- http://http://www.mobile.xqnqq.com/Article/3128684.shtml
- http://http://www.mobile.xqnqq.com/Article/9883034.shtml
- http://http://www.mobile.xqnqq.com/Article/82143.shtml
- http://http://www.read.usuhx.com/Article/9116.shtml
- http://http://www.mobile.xqnqq.com/Article/222384.shtml
- http://http://www.read.usuhx.com/Article/4967968.shtml
- http://http://www.mobile.xqnqq.com/Article/4931.shtml
- http://http://www.mobile.xqnqq.com/Article/377864.shtml
- http://http://www.read.usuhx.com/Article/56081.shtml
- http://http://www.read.usuhx.com/Article/5707.shtml
- http://http://www.mobile.xqnqq.com/Article/6327948.shtml
- http://http://www.mobile.xqnqq.com/Article/065060.shtml
- http://http://www.mobile.xqnqq.com/Article/697421.shtml
- http://http://www.read.usuhx.com/Article/49764.shtml
- http://http://www.mobile.xqnqq.com/Article/962147.shtml
- http://http://www.mobile.xqnqq.com/Article/4445.shtml
- http://http://www.mobile.xqnqq.com/Article/8818839.shtml
- http://http://www.mobile.xqnqq.com/Article/2971.shtml
- http://http://www.mobile.xqnqq.com/Article/3476440.shtml
- http://http://www.read.usuhx.com/Article/9412808.shtml
- http://http://www.mobile.xqnqq.com/Article/7304021.shtml
- http://http://www.mobile.xqnqq.com/Article/278014.shtml
- http://http://www.mobile.xqnqq.com/Article/0912046.shtml
- http://http://www.read.usuhx.com/Article/355103.shtml
- http://http://www.mobile.xqnqq.com/Article/3507043.shtml
- http://http://www.mobile.xqnqq.com/Article/9456927.shtml
- http://http://www.mobile.xqnqq.com/Article/86702.shtml
- http://http://www.read.usuhx.com/Article/8209.shtml
- http://http://www.mobile.xqnqq.com/Article/9958162.shtml
- http://http://www.mobile.xqnqq.com/Article/461531.shtml
- http://http://www.mobile.xqnqq.com/Article/351888.shtml
- http://http://www.read.usuhx.com/Article/837704.shtml
- http://http://www.read.usuhx.com/Article/518792.shtml
- http://http://www.read.usuhx.com/Article/720757.shtml
- http://http://www.read.usuhx.com/Article/99531.shtml
- http://http://www.mobile.xqnqq.com/Article/216180.shtml
- http://http://www.read.usuhx.com/Article/355039.shtml
- http://http://www.mobile.xqnqq.com/Article/3734893.shtml
- http://http://www.mobile.xqnqq.com/Article/85477.shtml
- http://http://www.mobile.xqnqq.com/Article/335056.shtml
- http://http://www.read.usuhx.com/Article/898355.shtml
- http://http://www.mobile.xqnqq.com/Article/747701.shtml
- http://http://www.mobile.xqnqq.com/Article/1743.shtml
- http://http://www.mobile.xqnqq.com/Article/99002.shtml
- http://http://www.mobile.xqnqq.com/Article/31536.shtml
- http://http://www.read.usuhx.com/Article/380138.shtml
- http://http://www.mobile.xqnqq.com/Article/93490.shtml
- http://http://www.read.usuhx.com/Article/233951.shtml
- http://http://www.read.usuhx.com/Article/5296089.shtml
- http://http://www.mobile.xqnqq.com/Article/35543.shtml
- http://http://www.mobile.xqnqq.com/Article/704851.shtml
- http://http://www.read.usuhx.com/Article/4943022.shtml
- http://http://www.mobile.xqnqq.com/Article/6911.shtml
- http://http://www.read.usuhx.com/Article/4937.shtml
- http://http://www.mobile.xqnqq.com/Article/3469.shtml
- http://http://www.read.usuhx.com/Article/74932.shtml
- http://http://www.read.usuhx.com/Article/06216.shtml
- http://http://www.read.usuhx.com/Article/9214.shtml
- http://http://www.read.usuhx.com/Article/81898.shtml
- http://http://www.mobile.xqnqq.com/Article/5446725.shtml
- http://http://www.read.usuhx.com/Article/0555726.shtml
- http://http://www.mobile.xqnqq.com/Article/021274.shtml
- http://http://www.mobile.xqnqq.com/Article/126323.shtml
- http://http://www.read.usuhx.com/Article/83341.shtml
- http://http://www.mobile.xqnqq.com/Article/9750949.shtml
- http://http://www.mobile.xqnqq.com/Article/07504.shtml
- http://http://www.mobile.xqnqq.com/Article/588509.shtml
- http://http://www.read.usuhx.com/Article/284816.shtml
- http://http://www.read.usuhx.com/Article/00587.shtml
- http://http://www.mobile.xqnqq.com/Article/773178.shtml
- http://http://www.mobile.xqnqq.com/Article/3604154.shtml
- http://http://www.read.usuhx.com/Article/88939.shtml
- http://http://www.read.usuhx.com/Article/06289.shtml
- http://http://www.read.usuhx.com/Article/741534.shtml
- http://http://www.read.usuhx.com/Article/75005.shtml
- http://http://www.mobile.xqnqq.com/Article/46136.shtml
- http://http://www.read.usuhx.com/Article/058592.shtml
- http://http://www.read.usuhx.com/Article/52108.shtml
- http://http://www.read.usuhx.com/Article/78682.shtml
- http://http://www.mobile.xqnqq.com/Article/552057.shtml
- http://http://www.mobile.xqnqq.com/Article/671793.shtml
- http://http://www.read.usuhx.com/Article/029256.shtml
- http://http://www.mobile.xqnqq.com/Article/8145.shtml
- http://http://www.mobile.xqnqq.com/Article/23568.shtml
- http://http://www.read.usuhx.com/Article/973736.shtml
- http://http://www.read.usuhx.com/Article/86219.shtml
- http://http://www.mobile.xqnqq.com/Article/7703.shtml
- http://http://www.read.usuhx.com/Article/8643.shtml
- http://http://www.read.usuhx.com/Article/4791951.shtml
- http://http://www.read.usuhx.com/Article/6534.shtml
- http://http://www.mobile.xqnqq.com/Article/556660.shtml
- http://http://www.mobile.xqnqq.com/Article/5432372.shtml
- http://http://www.read.usuhx.com/Article/865079.shtml
- http://http://www.mobile.xqnqq.com/Article/15315.shtml
- http://http://www.mobile.xqnqq.com/Article/271720.shtml
- http://http://www.read.usuhx.com/Article/6847342.shtml
- http://http://www.read.usuhx.com/Article/458989.shtml
- http://http://www.read.usuhx.com/Article/2287149.shtml
- http://http://www.mobile.xqnqq.com/Article/80637.shtml
- http://http://www.mobile.xqnqq.com/Article/0324.shtml
- http://http://www.mobile.xqnqq.com/Article/93666.shtml
- http://http://www.mobile.xqnqq.com/Article/73972.shtml
- http://http://www.mobile.xqnqq.com/Article/3261.shtml
- http://http://www.read.usuhx.com/Article/9858434.shtml
- http://http://www.mobile.xqnqq.com/Article/717609.shtml
- http://http://www.mobile.xqnqq.com/Article/98339.shtml
- http://http://www.mobile.xqnqq.com/Article/250675.shtml
- http://http://www.mobile.xqnqq.com/Article/1287120.shtml
- http://http://www.mobile.xqnqq.com/Article/2172887.shtml
- http://http://www.mobile.xqnqq.com/Article/25597.shtml
- http://http://www.mobile.xqnqq.com/Article/5840.shtml
- http://http://www.read.usuhx.com/Article/33551.shtml
- http://http://www.read.usuhx.com/Article/2599623.shtml
- http://http://www.mobile.xqnqq.com/Article/2709111.shtml
- http://http://www.mobile.xqnqq.com/Article/67922.shtml
- http://http://www.mobile.xqnqq.com/Article/8799.shtml
- http://http://www.read.usuhx.com/Article/1796570.shtml
- http://http://www.mobile.xqnqq.com/Article/091617.shtml
- http://http://www.mobile.xqnqq.com/Article/6768725.shtml
- http://http://www.read.usuhx.com/Article/151224.shtml
- http://http://www.mobile.xqnqq.com/Article/98215.shtml
- http://http://www.read.usuhx.com/Article/25641.shtml
- http://http://www.read.usuhx.com/Article/96054.shtml
- http://http://www.mobile.xqnqq.com/Article/0686667.shtml
- http://http://www.mobile.xqnqq.com/Article/968659.shtml
- http://http://www.read.usuhx.com/Article/1086.shtml
- http://http://www.read.usuhx.com/Article/584013.shtml
- http://http://www.mobile.xqnqq.com/Article/2630.shtml
- http://http://www.mobile.xqnqq.com/Article/8401951.shtml
- http://http://www.read.usuhx.com/Article/2704.shtml
- http://http://www.mobile.xqnqq.com/Article/29408.shtml
- http://http://www.read.usuhx.com/Article/412053.shtml
- http://http://www.read.usuhx.com/Article/0413909.shtml
- http://http://www.mobile.xqnqq.com/Article/812844.shtml
- http://http://www.read.usuhx.com/Article/2543.shtml
- http://http://www.read.usuhx.com/Article/8215022.shtml
- http://http://www.mobile.xqnqq.com/Article/530381.shtml
- http://http://www.mobile.xqnqq.com/Article/4161.shtml
- http://http://www.mobile.xqnqq.com/Article/4066.shtml
- http://http://www.mobile.xqnqq.com/Article/4398.shtml
- http://http://www.read.usuhx.com/Article/2803734.shtml
- http://http://www.read.usuhx.com/Article/1337356.shtml
- http://http://www.read.usuhx.com/Article/0258646.shtml
- http://http://www.mobile.xqnqq.com/Article/36253.shtml
- http://http://www.read.usuhx.com/Article/26010.shtml
- http://http://www.read.usuhx.com/Article/602695.shtml
- http://http://www.read.usuhx.com/Article/7021.shtml
- http://http://www.read.usuhx.com/Article/139586.shtml
- http://http://www.read.usuhx.com/Article/4421.shtml
- http://http://www.mobile.xqnqq.com/Article/8936620.shtml
- http://http://www.mobile.xqnqq.com/Article/8100.shtml
- http://http://www.mobile.xqnqq.com/Article/7376.shtml
- http://http://www.mobile.xqnqq.com/Article/13274.shtml
- http://http://www.mobile.xqnqq.com/Article/0551.shtml
- http://http://www.mobile.xqnqq.com/Article/217937.shtml
- http://http://www.read.usuhx.com/Article/9132.shtml
- http://http://www.read.usuhx.com/Article/222037.shtml
- http://http://www.read.usuhx.com/Article/3105.shtml
- http://http://www.read.usuhx.com/Article/030682.shtml
- http://http://www.mobile.xqnqq.com/Article/387247.shtml
- http://http://www.mobile.xqnqq.com/Article/1824.shtml
- http://http://www.read.usuhx.com/Article/89096.shtml
- http://http://www.mobile.xqnqq.com/Article/6424362.shtml
- http://http://www.read.usuhx.com/Article/1211.shtml
- http://http://www.mobile.xqnqq.com/Article/996517.shtml
- http://http://www.mobile.xqnqq.com/Article/137197.shtml
- http://http://www.read.usuhx.com/Article/796180.shtml
- http://http://www.read.usuhx.com/Article/14814.shtml
- http://http://www.read.usuhx.com/Article/0564243.shtml
- http://http://www.read.usuhx.com/Article/1603.shtml
- http://http://www.mobile.xqnqq.com/Article/30588.shtml
- http://http://www.mobile.xqnqq.com/Article/1222731.shtml
- http://http://www.mobile.xqnqq.com/Article/561253.shtml
- http://http://www.mobile.xqnqq.com/Article/5849.shtml
- http://http://www.mobile.xqnqq.com/Article/4608.shtml
- http://http://www.mobile.xqnqq.com/Article/5769.shtml
- http://http://www.read.usuhx.com/Article/8647362.shtml
- http://http://www.mobile.xqnqq.com/Article/0912600.shtml
- http://http://www.read.usuhx.com/Article/86709.shtml
- http://http://www.read.usuhx.com/Article/85912.shtml
- http://http://www.read.usuhx.com/Article/6321.shtml
- http://http://www.read.usuhx.com/Article/9652.shtml
- http://http://www.mobile.xqnqq.com/Article/409254.shtml
- http://http://www.read.usuhx.com/Article/602902.shtml
- http://http://www.read.usuhx.com/Article/4860.shtml
- http://http://www.mobile.xqnqq.com/Article/35706.shtml
- http://http://www.mobile.xqnqq.com/Article/897737.shtml
- http://http://www.mobile.xqnqq.com/Article/069629.shtml
- http://http://www.read.usuhx.com/Article/4691.shtml
- http://http://www.read.usuhx.com/Article/26881.shtml
- http://http://www.mobile.xqnqq.com/Article/85474.shtml
- http://http://www.read.usuhx.com/Article/0203.shtml
- http://http://www.mobile.xqnqq.com/Article/4216.shtml
- http://http://www.mobile.xqnqq.com/Article/321869.shtml
- http://http://www.mobile.xqnqq.com/Article/80145.shtml
- http://http://www.read.usuhx.com/Article/1676.shtml
- http://http://www.mobile.xqnqq.com/Article/2922078.shtml
- http://http://www.mobile.xqnqq.com/Article/954661.shtml
- http://http://www.mobile.xqnqq.com/Article/6119378.shtml
- http://http://www.read.usuhx.com/Article/71429.shtml
- http://http://www.mobile.xqnqq.com/Article/2202.shtml
- http://http://www.mobile.xqnqq.com/Article/69430.shtml
- http://http://www.read.usuhx.com/Article/5662.shtml
- http://http://www.mobile.xqnqq.com/Article/870378.shtml
- http://http://www.read.usuhx.com/Article/46248.shtml
- http://http://www.mobile.xqnqq.com/Article/9295732.shtml
- http://http://www.mobile.xqnqq.com/Article/2762.shtml
- http://http://www.mobile.xqnqq.com/Article/816612.shtml
- http://http://www.read.usuhx.com/Article/2691.shtml
- http://http://www.mobile.xqnqq.com/Article/123029.shtml
- http://http://www.mobile.xqnqq.com/Article/5276668.shtml
- http://http://www.read.usuhx.com/Article/0934845.shtml
- http://http://www.mobile.xqnqq.com/Article/3351.shtml
- http://http://www.mobile.xqnqq.com/Article/8416.shtml
- http://http://www.read.usuhx.com/Article/4054.shtml
- http://http://www.mobile.xqnqq.com/Article/3958078.shtml
- http://http://www.mobile.xqnqq.com/Article/0352592.shtml
- http://http://www.mobile.xqnqq.com/Article/31651.shtml
- http://http://www.read.usuhx.com/Article/3059.shtml
- http://http://www.read.usuhx.com/Article/5719159.shtml
- http://http://www.read.usuhx.com/Article/7316.shtml
- http://http://www.mobile.xqnqq.com/Article/317200.shtml
- http://http://www.read.usuhx.com/Article/60051.shtml
- http://http://www.mobile.xqnqq.com/Article/721368.shtml
- http://http://www.read.usuhx.com/Article/788522.shtml
- http://http://www.read.usuhx.com/Article/790637.shtml
- http://http://www.read.usuhx.com/Article/183796.shtml
- http://http://www.read.usuhx.com/Article/46874.shtml
- http://http://www.mobile.xqnqq.com/Article/0442661.shtml
- http://http://www.mobile.xqnqq.com/Article/65685.shtml
- http://http://www.read.usuhx.com/Article/96798.shtml
- http://http://www.read.usuhx.com/Article/2862.shtml
- http://http://www.mobile.xqnqq.com/Article/1610109.shtml

## 项目结构

```
webforward/
├── src/                           # 源代码主目录
│   ├── core/                      # 核心逻辑模块
│   │   ├── indexer.js             # 资源索引构建与更新
│   │   ├── parser.js              # URL 解析与规范化处理
│   │   └── validator.js           # 链接格式校验与去重
│   ├── server/                    # HTTP 服务层
│   │   ├── app.js                # Express 应用入口与路由挂载
│   │   ├── routes.js             # API 路由定义（资源查询、统计、状态）
│   │   └── middleware.js         # 请求日志、跨域、静态资源缓存中间件
│   ├── frontend/                  # 前端界面资源
│   │   ├── views/                # 模板视图文件（EJS 模板）
│   │   ├── static/               # 静态资产（CSS、JavaScript、图片）
│   │   └── components/           # 可复用的前端 UI 组件
│   ├── worker/                    # 后台任务处理
│   │   ├── health-check.js       # 链接可达性定时检测任务
│   │   └── report-generator.js   # 健康度报表生成
│   └── cli/                       # 命令行工具入口
│       ├── import.js             # 批量导入命令
│       └── build.js              # 静态站点生成命令
├── data/                          # 数据存储目录
│   ├── resources.json            # 主资源列表（核心数据文件）
│   ├── tags.json                 # 分类标签定义
│   └── metrics.db               # SQLite 轻量数据库（存储点击统计与检测记录）
├── tests/                         # 单元测试与集成测试
│   ├── unit/                     # 单元测试用例
│   └── integration/              # 端到端集成测试脚本
├── docs/                          # 项目文档（快速入门、配置手册、开发指南、运维手册）
├── scripts/                       # 辅助脚本（部署、数据迁移、环境初始化）
├── config/                        # 环境配置文件
│   ├── default.yaml              # 默认配置
│   └── production.yaml.example   # 生产环境配置示例
├── package.json                   # Node.js 项目清单与依赖声明
├── README.md                      # 项目说明文档（本文件）
└── LICENSE                        # MIT 许可证文本
```

## 贡献指南

1. 在 GitHub 上 Fork 本仓库至个人账户，随后将 Fork 后的仓库克隆至本地开发环境。请确保使用 Git 2.40 及以上版本，并配置好用户签名信息。

2. 创建一个新的功能分支，分支名称需清晰描述本次变更内容，例如 `feat/add-import-filter` 或 `fix/health-check-timeout`。请勿在主分支或 develop 分支上直接修改。

3. 完成代码修改后，请运行完整的测试套件以确保未破坏现有功能。测试命令为 `npm test`，包含单元测试与集成测试。新增功能必须附带对应的测试用例。

4. 提交前请检查代码格式是否符合项目 ESLint 配置，运行 `npm run lint` 进行静态检查。所有警告和错误需修复后方可提交。提交信息应遵循 Conventional Commits 规范，格式为 `<type>(<scope>): <subject>`。

5. 推送分支至个人 Fork 仓库，并通过 GitHub 界面发起 Pull Request 至本仓库的 `develop` 分支。PR 描述中需说明变更目的、实现方式及影响范围，并关联相关 Issue（如有）。

## 常见问题

问：系统最多能管理多少条资源链接？性能是否会随链接数量增加而下降？

答：系统设计上对资源数量没有硬性上限。在默认配置下，静态资源列表加载后全量缓存在内存中，对于 5000 条以内的链接，前端检索响应时间可控制在 300 毫秒以内。超过 5000 条时，建议启用分页加载模式（配置文件中设置 `pagination.enabled: true`），并将静态生成改为按需增量构建。后台健康检测任务建议配合队列机制分批执行，避免单次检测任务阻塞事件循环。

问：如何迁移已有的书签数据或第三方收藏夹内容到 WebForward？

答：系统内置了 `npm run import -- --from=html` 命令，支持导入浏览器导出的 HTML 书签文件（适用于 Chrome、Firefox、Edge 的收藏夹导出格式）。此外还支持 `--from=csv` 模式，CSV 文件需包含 `url`、`title`、`tags` 三列。导入工具会自动识别 URL 格式并剔除无效条目，生成冲突报告保存于 `data/import-report.json`。对于非标准格式的数据源，建议先转换为 CSV 再执行导入。

问：部署到生产环境后，如何配置链接健康检测的自动通知？

答：健康检测任务由 `src/worker/health-check.js` 模块驱动，默认每 24 小时执行一次。检测结果会写入 `data/metrics.db` 数据库。如需开启通知，可在生产配置文件中设置 `notify.enabled: true`，并配置 `notify.webhook` 字段为目标 Webhook 地址（支持飞书、钉钉、企业微信机器人和通用 Slack 兼容接口）。检测到连续三次不可达的链接时，系统会主动推送告警消息到配置的 Webhook 端点，消息内容包含链接原文、失败次数及最近一次检测时间。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
