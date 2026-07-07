# LinkMap 技术资源导航站

LinkMap 是一个面向开发者、技术研究人员与运维工程师的轻量级技术资源外链汇总与导航系统。该项目定位于将分散于互联网各处的优质技术文章、工具文档、开源组件说明与运维案例集中管理，通过结构化的分类与索引机制，帮助技术团队快速定位所需信息。LinkMap 适用于搭建内部技术知识库的补充检索层、开源项目文档的外部引用锚点，以及个人技术研究过程中的临时书签系统。

## 功能概览

- **多源链接聚合管理** 支持从多个域名来源批量导入外链，自动识别链接元数据并生成索引条目。
- **分类标签与全文检索** 每个链接可附加多级分类标签，配合标题与摘要的模糊搜索，实现高效定位。
- **文章快照与摘要提取** 自动抓取目标页面的标题、发布时间与正文前200字符，生成预览摘要。
- **定期健康检查** 内置链接存活检测任务，每日检查所有外链的可访问性，标记失效链接并生成报告。
- **导入导出标准格式** 支持 CSV、JSON 和 Markdown 列表格式的批量导入与导出，便于与其他系统集成。
- **访问统计与热度排序** 记录每个外链的点击次数与最后访问时间，支持按热度、更新时间或创建时间排序。
- **用户自定义分类体系** 允许管理员创建多级分类树，并将链接灵活挂载到不同分类节点下。
- **RSS 订阅与更新通知** 为每个分类生成独立的 RSS 订阅源，方便团队订阅关注领域的最新收录动态。

## 应用场景

**技术团队内部知识库的外链补充** 研发团队在使用 Confluence 或 Notion 管理内部文档时，可将 LinkMap 作为外部参考资料的中转站，将常见故障处理方案、第三方库官方文档、云服务规格说明等外链统一收录，避免在内部文档中散落大量冗长 URL。

**开源项目文档的外部引用锚点管理** 开源项目维护者可以在 README 或 Wiki 中引用 LinkMap 中收录的参考链接，当外部资源地址发生变更时，只需在 LinkMap 中更新一次，所有引用处自动生效，减少文档维护成本。

**技术研究人员的个人书签系统** 研究人员在阅读技术博客、论文预印本或 GitHub 仓库时，可通过 LinkMap 的快速添加功能保存链接，并附加研究主题标签，后续按标签回溯时无需依赖浏览器书签的文件夹层级限制。

**运维故障排查的快速跳转面板** 运维团队可将常见的监控面板地址、日志查询入口、云服务控制台链接及内部运维脚本仓库地址集中配置在 LinkMap 中，并设置快捷访问分组，在故障处理时快速跳转。

**技术资讯聚合与每日阅读清单** 将关注的技术博客、新闻站点、周报链接导入 LinkMap 后，通过 RSS 订阅功能生成统一的阅读列表，每日定时获取更新状态。

## 快速开始

以下命令适用于 Linux 与 macOS 环境，Windows 用户建议使用 WSL2 或 Git Bash 执行。

```bash
# 克隆项目仓库
git clone https://github.com/linkmap-io/linkmap-station.git
cd linkmap-station

# 安装依赖（Python 3.10+ 与 Node.js 18+）
pip install -r requirements.txt
npm install --prefix frontend

# 初始化数据库并导入示例数据
python manage.py migrate
python manage.py loaddata seed_data.json

# 启动开发服务（后端端口 8000，前端端口 3000）
python manage.py runserver &
npm run dev --prefix frontend
```

