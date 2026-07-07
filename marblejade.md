# WebLink Catalog Server

WebLink Catalog Server 是一个面向技术团队与内容研究者的轻量级外链资源归集与导航系统。该项目定位于解决分布式文档、技术博客、新闻资讯及学术资料在多个内容源之间分散、难以统一检索和回溯的问题，提供基于文章 ID 的确定性映射与静态资源索引能力。

项目核心目标用户为运维工程师、技术文档撰写者、数据分析师以及需要定期跟踪特定源站点内容更新的从业人员。通过将 URL 参数化与目录树结构化，本系统可在内网或本地环境中快速构建只读镜像站点的导航门户，降低人工整理成本，提升信息获取效率。

## 功能概览

批量资源导入与去重校验 系统提供命令行导入工具，支持批量检查 URL 可达性、提取文章元信息，并根据资源 ID 自动去重，避免条目冗余。

确定性映射路由机制 采用基于文章编号的哈希路由表，将外部链接映射为内部短标识，确保每次资源重组后访问路径的稳定性与可预测性。

多级目录分类挂载 允许管理员将采集的资源挂载至自定义分类树中，支持无限级子目录扩展，便于按主题或来源组织链接。

资源可用性健康检查 内置异步探活模块，定期对已收录的 URL 发起 HEAD 请求并记录状态码，输出异常清单供人工复核。

全文元数据缓存 对每个资源链接提取标题、来源域名、内容摘要及发布时间并持久化至本地 SQLite 数据库，提升检索响应速度。

纯静态站点生成模式 支持将当前资源目录与元数据导出为纯 HTML 与 JSON 文件，无需后端服务即可部署至 CDN 或对象存储。

访问日志统计分析 记录每个资源的点击频次与来源 IP 归属地，生成基础统计报表，帮助识别高频访问内容。

## 应用场景

技术博客聚合与内部周报生成 技术团队可将关注的外部博客、社区问答及更新日志链接统一录入系统，每周自动导出新增资源列表，用于撰写团队周报或技术雷达。

离线文档中心资源映射 企业内部文档平台在迁移或重构期间，可将旧版文档的分散外链通过本系统重新编目，快速生成临时导航页，保障业务方查阅连续性。

竞品动态监控与归档 市场分析人员可将竞品官网、媒体报道及版本发布公告的 URL 归入监控分类，系统按时间倒序排列，便于追踪关键事件节点。

学术资料引用整理 研究人员在撰写综述或论文时，可将参考引用的网络来源统一导入系统，生成带时间戳的引用清单，避免参考文献链接失效。

## 快速开始

以下步骤演示如何在 Linux 或 macOS 环境中完成本项目的克隆、安装与初次运行。

```bash
# 克隆项目仓库至本地
git clone https://github.com/weblink-catalog/weblink-catalog-server.git
cd weblink-catalog-server

# 安装项目依赖（使用 pip 与虚拟环境）
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# 执行资源导入与本地服务器启动
python manage.py import --source data/initial_links.json
python manage.py build --output ./public
python manage.py serve --port 8080
```

## 安装要求

| 依赖项 | 必需版本 | 说明 |
| :--- | :--- | :--- |
| Python | 3.9 及以上 | 主程序运行环境，低于此版本将导致类型注解解析异常 |
| pip | 22.0 及以上 | Python 包管理工具，用于安装依赖库 |
| SQLite | 3.35 及以上 | 本地元数据缓存数据库，支持 JSON 函数 |
| Git | 2.25 及以上 | 用于克隆仓库及版本管理操作 |
| gunicorn | 20.1.0 及以上 | 生产环境 WSGI 服务器，仅在部署时必需 |
| requests | 2.28.0 及以上 | 用于健康检查与 HTTP 请求处理 |
| beautifulsoup4 | 4.11.0 及以上 | 可选依赖，用于增强元数据提取准确性 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
| :--- | :--- | :--- |
| 入门指南 | docs/getting_started.md | 如何在一分钟内启动服务并导入首批资源链接？ |
| 管理手册 | docs/administration.md | 如何管理分类树、执行健康检查及清理无效链接？ |
| 路由映射说明 | docs/routing.md | 确定性映射路由的哈希算法与自定义映射规则如何配置？ |
| 导出与部署 | docs/deployment.md | 如何生成静态站点并部署至 Nginx 或 S3 兼容存储？ |

