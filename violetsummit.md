# LinkMaster Pro

LinkMaster Pro 是一个面向技术团队与内容运营者的外链资源归集与健康度监控平台。该项目旨在解决多源、多批次、大体量外部链接在采集、存储、校验与可视化展示过程中面临的碎片化与失效率问题。目标用户包括开源文档维护者、DevOps 工程师、数据爬虫开发者以及需要定期审计大量 URL 可用性的质量保障人员。通过统一的条目管理、状态标记与批量导出能力，LinkMaster Pro 将零散的原始链接转化为可检索、可追踪的结构化资产，显著降低人工维护成本。

## 功能概览

批量链接导入解析 支持从纯文本、CSV 及 JSON 格式批量摄入原始 URL，自动去重并识别协议头缺失或格式异常条目。

多维度状态标记 对每条链接标注来源批次（如第 73/80 批）、所属域名、路径层级与最后校验时间，支持自定义标签分类。

分布式健康检查 集成异步 HTTP 探活机制，可配置超时与重试策略，定期输出断链报告并标记响应码异常条目。

全文检索与过滤 基于路径关键词、域名或批次号进行多条件组合检索，支持正则表达式模式匹配高级查询。

结构化数据导出 支持将当前列表按 Markdown 列表、JSON 数组或纯文本行三种格式导出，适配不同下游系统输入要求。

审计日志追踪 记录每一次链接增删、状态变更与导出操作，保留操作人、时间戳与变更前后值，便于回溯。

权限分级管理 支持管理员、编辑者与访客三种角色，控制写入、校验触发与敏感信息可见范围。

## 应用场景

文档站外链定期巡检 技术文档站点维护者可使用 LinkMaster Pro 每日定时扫描文档内嵌的所有外部引用链接，自动标记返回 4xx 或 5xx 状态的失效链接，并生成待修复清单。

数据采集任务源头管理 数据工程师在启动大规模爬虫前，将待抓取的目标 URL 清单导入系统，系统自动剔除重复项并按照域名或路径前缀分组，显著提升调度效率。

多批次资源归档与比对 运营人员将不同批次的资源链接（如本项目的第 73/80 批）分别录入，利用批次标签进行横向比对，快速定位新增、删除或变更的条目。

合规审计前的链接审查 法务或安全团队在对外发布前，使用系统对全部外链进行协议与域名白名单校验，确保无敏感或违规外部资源混入。

## 快速开始

以下步骤指导您在本地环境快速启动 LinkMaster Pro 服务。

```bash
# 克隆代码仓库
git clone https://github.com/linkmaster-pro/linkmaster-pro.git

# 进入项目目录
cd linkmaster-pro

# 安装 Python 依赖（推荐使用 Python 3.9+ 虚拟环境）
pip install -r requirements.txt

# 初始化 SQLite 数据库表结构
python manage.py migrate

# 启动开发服务器（默认监听 127.0.0.1:8000）
python manage.py runserver
```

启动成功后，访问 http://127.0.0.1:8000 即可进入 Web 管理界面。首次使用请使用初始化脚本创建管理员账号：

```bash
python manage.py createsuperuser
```

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Python | 3.9 至 3.11 | 核心运行环境，3.12 暂未完成兼容性测试 |
| Django | 4.2.x LTS | Web 框架及 ORM 层，4.2 系列长期支持版本 |
| Celery | 5.3.x | 异步任务队列，用于定时健康检查与批量导入 |
| Redis | 7.0.x | Celery 消息代理与缓存后端，需启用持久化 |
| SQLite | 3.35+ | 默认轻量级数据库，生产环境可换用 PostgreSQL 14+ |
| aiohttp | 3.9.x | 异步 HTTP 客户端，用于并发链接探活 |
| pytest | 8.0.x | 单元测试与集成测试框架（仅开发环境需要） |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 用户手册 | /docs/user-guide/ | 如何导入链接、如何运行健康检查、如何导出报告 |
| 运维手册 | /docs/ops-guide/ | 如何配置 Celery 工作进程、如何更换数据库后端、如何设置日志轮转 |
| API 参考 | /docs/api-reference/ | 如何通过 RESTful API 批量提交 URL、如何获取批次状态 |
| 贡献者指南 | /docs/contributing/ | 代码风格规范、提交信息格式、本地测试流程 |

## 资源列表