访问 http://localhost:3000 进入前端界面，默认管理员账号 admin / admin123。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Python | 3.10 至 3.12 | 后端核心运行环境，3.13 暂不支持 |
| Node.js | 18.x 或 20.x LTS | 前端构建与开发服务器依赖 |
| PostgreSQL | 14 及以上 | 生产环境推荐，开发可使用 SQLite |
| Redis | 6.2 及以上 | 缓存与任务队列后端（健康检查任务使用） |
| Nginx | 1.22 及以上 | 生产环境反向代理与静态文件服务 |
| git | 2.30 及以上 | 版本控制与自动更新脚本依赖 |
| pip | 22.0 及以上 | Python 依赖管理工具 |
| npm | 9.0 及以上 | Node.js 包管理器 |
| Celery | 5.3 及以上 | 异步任务队列（链接健康检查） |
| Docker | 24.0 及以上 | 可选，用于容器化部署 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|----------|
| 入门指南 | /docs/quickstart.md | 如何在 10 分钟内完成首次部署并导入第一批链接 |
| 管理员手册 | /docs/admin-guide.md | 如何管理分类体系、批量导入导出、配置健康检查策略 |
| API 参考 | /docs/api-reference.md | 所有 RESTful 接口的请求参数、返回结构与鉴权方式 |
| 部署运维 | /docs/deployment.md | 生产环境下的 Nginx 配置、SSL 证书、进程守护与备份策略 |
| 二次开发 | /docs/development.md | 如何扩展自定义抓取解析器、增加新的统计维度 |
| 配置说明 | /docs/configuration.md | 环境变量清单、配置文件结构及各模块开关说明 |
| 常见问题 | /docs/faq.md | 收录链接失效后的处理、搜索结果不准确等日常疑问 |
| 版本记录 | /docs/changelog.md | 各版本新增功能、修复缺陷与 Breaking Changes 说明 |

## 资源列表

