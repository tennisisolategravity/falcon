# WebResource Aggregator

WebResource Aggregator 是一个面向技术研究者、数据挖掘工程师和内容聚合平台运营者的高密度外链资源归集系统。项目定位于将分散于多个内容源的结构化文章链接进行统一抽取、分类存储与状态监控，解决人工收集效率低下、链接失效不可感知、缺乏批量操作能力等痛点。当前批次为第 55/80 批，共计收录 250 个资源链接，覆盖双域名多目录深度数据。

本系统不提供内容抓取与渲染能力，专注于链接层面的元数据管理、可用性探测与批量导出，可作为上游数据源接入更大的 ETL 管道或检索前端。

## 功能概览

批量链接导入 支持从纯文本列表、CSV 或数据库查询结果批量注入链接池，自动去重并标记批次号。

定时可用性探测 基于可配置周期（默认 24 小时）对池内所有链接发起 HEAD/GET 请求，记录状态码、响应时间和内容长度。

失效自动标记 连续三次探测失败或返回 4xx/5xx 状态码的链接自动转入失效队列，支持人工复核与批量清理。

域名分类过滤 根据链接中的域名（read.usuhx.com 与 mobile.xqnqq.com）自动分区，支持按域名单独导出或执行差异化策略。

批次进度追踪 每个批次记录总链接数、有效数、失效数、探测次数与最后探测时间，便于统计通过率与质量趋势。

结构化导出 支持 JSON、CSV 与纯文本三种导出格式，可自定义输出字段，便于下游系统消费。

RESTful 管理接口 提供链接增删改查、手动触发探测、批量状态更新等 API，方便集成到自动化运维脚本中。

## 应用场景

技术文档归档系统前置校验 在将外部文章链接存入企业知识库之前，通过本系统批量检测所有引用链接的有效性，提前剔除失效资源，保证归档质量。

舆情监控平台数据源维护 舆情系统依赖大量外部资讯链接作为输入，使用本系统定期巡检订阅源链接的健康状况，及时发现内容下架或域名迁移，减少采集空跑。

学术参考文献链接保鲜 研究机构或高校实验室维护的论文引用数据库中，通过本系统周期性检查引用链接的可达性，自动标记失效文献，辅助馆藏更新决策。

内容聚合站外链审计 内容聚合站点在引入第三方文章链接时，利用本系统进行上线前批量筛查，确保所有外链均能正常访问，提升用户体验与搜索引擎评价。

数据交换质量看板 数据中台团队可将本系统作为数据源质量监控的一个环节，将链接可用率作为数据源健康度 KPI，接入统一监控告警体系。

## 快速开始

以下步骤演示如何在 Linux 服务器上完成项目克隆、依赖安装与服务启动。

```bash
git clone https://github.com/your-org/webresource-aggregator.git
cd webresource-aggregator

# 创建 Python 虚拟环境
python3 -m venv venv
source venv/bin/activate

# 安装核心依赖
pip install -r requirements.txt

# 复制环境变量模板并修改数据库连接
cp .env.example .env
vim .env

# 初始化数据库表结构
python manage.py migrate

# 导入当前批次链接列表（假设文件为 batch_55.txt）
python manage.py import --batch 55 --file ./data/batch_55.txt

# 启动探测任务（后台运行）
python manage.py probe --batch 55 --workers 4 --daemon

# 查看批次统计
python manage.py status --batch 55
```

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 及以上 | 核心运行环境，低于 3.9 将不支持类型注解与异步特性 |
| PostgreSQL | 13.0 及以上 | 主数据库，用于存储链接元数据、探测历史与批次信息 |
| Redis | 6.0 及以上 | 可选，用于分布式锁与任务队列缓存，单机模式可禁用 |
| aiohttp | 3.8.0 及以上 | 异步 HTTP 客户端，支撑高并发探测任务 |
| SQLAlchemy | 2.0.0 及以上 | ORM 框架，统一数据库操作接口 |
| alembic | 1.9.0 及以上 | 数据库版本迁移工具，用于 schema 变更管理 |
| python-dotenv | 1.0.0 及以上 | 环境变量加载，支持 .env 配置方式 |
| pytest | 7.0.0 及以上 | 仅开发与测试环境需要，用于单元测试与集成测试 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | /docs/user-guide.md | 如何配置探测策略、如何导入导出链接、如何查看批次报告 |
| 运维手册 | /docs/ops-guide.md | 如何部署生产环境、如何备份数据库、如何升级迁移 |
| API 参考 | /docs/api-reference.md | 各 RESTful 端点的请求/响应格式、鉴权方式、速率限制 |
| 设计文档 | /docs/design.md | 系统架构图、数据模型 ER 图、探测调度算法说明 |
| 测试指南 | /docs/testing.md | 如何运行单元测试、如何构造 mock 数据、如何覆盖边界条件 |

