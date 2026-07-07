# TechArchive Navigator

TechArchive Navigator 是一个面向技术文档、开源项目资料与研发外链的集中式索引与导航系统。该项目定位为技术团队、独立开发者及研究人员的辅助知识管理工具，用于解决日常研发过程中技术资料分散、优质外链难以回溯、项目文档与外部参考之间缺乏统一入口等问题。通过将分散于多个内容源的技术文章与资源链接进行结构化整理，TechArchive Navigator 提供了一套可本地部署、可扩展、支持快速检索的资源导航方案。

本项目不依赖外部数据库，所有资源链接以纯文本形式维护，支持通过脚本进行批量校验、分类标记与全文检索索引构建。适用于搭建内部技术文库、开源项目附属资料站、以及个人知识体系的资源中台。

## 功能概览

- 资源链接批量导入与去重：支持从文本文件批量导入 URL，自动识别重复条目并生成去重报告。

- 多维度分类标记：每个资源条目可标记所属技术领域、内容类型、优先级及阅读状态。

- 本地全文检索引擎：基于倒排索引构建轻量级检索系统，支持标题与正文片段的模糊匹配。

- 链接可用性定时检测：内置 HTTP 状态检查模块，可定期扫描资源列表，输出失效链接报表。

- 静态站点生成器：将资源数据渲染为响应式 HTML 文档，便于内网部署或托管至 GitHub Pages。

- 导入导出兼容性：支持 Markdown 列表、CSV 及 JSON 格式的导入导出，便于与第三方工具集成。

- 标签云与热力图：自动统计资源标签频率，生成可视化标签云与按时间维度的资源增长热力图。

## 应用场景

技术团队内部知识库建设：研发团队可将日常遇到的技术博客、官方文档、API 参考与故障排查记录统一归档至 TechArchive Navigator，形成团队共享的技术资源池，降低信息孤岛效应。

开源项目附属资料站维护：开源项目维护者可在项目仓库之外单独部署本系统，用于整理社区贡献的教程、视频链接、第三方生态工具列表，作为项目官网的补充导航。

个人技术阅读与收藏管理：独立开发者或技术爱好者可使用本系统管理个人阅读列表，对收藏的文章按主题分类，并设置待读、已读、待整理等状态，提升信息处理效率。

技术培训与课程资源支撑：技术培训机构或高校实验室可借助本系统搭建课程参考资料索引，将课件链接、实验手册、视频地址与扩展阅读材料统一汇聚，方便学员按需查阅。

## 快速开始

以下步骤适用于 Linux / macOS / Windows WSL 环境。

```bash
# 克隆项目仓库
git clone https://github.com/techarchive/navigator.git
cd navigator

# 安装依赖（Python 3.9+ 环境）
pip install -r requirements.txt

# 初始化资源数据库（生成示例数据）
python manage.py initdb

# 启动本地开发服务器
python manage.py runserver --port 8000
```

启动后，浏览器访问 `http://127.0.0.1:8000` 即可查看导航主页。默认管理员账号为 `admin`，初始密码在首次启动时打印于控制台日志中。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Python | 3.9 及以上 | 核心运行环境，建议使用 3.11 LTS |
| pip | 22.0 及以上 | Python 包管理工具 |
| SQLite | 3.35 及以上 | 内置轻量级数据库，用于存储资源元数据 |
| Git | 2.30 及以上 | 用于版本控制与仓库克隆 |
| make | 3.82 及以上 | 可选，用于自动化构建任务 |
| curl | 7.68 及以上 | 用于链接可用性检测模块 |
| Node.js | 16.0 及以上 | 仅当启用前端资源构建时必需 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|-----|------|----------|
| 用户手册 | /docs/user-guide/ | 如何添加资源、分类管理、执行检索以及生成静态站点 |
| 运维指南 | /docs/operations/ | 如何进行数据备份、迁移、链接检测调度与性能调优 |
| 开发者文档 | /docs/developer/ | API 接口说明、插件扩展机制、数据库表结构及贡献流程 |
| 部署方案 | /docs/deployment/ | 支持 Docker 部署、Nginx 反向代理配置、HTTPS 证书自动续期方案 |

## 资源列表