- http://http://map.mobile.xqnqq.com/Article/4759.shtml
- http://http://map.read.usuhx.com/Article/40621.shtml
- http://http://map.read.usuhx.com/Article/609261.shtml
- http://http://map.read.usuhx.com/Article/15481.shtml
- http://http://map.read.usuhx.com/Article/0442900.shtml
- http://http://map.mobile.xqnqq.com/Article/9430.shtml
- http://http://map.read.usuhx.com/Article/0145089.shtml
- http://http://map.read.usuhx.com/Article/705342.shtml
- http://http://map.mobile.xqnqq.com/Article/9894603.shtml
- http://http://map.mobile.xqnqq.com/Article/4602.shtml
- http://http://map.mobile.xqnqq.com/Article/68992.shtml
- http://http://map.mobile.xqnqq.com/Article/384852.shtml
- http://http://map.mobile.xqnqq.com/Article/8914199.shtml
- http://http://map.mobile.xqnqq.com/Article/71165.shtml
- http://http://map.read.usuhx.com/Article/7991856.shtml
- http://http://map.mobile.xqnqq.com/Article/7284975.shtml
- http://http://map.mobile.xqnqq.com/Article/17680.shtml
- http://http://map.read.usuhx.com/Article/073429.shtml
- http://http://map.mobile.xqnqq.com/Article/5145.shtml
- http://http://map.read.usuhx.com/Article/9503.shtml
- http://http://map.mobile.xqnqq.com/Article/1872783.shtml
- http://http://map.mobile.xqnqq.com/Article/039292.shtml
- http://http://map.read.usuhx.com/Article/08049.shtml
- http://http://map.mobile.xqnqq.com/Article/17057.shtml
- http://http://map.read.usuhx.com/Article/959197.shtml
- http://http://map.mobile.xqnqq.com/Article/162538.shtml
- http://http://map.read.usuhx.com/Article/165834.shtml
- http://http://map.mobile.xqnqq.com/Article/21731.shtml
- http://http://map.mobile.xqnqq.com/Article/1750.shtml
- http://http://map.read.usuhx.com/Article/5436674.shtml
- http://http://map.read.usuhx.com/Article/9268.shtml
- http://http://map.mobile.xqnqq.com/Article/5092.shtml
- http://http://map.read.usuhx.com/Article/7193.shtml
- http://http://map.read.usuhx.com/Article/022235.shtml
- http://http://map.read.usuhx.com/Article/2460077.shtml
- http://http://map.read.usuhx.com/Article/6788089.shtml
- http://http://map.read.usuhx.com/Article/5135786.shtml
- http://http://map.mobile.xqnqq.com/Article/6131638.shtml
- http://http://map.read.usuhx.com/Article/9018553.shtml
- http://http://map.read.usuhx.com/Article/1864385.shtml
- http://http://map.read.usuhx.com/Article/38336.shtml
- http://http://map.read.usuhx.com/Article/5147701.shtml
- http://http://map.mobile.xqnqq.com/Article/38092.shtml
- http://http://map.read.usuhx.com/Article/2141461.shtml
- http://http://map.read.usuhx.com/Article/424680.shtml
- http://http://map.mobile.xqnqq.com/Article/9826.shtml
- http://http://map.mobile.xqnqq.com/Article/579305.shtml
- http://http://map.read.usuhx.com/Article/3906.shtml
- http://http://map.mobile.xqnqq.com/Article/3817.shtml
- http://http://map.mobile.xqnqq.com/Article/2069235.shtml
- http://http://map.read.usuhx.com/Article/4460807.shtml
- http://http://map.mobile.xqnqq.com/Article/6133.shtml
- http://http://map.mobile.xqnqq.com/Article/148044.shtml
- http://http://map.mobile.xqnqq.com/Article/9642533.shtml
- http://http://map.mobile.xqnqq.com/Article/6237.shtml
- http://http://map.mobile.xqnqq.com/Article/76627.shtml
- http://http://map.mobile.xqnqq.com/Article/810621.shtml
- http://http://map.mobile.xqnqq.com/Article/6382.shtml
- http://http://map.mobile.xqnqq.com/Article/63476.shtml
- http://http://map.read.usuhx.com/Article/97528.shtml
- http://http://map.mobile.xqnqq.com/Article/33560.shtml
- http://http://map.read.usuhx.com/Article/98295.shtml
- http://http://map.read.usuhx.com/Article/57143.shtml
- http://http://map.read.usuhx.com/Article/35489.shtml
- http://http://map.mobile.xqnqq.com/Article/67069.shtml
- http://http://map.mobile.xqnqq.com/Article/6905289.shtml
- http://http://map.read.usuhx.com/Article/19037.shtml
- http://http://map.read.usuhx.com/Article/199707.shtml
- http://http://map.mobile.xqnqq.com/Article/756318.shtml
- http://http://map.mobile.xqnqq.com/Article/78085.shtml
- http://http://map.read.usuhx.com/Article/8562527.shtml
- http://http://map.read.usuhx.com/Article/854915.shtml
- http://http://map.read.usuhx.com/Article/7599319.shtml
- http://http://map.mobile.xqnqq.com/Article/6826.shtml
- http://http://map.read.usuhx.com/Article/252131.shtml
- http://http://map.read.usuhx.com/Article/9603611.shtml
- http://http://map.mobile.xqnqq.com/Article/00969.shtml
- http://http://map.mobile.xqnqq.com/Article/7600149.shtml
- http://http://map.mobile.xqnqq.com/Article/419847.shtml
- http://http://map.mobile.xqnqq.com/Article/07593.shtml
- http://http://map.read.usuhx.com/Article/3079236.shtml
- http://http://map.read.usuhx.com/Article/8155.shtml
- http://http://map.read.usuhx.com/Article/4386.shtml
- http://http://map.read.usuhx.com/Article/6162.shtml
- http://http://map.mobile.xqnqq.com/Article/4412300.shtml
- http://http://map.mobile.xqnqq.com/Article/5422440.shtml
- http://http://map.read.usuhx.com/Article/017278.shtml
- http://http://map.mobile.xqnqq.com/Article/5814143.shtml
- http://http://map.read.usuhx.com/Article/54122.shtml
- http://http://map.mobile.xqnqq.com/Article/9742476.shtml
- http://http://map.read.usuhx.com/Article/2475.shtml
- http://http://map.read.usuhx.com/Article/00770.shtml
- http://http://map.read.usuhx.com/Article/3305538.shtml
- http://http://map.mobile.xqnqq.com/Article/488086.shtml
- http://http://map.read.usuhx.com/Article/41772.shtml
- http://http://map.read.usuhx.com/Article/15459.shtml
- http://http://map.mobile.xqnqq.com/Article/45267.shtml
- http://http://map.mobile.xqnqq.com/Article/4340430.shtml
- http://http://map.mobile.xqnqq.com/Article/87515.shtml
- http://http://map.read.usuhx.com/Article/68436.shtml
- http://http://map.read.usuhx.com/Article/178467.shtml
- http://http://map.mobile.xqnqq.com/Article/52346.shtml
- http://http://map.mobile.xqnqq.com/Article/1775699.shtml
- http://http://map.read.usuhx.com/Article/41922.shtml
- http://http://map.read.usuhx.com/Article/36357.shtml
- http://http://map.mobile.xqnqq.com/Article/6739.shtml
- http://http://map.read.usuhx.com/Article/81339.shtml
- http://http://map.read.usuhx.com/Article/45965.shtml
- http://http://map.mobile.xqnqq.com/Article/078562.shtml
- http://http://map.read.usuhx.com/Article/7536.shtml
- http://http://map.mobile.xqnqq.com/Article/21510.shtml
- http://http://map.mobile.xqnqq.com/Article/753731.shtml
- http://http://map.mobile.xqnqq.com/Article/44717.shtml
- http://http://map.mobile.xqnqq.com/Article/935594.shtml
- http://http://map.mobile.xqnqq.com/Article/898988.shtml
- http://http://map.mobile.xqnqq.com/Article/8084.shtml
- http://http://map.mobile.xqnqq.com/Article/1049.shtml
- http://http://map.read.usuhx.com/Article/8905.shtml
- http://http://map.read.usuhx.com/Article/3083923.shtml
- http://http://map.read.usuhx.com/Article/09960.shtml
- http://http://map.mobile.xqnqq.com/Article/7817096.shtml
- http://http://map.mobile.xqnqq.com/Article/014843.shtml
- http://http://map.read.usuhx.com/Article/3714.shtml
- http://http://map.read.usuhx.com/Article/5229.shtml
- http://http://map.read.usuhx.com/Article/1106.shtml
- http://http://map.read.usuhx.com/Article/180744.shtml
- http://http://map.mobile.xqnqq.com/Article/1955.shtml
- http://http://map.mobile.xqnqq.com/Article/387848.shtml
- http://http://map.read.usuhx.com/Article/1876.shtml
- http://http://map.read.usuhx.com/Article/3287475.shtml
- http://http://map.mobile.xqnqq.com/Article/4935676.shtml
- http://http://map.mobile.xqnqq.com/Article/78984.shtml
- http://http://map.mobile.xqnqq.com/Article/1202817.shtml
- http://http://map.read.usuhx.com/Article/2460675.shtml
- http://http://map.mobile.xqnqq.com/Article/44063.shtml
- http://http://map.read.usuhx.com/Article/446680.shtml
- http://http://map.mobile.xqnqq.com/Article/1137165.shtml
- http://http://map.read.usuhx.com/Article/5647.shtml
- http://http://map.read.usuhx.com/Article/966666.shtml
- http://http://map.mobile.xqnqq.com/Article/5819959.shtml
- http://http://map.read.usuhx.com/Article/973626.shtml
- http://http://map.read.usuhx.com/Article/4175.shtml
- http://http://map.read.usuhx.com/Article/7222.shtml
- http://http://map.mobile.xqnqq.com/Article/8852.shtml
- http://http://map.mobile.xqnqq.com/Article/33688.shtml
- http://http://map.read.usuhx.com/Article/5568.shtml
- http://http://map.mobile.xqnqq.com/Article/879215.shtml
- http://http://map.mobile.xqnqq.com/Article/754832.shtml
- http://http://map.mobile.xqnqq.com/Article/433104.shtml
- http://http://map.mobile.xqnqq.com/Article/4526625.shtml
- http://http://map.read.usuhx.com/Article/6822087.shtml
- http://http://map.mobile.xqnqq.com/Article/748636.shtml
- http://http://map.mobile.xqnqq.com/Article/1010338.shtml
- http://http://map.read.usuhx.com/Article/1231957.shtml
- http://http://map.read.usuhx.com/Article/0931029.shtml
- http://http://map.read.usuhx.com/Article/635759.shtml
- http://http://map.mobile.xqnqq.com/Article/644849.shtml
- http://http://map.mobile.xqnqq.com/Article/7658.shtml
- http://http://map.read.usuhx.com/Article/12684.shtml
- http://http://map.read.usuhx.com/Article/030378.shtml
- http://http://map.mobile.xqnqq.com/Article/442501.shtml
- http://http://map.mobile.xqnqq.com/Article/4378075.shtml
- http://http://map.mobile.xqnqq.com/Article/515213.shtml
- http://http://map.read.usuhx.com/Article/31253.shtml
- http://http://map.mobile.xqnqq.com/Article/2769.shtml
- http://http://map.mobile.xqnqq.com/Article/227663.shtml
- http://http://map.mobile.xqnqq.com/Article/1664352.shtml
- http://http://map.mobile.xqnqq.com/Article/1111.shtml
- http://http://map.mobile.xqnqq.com/Article/8127.shtml
- http://http://map.read.usuhx.com/Article/97512.shtml
- http://http://map.read.usuhx.com/Article/0552918.shtml
- http://http://map.mobile.xqnqq.com/Article/1033.shtml
- http://http://map.read.usuhx.com/Article/6952379.shtml
- http://http://map.read.usuhx.com/Article/81856.shtml
- http://http://map.read.usuhx.com/Article/5884.shtml
- http://http://map.mobile.xqnqq.com/Article/58149.shtml
- http://http://map.read.usuhx.com/Article/3665087.shtml
- http://http://map.mobile.xqnqq.com/Article/9871107.shtml
- http://http://map.mobile.xqnqq.com/Article/8730.shtml
- http://http://map.mobile.xqnqq.com/Article/0090.shtml
- http://http://map.mobile.xqnqq.com/Article/358365.shtml
- http://http://map.read.usuhx.com/Article/47782.shtml
- http://http://map.read.usuhx.com/Article/5474871.shtml
- http://http://map.mobile.xqnqq.com/Article/4678.shtml
- http://http://map.mobile.xqnqq.com/Article/434283.shtml
- http://http://map.read.usuhx.com/Article/43079.shtml
- http://http://map.mobile.xqnqq.com/Article/467964.shtml
- http://http://map.mobile.xqnqq.com/Article/2201.shtml
- http://http://map.read.usuhx.com/Article/23947.shtml
- http://http://map.mobile.xqnqq.com/Article/1385.shtml
- http://http://map.read.usuhx.com/Article/2436120.shtml
- http://http://map.mobile.xqnqq.com/Article/37368.shtml
- http://http://map.read.usuhx.com/Article/6547.shtml
- http://http://map.mobile.xqnqq.com/Article/5106981.shtml
- http://http://map.mobile.xqnqq.com/Article/505643.shtml
- http://http://map.read.usuhx.com/Article/4043.shtml
- http://http://map.read.usuhx.com/Article/70307.shtml
- http://http://map.read.usuhx.com/Article/8264102.shtml
- http://http://map.read.usuhx.com/Article/6917.shtml
- http://http://map.read.usuhx.com/Article/2062659.shtml
- http://http://map.mobile.xqnqq.com/Article/931366.shtml
- http://http://map.mobile.xqnqq.com/Article/4342998.shtml
- http://http://map.read.usuhx.com/Article/9943824.shtml
- http://http://map.read.usuhx.com/Article/0098.shtml
- http://http://map.mobile.xqnqq.com/Article/428491.shtml
- http://http://map.mobile.xqnqq.com/Article/738966.shtml
- http://http://map.mobile.xqnqq.com/Article/7046711.shtml
- http://http://map.read.usuhx.com/Article/1563445.shtml
- http://http://map.mobile.xqnqq.com/Article/5996977.shtml
- http://http://map.mobile.xqnqq.com/Article/7388153.shtml
- http://http://map.read.usuhx.com/Article/92994.shtml
- http://http://map.read.usuhx.com/Article/9397439.shtml
- http://http://map.mobile.xqnqq.com/Article/0008313.shtml
- http://http://map.mobile.xqnqq.com/Article/1113025.shtml
- http://http://map.read.usuhx.com/Article/5461.shtml
- http://http://map.read.usuhx.com/Article/32543.shtml
- http://http://map.mobile.xqnqq.com/Article/1923.shtml
- http://http://map.mobile.xqnqq.com/Article/946721.shtml
- http://http://map.read.usuhx.com/Article/614650.shtml
- http://http://map.mobile.xqnqq.com/Article/8858.shtml
- http://http://map.mobile.xqnqq.com/Article/428196.shtml
- http://http://map.mobile.xqnqq.com/Article/274253.shtml
- http://http://map.mobile.xqnqq.com/Article/6244.shtml
- http://http://map.read.usuhx.com/Article/0655.shtml
- http://http://map.mobile.xqnqq.com/Article/4337503.shtml
- http://http://map.read.usuhx.com/Article/605237.shtml
- http://http://map.mobile.xqnqq.com/Article/169474.shtml
- http://http://map.read.usuhx.com/Article/1022.shtml
- http://http://map.mobile.xqnqq.com/Article/183797.shtml
- http://http://map.read.usuhx.com/Article/615691.shtml
- http://http://map.read.usuhx.com/Article/9028411.shtml
- http://http://map.mobile.xqnqq.com/Article/198732.shtml
- http://http://map.mobile.xqnqq.com/Article/0169.shtml
- http://http://map.read.usuhx.com/Article/0553124.shtml
- http://http://map.read.usuhx.com/Article/00569.shtml
- http://http://map.read.usuhx.com/Article/15561.shtml
- http://http://map.read.usuhx.com/Article/67313.shtml
- http://http://map.read.usuhx.com/Article/3086.shtml
- http://http://map.mobile.xqnqq.com/Article/04921.shtml
- http://http://map.read.usuhx.com/Article/57916.shtml
- http://http://map.mobile.xqnqq.com/Article/29510.shtml
- http://http://map.read.usuhx.com/Article/54436.shtml
- http://http://map.read.usuhx.com/Article/67191.shtml
- http://http://map.mobile.xqnqq.com/Article/61317.shtml
- http://http://map.read.usuhx.com/Article/7415724.shtml
- http://http://map.mobile.xqnqq.com/Article/8202.shtml
- http://http://map.read.usuhx.com/Article/597102.shtml
- http://http://map.mobile.xqnqq.com/Article/1868.shtml
- http://http://map.mobile.xqnqq.com/Article/2446.shtml
- http://http://map.mobile.xqnqq.com/Article/57412.shtml