- http://http://map.read.usuhx.com/Article/3694.shtml
- http://http://map.mobile.xqnqq.com/Article/89729.shtml
- http://http://map.mobile.xqnqq.com/Article/1200424.shtml
- http://http://map.mobile.xqnqq.com/Article/1451.shtml
- http://http://map.read.usuhx.com/Article/591020.shtml
- http://http://map.mobile.xqnqq.com/Article/74410.shtml
- http://http://map.read.usuhx.com/Article/8272175.shtml
- http://http://map.read.usuhx.com/Article/90032.shtml
- http://http://map.mobile.xqnqq.com/Article/4484408.shtml
- http://http://map.mobile.xqnqq.com/Article/8914.shtml
- http://http://map.read.usuhx.com/Article/56336.shtml
- http://http://map.mobile.xqnqq.com/Article/9997.shtml
- http://http://map.mobile.xqnqq.com/Article/7164846.shtml
- http://http://map.read.usuhx.com/Article/7476.shtml
- http://http://map.read.usuhx.com/Article/01648.shtml
- http://http://map.read.usuhx.com/Article/46240.shtml
- http://http://map.read.usuhx.com/Article/9303345.shtml
- http://http://map.read.usuhx.com/Article/7127.shtml
- http://http://map.read.usuhx.com/Article/94741.shtml
- http://http://map.mobile.xqnqq.com/Article/144309.shtml
- http://http://map.mobile.xqnqq.com/Article/9877.shtml
- http://http://map.mobile.xqnqq.com/Article/6180.shtml
- http://http://map.mobile.xqnqq.com/Article/7926.shtml
- http://http://map.read.usuhx.com/Article/128481.shtml
- http://http://map.read.usuhx.com/Article/20600.shtml
- http://http://map.read.usuhx.com/Article/2158102.shtml
- http://http://map.mobile.xqnqq.com/Article/311130.shtml
- http://http://map.mobile.xqnqq.com/Article/34456.shtml
- http://http://map.read.usuhx.com/Article/6194849.shtml
- http://http://map.read.usuhx.com/Article/4562725.shtml
- http://http://map.mobile.xqnqq.com/Article/4724.shtml
- http://http://map.mobile.xqnqq.com/Article/25236.shtml
- http://http://map.read.usuhx.com/Article/953340.shtml
- http://http://map.mobile.xqnqq.com/Article/380772.shtml
- http://http://map.read.usuhx.com/Article/6413.shtml
- http://http://map.read.usuhx.com/Article/7963.shtml
- http://http://map.mobile.xqnqq.com/Article/302866.shtml
- http://http://map.read.usuhx.com/Article/102337.shtml
- http://http://map.read.usuhx.com/Article/95185.shtml
- http://http://map.mobile.xqnqq.com/Article/75769.shtml
- http://http://map.read.usuhx.com/Article/8316192.shtml
- http://http://map.mobile.xqnqq.com/Article/70647.shtml
- http://http://map.read.usuhx.com/Article/76719.shtml
- http://http://map.mobile.xqnqq.com/Article/3708.shtml
- http://http://map.mobile.xqnqq.com/Article/9192179.shtml
- http://http://map.read.usuhx.com/Article/824249.shtml
- http://http://map.mobile.xqnqq.com/Article/484066.shtml
- http://http://map.mobile.xqnqq.com/Article/9205184.shtml
- http://http://map.read.usuhx.com/Article/1018458.shtml
- http://http://map.read.usuhx.com/Article/7400.shtml
- http://http://map.read.usuhx.com/Article/9180185.shtml
- http://http://map.read.usuhx.com/Article/1492.shtml
- http://http://map.read.usuhx.com/Article/942407.shtml
- http://http://map.mobile.xqnqq.com/Article/0862810.shtml
- http://http://map.mobile.xqnqq.com/Article/40056.shtml
- http://http://map.read.usuhx.com/Article/72368.shtml
- http://http://map.mobile.xqnqq.com/Article/7539398.shtml
- http://http://map.read.usuhx.com/Article/73259.shtml
- http://http://map.read.usuhx.com/Article/5313537.shtml
- http://http://map.read.usuhx.com/Article/207119.shtml
- http://http://map.read.usuhx.com/Article/919989.shtml
- http://http://map.mobile.xqnqq.com/Article/1322067.shtml
- http://http://map.read.usuhx.com/Article/41660.shtml
- http://http://map.mobile.xqnqq.com/Article/4319.shtml
- http://http://map.read.usuhx.com/Article/739099.shtml
- http://http://map.mobile.xqnqq.com/Article/8027.shtml
- http://http://map.read.usuhx.com/Article/30922.shtml
- http://http://map.mobile.xqnqq.com/Article/559349.shtml
- http://http://map.mobile.xqnqq.com/Article/1676739.shtml
- http://http://map.mobile.xqnqq.com/Article/932514.shtml
- http://http://map.read.usuhx.com/Article/4452.shtml
- http://http://map.read.usuhx.com/Article/8065822.shtml
- http://http://map.read.usuhx.com/Article/0056501.shtml
- http://http://map.read.usuhx.com/Article/8500.shtml
- http://http://map.read.usuhx.com/Article/17267.shtml
- http://http://map.mobile.xqnqq.com/Article/09672.shtml
- http://http://map.mobile.xqnqq.com/Article/46488.shtml
- http://http://map.read.usuhx.com/Article/520738.shtml
- http://http://map.mobile.xqnqq.com/Article/172993.shtml
- http://http://map.mobile.xqnqq.com/Article/2271.shtml
- http://http://map.read.usuhx.com/Article/9316.shtml
- http://http://map.read.usuhx.com/Article/420045.shtml
- http://http://map.read.usuhx.com/Article/6556695.shtml
- http://http://map.mobile.xqnqq.com/Article/475069.shtml
- http://http://map.mobile.xqnqq.com/Article/8109967.shtml
- http://http://map.mobile.xqnqq.com/Article/1626.shtml
- http://http://map.mobile.xqnqq.com/Article/2329832.shtml
- http://http://map.read.usuhx.com/Article/1087.shtml
- http://http://map.read.usuhx.com/Article/069267.shtml
- http://http://map.mobile.xqnqq.com/Article/54396.shtml
- http://http://map.mobile.xqnqq.com/Article/2630610.shtml
- http://http://map.read.usuhx.com/Article/8539002.shtml
- http://http://map.mobile.xqnqq.com/Article/2982700.shtml
- http://http://map.mobile.xqnqq.com/Article/11722.shtml
- http://http://map.mobile.xqnqq.com/Article/7814.shtml
- http://http://map.mobile.xqnqq.com/Article/1150.shtml
- http://http://map.read.usuhx.com/Article/04752.shtml
- http://http://map.read.usuhx.com/Article/1350845.shtml
- http://http://map.read.usuhx.com/Article/728149.shtml
- http://http://map.read.usuhx.com/Article/98779.shtml
- http://http://map.read.usuhx.com/Article/27522.shtml
- http://http://map.read.usuhx.com/Article/1389600.shtml
- http://http://map.read.usuhx.com/Article/504049.shtml
- http://http://map.mobile.xqnqq.com/Article/7622.shtml
- http://http://map.mobile.xqnqq.com/Article/754525.shtml
- http://http://map.mobile.xqnqq.com/Article/76896.shtml
- http://http://map.read.usuhx.com/Article/101205.shtml
- http://http://map.mobile.xqnqq.com/Article/502526.shtml
- http://http://map.read.usuhx.com/Article/8522653.shtml
- http://http://map.read.usuhx.com/Article/996562.shtml
- http://http://map.read.usuhx.com/Article/7687.shtml
- http://http://map.mobile.xqnqq.com/Article/6638782.shtml
- http://http://map.mobile.xqnqq.com/Article/09419.shtml
- http://http://map.read.usuhx.com/Article/2723.shtml
- http://http://map.read.usuhx.com/Article/84573.shtml
- http://http://map.mobile.xqnqq.com/Article/1946024.shtml
- http://http://map.read.usuhx.com/Article/38643.shtml
- http://http://map.read.usuhx.com/Article/1044.shtml
- http://http://map.read.usuhx.com/Article/10935.shtml
- http://http://map.mobile.xqnqq.com/Article/575389.shtml
- http://http://map.read.usuhx.com/Article/7669286.shtml
- http://http://map.read.usuhx.com/Article/9248205.shtml
- http://http://map.read.usuhx.com/Article/156868.shtml
- http://http://map.read.usuhx.com/Article/0222.shtml
- http://http://map.mobile.xqnqq.com/Article/3856559.shtml
- http://http://map.mobile.xqnqq.com/Article/26405.shtml
- http://http://map.read.usuhx.com/Article/534897.shtml
- http://http://map.mobile.xqnqq.com/Article/17128.shtml
- http://http://map.mobile.xqnqq.com/Article/133037.shtml
- http://http://map.read.usuhx.com/Article/4263593.shtml
- http://http://map.read.usuhx.com/Article/232487.shtml
- http://http://map.read.usuhx.com/Article/82583.shtml
- http://http://map.read.usuhx.com/Article/858825.shtml
- http://http://map.mobile.xqnqq.com/Article/412416.shtml
- http://http://map.read.usuhx.com/Article/9637486.shtml
- http://http://map.read.usuhx.com/Article/519614.shtml
- http://http://map.mobile.xqnqq.com/Article/6076730.shtml
- http://http://map.mobile.xqnqq.com/Article/38184.shtml
- http://http://map.read.usuhx.com/Article/5859857.shtml
- http://http://map.read.usuhx.com/Article/942831.shtml
- http://http://map.read.usuhx.com/Article/8400738.shtml
- http://http://map.mobile.xqnqq.com/Article/451315.shtml
- http://http://map.mobile.xqnqq.com/Article/5201668.shtml
- http://http://map.mobile.xqnqq.com/Article/9744865.shtml
- http://http://map.read.usuhx.com/Article/5511.shtml
- http://http://map.read.usuhx.com/Article/1305172.shtml
- http://http://map.mobile.xqnqq.com/Article/5303.shtml
- http://http://map.mobile.xqnqq.com/Article/3234.shtml
- http://http://map.read.usuhx.com/Article/4156.shtml
- http://http://map.read.usuhx.com/Article/0765.shtml
- http://http://map.mobile.xqnqq.com/Article/41695.shtml
- http://http://map.mobile.xqnqq.com/Article/6858.shtml
- http://http://map.read.usuhx.com/Article/4332.shtml
- http://http://map.mobile.xqnqq.com/Article/6870.shtml
- http://http://map.read.usuhx.com/Article/254004.shtml
- http://http://map.mobile.xqnqq.com/Article/141412.shtml
- http://http://map.read.usuhx.com/Article/695995.shtml
- http://http://map.mobile.xqnqq.com/Article/5198929.shtml
- http://http://map.read.usuhx.com/Article/12888.shtml
- http://http://map.read.usuhx.com/Article/666705.shtml
- http://http://map.read.usuhx.com/Article/4540.shtml
- http://http://map.mobile.xqnqq.com/Article/1628554.shtml
- http://http://map.mobile.xqnqq.com/Article/37164.shtml
- http://http://map.mobile.xqnqq.com/Article/9655.shtml
- http://http://map.read.usuhx.com/Article/7728925.shtml
- http://http://map.mobile.xqnqq.com/Article/3158741.shtml
- http://http://map.read.usuhx.com/Article/8458.shtml
- http://http://map.mobile.xqnqq.com/Article/9682.shtml
- http://http://map.mobile.xqnqq.com/Article/525071.shtml
- http://http://map.read.usuhx.com/Article/8403.shtml
- http://http://map.read.usuhx.com/Article/08014.shtml
- http://http://map.mobile.xqnqq.com/Article/926162.shtml
- http://http://map.read.usuhx.com/Article/97202.shtml
- http://http://map.read.usuhx.com/Article/23154.shtml
- http://http://map.read.usuhx.com/Article/25656.shtml
- http://http://map.mobile.xqnqq.com/Article/3703.shtml
- http://http://map.read.usuhx.com/Article/129447.shtml
- http://http://map.read.usuhx.com/Article/5418286.shtml
- http://http://map.read.usuhx.com/Article/272036.shtml
- http://http://map.mobile.xqnqq.com/Article/778544.shtml
- http://http://map.mobile.xqnqq.com/Article/5088.shtml
- http://http://map.read.usuhx.com/Article/37472.shtml
- http://http://map.mobile.xqnqq.com/Article/12215.shtml
- http://http://map.mobile.xqnqq.com/Article/91832.shtml
- http://http://map.mobile.xqnqq.com/Article/7036418.shtml
- http://http://map.mobile.xqnqq.com/Article/0103.shtml
- http://http://map.read.usuhx.com/Article/38394.shtml
- http://http://map.mobile.xqnqq.com/Article/5321.shtml
- http://http://map.read.usuhx.com/Article/87397.shtml
- http://http://map.read.usuhx.com/Article/8116.shtml
- http://http://map.read.usuhx.com/Article/729454.shtml
- http://http://map.read.usuhx.com/Article/3335325.shtml
- http://http://map.mobile.xqnqq.com/Article/0762340.shtml
- http://http://map.read.usuhx.com/Article/94531.shtml
- http://http://map.mobile.xqnqq.com/Article/023287.shtml
- http://http://map.mobile.xqnqq.com/Article/47945.shtml
- http://http://map.read.usuhx.com/Article/89430.shtml
- http://http://map.read.usuhx.com/Article/976318.shtml
- http://http://map.read.usuhx.com/Article/613470.shtml
- http://http://map.mobile.xqnqq.com/Article/7747.shtml
- http://http://map.mobile.xqnqq.com/Article/2746780.shtml
- http://http://map.mobile.xqnqq.com/Article/9215.shtml
- http://http://map.mobile.xqnqq.com/Article/74868.shtml
- http://http://map.read.usuhx.com/Article/272103.shtml
- http://http://map.read.usuhx.com/Article/188598.shtml
- http://http://map.mobile.xqnqq.com/Article/35842.shtml
- http://http://map.mobile.xqnqq.com/Article/06111.shtml
- http://http://map.mobile.xqnqq.com/Article/1083364.shtml
- http://http://map.mobile.xqnqq.com/Article/7993.shtml
- http://http://map.mobile.xqnqq.com/Article/219621.shtml
- http://http://map.mobile.xqnqq.com/Article/2120537.shtml
- http://http://map.mobile.xqnqq.com/Article/332391.shtml
- http://http://map.mobile.xqnqq.com/Article/88404.shtml
- http://http://map.mobile.xqnqq.com/Article/8243.shtml
- http://http://map.read.usuhx.com/Article/72589.shtml
- http://http://map.read.usuhx.com/Article/3184.shtml
- http://http://map.mobile.xqnqq.com/Article/3571.shtml
- http://http://map.mobile.xqnqq.com/Article/51835.shtml
- http://http://map.mobile.xqnqq.com/Article/284894.shtml
- http://http://map.read.usuhx.com/Article/327727.shtml
- http://http://map.read.usuhx.com/Article/5016619.shtml
- http://http://map.mobile.xqnqq.com/Article/2260.shtml
- http://http://map.read.usuhx.com/Article/5126209.shtml
- http://http://map.mobile.xqnqq.com/Article/0237449.shtml
- http://http://map.mobile.xqnqq.com/Article/93745.shtml
- http://http://map.read.usuhx.com/Article/515621.shtml
- http://http://map.mobile.xqnqq.com/Article/65349.shtml
- http://http://map.read.usuhx.com/Article/9327284.shtml
- http://http://map.mobile.xqnqq.com/Article/5310.shtml
- http://http://map.mobile.xqnqq.com/Article/5779607.shtml
- http://http://map.mobile.xqnqq.com/Article/5265.shtml
- http://http://map.mobile.xqnqq.com/Article/08641.shtml
- http://http://map.mobile.xqnqq.com/Article/0624217.shtml
- http://http://map.read.usuhx.com/Article/19761.shtml
- http://http://map.mobile.xqnqq.com/Article/727417.shtml
- http://http://map.read.usuhx.com/Article/97276.shtml
- http://http://map.read.usuhx.com/Article/07779.shtml
- http://http://map.read.usuhx.com/Article/571678.shtml
- http://http://map.mobile.xqnqq.com/Article/62429.shtml
- http://http://map.read.usuhx.com/Article/282568.shtml
- http://http://map.read.usuhx.com/Article/84851.shtml
- http://http://map.read.usuhx.com/Article/3916.shtml
- http://http://map.mobile.xqnqq.com/Article/7520.shtml
- http://http://map.read.usuhx.com/Article/1972537.shtml
- http://http://map.read.usuhx.com/Article/1951.shtml
- http://http://map.mobile.xqnqq.com/Article/74102.shtml
- http://http://map.mobile.xqnqq.com/Article/0501482.shtml
- http://http://map.read.usuhx.com/Article/1365.shtml
- http://http://map.mobile.xqnqq.com/Article/528627.shtml
- http://http://map.mobile.xqnqq.com/Article/01544.shtml