## 资源列表

- http://http://map.read.usuhx.com/Article/720590.shtml
- http://http://map.read.usuhx.com/Article/4359.shtml
- http://http://map.read.usuhx.com/Article/8318863.shtml
- http://http://map.read.usuhx.com/Article/9205981.shtml
- http://http://map.mobile.xqnqq.com/Article/5154813.shtml
- http://http://map.mobile.xqnqq.com/Article/941284.shtml
- http://http://map.read.usuhx.com/Article/227012.shtml
- http://http://map.mobile.xqnqq.com/Article/153313.shtml
- http://http://map.mobile.xqnqq.com/Article/0491498.shtml
- http://http://map.mobile.xqnqq.com/Article/7445773.shtml
- http://http://map.read.usuhx.com/Article/138595.shtml
- http://http://map.mobile.xqnqq.com/Article/1044476.shtml
- http://http://map.mobile.xqnqq.com/Article/97716.shtml
- http://http://map.mobile.xqnqq.com/Article/34360.shtml
- http://http://map.mobile.xqnqq.com/Article/789815.shtml
- http://http://map.read.usuhx.com/Article/634710.shtml
- http://http://map.read.usuhx.com/Article/4650585.shtml
- http://http://map.mobile.xqnqq.com/Article/1459.shtml
- http://http://map.read.usuhx.com/Article/411426.shtml
- http://http://map.mobile.xqnqq.com/Article/594277.shtml
- http://http://map.read.usuhx.com/Article/29418.shtml
- http://http://map.mobile.xqnqq.com/Article/5513.shtml
- http://http://map.mobile.xqnqq.com/Article/61533.shtml
- http://http://map.read.usuhx.com/Article/5057.shtml
- http://http://map.mobile.xqnqq.com/Article/04742.shtml
- http://http://map.mobile.xqnqq.com/Article/65509.shtml
- http://http://map.mobile.xqnqq.com/Article/5291.shtml
- http://http://map.read.usuhx.com/Article/13286.shtml
- http://http://map.read.usuhx.com/Article/70119.shtml
- http://http://map.read.usuhx.com/Article/7548.shtml
- http://http://map.mobile.xqnqq.com/Article/2682.shtml
- http://http://map.mobile.xqnqq.com/Article/19212.shtml
- http://http://map.mobile.xqnqq.com/Article/785831.shtml
- http://http://map.read.usuhx.com/Article/4027.shtml
- http://http://map.read.usuhx.com/Article/3140164.shtml
- http://http://map.mobile.xqnqq.com/Article/1241.shtml
- http://http://map.read.usuhx.com/Article/3151011.shtml
- http://http://map.mobile.xqnqq.com/Article/786461.shtml
- http://http://map.mobile.xqnqq.com/Article/8651.shtml
- http://http://map.read.usuhx.com/Article/47817.shtml
- http://http://map.read.usuhx.com/Article/77953.shtml
- http://http://map.read.usuhx.com/Article/469706.shtml
- http://http://map.read.usuhx.com/Article/3099.shtml
- http://http://map.read.usuhx.com/Article/1023796.shtml
- http://http://map.read.usuhx.com/Article/799496.shtml
- http://http://map.mobile.xqnqq.com/Article/255249.shtml
- http://http://map.read.usuhx.com/Article/6204336.shtml
- http://http://map.read.usuhx.com/Article/7138530.shtml
- http://http://map.read.usuhx.com/Article/7125.shtml
- http://http://map.read.usuhx.com/Article/013322.shtml
- http://http://map.read.usuhx.com/Article/8064773.shtml
- http://http://map.read.usuhx.com/Article/875700.shtml
- http://http://map.mobile.xqnqq.com/Article/9337.shtml
- http://http://map.read.usuhx.com/Article/5310216.shtml
- http://http://map.read.usuhx.com/Article/7108.shtml
- http://http://map.read.usuhx.com/Article/2081.shtml
- http://http://map.mobile.xqnqq.com/Article/55553.shtml
- http://http://map.mobile.xqnqq.com/Article/994900.shtml
- http://http://map.mobile.xqnqq.com/Article/6669887.shtml
- http://http://map.read.usuhx.com/Article/64038.shtml
- http://http://map.read.usuhx.com/Article/17955.shtml
- http://http://map.mobile.xqnqq.com/Article/30840.shtml
- http://http://map.mobile.xqnqq.com/Article/2035901.shtml
- http://http://map.mobile.xqnqq.com/Article/256346.shtml
- http://http://map.mobile.xqnqq.com/Article/60781.shtml
- http://http://map.mobile.xqnqq.com/Article/9993.shtml
- http://http://map.read.usuhx.com/Article/30618.shtml
- http://http://map.mobile.xqnqq.com/Article/2407349.shtml
- http://http://map.mobile.xqnqq.com/Article/4006845.shtml
- http://http://map.read.usuhx.com/Article/39634.shtml
- http://http://map.mobile.xqnqq.com/Article/4331.shtml
- http://http://map.mobile.xqnqq.com/Article/4485345.shtml
- http://http://map.mobile.xqnqq.com/Article/4114.shtml
- http://http://map.read.usuhx.com/Article/6907.shtml
- http://http://map.read.usuhx.com/Article/07723.shtml
- http://http://map.mobile.xqnqq.com/Article/947297.shtml
- http://http://map.read.usuhx.com/Article/7254287.shtml
- http://http://map.read.usuhx.com/Article/7763358.shtml
- http://http://map.read.usuhx.com/Article/2032.shtml
- http://http://map.mobile.xqnqq.com/Article/2019.shtml
- http://http://map.mobile.xqnqq.com/Article/26331.shtml
- http://http://map.mobile.xqnqq.com/Article/77598.shtml
- http://http://map.read.usuhx.com/Article/48284.shtml
- http://http://map.read.usuhx.com/Article/626681.shtml
- http://http://map.read.usuhx.com/Article/2283975.shtml
- http://http://map.mobile.xqnqq.com/Article/28311.shtml
- http://http://map.mobile.xqnqq.com/Article/6288.shtml
- http://http://map.read.usuhx.com/Article/3510.shtml
- http://http://map.mobile.xqnqq.com/Article/2877570.shtml
- http://http://map.read.usuhx.com/Article/40102.shtml
- http://http://map.mobile.xqnqq.com/Article/7508394.shtml
- http://http://map.mobile.xqnqq.com/Article/0163505.shtml
- http://http://map.mobile.xqnqq.com/Article/2082.shtml
- http://http://map.mobile.xqnqq.com/Article/144642.shtml
- http://http://map.mobile.xqnqq.com/Article/75659.shtml
- http://http://map.mobile.xqnqq.com/Article/4217.shtml
- http://http://map.mobile.xqnqq.com/Article/4269.shtml
- http://http://map.mobile.xqnqq.com/Article/2004910.shtml
- http://http://map.read.usuhx.com/Article/42674.shtml
- http://http://map.mobile.xqnqq.com/Article/3401443.shtml
- http://http://map.mobile.xqnqq.com/Article/7521803.shtml
- http://http://map.read.usuhx.com/Article/723654.shtml
- http://http://map.read.usuhx.com/Article/1528628.shtml
- http://http://map.mobile.xqnqq.com/Article/2153.shtml
- http://http://map.read.usuhx.com/Article/0187694.shtml
- http://http://map.read.usuhx.com/Article/819819.shtml
- http://http://map.read.usuhx.com/Article/1146.shtml
- http://http://map.mobile.xqnqq.com/Article/6550875.shtml
- http://http://map.read.usuhx.com/Article/7261.shtml
- http://http://map.read.usuhx.com/Article/4335846.shtml
- http://http://map.mobile.xqnqq.com/Article/99537.shtml
- http://http://map.read.usuhx.com/Article/7674701.shtml
- http://http://map.read.usuhx.com/Article/763139.shtml
- http://http://map.mobile.xqnqq.com/Article/8952.shtml
- http://http://map.read.usuhx.com/Article/71884.shtml
- http://http://map.read.usuhx.com/Article/889002.shtml
- http://http://map.read.usuhx.com/Article/796013.shtml
- http://http://map.read.usuhx.com/Article/8599758.shtml
- http://http://map.read.usuhx.com/Article/7501.shtml
- http://http://map.read.usuhx.com/Article/348691.shtml
- http://http://map.read.usuhx.com/Article/2279.shtml
- http://http://map.read.usuhx.com/Article/6604080.shtml
- http://http://map.mobile.xqnqq.com/Article/178854.shtml
- http://http://map.mobile.xqnqq.com/Article/8496817.shtml
- http://http://map.read.usuhx.com/Article/73774.shtml
- http://http://map.mobile.xqnqq.com/Article/150610.shtml
- http://http://map.read.usuhx.com/Article/7469.shtml
- http://http://map.mobile.xqnqq.com/Article/3588.shtml
- http://http://map.mobile.xqnqq.com/Article/916889.shtml
- http://http://map.read.usuhx.com/Article/6704042.shtml
- http://http://map.read.usuhx.com/Article/9238.shtml
- http://http://map.read.usuhx.com/Article/6376563.shtml
- http://http://map.read.usuhx.com/Article/7494.shtml
- http://http://map.read.usuhx.com/Article/4276800.shtml
- http://http://map.read.usuhx.com/Article/0772.shtml
- http://http://map.read.usuhx.com/Article/456290.shtml
- http://http://map.read.usuhx.com/Article/291093.shtml
- http://http://map.read.usuhx.com/Article/9507.shtml
- http://http://map.mobile.xqnqq.com/Article/5699.shtml
- http://http://map.read.usuhx.com/Article/405917.shtml
- http://http://map.mobile.xqnqq.com/Article/4447709.shtml
- http://http://map.mobile.xqnqq.com/Article/634144.shtml
- http://http://map.read.usuhx.com/Article/021351.shtml
- http://http://map.read.usuhx.com/Article/0527305.shtml
- http://http://map.mobile.xqnqq.com/Article/64434.shtml
- http://http://map.read.usuhx.com/Article/49193.shtml
- http://http://map.mobile.xqnqq.com/Article/7901744.shtml
- http://http://map.mobile.xqnqq.com/Article/1996884.shtml
- http://http://map.mobile.xqnqq.com/Article/99491.shtml
- http://http://map.mobile.xqnqq.com/Article/9060812.shtml
- http://http://map.read.usuhx.com/Article/3304.shtml
- http://http://map.mobile.xqnqq.com/Article/5074261.shtml
- http://http://map.mobile.xqnqq.com/Article/442437.shtml
- http://http://map.read.usuhx.com/Article/149802.shtml
- http://http://map.mobile.xqnqq.com/Article/179538.shtml
- http://http://map.mobile.xqnqq.com/Article/27700.shtml
- http://http://map.read.usuhx.com/Article/9501862.shtml
- http://http://map.read.usuhx.com/Article/088249.shtml
- http://http://map.read.usuhx.com/Article/06945.shtml
- http://http://map.mobile.xqnqq.com/Article/3540.shtml
- http://http://map.read.usuhx.com/Article/6808.shtml
- http://http://map.read.usuhx.com/Article/2954998.shtml
- http://http://map.read.usuhx.com/Article/4607085.shtml
- http://http://map.mobile.xqnqq.com/Article/3950.shtml
- http://http://map.mobile.xqnqq.com/Article/9233458.shtml
- http://http://map.mobile.xqnqq.com/Article/56968.shtml
- http://http://map.read.usuhx.com/Article/8425512.shtml
- http://http://map.mobile.xqnqq.com/Article/2804.shtml
- http://http://map.mobile.xqnqq.com/Article/745137.shtml
- http://http://map.mobile.xqnqq.com/Article/377912.shtml
- http://http://map.mobile.xqnqq.com/Article/06309.shtml
- http://http://map.read.usuhx.com/Article/5698682.shtml
- http://http://map.mobile.xqnqq.com/Article/4429652.shtml
- http://http://map.read.usuhx.com/Article/381308.shtml
- http://http://map.mobile.xqnqq.com/Article/253484.shtml
- http://http://map.read.usuhx.com/Article/179150.shtml
- http://http://map.mobile.xqnqq.com/Article/630228.shtml
- http://http://map.read.usuhx.com/Article/446774.shtml
- http://http://map.read.usuhx.com/Article/2642.shtml
- http://http://map.mobile.xqnqq.com/Article/46222.shtml
- http://http://map.mobile.xqnqq.com/Article/703371.shtml
- http://http://map.mobile.xqnqq.com/Article/4069829.shtml
- http://http://map.mobile.xqnqq.com/Article/6581.shtml
- http://http://map.mobile.xqnqq.com/Article/849672.shtml
- http://http://map.mobile.xqnqq.com/Article/085839.shtml
- http://http://map.mobile.xqnqq.com/Article/1070.shtml
- http://http://map.read.usuhx.com/Article/2301.shtml
- http://http://map.read.usuhx.com/Article/5014.shtml
- http://http://map.mobile.xqnqq.com/Article/4390.shtml
- http://http://map.read.usuhx.com/Article/6093645.shtml
- http://http://map.mobile.xqnqq.com/Article/9271061.shtml
- http://http://map.read.usuhx.com/Article/450338.shtml
- http://http://map.read.usuhx.com/Article/858525.shtml
- http://http://map.mobile.xqnqq.com/Article/11120.shtml
- http://http://map.read.usuhx.com/Article/76036.shtml
- http://http://map.read.usuhx.com/Article/4587208.shtml
- http://http://map.read.usuhx.com/Article/62380.shtml
- http://http://map.mobile.xqnqq.com/Article/0459.shtml
- http://http://map.mobile.xqnqq.com/Article/1010.shtml
- http://http://map.read.usuhx.com/Article/7781259.shtml
- http://http://map.mobile.xqnqq.com/Article/7236008.shtml
- http://http://map.mobile.xqnqq.com/Article/56428.shtml
- http://http://map.read.usuhx.com/Article/43839.shtml
- http://http://map.mobile.xqnqq.com/Article/7948.shtml
- http://http://map.read.usuhx.com/Article/842061.shtml
- http://http://map.mobile.xqnqq.com/Article/72928.shtml
- http://http://map.read.usuhx.com/Article/4618.shtml
- http://http://map.mobile.xqnqq.com/Article/3349.shtml
- http://http://map.mobile.xqnqq.com/Article/226243.shtml
- http://http://map.mobile.xqnqq.com/Article/558717.shtml
- http://http://map.read.usuhx.com/Article/14784.shtml
- http://http://map.mobile.xqnqq.com/Article/02871.shtml
- http://http://map.mobile.xqnqq.com/Article/982808.shtml
- http://http://map.mobile.xqnqq.com/Article/0685270.shtml
- http://http://map.mobile.xqnqq.com/Article/00371.shtml
- http://http://map.read.usuhx.com/Article/8831.shtml
- http://http://map.mobile.xqnqq.com/Article/35102.shtml
- http://http://map.read.usuhx.com/Article/218709.shtml
- http://http://map.mobile.xqnqq.com/Article/3885.shtml
- http://http://map.mobile.xqnqq.com/Article/969957.shtml
- http://http://map.read.usuhx.com/Article/3436.shtml
- http://http://map.mobile.xqnqq.com/Article/118481.shtml
- http://http://map.mobile.xqnqq.com/Article/6990542.shtml
- http://http://map.read.usuhx.com/Article/2468025.shtml
- http://http://map.mobile.xqnqq.com/Article/308289.shtml
- http://http://map.mobile.xqnqq.com/Article/780802.shtml
- http://http://map.mobile.xqnqq.com/Article/5856927.shtml
- http://http://map.mobile.xqnqq.com/Article/9211734.shtml
- http://http://map.mobile.xqnqq.com/Article/854422.shtml
- http://http://map.mobile.xqnqq.com/Article/6477681.shtml
- http://http://map.mobile.xqnqq.com/Article/054200.shtml
- http://http://map.read.usuhx.com/Article/68959.shtml
- http://http://map.mobile.xqnqq.com/Article/18281.shtml
- http://http://map.read.usuhx.com/Article/597047.shtml
- http://http://map.mobile.xqnqq.com/Article/087772.shtml
- http://http://map.mobile.xqnqq.com/Article/5450037.shtml
- http://http://map.read.usuhx.com/Article/072381.shtml
- http://http://map.mobile.xqnqq.com/Article/392439.shtml
- http://http://map.mobile.xqnqq.com/Article/5170911.shtml
- http://http://map.mobile.xqnqq.com/Article/49837.shtml
- http://http://map.mobile.xqnqq.com/Article/142450.shtml
- http://http://map.mobile.xqnqq.com/Article/8596.shtml
- http://http://map.mobile.xqnqq.com/Article/7620.shtml
- http://http://map.read.usuhx.com/Article/1804.shtml
- http://http://map.mobile.xqnqq.com/Article/2397.shtml
- http://http://map.read.usuhx.com/Article/1733.shtml
- http://http://map.mobile.xqnqq.com/Article/62355.shtml
- http://http://map.mobile.xqnqq.com/Article/101345.shtml
- http://http://map.mobile.xqnqq.com/Article/97154.shtml
- http://http://map.mobile.xqnqq.com/Article/99048.shtml