## 项目结构

```
linkmap-station/
├── backend/                                # 后端 Django 应用主目录
│   ├── manage.py                           # Django 项目管理脚本
│   ├── config/                             # 全局配置模块
│   │   ├── settings.py                     # 主配置文件（数据库、缓存、中间件）
│   │   ├── urls.py                         # 根路由分发器
│   │   └── celery.py                       # Celery 任务队列配置
│   ├── apps/                               # 所有子应用集合
│   │   ├── links/                          # 链接管理核心应用
│   │   │   ├── models.py                   # Link、Category、Tag 数据模型
│   │   │   ├── views.py                    # RESTful API 视图集
│   │   │   ├── serializers.py              # 序列化器与数据校验
│   │   │   └── tasks.py                    # 健康检查、摘要抓取异步任务
│   │   ├── users/                          # 用户认证与权限管理
│   │   │   ├── models.py                   # 用户扩展信息与角色
│   │   │   └── permissions.py              # 自定义权限类
│   │   └── stats/                          # 访问统计与热度计算
│   │       ├── models.py                   # 点击日志与聚合统计
│   │       └── middleware.py               # 请求拦截与异步落库
│   ├── libs/                               # 公共工具库
│   │   ├── fetcher.py                      # HTTP 请求封装与重试策略
│   │   ├── parser.py                       # HTML 元数据解析器
│   │   └── exporter.py                     # CSV/JSON/Markdown 导出器
│   └── tests/                              # 单元测试与集成测试
│       ├── test_models.py                  # 模型层测试用例
│       └── test_api.py                     # API 接口测试
├── frontend/                               # 前端 Vue 3 单页应用
│   ├── src/
│   │   ├── views/                          # 页面级组件
│   │   │   ├── Dashboard.vue               # 总览面板（统计卡片与趋势图）
│   │   │   ├── LinkList.vue                # 链接列表与搜索筛选
│   │   │   ├── LinkEditor.vue              # 新增/编辑链接表单
│   │   │   └── CategoryManager.vue         # 分类树管理界面
│   │   ├── components/                     # 可复用 UI 组件
│   │   │   ├── LinkCard.vue                # 单条链接展示卡片
│   │   │   └── SearchBar.vue               # 全局搜索输入框
│   │   ├── stores/                         # Pinia 状态管理
│   │   │   ├── linkStore.js                # 链接数据 CRUD 状态
│   │   │   └── userStore.js                # 登录状态与权限标识
│   │   └── router/                         # 客户端路由定义
│   ├── package.json                        # 前端依赖声明
│   └── vite.config.js                      # 构建工具配置
├── docker/                                 # 容器化部署文件
│   ├── Dockerfile.backend                  # 后端镜像构建脚本
│   ├── Dockerfile.frontend                 # 前端镜像构建脚本
│   └── docker-compose.yml                  # 多服务编排（PostgreSQL + Redis + Nginx）
├── scripts/                                # 运维与辅助脚本
│   ├── backup_db.sh                        # 数据库定时备份脚本
│   ├── import_links.py                     # 批量导入外链命令行工具
│   └── health_check_runner.py              # 手动触发健康检查脚本
├── docs/                                   # 完整文档目录
│   ├── quickstart.md                       # 快速入门指南
│   ├── admin-guide.md                      # 管理员操作手册
│   ├── api-reference.md                    # API 接口详细说明
│   ├── deployment.md                       # 生产环境部署流程
│   └── development.md                      # 二次开发环境搭建与规范
├── requirements.txt                        # Python 依赖清单
├── README.md                               # 项目说明文件（本文件）
└── LICENSE                                 # MIT 许可证文本
```