## 项目结构

```
linkmaster-pro/
├── manage.py                       # Django 项目管理入口
├── requirements.txt                # 生产环境 Python 依赖列表
├── config/                         # 项目全局配置目录
│   ├── settings.py                 # 基础配置（含数据库、缓存、时区）
│   ├── settings_dev.py             # 开发环境覆盖配置（DEBUG=True）
│   └── settings_prod.py            # 生产环境覆盖配置（需外部 secrets）
├── apps/                           # 所有自定义 Django 应用
│   ├── links/                      # 链接核心管理模块
│   │   ├── models.py               # Link, Batch, Tag 数据模型
│   │   ├── services.py             # 导入、去重、校验业务逻辑
│   │   └── tasks.py                # Celery 异步探活与通知任务
│   ├── checks/                     # 健康检查子模块
│   │   ├── http_client.py          # aiohttp 异步请求封装
│   │   └── reporters.py            # 断链报告生成器（Markdown/JSON）
│   └── accounts/                   # 用户与权限管理
│       ├── models.py               # 扩展 Django User 模型
│       └── middleware.py           # 操作审计中间件
├── static/                         # 静态资源（CSS, JS, 图片）
│   ├── css/                        # Bootstrap 5 定制主题
│   └── js/                         # 前端表格交互与实时过滤
├── templates/                      # Django 模板文件
│   ├── base.html                   # 基础布局模板
│   └── links/                      # 链接列表、详情、导入页面模板
├── docs/                           # 完整文档源文件（Markdown）
│   ├── user-guide/                 # 用户手册章节
│   ├── ops-guide/                  # 运维部署文档
│   └── api-reference/              # RESTful API 端点说明
├── tests/                          # 单元测试与集成测试
│   ├── test_models.py              # 数据模型测试用例
│   ├── test_services.py            # 核心业务逻辑测试
│   └── test_http_client.py         # 异步 HTTP 客户端模拟测试
├── scripts/                        # 运维与辅助脚本
│   ├── init_db.py                  # 初始化数据库与默认标签
│   └── batch_import.py             # 命令行批量导入工具（支持 CSV/JSON）
└── docker/                         # 容器化部署文件
    ├── Dockerfile                  # 多阶段构建镜像定义
    └── docker-compose.yml          # 含 Redis、Celery worker、Beat 服务
```

