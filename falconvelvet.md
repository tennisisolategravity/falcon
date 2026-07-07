# LinkNavigator

LinkNavigator 是一个面向开发者和技术研究人员的结构化外链资源聚合平台，专注于对分散在多个内容源站点的技术文章、数据报告与工程实践文档进行统一采集、分类索引与快速检索。该项目的目标用户包括需要批量查阅移动端地图服务技术文档的研发团队、从事地理信息数据解析的数据工程师，以及需要追踪特定技术站点更新动态的技术决策者。

LinkNavigator 通过自动化采集流程与标准化元数据提取，将原始来源中大量非结构化的 HTML 文章页面转换为可被二次处理的资源清单，并提供命令行界面与 JSON API 两种使用方式。项目本身不存储文章内容，仅维护资源定位信息与基础分类标签，帮助用户在庞大且杂乱的外链数据中快速定位到真正需要的技术资料。

## 功能概览

- 多源并发采集：内置基于 asyncio 的异步 HTTP 客户端，支持同时对 map.mobile.xqnqq.com 与 map.read.usuhx.com 两个来源站点的文章列表进行并发拉取，显著缩短全量同步周期。

- 增量更新机制：通过记录每篇文章的最后抓取时间戳与内容哈希值，仅当源页面发生变更时才重新拉取，有效降低带宽消耗与源站压力。

- 元数据自动提取：从 HTML 文档中自动抽取标题、发布时间、正文前 200 字符摘要以及文章分类标签，并将其结构化存储于本地 SQLite 数据库中。

- 命令行检索工具：提供 nav-search 与 nav-list 两条核心命令，支持按关键词、来源域名、时间范围等多维度组合条件检索已收录的资源链接。

- JSON RESTful API：基于 FastAPI 构建只读查询接口，支持分页、排序与字段过滤，便于与其他内部系统或自动化脚本进行集成。

- 去重与死链检测：定期运行后台任务，对已收录的 URL 进行重复项合并与可访问性探测，自动标记响应状态码非 200 的链接。

## 应用场景

- 移动端地图服务文档归档：技术团队可将 map.mobile.xqnqq.com 下大量关于定位、轨迹绘制与瓦片加载的文章统一接入平台，构建内部知识库的补充数据源。

- 地理信息系统（GIS）数据解析参考：map.read.usuhx.com 域名下存放了大量与空间数据格式、坐标转换算法相关的案例文章，研究者可通过 LinkNavigator 快速筛选出特定主题的参考链接。

- 技术站点更新监控：运维人员可配置定时采集任务，每日获取两个站点的新增或更新文章列表，并将结果推送至企业微信或邮件组，替代手工逐页浏览。

- 外链数据迁移前评估：在进行站点改版或域名迁移时，可通过平台导出的完整资源清单快速评估原有外链的引用规模与分布情况，辅助制定重定向策略。

## 快速开始

以下指令适用于 Linux 与 macOS 环境，Windows 用户建议使用 WSL2 或 Git Bash 执行。

```bash
# 克隆项目仓库
git clone https://github.com/tech-resource/link-navigator.git
cd link-navigator

# 创建并激活 Python 虚拟环境
python3 -m venv venv
source venv/bin/activate

# 安装项目依赖
pip install --upgrade pip
pip install -r requirements.txt

# 执行首次全量采集（默认使用内置的 250 条初始资源清单）
python nav_cli.py sync --full

# 启动本地 API 服务（默认监听 8000 端口）
uvicorn nav_api:app --host 0.0.0.0 --port 8000 --reload
```

首次启动后，可通过浏览器访问 http://127.0.0.1:8000/docs 查看自动生成的 Swagger 接口文档。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 及以上 | 核心运行环境，不支持 3.8 以下版本 |
| aiohttp | 3.9.0 | 异步 HTTP 客户端，用于并发采集 |
| beautifulsoup4 | 4.12.0 | HTML 解析库，用于元数据提取 |
| fastapi | 0.115.0 | API 服务框架 |
| uvicorn | 0.30.0 | ASGI 服务器，用于生产环境部署 |
| sqlite3 | 内置模块 | 本地轻量级存储引擎，无需额外安装 |