## 资源列表

- http://http://map.read.usuhx.com/Article/7684199.shtml
- http://http://map.read.usuhx.com/Article/467014.shtml
- http://http://map.mobile.xqnqq.com/Article/27012.shtml
- http://http://map.mobile.xqnqq.com/Article/4307703.shtml
- http://http://map.mobile.xqnqq.com/Article/9191741.shtml
- http://http://map.read.usuhx.com/Article/098307.shtml
- http://http://map.mobile.xqnqq.com/Article/5922017.shtml
- http://http://map.read.usuhx.com/Article/69257.shtml
- http://http://map.mobile.xqnqq.com/Article/755909.shtml
- http://http://map.mobile.xqnqq.com/Article/4272.shtml
- http://http://map.mobile.xqnqq.com/Article/2785309.shtml
- http://http://map.mobile.xqnqq.com/Article/6816.shtml
- http://http://map.mobile.xqnqq.com/Article/3121537.shtml
- http://http://map.mobile.xqnqq.com/Article/6709379.shtml
- http://http://map.mobile.xqnqq.com/Article/28176.shtml
- http://http://map.mobile.xqnqq.com/Article/73574.shtml
- http://http://map.mobile.xqnqq.com/Article/7929.shtml
- http://http://map.read.usuhx.com/Article/08310.shtml
- http://http://map.read.usuhx.com/Article/8675402.shtml
- http://http://map.mobile.xqnqq.com/Article/46154.shtml
- http://http://map.read.usuhx.com/Article/7310570.shtml
- http://http://map.read.usuhx.com/Article/0151.shtml
- http://http://map.mobile.xqnqq.com/Article/102112.shtml
- http://http://map.mobile.xqnqq.com/Article/1571.shtml
- http://http://map.mobile.xqnqq.com/Article/676914.shtml
- http://http://map.read.usuhx.com/Article/1794.shtml
- http://http://map.mobile.xqnqq.com/Article/417314.shtml
- http://http://map.mobile.xqnqq.com/Article/705285.shtml
- http://http://map.read.usuhx.com/Article/97546.shtml
- http://http://map.mobile.xqnqq.com/Article/1735840.shtml
- http://http://map.mobile.xqnqq.com/Article/4917720.shtml
- http://http://map.mobile.xqnqq.com/Article/709602.shtml
- http://http://map.mobile.xqnqq.com/Article/8942615.shtml
- http://http://map.mobile.xqnqq.com/Article/203286.shtml
- http://http://map.read.usuhx.com/Article/6414622.shtml
- http://http://map.read.usuhx.com/Article/99003.shtml
- http://http://map.read.usuhx.com/Article/0748.shtml
- http://http://map.read.usuhx.com/Article/989548.shtml
- http://http://map.read.usuhx.com/Article/398714.shtml
- http://http://map.mobile.xqnqq.com/Article/0747840.shtml
- http://http://map.read.usuhx.com/Article/1166.shtml
- http://http://map.mobile.xqnqq.com/Article/33484.shtml
- http://http://map.read.usuhx.com/Article/911412.shtml
- http://http://map.read.usuhx.com/Article/60404.shtml
- http://http://map.mobile.xqnqq.com/Article/70779.shtml
- http://http://map.read.usuhx.com/Article/35274.shtml
- http://http://map.read.usuhx.com/Article/8279714.shtml
- http://http://map.mobile.xqnqq.com/Article/912690.shtml
- http://http://map.read.usuhx.com/Article/4080.shtml
- http://http://map.mobile.xqnqq.com/Article/90941.shtml
- http://http://map.read.usuhx.com/Article/20655.shtml
- http://http://map.read.usuhx.com/Article/8642.shtml
- http://http://map.read.usuhx.com/Article/4532698.shtml
- http://http://map.read.usuhx.com/Article/4724.shtml
- http://http://map.mobile.xqnqq.com/Article/667802.shtml
- http://http://map.mobile.xqnqq.com/Article/3399.shtml
- http://http://map.read.usuhx.com/Article/647997.shtml
- http://http://map.read.usuhx.com/Article/3990737.shtml
- http://http://map.read.usuhx.com/Article/084393.shtml
- http://http://map.mobile.xqnqq.com/Article/850186.shtml
- http://http://map.mobile.xqnqq.com/Article/67460.shtml
- http://http://map.read.usuhx.com/Article/875732.shtml
- http://http://map.read.usuhx.com/Article/8391.shtml
- http://http://map.read.usuhx.com/Article/3085.shtml
- http://http://map.read.usuhx.com/Article/7576.shtml
- http://http://map.read.usuhx.com/Article/3432848.shtml
- http://http://map.read.usuhx.com/Article/60425.shtml
- http://http://map.read.usuhx.com/Article/337738.shtml
- http://http://map.read.usuhx.com/Article/924784.shtml
- http://http://map.read.usuhx.com/Article/0320.shtml
- http://http://map.mobile.xqnqq.com/Article/451103.shtml
- http://http://map.read.usuhx.com/Article/30534.shtml
- http://http://map.read.usuhx.com/Article/497524.shtml
- http://http://map.mobile.xqnqq.com/Article/1210.shtml
- http://http://map.read.usuhx.com/Article/9653660.shtml
- http://http://map.read.usuhx.com/Article/4771.shtml
- http://http://map.mobile.xqnqq.com/Article/575406.shtml
- http://http://map.read.usuhx.com/Article/846097.shtml
- http://http://map.mobile.xqnqq.com/Article/36819.shtml
- http://http://map.read.usuhx.com/Article/344154.shtml
- http://http://map.read.usuhx.com/Article/204457.shtml
- http://http://map.read.usuhx.com/Article/852191.shtml
- http://http://map.read.usuhx.com/Article/4283.shtml
- http://http://map.read.usuhx.com/Article/2582.shtml
- http://http://map.read.usuhx.com/Article/12867.shtml
- http://http://map.mobile.xqnqq.com/Article/36363.shtml
- http://http://map.read.usuhx.com/Article/699832.shtml
- http://http://map.read.usuhx.com/Article/0581891.shtml
- http://http://map.mobile.xqnqq.com/Article/9000.shtml
- http://http://map.mobile.xqnqq.com/Article/11527.shtml
- http://http://map.read.usuhx.com/Article/0327239.shtml
- http://http://map.read.usuhx.com/Article/0760.shtml
- http://http://map.mobile.xqnqq.com/Article/20722.shtml
- http://http://map.mobile.xqnqq.com/Article/890341.shtml
- http://http://map.read.usuhx.com/Article/4290228.shtml
- http://http://map.read.usuhx.com/Article/0849249.shtml
- http://http://map.mobile.xqnqq.com/Article/2214.shtml
- http://http://map.read.usuhx.com/Article/3231693.shtml
- http://http://map.read.usuhx.com/Article/7727.shtml
- http://http://map.read.usuhx.com/Article/38297.shtml
- http://http://map.read.usuhx.com/Article/15138.shtml
- http://http://map.mobile.xqnqq.com/Article/80156.shtml
- http://http://map.read.usuhx.com/Article/264044.shtml
- http://http://map.mobile.xqnqq.com/Article/6143.shtml
- http://http://map.mobile.xqnqq.com/Article/92234.shtml
- http://http://map.mobile.xqnqq.com/Article/1969976.shtml
- http://http://map.mobile.xqnqq.com/Article/6132110.shtml
- http://http://map.mobile.xqnqq.com/Article/95497.shtml
- http://http://map.read.usuhx.com/Article/7886755.shtml
- http://http://map.read.usuhx.com/Article/27388.shtml
- http://http://map.read.usuhx.com/Article/7147.shtml
- http://http://map.mobile.xqnqq.com/Article/980230.shtml
- http://http://map.mobile.xqnqq.com/Article/50605.shtml
- http://http://map.read.usuhx.com/Article/0346.shtml
- http://http://map.read.usuhx.com/Article/28316.shtml
- http://http://map.mobile.xqnqq.com/Article/36907.shtml
- http://http://map.read.usuhx.com/Article/4959911.shtml
- http://http://map.mobile.xqnqq.com/Article/4083.shtml
- http://http://map.read.usuhx.com/Article/19181.shtml
- http://http://map.read.usuhx.com/Article/367528.shtml
- http://http://map.mobile.xqnqq.com/Article/0500458.shtml
- http://http://map.mobile.xqnqq.com/Article/2754.shtml
- http://http://map.mobile.xqnqq.com/Article/6105718.shtml
- http://http://map.read.usuhx.com/Article/57213.shtml
- http://http://map.read.usuhx.com/Article/748975.shtml
- http://http://map.mobile.xqnqq.com/Article/104570.shtml
- http://http://map.mobile.xqnqq.com/Article/16272.shtml
- http://http://map.mobile.xqnqq.com/Article/13516.shtml
- http://http://map.read.usuhx.com/Article/293565.shtml
- http://http://map.mobile.xqnqq.com/Article/533957.shtml
- http://http://map.read.usuhx.com/Article/1637485.shtml
- http://http://map.read.usuhx.com/Article/6053.shtml
- http://http://map.mobile.xqnqq.com/Article/6557.shtml
- http://http://map.mobile.xqnqq.com/Article/595813.shtml
- http://http://map.read.usuhx.com/Article/3394.shtml
- http://http://map.mobile.xqnqq.com/Article/015879.shtml
- http://http://map.read.usuhx.com/Article/9918492.shtml
- http://http://map.read.usuhx.com/Article/0873675.shtml
- http://http://map.read.usuhx.com/Article/40439.shtml
- http://http://map.read.usuhx.com/Article/4156644.shtml
- http://http://map.mobile.xqnqq.com/Article/5023639.shtml
- http://http://map.mobile.xqnqq.com/Article/3108.shtml
- http://http://map.read.usuhx.com/Article/9727109.shtml
- http://http://map.read.usuhx.com/Article/39701.shtml
- http://http://map.mobile.xqnqq.com/Article/15757.shtml
- http://http://map.read.usuhx.com/Article/06928.shtml
- http://http://map.mobile.xqnqq.com/Article/57815.shtml
- http://http://map.read.usuhx.com/Article/90361.shtml
- http://http://map.read.usuhx.com/Article/1913539.shtml
- http://http://map.mobile.xqnqq.com/Article/2379.shtml
- http://http://map.read.usuhx.com/Article/46357.shtml
- http://http://map.mobile.xqnqq.com/Article/15867.shtml
- http://http://map.mobile.xqnqq.com/Article/170332.shtml
- http://http://map.read.usuhx.com/Article/132432.shtml
- http://http://map.mobile.xqnqq.com/Article/7173.shtml
- http://http://map.mobile.xqnqq.com/Article/564337.shtml
- http://http://map.mobile.xqnqq.com/Article/248019.shtml
- http://http://map.read.usuhx.com/Article/70752.shtml
- http://http://map.mobile.xqnqq.com/Article/916883.shtml
- http://http://map.mobile.xqnqq.com/Article/013344.shtml
- http://http://map.read.usuhx.com/Article/50496.shtml
- http://http://map.mobile.xqnqq.com/Article/4253.shtml
- http://http://map.read.usuhx.com/Article/3214201.shtml
- http://http://map.read.usuhx.com/Article/93612.shtml
- http://http://map.read.usuhx.com/Article/021937.shtml
- http://http://map.mobile.xqnqq.com/Article/077552.shtml
- http://http://map.mobile.xqnqq.com/Article/3702152.shtml
- http://http://map.mobile.xqnqq.com/Article/847214.shtml
- http://http://map.read.usuhx.com/Article/81506.shtml
- http://http://map.read.usuhx.com/Article/45754.shtml
- http://http://map.mobile.xqnqq.com/Article/622812.shtml
- http://http://map.mobile.xqnqq.com/Article/5294209.shtml
- http://http://map.read.usuhx.com/Article/1799838.shtml
- http://http://map.read.usuhx.com/Article/0310874.shtml
- http://http://map.mobile.xqnqq.com/Article/3015078.shtml
- http://http://map.mobile.xqnqq.com/Article/4966877.shtml
- http://http://map.mobile.xqnqq.com/Article/6224030.shtml
- http://http://map.mobile.xqnqq.com/Article/9772.shtml
- http://http://map.read.usuhx.com/Article/8538847.shtml
- http://http://map.mobile.xqnqq.com/Article/268025.shtml
- http://http://map.read.usuhx.com/Article/8342934.shtml
- http://http://map.read.usuhx.com/Article/22617.shtml
- http://http://map.mobile.xqnqq.com/Article/34658.shtml
- http://http://map.mobile.xqnqq.com/Article/9199.shtml
- http://http://map.mobile.xqnqq.com/Article/2580.shtml
- http://http://map.mobile.xqnqq.com/Article/5125753.shtml
- http://http://map.read.usuhx.com/Article/9890.shtml
- http://http://map.mobile.xqnqq.com/Article/4379.shtml
- http://http://map.read.usuhx.com/Article/6224201.shtml
- http://http://map.mobile.xqnqq.com/Article/0799446.shtml
- http://http://map.read.usuhx.com/Article/9086493.shtml
- http://http://map.mobile.xqnqq.com/Article/1557.shtml
- http://http://map.mobile.xqnqq.com/Article/8754.shtml
- http://http://map.read.usuhx.com/Article/45468.shtml
- http://http://map.read.usuhx.com/Article/817189.shtml
- http://http://map.mobile.xqnqq.com/Article/6297.shtml
- http://http://map.mobile.xqnqq.com/Article/001505.shtml
- http://http://map.mobile.xqnqq.com/Article/9651951.shtml
- http://http://map.mobile.xqnqq.com/Article/6037984.shtml
- http://http://map.read.usuhx.com/Article/539116.shtml
- http://http://map.read.usuhx.com/Article/77737.shtml
- http://http://map.read.usuhx.com/Article/0011.shtml
- http://http://map.read.usuhx.com/Article/3847.shtml
- http://http://map.mobile.xqnqq.com/Article/050923.shtml
- http://http://map.mobile.xqnqq.com/Article/01052.shtml
- http://http://map.read.usuhx.com/Article/104170.shtml
- http://http://map.read.usuhx.com/Article/01522.shtml
- http://http://map.mobile.xqnqq.com/Article/21186.shtml
- http://http://map.read.usuhx.com/Article/3603022.shtml
- http://http://map.mobile.xqnqq.com/Article/6241.shtml
- http://http://map.read.usuhx.com/Article/5848.shtml
- http://http://map.mobile.xqnqq.com/Article/1643155.shtml
- http://http://map.mobile.xqnqq.com/Article/17345.shtml
- http://http://map.read.usuhx.com/Article/6473599.shtml
- http://http://map.mobile.xqnqq.com/Article/9061.shtml
- http://http://map.mobile.xqnqq.com/Article/1788.shtml
- http://http://map.mobile.xqnqq.com/Article/59757.shtml
- http://http://map.mobile.xqnqq.com/Article/377203.shtml
- http://http://map.mobile.xqnqq.com/Article/2793.shtml
- http://http://map.read.usuhx.com/Article/99354.shtml
- http://http://map.mobile.xqnqq.com/Article/5689104.shtml
- http://http://map.mobile.xqnqq.com/Article/0914944.shtml
- http://http://map.mobile.xqnqq.com/Article/721272.shtml
- http://http://map.mobile.xqnqq.com/Article/5859046.shtml
- http://http://map.read.usuhx.com/Article/981647.shtml
- http://http://map.mobile.xqnqq.com/Article/0418000.shtml
- http://http://map.read.usuhx.com/Article/410834.shtml
- http://http://map.mobile.xqnqq.com/Article/74707.shtml
- http://http://map.mobile.xqnqq.com/Article/81285.shtml
- http://http://map.mobile.xqnqq.com/Article/25753.shtml
- http://http://map.mobile.xqnqq.com/Article/1770.shtml
- http://http://map.mobile.xqnqq.com/Article/392216.shtml
- http://http://map.mobile.xqnqq.com/Article/00327.shtml
- http://http://map.mobile.xqnqq.com/Article/467073.shtml
- http://http://map.mobile.xqnqq.com/Article/41817.shtml
- http://http://map.mobile.xqnqq.com/Article/603137.shtml
- http://http://map.read.usuhx.com/Article/1196.shtml
- http://http://map.mobile.xqnqq.com/Article/6999536.shtml
- http://http://map.read.usuhx.com/Article/597896.shtml
- http://http://map.mobile.xqnqq.com/Article/78288.shtml
- http://http://map.read.usuhx.com/Article/3830280.shtml
- http://http://map.mobile.xqnqq.com/Article/6343597.shtml
- http://http://map.read.usuhx.com/Article/0345541.shtml
- http://http://map.mobile.xqnqq.com/Article/6259674.shtml
- http://http://map.mobile.xqnqq.com/Article/213335.shtml
- http://http://map.mobile.xqnqq.com/Article/7236809.shtml
- http://http://map.mobile.xqnqq.com/Article/9185903.shtml
- http://http://map.mobile.xqnqq.com/Article/6136709.shtml
- http://http://map.mobile.xqnqq.com/Article/4676344.shtml
- http://http://map.read.usuhx.com/Article/844226.shtml