## 贡献指南

提交代码前请确保本地测试全部通过，并遵循以下标准化流程。

1. 查阅 issue 列表或发起新 issue 说明待解决的问题或提议的新功能，等待维护者确认方向以避免重复工作。

2. 从主分支检出新的功能分支，分支命名遵循 `feature/简短描述` 或 `fix/问题编号` 格式，例如 `feature/batch-export-json`。

3. 编写代码时严格遵守 PEP 8 风格规范，并为所有新增函数或类添加 docstring 说明。对于涉及外部请求的模块，必须编写模拟网络响应的单元测试。

4. 提交信息使用约定式提交格式，即 `<类型>: <简短描述>`，类型包括 `feat`、`fix`、`docs`、`test`、`chore` 等，描述部分使用现在时祈使语气。

5. 发起 Pull Request 到主分支，PR 描述中需关联对应 issue 编号，并附上手动测试截图或日志片段。等待至少一位维护者审核通过后合并。

## 常见问题

Q: 导入大量链接（超过 5000 条）时页面响应缓慢或超时，如何处理？

A: 推荐使用命令行批量导入工具 `scripts/batch_import.py`，该工具通过 Celery 任务链分批处理，避免 HTTP 请求超时。同时可在 `settings.py` 中调整 `DATA_UPLOAD_MAX_NUMBER_FIELDS` 参数，并确认 Redis 服务内存充足。

Q: 健康检查任务执行后，部分链接始终标记为超时，但浏览器访问正常，是什么原因？

A: 默认超时时间为 5 秒，部分目标服务器响应较慢或存在地域性延迟。请在管理界面或环境变量中调整 `CHECK_TIMEOUT` 至 10 秒或 15 秒。若仍失败，检查目标站点是否屏蔽了非浏览器 User-Agent，可在配置中修改探活请求头。

Q: 如何将当前 SQLite 数据库迁移至 PostgreSQL 用于生产环境？

A: 使用 Django 内置的 dumpdata 和 loaddata 命令完成数据导出。首先在 PostgreSQL 中创建空数据库，修改 `settings.py` 中的 `DATABASES` 配置为 PostgreSQL 连接串，然后执行 `python manage.py migrate` 创建表结构，最后运行 `python manage.py loaddata --exclude auth.permission --exclude contenttypes dump.json` 导入数据。注意导出前需清理缓存表。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