- http://http://www.read.usuhx.com/Article/7083594.shtml
- http://http://www.read.usuhx.com/Article/4639.shtml
- http://http://www.read.usuhx.com/Article/63302.shtml
- http://http://www.mobile.xqnqq.com/Article/7782878.shtml
- http://http://www.read.usuhx.com/Article/05170.shtml
- http://http://www.read.usuhx.com/Article/55682.shtml
- http://http://www.mobile.xqnqq.com/Article/54456.shtml
- http://http://www.read.usuhx.com/Article/192333.shtml
- http://http://www.mobile.xqnqq.com/Article/6781565.shtml
- http://http://www.read.usuhx.com/Article/85342.shtml
- http://http://www.read.usuhx.com/Article/6733648.shtml
- http://http://www.read.usuhx.com/Article/343891.shtml
- http://http://www.read.usuhx.com/Article/20155.shtml
- http://http://www.mobile.xqnqq.com/Article/9365.shtml
- http://http://www.mobile.xqnqq.com/Article/63891.shtml
- http://http://www.mobile.xqnqq.com/Article/219003.shtml
- http://http://www.read.usuhx.com/Article/448436.shtml
- http://http://www.mobile.xqnqq.com/Article/1934924.shtml
- http://http://www.mobile.xqnqq.com/Article/222781.shtml
- http://http://www.mobile.xqnqq.com/Article/20571.shtml
- http://http://www.mobile.xqnqq.com/Article/35818.shtml
- http://http://www.read.usuhx.com/Article/395525.shtml
- http://http://www.mobile.xqnqq.com/Article/938842.shtml
- http://http://www.mobile.xqnqq.com/Article/3258798.shtml
- http://http://www.mobile.xqnqq.com/Article/9660.shtml
- http://http://www.mobile.xqnqq.com/Article/28751.shtml
- http://http://www.mobile.xqnqq.com/Article/49225.shtml
- http://http://www.mobile.xqnqq.com/Article/8873.shtml
- http://http://www.read.usuhx.com/Article/28386.shtml
- http://http://www.read.usuhx.com/Article/480740.shtml
- http://http://www.mobile.xqnqq.com/Article/5405.shtml
- http://http://www.read.usuhx.com/Article/247711.shtml
- http://http://www.read.usuhx.com/Article/74642.shtml
- http://http://www.read.usuhx.com/Article/736662.shtml
- http://http://www.mobile.xqnqq.com/Article/81514.shtml
- http://http://www.read.usuhx.com/Article/9032715.shtml
- http://http://www.read.usuhx.com/Article/1532.shtml
- http://http://www.read.usuhx.com/Article/134578.shtml
- http://http://www.read.usuhx.com/Article/3248254.shtml
- http://http://www.mobile.xqnqq.com/Article/8968.shtml
- http://http://www.read.usuhx.com/Article/9102268.shtml
- http://http://www.mobile.xqnqq.com/Article/83812.shtml
- http://http://www.mobile.xqnqq.com/Article/8304603.shtml
- http://http://www.read.usuhx.com/Article/2532.shtml
- http://http://www.mobile.xqnqq.com/Article/89182.shtml
- http://http://www.read.usuhx.com/Article/2804813.shtml
- http://http://www.mobile.xqnqq.com/Article/49881.shtml
- http://http://www.mobile.xqnqq.com/Article/9685.shtml
- http://http://www.mobile.xqnqq.com/Article/2117.shtml
- http://http://www.read.usuhx.com/Article/6531.shtml
- http://http://www.mobile.xqnqq.com/Article/5352.shtml
- http://http://www.read.usuhx.com/Article/54257.shtml
- http://http://www.read.usuhx.com/Article/640935.shtml
- http://http://www.read.usuhx.com/Article/673189.shtml
- http://http://www.mobile.xqnqq.com/Article/3371.shtml
- http://http://www.read.usuhx.com/Article/4765399.shtml
- http://http://www.mobile.xqnqq.com/Article/946770.shtml
- http://http://www.mobile.xqnqq.com/Article/3980.shtml
- http://http://www.read.usuhx.com/Article/267736.shtml
- http://http://www.mobile.xqnqq.com/Article/61792.shtml
- http://http://www.mobile.xqnqq.com/Article/906635.shtml
- http://http://www.mobile.xqnqq.com/Article/714451.shtml
- http://http://www.mobile.xqnqq.com/Article/25321.shtml
- http://http://www.mobile.xqnqq.com/Article/12756.shtml
- http://http://www.read.usuhx.com/Article/589350.shtml
- http://http://www.mobile.xqnqq.com/Article/972329.shtml
- http://http://www.mobile.xqnqq.com/Article/01056.shtml
- http://http://www.read.usuhx.com/Article/53471.shtml
- http://http://www.mobile.xqnqq.com/Article/655470.shtml
- http://http://www.mobile.xqnqq.com/Article/8780348.shtml
- http://http://www.mobile.xqnqq.com/Article/902131.shtml
- http://http://www.read.usuhx.com/Article/1277.shtml
- http://http://www.read.usuhx.com/Article/7128.shtml
- http://http://www.mobile.xqnqq.com/Article/09624.shtml
- http://http://www.read.usuhx.com/Article/3057063.shtml
- http://http://www.mobile.xqnqq.com/Article/216342.shtml
- http://http://www.read.usuhx.com/Article/8375.shtml
- http://http://www.mobile.xqnqq.com/Article/753114.shtml
- http://http://www.mobile.xqnqq.com/Article/55282.shtml
- http://http://www.read.usuhx.com/Article/9776007.shtml
- http://http://www.mobile.xqnqq.com/Article/784797.shtml
- http://http://www.mobile.xqnqq.com/Article/99133.shtml
- http://http://www.mobile.xqnqq.com/Article/7090855.shtml
- http://http://www.read.usuhx.com/Article/1895.shtml
- http://http://www.mobile.xqnqq.com/Article/94247.shtml
- http://http://www.read.usuhx.com/Article/941580.shtml
- http://http://www.read.usuhx.com/Article/1864.shtml
- http://http://www.read.usuhx.com/Article/56078.shtml
- http://http://www.read.usuhx.com/Article/856514.shtml
- http://http://www.mobile.xqnqq.com/Article/52849.shtml
- http://http://www.read.usuhx.com/Article/0064.shtml
- http://http://www.mobile.xqnqq.com/Article/040784.shtml
- http://http://www.read.usuhx.com/Article/44887.shtml
- http://http://www.mobile.xqnqq.com/Article/0604.shtml
- http://http://www.mobile.xqnqq.com/Article/4405.shtml
- http://http://www.mobile.xqnqq.com/Article/905793.shtml
- http://http://www.mobile.xqnqq.com/Article/2096432.shtml
- http://http://www.read.usuhx.com/Article/2288.shtml
- http://http://www.read.usuhx.com/Article/543476.shtml
- http://http://www.read.usuhx.com/Article/345452.shtml
- http://http://www.read.usuhx.com/Article/00239.shtml
- http://http://www.mobile.xqnqq.com/Article/93853.shtml
- http://http://www.read.usuhx.com/Article/72571.shtml
- http://http://www.read.usuhx.com/Article/3632862.shtml
- http://http://www.read.usuhx.com/Article/5688290.shtml
- http://http://www.mobile.xqnqq.com/Article/205677.shtml
- http://http://www.mobile.xqnqq.com/Article/06301.shtml
- http://http://www.mobile.xqnqq.com/Article/282199.shtml
- http://http://www.read.usuhx.com/Article/231415.shtml
- http://http://www.mobile.xqnqq.com/Article/5424413.shtml
- http://http://www.mobile.xqnqq.com/Article/9968535.shtml
- http://http://www.read.usuhx.com/Article/2662460.shtml
- http://http://www.read.usuhx.com/Article/4092.shtml
- http://http://www.read.usuhx.com/Article/6934.shtml
- http://http://www.read.usuhx.com/Article/04146.shtml
- http://http://www.read.usuhx.com/Article/9776040.shtml
- http://http://www.mobile.xqnqq.com/Article/346280.shtml
- http://http://www.mobile.xqnqq.com/Article/630803.shtml
- http://http://www.mobile.xqnqq.com/Article/9713.shtml
- http://http://www.mobile.xqnqq.com/Article/7908.shtml
- http://http://www.read.usuhx.com/Article/9411.shtml
- http://http://www.mobile.xqnqq.com/Article/913955.shtml
- http://http://www.mobile.xqnqq.com/Article/264301.shtml
- http://http://www.mobile.xqnqq.com/Article/4073862.shtml
- http://http://www.read.usuhx.com/Article/3421.shtml
- http://http://www.mobile.xqnqq.com/Article/510046.shtml
- http://http://www.read.usuhx.com/Article/787776.shtml
- http://http://www.read.usuhx.com/Article/7231663.shtml
- http://http://www.mobile.xqnqq.com/Article/805371.shtml
- http://http://www.read.usuhx.com/Article/7215960.shtml
- http://http://www.mobile.xqnqq.com/Article/4739.shtml
- http://http://www.read.usuhx.com/Article/9769.shtml
- http://http://www.mobile.xqnqq.com/Article/097317.shtml
- http://http://www.read.usuhx.com/Article/4081620.shtml
- http://http://www.read.usuhx.com/Article/2020.shtml
- http://http://www.read.usuhx.com/Article/6760.shtml
- http://http://www.mobile.xqnqq.com/Article/0565.shtml
- http://http://www.mobile.xqnqq.com/Article/8216706.shtml
- http://http://www.read.usuhx.com/Article/356996.shtml
- http://http://www.mobile.xqnqq.com/Article/1658034.shtml
- http://http://www.mobile.xqnqq.com/Article/63223.shtml
- http://http://www.mobile.xqnqq.com/Article/5125.shtml
- http://http://www.read.usuhx.com/Article/512281.shtml
- http://http://www.mobile.xqnqq.com/Article/5688.shtml
- http://http://www.read.usuhx.com/Article/0008210.shtml
- http://http://www.read.usuhx.com/Article/9023.shtml
- http://http://www.mobile.xqnqq.com/Article/8974.shtml
- http://http://www.read.usuhx.com/Article/986609.shtml
- http://http://www.mobile.xqnqq.com/Article/63615.shtml
- http://http://www.read.usuhx.com/Article/175767.shtml
- http://http://www.read.usuhx.com/Article/12950.shtml
- http://http://www.mobile.xqnqq.com/Article/7147456.shtml
- http://http://www.read.usuhx.com/Article/752366.shtml
- http://http://www.mobile.xqnqq.com/Article/6696.shtml
- http://http://www.read.usuhx.com/Article/0927756.shtml
- http://http://www.mobile.xqnqq.com/Article/777943.shtml
- http://http://www.read.usuhx.com/Article/8031768.shtml
- http://http://www.read.usuhx.com/Article/7099.shtml
- http://http://www.mobile.xqnqq.com/Article/3000579.shtml
- http://http://www.mobile.xqnqq.com/Article/7776.shtml
- http://http://www.read.usuhx.com/Article/2454.shtml
- http://http://www.read.usuhx.com/Article/694474.shtml
- http://http://www.mobile.xqnqq.com/Article/1162024.shtml
- http://http://www.read.usuhx.com/Article/754205.shtml
- http://http://www.read.usuhx.com/Article/35079.shtml
- http://http://www.read.usuhx.com/Article/483455.shtml
- http://http://www.mobile.xqnqq.com/Article/6363.shtml
- http://http://www.read.usuhx.com/Article/268703.shtml
- http://http://www.mobile.xqnqq.com/Article/8317.shtml
- http://http://www.mobile.xqnqq.com/Article/5203561.shtml
- http://http://www.read.usuhx.com/Article/1342.shtml
- http://http://www.read.usuhx.com/Article/4605.shtml
- http://http://www.mobile.xqnqq.com/Article/79507.shtml
- http://http://www.read.usuhx.com/Article/06831.shtml
- http://http://www.mobile.xqnqq.com/Article/48500.shtml
- http://http://www.mobile.xqnqq.com/Article/973444.shtml
- http://http://www.read.usuhx.com/Article/891964.shtml
- http://http://www.mobile.xqnqq.com/Article/8362941.shtml
- http://http://www.read.usuhx.com/Article/201856.shtml
- http://http://www.mobile.xqnqq.com/Article/805444.shtml
- http://http://www.read.usuhx.com/Article/24088.shtml
- http://http://www.read.usuhx.com/Article/0269354.shtml
- http://http://www.mobile.xqnqq.com/Article/05349.shtml
- http://http://www.read.usuhx.com/Article/56774.shtml
- http://http://www.mobile.xqnqq.com/Article/44057.shtml
- http://http://www.read.usuhx.com/Article/7268.shtml
- http://http://www.read.usuhx.com/Article/04834.shtml
- http://http://www.mobile.xqnqq.com/Article/1346374.shtml
- http://http://www.read.usuhx.com/Article/539055.shtml
- http://http://www.mobile.xqnqq.com/Article/0492441.shtml
- http://http://www.read.usuhx.com/Article/4184330.shtml
- http://http://www.read.usuhx.com/Article/17902.shtml
- http://http://www.read.usuhx.com/Article/5203.shtml
- http://http://www.read.usuhx.com/Article/1337.shtml
- http://http://www.read.usuhx.com/Article/40704.shtml
- http://http://www.read.usuhx.com/Article/2171.shtml
- http://http://www.read.usuhx.com/Article/666813.shtml
- http://http://www.read.usuhx.com/Article/35396.shtml
- http://http://www.read.usuhx.com/Article/233046.shtml
- http://http://www.mobile.xqnqq.com/Article/7801093.shtml
- http://http://www.read.usuhx.com/Article/34664.shtml
- http://http://www.read.usuhx.com/Article/3961.shtml
- http://http://www.read.usuhx.com/Article/451087.shtml
- http://http://www.mobile.xqnqq.com/Article/491035.shtml
- http://http://www.read.usuhx.com/Article/043645.shtml
- http://http://www.read.usuhx.com/Article/52398.shtml
- http://http://www.read.usuhx.com/Article/082017.shtml
- http://http://www.mobile.xqnqq.com/Article/9584.shtml
- http://http://www.read.usuhx.com/Article/235279.shtml
- http://http://www.mobile.xqnqq.com/Article/8692.shtml
- http://http://www.read.usuhx.com/Article/25406.shtml
- http://http://www.read.usuhx.com/Article/86346.shtml
- http://http://www.read.usuhx.com/Article/01258.shtml
- http://http://www.read.usuhx.com/Article/4867.shtml
- http://http://www.read.usuhx.com/Article/043567.shtml
- http://http://www.mobile.xqnqq.com/Article/291092.shtml
- http://http://www.mobile.xqnqq.com/Article/3982239.shtml
- http://http://www.mobile.xqnqq.com/Article/71354.shtml
- http://http://www.read.usuhx.com/Article/39949.shtml
- http://http://www.read.usuhx.com/Article/686146.shtml
- http://http://www.mobile.xqnqq.com/Article/49041.shtml
- http://http://www.read.usuhx.com/Article/653955.shtml
- http://http://www.read.usuhx.com/Article/2158.shtml
- http://http://www.read.usuhx.com/Article/725865.shtml
- http://http://www.read.usuhx.com/Article/6904838.shtml
- http://http://www.read.usuhx.com/Article/04119.shtml
- http://http://www.read.usuhx.com/Article/459553.shtml
- http://http://www.read.usuhx.com/Article/749833.shtml
- http://http://www.mobile.xqnqq.com/Article/5685.shtml
- http://http://www.read.usuhx.com/Article/31452.shtml
- http://http://www.read.usuhx.com/Article/0032692.shtml
- http://http://www.mobile.xqnqq.com/Article/780533.shtml
- http://http://www.read.usuhx.com/Article/70793.shtml
- http://http://www.mobile.xqnqq.com/Article/67695.shtml
- http://http://www.read.usuhx.com/Article/804315.shtml
- http://http://www.mobile.xqnqq.com/Article/4344.shtml
- http://http://www.mobile.xqnqq.com/Article/568121.shtml
- http://http://www.read.usuhx.com/Article/9248.shtml
- http://http://www.mobile.xqnqq.com/Article/2252.shtml
- http://http://www.mobile.xqnqq.com/Article/2489.shtml
- http://http://www.read.usuhx.com/Article/7217.shtml
- http://http://www.read.usuhx.com/Article/466475.shtml
- http://http://www.read.usuhx.com/Article/4147561.shtml
- http://http://www.mobile.xqnqq.com/Article/979098.shtml
- http://http://www.mobile.xqnqq.com/Article/8089044.shtml
- http://http://www.read.usuhx.com/Article/1117.shtml
- http://http://www.mobile.xqnqq.com/Article/83853.shtml
- http://http://www.read.usuhx.com/Article/66975.shtml
- http://http://www.mobile.xqnqq.com/Article/22744.shtml
- http://http://www.mobile.xqnqq.com/Article/8214.shtml