## 项目结构

```
weblink-catalog-server/
├── cmd/                                 # 命令行入口与子命令实现
│   ├── import.go                        # 资源导入子命令，支持 JSON/CSV 格式
│   ├── build.go                         # 静态站点生成逻辑
│   └── serve.go                         # 内置开发服务器启动
├── internal/                            # 内部核心包，不对外暴露
│   ├── catalog/                         # 资源分类与目录树管理
│   │   ├── tree.go                      # 多叉树数据结构与遍历算法
│   │   └── mapper.go                    # URL 到内部 ID 的确定性映射
│   ├── health/                          # 健康检查与探活模块
│   │   ├── checker.go                   # 并发 HTTP 请求与超时控制
│   │   └── reporter.go                  # 异常结果聚合与输出
│   └── storage/                         # 本地存储层
│       ├── sqlite.go                    # SQLite 连接池与 CRUD 操作
│       └── cache.go                     # 内存缓存与 LRU 淘汰策略
├── pkg/                                 # 可被外部引用的公共库
│   ├── metadata/                        # 元数据抽取工具集
│   │   ├── extractor.go                 # 基于正则与 HTML 解析的标题提取
│   │   └── validator.go                 # URL 格式校验与规范化
│   └── render/                          # 静态输出渲染引擎
│       ├── html.go                      # 生成响应式 HTML 页面模板
│       └── json.go                      # 导出结构化 JSON 数据
├── configs/                             # 配置文件与默认参数模板
│   ├── default.yaml                     # 默认端口、超时与数据库路径
│   └── schema.json                      # 导入资源格式的 JSON Schema 校验
├── docs/                                # 完整文档手册
│   ├── getting_started.md               # 快速入门指南
│   ├── administration.md                # 日常运维与调优说明
│   └── deployment.md                    # 生产环境部署参考
├── scripts/                             # 辅助工具脚本
│   ├── migrate_legacy.py                # 旧版数据迁移工具
│   └── benchmark.sh                     # 性能压测脚本
├── test/                                # 单元测试与集成测试套件
│   ├── catalog_test.go                  # 分类树模块测试
│   └── health_check_test.go             # 健康检查并发测试
├── go.mod                               # Go 模块依赖定义
├── go.sum                               # 依赖版本锁定校验
├── Makefile                             # 统一构建、测试与打包入口
└── README.md                            # 本文件
```