建议在 Debian 12 / Ubuntu 22.04 或 macOS Ventura 及以上版本中运行，Windows 系统需确保已安装 Visual C++ Redistributable。

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 入门指南 | docs/quickstart.md | 如何快速搭建运行环境并执行首次采集？ |
| 配置参考 | docs/configuration.md | 如何调整并发数、超时时间与存储路径？ |
| 命令手册 | docs/cli_commands.md | sync、search、list、check 各命令的详细参数说明 |
| API 规范 | docs/api_reference.md | 所有 RESTful 接口的请求/响应格式与状态码定义 |

## 资源列表

- http://http://map.mobile.xqnqq.com/Article/0493435.shtml
- http://http://map.mobile.xqnqq.com/Article/1760.shtml
- http://http://map.read.usuhx.com/Article/116343.shtml
- http://http://map.mobile.xqnqq.com/Article/5960539.shtml
- http://http://map.mobile.xqnqq.com/Article/52050.shtml
- http://http://map.mobile.xqnqq.com/Article/0980759.shtml
- http://http://map.mobile.xqnqq.com/Article/5680497.shtml
- http://http://map.read.usuhx.com/Article/89700.shtml
- http://http://map.read.usuhx.com/Article/6397.shtml
- http://http://map.read.usuhx.com/Article/0556602.shtml
- http://http://map.read.usuhx.com/Article/148402.shtml
- http://http://map.mobile.xqnqq.com/Article/505682.shtml
- http://http://map.mobile.xqnqq.com/Article/98245.shtml
- http://http://map.read.usuhx.com/Article/62678.shtml
- http://http://map.mobile.xqnqq.com/Article/192390.shtml
- http://http://map.mobile.xqnqq.com/Article/782457.shtml
- http://http://map.read.usuhx.com/Article/2601208.shtml
- http://http://map.read.usuhx.com/Article/8671137.shtml
- http://http://map.mobile.xqnqq.com/Article/8508965.shtml
- http://http://map.read.usuhx.com/Article/2736.shtml
- http://http://map.read.usuhx.com/Article/8734.shtml
- http://http://map.mobile.xqnqq.com/Article/6265340.shtml
- http://http://map.mobile.xqnqq.com/Article/1029.shtml
- http://http://map.read.usuhx.com/Article/62983.shtml
- http://http://map.mobile.xqnqq.com/Article/5684400.shtml
- http://http://map.read.usuhx.com/Article/96137.shtml
- http://http://map.read.usuhx.com/Article/8322.shtml
- http://http://map.mobile.xqnqq.com/Article/4074.shtml
- http://http://map.read.usuhx.com/Article/4304.shtml
- http://http://map.read.usuhx.com/Article/9819.shtml
- http://http://map.mobile.xqnqq.com/Article/70185.shtml
- http://http://map.read.usuhx.com/Article/1315494.shtml
- http://http://map.mobile.xqnqq.com/Article/3722523.shtml
- http://http://map.read.usuhx.com/Article/6521875.shtml
- http://http://map.mobile.xqnqq.com/Article/97006.shtml
- http://http://map.mobile.xqnqq.com/Article/4303109.shtml
- http://http://map.read.usuhx.com/Article/6118.shtml
- http://http://map.mobile.xqnqq.com/Article/5580119.shtml
- http://http://map.read.usuhx.com/Article/6759578.shtml
- http://http://map.mobile.xqnqq.com/Article/178269.shtml
- http://http://map.read.usuhx.com/Article/8531980.shtml
- http://http://map.mobile.xqnqq.com/Article/308043.shtml
- http://http://map.mobile.xqnqq.com/Article/13675.shtml
- http://http://map.read.usuhx.com/Article/867035.shtml
- http://http://map.read.usuhx.com/Article/83205.shtml
- http://http://map.read.usuhx.com/Article/7415.shtml
- http://http://map.read.usuhx.com/Article/78723.shtml
- http://http://map.mobile.xqnqq.com/Article/99854.shtml
- http://http://map.mobile.xqnqq.com/Article/75650.shtml
- http://http://map.mobile.xqnqq.com/Article/2408.shtml
- http://http://map.mobile.xqnqq.com/Article/905595.shtml
- http://http://map.mobile.xqnqq.com/Article/2997.shtml
- http://http://map.mobile.xqnqq.com/Article/2134487.shtml
- http://http://map.mobile.xqnqq.com/Article/25254.shtml
- http://http://map.read.usuhx.com/Article/7436.shtml
- http://http://map.read.usuhx.com/Article/8359.shtml
- http://http://map.read.usuhx.com/Article/96431.shtml
- http://http://map.read.usuhx.com/Article/7182.shtml
- http://http://map.read.usuhx.com/Article/32733.shtml
- http://http://map.read.usuhx.com/Article/65327.shtml
- http://http://map.read.usuhx.com/Article/7426.shtml
- http://http://map.read.usuhx.com/Article/057831.shtml
- http://http://map.mobile.xqnqq.com/Article/455721.shtml
- http://http://map.read.usuhx.com/Article/629054.shtml
- http://http://map.mobile.xqnqq.com/Article/1863261.shtml
- http://http://map.mobile.xqnqq.com/Article/4671.shtml
- http://http://map.read.usuhx.com/Article/8681.shtml
- http://http://map.read.usuhx.com/Article/94983.shtml
- http://http://map.mobile.xqnqq.com/Article/3994133.shtml
- http://http://map.mobile.xqnqq.com/Article/65546.shtml
- http://http://map.mobile.xqnqq.com/Article/11093.shtml
- http://http://map.mobile.xqnqq.com/Article/5487488.shtml
- http://http://map.read.usuhx.com/Article/6881.shtml
- http://http://map.read.usuhx.com/Article/715642.shtml
- http://http://map.mobile.xqnqq.com/Article/0456.shtml
- http://http://map.read.usuhx.com/Article/97632.shtml
- http://http://map.mobile.xqnqq.com/Article/9251.shtml
- http://http://map.mobile.xqnqq.com/Article/44679.shtml
- http://http://map.read.usuhx.com/Article/9944.shtml
- http://http://map.read.usuhx.com/Article/31922.shtml
- http://http://map.read.usuhx.com/Article/22321.shtml
- http://http://map.read.usuhx.com/Article/9644791.shtml
- http://http://map.mobile.xqnqq.com/Article/3043.shtml
- http://http://map.mobile.xqnqq.com/Article/0233246.shtml
- http://http://map.read.usuhx.com/Article/3508.shtml
- http://http://map.mobile.xqnqq.com/Article/9258912.shtml
- http://http://map.read.usuhx.com/Article/13284.shtml
- http://http://map.read.usuhx.com/Article/5511050.shtml
- http://http://map.mobile.xqnqq.com/Article/81613.shtml
- http://http://map.mobile.xqnqq.com/Article/813062.shtml
- http://http://map.mobile.xqnqq.com/Article/558574.shtml
- http://http://map.read.usuhx.com/Article/235344.shtml
- http://http://map.read.usuhx.com/Article/270840.shtml
- http://http://map.read.usuhx.com/Article/35418.shtml
- http://http://map.mobile.xqnqq.com/Article/0866562.shtml
- http://http://map.mobile.xqnqq.com/Article/49465.shtml
- http://http://map.mobile.xqnqq.com/Article/5527563.shtml
- http://http://map.read.usuhx.com/Article/81138.shtml
- http://http://map.read.usuhx.com/Article/68010.shtml
- http://http://map.mobile.xqnqq.com/Article/8299886.shtml
- http://http://map.mobile.xqnqq.com/Article/949891.shtml
- http://http://map.read.usuhx.com/Article/59306.shtml
- http://http://map.read.usuhx.com/Article/01460.shtml
- http://http://map.mobile.xqnqq.com/Article/6783660.shtml
- http://http://map.mobile.xqnqq.com/Article/70990.shtml
- http://http://map.mobile.xqnqq.com/Article/791443.shtml
- http://http://map.mobile.xqnqq.com/Article/3909.shtml
- http://http://map.mobile.xqnqq.com/Article/44334.shtml
- http://http://map.mobile.xqnqq.com/Article/3583.shtml
- http://http://map.read.usuhx.com/Article/38500.shtml
- http://http://map.mobile.xqnqq.com/Article/1040.shtml
- http://http://map.read.usuhx.com/Article/3106.shtml
- http://http://map.read.usuhx.com/Article/806605.shtml
- http://http://map.mobile.xqnqq.com/Article/230737.shtml
- http://http://map.mobile.xqnqq.com/Article/016876.shtml
- http://http://map.read.usuhx.com/Article/3241544.shtml
- http://http://map.mobile.xqnqq.com/Article/850411.shtml
- http://http://map.mobile.xqnqq.com/Article/5575.shtml
- http://http://map.read.usuhx.com/Article/139988.shtml
- http://http://map.read.usuhx.com/Article/144857.shtml
- http://http://map.mobile.xqnqq.com/Article/95432.shtml
- http://http://map.mobile.xqnqq.com/Article/2621146.shtml
- http://http://map.mobile.xqnqq.com/Article/29593.shtml
- http://http://map.read.usuhx.com/Article/112977.shtml
- http://http://map.mobile.xqnqq.com/Article/813605.shtml
- http://http://map.read.usuhx.com/Article/6315056.shtml
- http://http://map.read.usuhx.com/Article/54785.shtml
- http://http://map.read.usuhx.com/Article/0907.shtml
- http://http://map.read.usuhx.com/Article/607951.shtml
- http://http://map.read.usuhx.com/Article/477414.shtml
- http://http://map.mobile.xqnqq.com/Article/7062.shtml
- http://http://map.mobile.xqnqq.com/Article/176682.shtml
- http://http://map.read.usuhx.com/Article/6483513.shtml
- http://http://map.mobile.xqnqq.com/Article/6582988.shtml
- http://http://map.mobile.xqnqq.com/Article/550674.shtml
- http://http://map.read.usuhx.com/Article/0245.shtml
- http://http://map.mobile.xqnqq.com/Article/782322.shtml
- http://http://map.read.usuhx.com/Article/53874.shtml
- http://http://map.mobile.xqnqq.com/Article/855369.shtml
- http://http://map.mobile.xqnqq.com/Article/521238.shtml
- http://http://map.mobile.xqnqq.com/Article/87005.shtml
- http://http://map.read.usuhx.com/Article/8376618.shtml
- http://http://map.read.usuhx.com/Article/2842226.shtml
- http://http://map.read.usuhx.com/Article/72216.shtml
- http://http://map.mobile.xqnqq.com/Article/79383.shtml
- http://http://map.mobile.xqnqq.com/Article/7748.shtml
- http://http://map.mobile.xqnqq.com/Article/4530.shtml
- http://http://map.mobile.xqnqq.com/Article/7317346.shtml
- http://http://map.mobile.xqnqq.com/Article/084219.shtml
- http://http://map.mobile.xqnqq.com/Article/185202.shtml
- http://http://map.read.usuhx.com/Article/8765194.shtml
- http://http://map.mobile.xqnqq.com/Article/37403.shtml
- http://http://map.mobile.xqnqq.com/Article/3940.shtml
- http://http://map.read.usuhx.com/Article/824389.shtml
- http://http://map.mobile.xqnqq.com/Article/28312.shtml
- http://http://map.mobile.xqnqq.com/Article/276627.shtml
- http://http://map.read.usuhx.com/Article/45661.shtml
- http://http://map.mobile.xqnqq.com/Article/79891.shtml
- http://http://map.read.usuhx.com/Article/571085.shtml
- http://http://map.read.usuhx.com/Article/8184.shtml
- http://http://map.mobile.xqnqq.com/Article/278188.shtml
- http://http://map.read.usuhx.com/Article/9519448.shtml
- http://http://map.read.usuhx.com/Article/0069.shtml
- http://http://map.mobile.xqnqq.com/Article/087289.shtml
- http://http://map.mobile.xqnqq.com/Article/2749104.shtml
- http://http://map.mobile.xqnqq.com/Article/2544068.shtml
- http://http://map.read.usuhx.com/Article/4883511.shtml
- http://http://map.read.usuhx.com/Article/142885.shtml
- http://http://map.read.usuhx.com/Article/5172.shtml
- http://http://map.mobile.xqnqq.com/Article/677598.shtml
- http://http://map.read.usuhx.com/Article/82921.shtml
- http://http://map.mobile.xqnqq.com/Article/8309384.shtml
- http://http://map.mobile.xqnqq.com/Article/2730336.shtml
- http://http://map.read.usuhx.com/Article/01215.shtml
- http://http://map.read.usuhx.com/Article/4400477.shtml
- http://http://map.read.usuhx.com/Article/6644.shtml
- http://http://map.mobile.xqnqq.com/Article/38268.shtml
- http://http://map.mobile.xqnqq.com/Article/614201.shtml
- http://http://map.read.usuhx.com/Article/10454.shtml
- http://http://map.mobile.xqnqq.com/Article/4536.shtml
- http://http://map.read.usuhx.com/Article/4930.shtml
- http://http://map.read.usuhx.com/Article/5876631.shtml
- http://http://map.read.usuhx.com/Article/592315.shtml
- http://http://map.read.usuhx.com/Article/187455.shtml
- http://http://map.read.usuhx.com/Article/7725786.shtml
- http://http://map.read.usuhx.com/Article/414861.shtml
- http://http://map.read.usuhx.com/Article/31457.shtml
- http://http://map.read.usuhx.com/Article/45187.shtml
- http://http://map.read.usuhx.com/Article/8594.shtml
- http://http://map.read.usuhx.com/Article/4597987.shtml
- http://http://map.read.usuhx.com/Article/50518.shtml
- http://http://map.mobile.xqnqq.com/Article/463532.shtml
- http://http://map.read.usuhx.com/Article/065982.shtml
- http://http://map.mobile.xqnqq.com/Article/0002.shtml
- http://http://map.mobile.xqnqq.com/Article/7734.shtml
- http://http://map.read.usuhx.com/Article/8364.shtml
- http://http://map.mobile.xqnqq.com/Article/1648.shtml
- http://http://map.read.usuhx.com/Article/4795.shtml
- http://http://map.read.usuhx.com/Article/0664523.shtml
- http://http://map.read.usuhx.com/Article/5078.shtml
- http://http://map.mobile.xqnqq.com/Article/2491719.shtml
- http://http://map.mobile.xqnqq.com/Article/50824.shtml
- http://http://map.mobile.xqnqq.com/Article/34653.shtml
- http://http://map.read.usuhx.com/Article/3301.shtml
- http://http://map.mobile.xqnqq.com/Article/5328.shtml
- http://http://map.read.usuhx.com/Article/832492.shtml
- http://http://map.read.usuhx.com/Article/2118667.shtml
- http://http://map.mobile.xqnqq.com/Article/376926.shtml
- http://http://map.mobile.xqnqq.com/Article/550426.shtml
- http://http://map.mobile.xqnqq.com/Article/7701.shtml
- http://http://map.read.usuhx.com/Article/73806.shtml
- http://http://map.read.usuhx.com/Article/089863.shtml
- http://http://map.mobile.xqnqq.com/Article/29227.shtml
- http://http://map.read.usuhx.com/Article/5983663.shtml
- http://http://map.read.usuhx.com/Article/851011.shtml
- http://http://map.read.usuhx.com/Article/0714.shtml
- http://http://map.read.usuhx.com/Article/2212.shtml
- http://http://map.mobile.xqnqq.com/Article/0958.shtml
- http://http://map.read.usuhx.com/Article/5296385.shtml
- http://http://map.mobile.xqnqq.com/Article/674695.shtml
- http://http://map.read.usuhx.com/Article/6339471.shtml
- http://http://map.read.usuhx.com/Article/8064715.shtml
- http://http://map.mobile.xqnqq.com/Article/295921.shtml
- http://http://map.read.usuhx.com/Article/7263390.shtml
- http://http://map.read.usuhx.com/Article/66080.shtml
- http://http://map.read.usuhx.com/Article/991904.shtml
- http://http://map.read.usuhx.com/Article/345636.shtml
- http://http://map.read.usuhx.com/Article/5668.shtml
- http://http://map.mobile.xqnqq.com/Article/1277970.shtml
- http://http://map.read.usuhx.com/Article/9901165.shtml
- http://http://map.mobile.xqnqq.com/Article/0373.shtml
- http://http://map.read.usuhx.com/Article/7105.shtml
- http://http://map.read.usuhx.com/Article/174461.shtml
- http://http://map.read.usuhx.com/Article/4875.shtml
- http://http://map.read.usuhx.com/Article/4928253.shtml
- http://http://map.read.usuhx.com/Article/726192.shtml
- http://http://map.read.usuhx.com/Article/5892878.shtml
- http://http://map.mobile.xqnqq.com/Article/3201.shtml
- http://http://map.read.usuhx.com/Article/169395.shtml
- http://http://map.read.usuhx.com/Article/7424.shtml
- http://http://map.mobile.xqnqq.com/Article/62465.shtml
- http://http://map.mobile.xqnqq.com/Article/029420.shtml
- http://http://map.mobile.xqnqq.com/Article/0907891.shtml
- http://http://map.read.usuhx.com/Article/77248.shtml
- http://http://map.read.usuhx.com/Article/13265.shtml
- http://http://map.mobile.xqnqq.com/Article/7426348.shtml
- http://http://map.mobile.xqnqq.com/Article/3978977.shtml
- http://http://map.mobile.xqnqq.com/Article/0600.shtml
- http://http://map.read.usuhx.com/Article/59515.shtml
- http://http://map.mobile.xqnqq.com/Article/0414.shtml