## 项目结构

```
navigator/
├── app/                                 # 主应用目录
│   ├── api/                             # RESTful API 路由层
│   │   ├── resources.py                 # 资源增删改查接口
│   │   └── tags.py                      # 标签管理与统计接口
│   ├── core/                            # 核心业务逻辑层
│   │   ├── indexer.py                   # 全文索引构建与检索
│   │   ├── validator.py                 # 链接格式校验与去重
│   │   └── checker.py                   # HTTP 状态检测调度器
│   ├── models/                          # 数据模型层（SQLAlchemy）
│   │   ├── resource.py                  # 资源条目模型
│   │   └── tag.py                       # 标签关联模型
│   ├── static/                          # 静态资源（CSS / JS / 图片）
│   │   ├── css/                         # 主题样式文件
│   │   └── js/                          # 前端交互脚本
│   └── templates/                       # Jinja2 模板文件
│       ├── layout.html                  # 基础布局模板
│       └── index.html                   # 导航主页模板
├── bin/                                 # 可执行命令行脚本
│   ├── manage.py                        # 统一管理入口（启动/初始化/检测）
│   └── cron_jobs.py                     # 定时任务脚本（链接检测、报表生成）
├── config/                              # 配置文件目录
│   ├── settings.py                      # 应用配置（数据库、端口、日志）
│   └── resources.yaml                   # 默认资源分类映射表
├── data/                                # 数据存储目录（运行时生成）
│   ├── database/                        # SQLite 数据库文件
│   └── cache/                           # 索引缓存与临时文件
├── docs/                                # 项目文档
│   ├── user-guide/                      # 用户手册
│   ├── developer/                       # 开发者文档
│   └── deployment/                      # 部署方案
├── tests/                               # 单元测试与集成测试
│   ├── test_indexer.py                  # 索引模块测试
│   └── test_validator.py                # 校验模块测试
├── requirements.txt                     # Python 依赖清单
├── Makefile                             # 自动化构建脚本
└── README.md                            # 项目说明文档（本文件）
```