## 贡献指南

1. 在 GitHub 仓库中点击 Fork 按钮，将项目复制至个人账户下，并克隆至本地开发环境。确保远端仓库已正确关联 upstream 源。

2. 创建以 feature/ 或 fix/ 为前缀的分支，例如 feature/optimize-mapper，在该分支上进行代码修改或文档更新。

3. 遵循项目既有的代码风格与注释规范，所有新增导出函数需附带文档注释，并补充对应的单元测试用例至 test/ 目录。

4. 运行完整测试套件，确保所有已有测试通过，且新增代码的测试覆盖率不低于 80%。使用 make test 命令一键执行。

5. 提交 Pull Request 至主仓库的 main 分支，并在 PR 描述中清晰说明改动目的、影响范围以及测试结果摘要。等待维护者审核与合并。

## 常见问题

Q: 系统能否处理包含中文或特殊字符的 URL 导入？

A: 可以。导入模块会对 URL 进行自动百分号编码与解码校验，支持 RFC 3986 标准字符集。若 URL 中包含非法字符，系统会记录警告并跳过该条目，同时将异常输出至 logs/import_errors.log 供人工核查。

Q: 如何迁移已有的资源分类数据至新版本？

A: 项目提供了 scripts/migrate_legacy.py 脚本，支持从旧版 SQLite 数据库或 JSON 导出文件中读取数据。执行时需指定源文件路径与目标分类映射规则，迁移完成后运行 build 命令重新生成静态站点即可。

Q: 静态站点的访问统计功能是否需要额外数据库支持？

A: 不需要。统计功能基于内存计数器与定期持久化至本地 SQLite 的实现方式，无需外部 Redis 或 MySQL 服务。统计数据的聚合周期可在 configs/default.yaml 中通过 stats.interval 参数调整，默认每 10 分钟刷盘一次。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