## 项目结构

```
link-navigator/
├── nav_cli.py               # 命令行入口，定义 sync/search/list/check 子命令
├── nav_api.py               # FastAPI 应用实例，挂载路由与异常处理器
├── requirements.txt         # 生产环境依赖清单（固定版本）
├── requirements-dev.txt     # 开发环境额外依赖（pytest, black, mypy）
├── src/
│   ├── collector/           # 采集引擎模块
│   │   ├── fetcher.py       # 异步 HTTP 请求封装，含重试与超时逻辑
│   │   ├── parser.py        # HTML 解析器，针对两个来源站点的 DOM 结构分别实现
│   │   └── pipeline.py      # 采集流水线，协调 fetcher 与 parser 的工作
│   ├── storage/             # 存储层模块
│   │   ├── database.py      # SQLite 连接池与表结构初始化
│   │   ├── repository.py    # 数据访问对象（DAO），封装增删改查操作
│   │   └── migration/       # 数据库迁移脚本（按版本号命名）
│   ├── service/             # 业务逻辑层
│   │   ├── indexer.py       # 资源索引服务，处理去重与标签生成
│   │   ├── checker.py       # 死链检测服务，使用 aiohttp 发起 HEAD 请求
│   │   └── exporter.py      # 导出服务，支持 JSON / CSV / Markdown 格式
│   ├── api/                 # API 路由定义
│   │   ├── routes.py        # 路由注册与依赖注入
│   │   └── schemas.py       # Pydantic 请求/响应模型
│   └── utils/               # 通用工具函数
│       ├── logger.py        # 日志配置（按天滚动）
│       └── validators.py    # URL 格式校验与规范化工具
├── config/
│   ├── default.yaml         # 默认配置（并发数 20，超时 30 秒）
│   └── production.yaml      # 生产环境覆盖配置（并发数 50，启用死链检测）
├── tests/                   # 单元测试与集成测试
│   ├── test_fetcher.py
│   ├── test_parser.py
│   └── test_api.py
├── docs/                    # 文档目录
│   ├── quickstart.md
│   ├── configuration.md
│   ├── cli_commands.md
│   └── api_reference.md
├── scripts/                 # 运维辅助脚本
│   ├── init_db.sh           # 首次启动时初始化数据库
│   └── daily_sync.sh        # 每日增量采集的 cron 任务脚本
├── .env.example             # 环境变量模板（用于覆盖配置项）
├── .gitignore
└── LICENSE
```