## 项目结构

```
webresource-aggregator/
├── cmd/                                    # 命令行入口
│   ├── cli.py                              # 主 CLI 调度器，注册所有子命令
│   └── commands/                           # 子命令实现
│       ├── import.py                       # 导入链接列表，支持去重与批次绑定
│       ├── probe.py                        # 触发探测任务，可指定并发数与超时
│       ├── status.py                       # 查询批次统计与详细状态
│       └── export.py                       # 导出链接数据，支持多种格式
├── internal/                               # 内部核心逻辑，不对外暴露
│   ├── core/                               # 核心业务模型
│   │   ├── link.py                         # Link 实体，包含 URL、域名、状态、批次号
│   │   ├── batch.py                        # Batch 实体，管理批次元数据与进度
│   │   └── probe_result.py                 # 探测结果记录，含状态码与响应时间
│   ├── engine/                             # 探测引擎
│   │   ├── http_client.py                  # 异步 HTTP 客户端封装，支持重试与代理
│   │   ├── scheduler.py                    # 调度器，控制探测频率与队列管理
│   │   └── worker_pool.py                  # 工作池，管理并发探测协程
│   └── storage/                            # 存储层
│       ├── database.py                     # 数据库连接池与会话管理
│       ├── repository.py                   # 数据仓库，封装 CRUD 与复杂查询
│       └── migrations/                     # Alembic 迁移脚本
├── api/                                    # RESTful 服务
│   ├── app.py                              # FastAPI 应用实例，注册路由
│   ├── routes/                             # 路由分组
│   │   ├── links.py                        # /api/v1/links 增删改查端点
│   │   ├── batches.py                      # /api/v1/batches 批次管理端点
│   │   └── probe.py                        # /api/v1/probe 手动触发探测端点
│   └── schemas/                            # Pydantic 请求/响应模型
├── scripts/                                # 运维与辅助脚本
│   ├── health_check.sh                     # 健康检查脚本，用于容器探针
│   ├── backup_db.sh                        # 数据库备份脚本，保留最近 7 天
│   └── seed_demo_data.py                   # 生成演示数据用于测试环境
├── tests/                                  # 测试代码
│   ├── unit/                               # 单元测试，覆盖核心模型与工具函数
│   ├── integration/                        # 集成测试，需要真实数据库与 Redis
│   └── fixtures/                           # 测试固件，包含 mock 链接列表
├── docs/                                   # 文档目录
│   ├── user-guide.md                       # 用户手册，含操作截图与常见流程
│   ├── ops-guide.md                        # 运维手册，含部署拓扑与监控配置
│   └── api-reference.md                    # API 详细参考，含 curl 示例
├── data/                                   # 数据文件目录
│   └── batch_55.txt                        # 第 55 批次原始链接列表
├── .env.example                            # 环境变量模板
├── requirements.txt                        # 生产依赖
├── requirements-dev.txt                    # 开发额外依赖
├── pyproject.toml                          # 项目元数据与构建配置
└── README.md                               # 本文件
```