## 贡献指南

1. 阅读项目代码风格规范与提交信息格式要求，确保新增代码符合 PEP 8 标准，并编写对应的单元测试。

2. 在 Issue 列表中查找未认领的任务，或提交新 Issue 描述建议新增的功能或改进点，等待维护者确认。

3. Fork 主仓库，在本地分支上进行开发，提交前运行完整测试套件确保无回归问题。

4. 提交 Pull Request 时，需在描述中关联对应 Issue 编号，并附上变更摘要与测试结果截图。

5. 代码审查通过后由维护者合并，合并后自动触发 CI 流水线进行构建与部署预览。

## 常见问题

Q: 资源列表导入后，部分链接无法访问，系统如何处理？

A: 系统内置的链接可用性检测模块会定期扫描所有资源，将返回 4xx 或 5xx 状态码的链接标记为“异常”。异常链接会出现在管理后台的“失效列表”中，管理员可批量移除或手动更新。同时，检测结果会生成 JSON 报表存放在 data/reports 目录下。

Q: 是否支持多用户协作与权限管理？

A: 当前版本仅支持单管理员账户，所有操作均通过同一账户执行。多用户与基于角色的权限控制已在 v2.0 规划中，预计通过引入 Flask-Login 与 RBAC 模型实现，届时将支持只读访客、编辑者与管理员三级权限。

Q: 如何将现有书签或浏览器收藏夹批量导入系统？

A: 系统提供了 import_bookmark 命令，支持解析 Chrome / Firefox 导出的 HTML 书签文件，自动提取标题与 URL 并生成资源条目。具体用法参见 docs/user-guide/import-export.md 章节。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