## 贡献指南

1. 在 GitHub 仓库中创建 Issue 描述你发现的问题或希望新增的功能，等待维护者确认后再开始代码编写，避免无效工作。

2. Fork 本仓库到你的个人账号下，在本地切换到 develop 分支（若不存在则基于 main 创建），并按照项目根目录下的 .pre-commit-config.yaml 配置代码格式化钩子。

3. 编写代码时请遵循 PEP 8 规范，所有新增函数必须包含 docstring 说明，涉及异步操作的部分需要显式标注 await 链路的错误处理。

4. 提交前执行 pytest tests/ 确保所有已有测试用例通过，若新增功能或修复缺陷需同步补充对应的测试代码，覆盖率不得低于 85%。

5. 提交 Pull Request 至 main 分支，描述中需关联对应的 Issue 编号，并附上手动测试截图或日志片段，等待至少一名维护者审核。

## 常见问题

Q：采集过程中出现大量超时或连接重置错误应如何处理？

A：首先检查源站是否可正常访问，排除网络防火墙干扰。若源站稳定，可在 config/default.yaml 中适当增大超时时间（timeout 字段）并降低并发数（concurrency 字段）。项目也支持通过 -t 和 -c 命令行参数临时覆盖这两个值，例如 nav_cli.py sync --full -t 60 -c 10。

Q：如何将已采集的资源清单导出为其他系统可导入的格式？

A：使用 nav_cli.py export --format csv --output resources.csv 可将当前数据库中的全部记录导出为 CSV 格式。目前支持 csv、json 与 markdown 三种格式，其中 markdown 格式会直接生成与资源列表章节结构相同的表格，便于嵌入文档。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