## 贡献指南

提交 Issue 报告缺陷或功能请求 在 GitHub Issues 页面选择对应模板，详细描述复现步骤、预期行为与实际行为，并附上相关日志或截图。

Fork 仓库并创建功能分支 从主分支 checkout 出新分支，命名规范为 feature/功能简述 或 fix/问题简述，避免直接在 main 分支上修改。

编写单元测试与集成测试 新增或修改代码必须同步更新对应测试用例，确保测试覆盖率达到 80% 以上，所有测试用例在提交前必须通过。

提交 Pull Request 并关联 Issue PR 标题需简明扼要，正文描述改动内容、影响范围与测试结果，并关联相关 Issue 编号。等待至少一名维护者 review 后合并。

遵守代码风格规范 项目使用 Black 作为 Python 代码格式化工具，isort 管理 import 顺序，flake8 进行静态检查。提交前运行 make lint 自动修复格式问题。

## 常见问题

Q: 探测时遇到大量超时或连接拒绝，如何调整参数？

A: 可通过环境变量或命令行参数调整探测超时时间（--timeout 默认 10 秒）、重试次数（--retries 默认 3 次）以及并发工作数（--workers 默认 4）。对于网络环境较差的场景，建议适当降低并发数并增加超时与重试。同时可配置代理服务器（通过 HTTP_PROXY 环境变量）以绕过网络限制。

Q: 如何迁移已有链接数据到新版本数据库？

A: 项目使用 Alembic 管理数据库迁移。执行 python manage.py migrate 会自动检测当前数据库版本并应用所有未执行的迁移脚本。若需要回滚，可使用 alembic downgrade -1 回退一个版本。建议在生产环境升级前先在测试环境执行迁移并验证数据完整性。迁移过程中会自动保留已有链接数据，不会发生数据丢失。

Q: 能否自定义探测请求头或携带 Cookie？

A: 支持通过配置文件或环境变量自定义请求头。在 .env 文件中设置 PROBE_HEADERS='{"User-Agent": "CustomBot/1.0", "X-Custom": "value"}'，或在命令行调用时通过 --headers 参数传递 JSON 格式字符串。对于需要维持会话的场景，可在配置中启用 Cookie 持久化（--cookies 参数），系统会自动保存并重用响应的 Set-Cookie。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