## 贡献指南

1. 在 GitHub 上 Fork 本仓库，并克隆到本地开发环境。创建新的功能分支时，请使用 `feature/` 或 `fix/` 前缀，例如 `feature/add-import-from-rss`。

2. 安装开发依赖并启动本地服务后，运行完整的测试套件确保现有功能未被破坏。新增功能需附带对应的单元测试与集成测试，测试覆盖率不低于 80%。

3. 提交代码前执行代码格式化工具（Black 用于 Python，Prettier 用于前端），并确保所有 lint 检查通过。提交信息遵循 Conventional Commits 规范，使用 `feat:`、`fix:`、`docs:`、`refactor:` 等类型前缀。

4. 对于新增功能或较大改动，请先在 Issues 中创建讨论帖，说明设计思路与实现方案，获得核心维护者反馈后再着手开发，避免无效提交。

5. 完成开发后发起 Pull Request 到主仓库的 `main` 分支，PR 描述中需明确关联对应的 Issue 编号，并附上测试结果截图或日志。PR 经过 Code Review 并通过 CI 流水线检查后合并。

## 常见问题

**问：导入大量外链时，链接健康检查任务导致服务响应缓慢，如何优化？**

答：健康检查任务默认使用 Celery 异步队列，建议在生产环境中将检查任务调度至独立的 Worker 进程，并设置并发数为 4 至 8。同时可在管理后台调整检查超时时间为 10 秒，并开启增量检查模式，仅检查 30 天内未更新的链接。对于大规模导入场景，建议分批次导入，每批不超过 500 条。

**问：自动抓取的摘要内容不完整或包含无关信息，能否自定义解析规则？**

答：系统提供可扩展的解析器接口。您可以在 `backend/libs/parser.py` 中继承 `BaseParser` 类，重写 `extract_title` 和 `extract_summary` 方法，针对特定域名编写专属选择器。配置文件中支持按域名匹配解析器类，实现差异化抓取策略。

**问：部署后无法访问前端页面，提示 API 请求跨域被拒绝，如何解决？**

答：检查后端 `settings.py` 中的 `CORS_ALLOWED_ORIGINS` 配置项，确保已将前端开发地址（如 http://localhost:3000）和生产域名加入白名单。生产环境建议使用 Nginx 反向代理统一端口，避免跨域问题。若使用 Docker Compose 部署，请确认环境变量 `FRONTEND_URL` 设置正确。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
