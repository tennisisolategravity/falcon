# LinkMaster Pro

LinkMaster Pro 是一个面向技术团队与内容运营者的外链资源管理与导航聚合系统。该项目定位为轻量级、可自托管的技术资源目录中枢，旨在帮助用户将分散于各类文档、邮件、书签中的外部链接进行统一采集、分类标注、健康检查与快速检索。目标用户包括运维工程师、技术文档撰写者、知识库管理员以及需要长期维护大量外链引用的开发团队。LinkMaster Pro 通过标准化的数据模型与 RESTful API，将无序的 URL 集合转化为可维护、可审计、可共享的结构化资产，有效解决外链失效、引用混乱与检索困难等常见痛点。

## 功能概览

批量链接导入与去重：支持从纯文本、CSV 及 JSON 格式批量导入 URL 列表，系统自动执行语法校验与重复检测，避免冗余条目入库。

自动健康状态巡检：内置定时任务引擎，可对已收录链接进行 HTTP 状态码检查，标记失效链接并生成变更报告。

多维度分类标签系统：允许用户为每条链接自定义标签组，支持层级标签与模糊搜索，便于按项目、领域或优先级组织资源。

全文元数据提取：自动抓取目标页面的标题、描述与关键词信息，辅助用户快速了解链接内容，减少手动备注成本。

检索与过滤接口：提供基于标签、域名、状态码、收录时间等多条件组合的查询 API，支持分页与排序，适配前端展示需求。

导入导出兼容性：支持将链接库导出为 Markdown 列表、HTML 目录或 JSON 结构化数据，便于嵌入文档站点或迁移至其他平台。

权限与操作日志：内置基于角色的访问控制，记录所有增删改查操作日志，满足团队协作与审计追溯要求。

## 应用场景

技术文档团队的外链资产管理：文档中引用了大量外部规范、SDK 下载页与 API 参考链接，LinkMaster Pro 可定期检查这些链接的可达性，在文档发布前自动预警失效条目，避免用户点击后遇到 404 错误。

开源项目 README 与官网的资源导航：开源项目维护者可使用该系统维护项目生态链中的相关工具、插件、教程与社区论坛链接，通过标签分类后一键生成标准的 Markdown 资源列表，直接嵌入项目仓库。

企业知识库的内外部引用中介：企业内部的 Confluence 或 Notion 知识库中混杂了大量外部参考链接，通过 LinkMaster Pro 统一代理引用，既便于统一更新失效地址，也可通过访问日志分析团队关注的外部资源趋势。

个人开发者的书签集中管理：开发者将日常查阅的技术博客、在线工具、API 文档与 GitHub 仓库链接集中录入系统，利用全文检索与标签过滤快速定位所需资源，替代浏览器自带书签的扁平化组织方式。

运维监控看板的依赖项检查：运维团队将监控告警规则中引用的外部数据源地址、仪表盘嵌入链接等纳入系统，定时巡检其可用性，在依赖服务出现故障时提前发现并切换备用地址。

## 快速开始

以下步骤将指导您在本地环境快速启动 LinkMaster Pro 服务。

```bash
# 1. 克隆项目仓库
git clone https://github.com/your-org/linkmaster-pro.git

# 2. 进入项目根目录
cd linkmaster-pro

# 3. 安装依赖项（使用 pip 与虚拟环境）
python -m venv venv
source venv/bin/activate  # Windows 系统请使用 venv\Scripts\activate
pip install -r requirements.txt

# 4. 初始化数据库结构
python manage.py migrate

# 5. 创建管理员账户
python manage.py createsuperuser

# 6. 启动开发服务器
python manage.py runserver 0.0.0.0:8000
```

服务启动后，访问 http://localhost:8000 即可进入系统主页。使用创建的管理员账户登录后，可通过界面右上角的导入功能开始录入链接资源。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.8 及以上 | 核心运行环境，建议使用 3.10 LTS 版本 |
| Django | 4.2.x LTS | 后端 Web 框架，提供 ORM 与路由管理 |
| PostgreSQL | 14.x 及以上 | 生产环境推荐使用的数据库，支持 JSON 字段索引 |
| Redis | 7.x 及以上 | 缓存后端与消息队列代理，用于定时任务调度 |
| Celery | 5.3.x | 分布式任务队列，执行健康巡检与元数据抓取 |
| gunicorn | 21.x | WSGI 服务器，用于生产环境部署 |
| Node.js | 18.x 及以上 | 仅当需要构建前端静态资源时使用 |
| Nginx | 1.24.x | 反向代理与静态文件服务（生产环境推荐） |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户指南 | /docs/user-guide/ | 如何导入链接、设置标签、查看健康报告以及导出资源列表 |
| 运维手册 | /docs/ops-guide/ | 如何配置巡检频率、备份数据库、扩展 Celery Worker 以及升级版本 |
| API 参考 | /docs/api-reference/ | 有哪些 RESTful 端点、请求参数格式、认证方式以及错误码含义 |
| 开发贡献 | /docs/contributing/ | 本地开发环境如何搭建、代码风格规范、PR 提交流程以及测试编写要求 |

## 资源列表

- http://http://map.read.usuhx.com/Article/1464.shtml
- http://http://map.mobile.xqnqq.com/Article/4889.shtml
- http://http://map.mobile.xqnqq.com/Article/4521001.shtml
- http://http://map.read.usuhx.com/Article/7253573.shtml
- http://http://map.read.usuhx.com/Article/898464.shtml
- http://http://map.read.usuhx.com/Article/924574.shtml
- http://http://map.read.usuhx.com/Article/2888.shtml
- http://http://map.read.usuhx.com/Article/11104.shtml
- http://http://map.mobile.xqnqq.com/Article/4140818.shtml
- http://http://map.mobile.xqnqq.com/Article/0760.shtml
- http://http://map.mobile.xqnqq.com/Article/01578.shtml
- http://http://map.mobile.xqnqq.com/Article/6881.shtml
- http://http://map.mobile.xqnqq.com/Article/3173.shtml
- http://http://map.mobile.xqnqq.com/Article/67463.shtml
- http://http://map.mobile.xqnqq.com/Article/493614.shtml
- http://http://map.mobile.xqnqq.com/Article/2556.shtml
- http://http://map.read.usuhx.com/Article/54650.shtml
- http://http://map.mobile.xqnqq.com/Article/1092764.shtml
- http://http://map.read.usuhx.com/Article/8397309.shtml
- http://http://map.read.usuhx.com/Article/629497.shtml
- http://http://map.mobile.xqnqq.com/Article/853314.shtml
- http://http://map.read.usuhx.com/Article/6161.shtml
- http://http://map.mobile.xqnqq.com/Article/2476311.shtml
- http://http://map.mobile.xqnqq.com/Article/4008246.shtml
- http://http://map.read.usuhx.com/Article/39980.shtml
- http://http://map.read.usuhx.com/Article/2420.shtml
- http://http://map.mobile.xqnqq.com/Article/10950.shtml
- http://http://map.mobile.xqnqq.com/Article/744901.shtml
- http://http://map.read.usuhx.com/Article/0444766.shtml
- http://http://map.read.usuhx.com/Article/2490344.shtml
- http://http://map.mobile.xqnqq.com/Article/4457248.shtml
- http://http://map.mobile.xqnqq.com/Article/7450.shtml
- http://http://map.mobile.xqnqq.com/Article/796536.shtml
- http://http://map.mobile.xqnqq.com/Article/404440.shtml
- http://http://map.read.usuhx.com/Article/491591.shtml
- http://http://map.read.usuhx.com/Article/3766.shtml
- http://http://map.read.usuhx.com/Article/451809.shtml
- http://http://map.read.usuhx.com/Article/45148.shtml
- http://http://map.mobile.xqnqq.com/Article/0982092.shtml
- http://http://map.read.usuhx.com/Article/04593.shtml
- http://http://map.read.usuhx.com/Article/7240480.shtml
- http://http://map.read.usuhx.com/Article/100837.shtml
- http://http://map.read.usuhx.com/Article/748864.shtml
- http://http://map.read.usuhx.com/Article/787444.shtml
- http://http://map.read.usuhx.com/Article/05063.shtml
- http://http://map.mobile.xqnqq.com/Article/1913789.shtml
- http://http://map.read.usuhx.com/Article/8169899.shtml
- http://http://map.read.usuhx.com/Article/178721.shtml
- http://http://map.read.usuhx.com/Article/01685.shtml
- http://http://map.mobile.xqnqq.com/Article/6049.shtml
- http://http://map.read.usuhx.com/Article/802743.shtml
- http://http://map.mobile.xqnqq.com/Article/70268.shtml
- http://http://map.mobile.xqnqq.com/Article/0657.shtml
- http://http://map.read.usuhx.com/Article/544494.shtml
- http://http://map.read.usuhx.com/Article/314979.shtml
- http://http://map.read.usuhx.com/Article/270887.shtml
- http://http://map.read.usuhx.com/Article/86307.shtml
- http://http://map.mobile.xqnqq.com/Article/6702494.shtml
- http://http://map.mobile.xqnqq.com/Article/2866561.shtml
- http://http://map.mobile.xqnqq.com/Article/2083.shtml
- http://http://map.read.usuhx.com/Article/3330.shtml
- http://http://map.read.usuhx.com/Article/55936.shtml
- http://http://map.read.usuhx.com/Article/4923525.shtml
- http://http://map.mobile.xqnqq.com/Article/96041.shtml
- http://http://map.mobile.xqnqq.com/Article/281793.shtml
- http://http://map.mobile.xqnqq.com/Article/99612.shtml
- http://http://map.mobile.xqnqq.com/Article/12585.shtml
- http://http://map.mobile.xqnqq.com/Article/0748593.shtml
- http://http://map.mobile.xqnqq.com/Article/08206.shtml
- http://http://map.read.usuhx.com/Article/6562776.shtml
- http://http://map.mobile.xqnqq.com/Article/0068043.shtml
- http://http://map.read.usuhx.com/Article/0619938.shtml
- http://http://map.read.usuhx.com/Article/5836.shtml
- http://http://map.read.usuhx.com/Article/020709.shtml
- http://http://map.mobile.xqnqq.com/Article/5201.shtml
- http://http://map.read.usuhx.com/Article/3630455.shtml
- http://http://map.read.usuhx.com/Article/2617.shtml
- http://http://map.mobile.xqnqq.com/Article/79473.shtml
- http://http://map.read.usuhx.com/Article/6841.shtml
- http://http://map.read.usuhx.com/Article/5795.shtml
- http://http://map.mobile.xqnqq.com/Article/2788.shtml
- http://http://map.mobile.xqnqq.com/Article/983913.shtml
- http://http://map.mobile.xqnqq.com/Article/4399101.shtml
- http://http://map.mobile.xqnqq.com/Article/8430523.shtml
- http://http://map.read.usuhx.com/Article/919382.shtml
- http://http://map.mobile.xqnqq.com/Article/918612.shtml
- http://http://map.read.usuhx.com/Article/41761.shtml
- http://http://map.read.usuhx.com/Article/5742030.shtml
- http://http://map.read.usuhx.com/Article/6673675.shtml
- http://http://map.read.usuhx.com/Article/1259.shtml
- http://http://map.read.usuhx.com/Article/5922.shtml
- http://http://map.read.usuhx.com/Article/4593281.shtml
- http://http://map.mobile.xqnqq.com/Article/62424.shtml
- http://http://map.read.usuhx.com/Article/4081.shtml
- http://http://map.mobile.xqnqq.com/Article/6235.shtml
- http://http://map.read.usuhx.com/Article/88105.shtml
- http://http://map.mobile.xqnqq.com/Article/7923.shtml
- http://http://map.mobile.xqnqq.com/Article/8274302.shtml
- http://http://map.read.usuhx.com/Article/4195417.shtml
- http://http://map.read.usuhx.com/Article/0232.shtml
- http://http://map.mobile.xqnqq.com/Article/635077.shtml
- http://http://map.mobile.xqnqq.com/Article/732210.shtml
- http://http://map.read.usuhx.com/Article/229533.shtml
- http://http://map.read.usuhx.com/Article/11015.shtml
- http://http://map.read.usuhx.com/Article/615312.shtml
- http://http://map.mobile.xqnqq.com/Article/98121.shtml
- http://http://map.mobile.xqnqq.com/Article/909017.shtml
- http://http://map.read.usuhx.com/Article/749252.shtml
- http://http://map.read.usuhx.com/Article/25633.shtml
- http://http://map.mobile.xqnqq.com/Article/0577.shtml
- http://http://map.mobile.xqnqq.com/Article/58934.shtml
- http://http://map.read.usuhx.com/Article/035327.shtml
- http://http://map.mobile.xqnqq.com/Article/4260.shtml
- http://http://map.read.usuhx.com/Article/71376.shtml
- http://http://map.read.usuhx.com/Article/95650.shtml
- http://http://map.read.usuhx.com/Article/5630114.shtml
- http://http://map.read.usuhx.com/Article/214165.shtml
- http://http://map.mobile.xqnqq.com/Article/9982.shtml
- http://http://map.mobile.xqnqq.com/Article/6810.shtml
- http://http://map.mobile.xqnqq.com/Article/269391.shtml
- http://http://map.mobile.xqnqq.com/Article/40763.shtml
- http://http://map.read.usuhx.com/Article/0171.shtml
- http://http://map.mobile.xqnqq.com/Article/9949.shtml
- http://http://map.read.usuhx.com/Article/3574.shtml
- http://http://map.mobile.xqnqq.com/Article/839205.shtml
- http://http://map.read.usuhx.com/Article/6869559.shtml
- http://http://map.read.usuhx.com/Article/686576.shtml
- http://http://map.mobile.xqnqq.com/Article/4658121.shtml
- http://http://map.mobile.xqnqq.com/Article/73934.shtml
- http://http://map.read.usuhx.com/Article/6510184.shtml
- http://http://map.mobile.xqnqq.com/Article/8904.shtml
- http://http://map.mobile.xqnqq.com/Article/56076.shtml
- http://http://map.mobile.xqnqq.com/Article/50019.shtml
- http://http://map.mobile.xqnqq.com/Article/9824.shtml
- http://http://map.mobile.xqnqq.com/Article/9555.shtml
- http://http://map.mobile.xqnqq.com/Article/2805477.shtml
- http://http://map.read.usuhx.com/Article/471261.shtml
- http://http://map.read.usuhx.com/Article/4497.shtml
- http://http://map.read.usuhx.com/Article/2545483.shtml
- http://http://map.read.usuhx.com/Article/0998.shtml
- http://http://map.mobile.xqnqq.com/Article/922644.shtml
- http://http://map.mobile.xqnqq.com/Article/41604.shtml
- http://http://map.mobile.xqnqq.com/Article/4709447.shtml
- http://http://map.read.usuhx.com/Article/679844.shtml
- http://http://map.mobile.xqnqq.com/Article/07137.shtml
- http://http://map.mobile.xqnqq.com/Article/8996.shtml
- http://http://map.mobile.xqnqq.com/Article/9653729.shtml
- http://http://map.read.usuhx.com/Article/223097.shtml
- http://http://map.read.usuhx.com/Article/563193.shtml
- http://http://map.mobile.xqnqq.com/Article/8374988.shtml
- http://http://map.read.usuhx.com/Article/624554.shtml
- http://http://map.read.usuhx.com/Article/5457.shtml
- http://http://map.read.usuhx.com/Article/5940.shtml
- http://http://map.mobile.xqnqq.com/Article/308795.shtml
- http://http://map.read.usuhx.com/Article/229508.shtml
- http://http://map.read.usuhx.com/Article/95560.shtml
- http://http://map.read.usuhx.com/Article/0164.shtml
- http://http://map.mobile.xqnqq.com/Article/3980613.shtml
- http://http://map.mobile.xqnqq.com/Article/3490.shtml
- http://http://map.mobile.xqnqq.com/Article/8727806.shtml
- http://http://map.read.usuhx.com/Article/1229.shtml
- http://http://map.mobile.xqnqq.com/Article/33139.shtml
- http://http://map.read.usuhx.com/Article/3003.shtml
- http://http://map.mobile.xqnqq.com/Article/8928.shtml
- http://http://map.mobile.xqnqq.com/Article/14053.shtml
- http://http://map.mobile.xqnqq.com/Article/555959.shtml
- http://http://map.read.usuhx.com/Article/3755.shtml
- http://http://map.mobile.xqnqq.com/Article/4267.shtml
- http://http://map.read.usuhx.com/Article/4209.shtml
- http://http://map.mobile.xqnqq.com/Article/39679.shtml
- http://http://map.read.usuhx.com/Article/1137610.shtml
- http://http://map.read.usuhx.com/Article/409766.shtml
- http://http://map.read.usuhx.com/Article/384548.shtml
- http://http://map.read.usuhx.com/Article/5788.shtml
- http://http://map.read.usuhx.com/Article/728529.shtml
- http://http://map.mobile.xqnqq.com/Article/6263.shtml
- http://http://map.mobile.xqnqq.com/Article/44083.shtml
- http://http://map.mobile.xqnqq.com/Article/887301.shtml
- http://http://map.mobile.xqnqq.com/Article/92097.shtml
- http://http://map.mobile.xqnqq.com/Article/46252.shtml
- http://http://map.mobile.xqnqq.com/Article/24124.shtml
- http://http://map.read.usuhx.com/Article/25941.shtml
- http://http://map.mobile.xqnqq.com/Article/732229.shtml
- http://http://map.read.usuhx.com/Article/62255.shtml
- http://http://map.mobile.xqnqq.com/Article/8493.shtml
- http://http://map.read.usuhx.com/Article/70642.shtml
- http://http://map.mobile.xqnqq.com/Article/931798.shtml
- http://http://map.mobile.xqnqq.com/Article/89243.shtml
- http://http://map.mobile.xqnqq.com/Article/1890.shtml
- http://http://map.read.usuhx.com/Article/3042627.shtml
- http://http://map.mobile.xqnqq.com/Article/6675.shtml
- http://http://map.mobile.xqnqq.com/Article/05414.shtml
- http://http://map.read.usuhx.com/Article/13203.shtml
- http://http://map.read.usuhx.com/Article/2194.shtml
- http://http://map.mobile.xqnqq.com/Article/973177.shtml
- http://http://map.mobile.xqnqq.com/Article/8835864.shtml
- http://http://map.read.usuhx.com/Article/39828.shtml
- http://http://map.read.usuhx.com/Article/0588010.shtml
- http://http://map.mobile.xqnqq.com/Article/910106.shtml
- http://http://map.read.usuhx.com/Article/2706992.shtml
- http://http://map.read.usuhx.com/Article/6826403.shtml
- http://http://map.read.usuhx.com/Article/2583053.shtml
- http://http://map.read.usuhx.com/Article/3711035.shtml
- http://http://map.read.usuhx.com/Article/7712060.shtml
- http://http://map.read.usuhx.com/Article/6526011.shtml
- http://http://map.read.usuhx.com/Article/6281404.shtml
- http://http://map.mobile.xqnqq.com/Article/69723.shtml
- http://http://map.read.usuhx.com/Article/57699.shtml
- http://http://map.read.usuhx.com/Article/98546.shtml
- http://http://map.read.usuhx.com/Article/7507484.shtml
- http://http://map.read.usuhx.com/Article/1489693.shtml
- http://http://map.mobile.xqnqq.com/Article/67101.shtml
- http://http://map.read.usuhx.com/Article/6390.shtml
- http://http://map.read.usuhx.com/Article/40842.shtml
- http://http://map.mobile.xqnqq.com/Article/1892035.shtml
- http://http://map.read.usuhx.com/Article/18778.shtml
- http://http://map.read.usuhx.com/Article/8372764.shtml
- http://http://map.read.usuhx.com/Article/78055.shtml
- http://http://map.read.usuhx.com/Article/9354.shtml
- http://http://map.read.usuhx.com/Article/5073.shtml
- http://http://map.mobile.xqnqq.com/Article/7355598.shtml
- http://http://map.read.usuhx.com/Article/1590645.shtml
- http://http://map.mobile.xqnqq.com/Article/7874.shtml
- http://http://map.mobile.xqnqq.com/Article/7934173.shtml
- http://http://map.read.usuhx.com/Article/7453548.shtml
- http://http://map.read.usuhx.com/Article/190500.shtml
- http://http://map.mobile.xqnqq.com/Article/3660846.shtml
- http://http://map.mobile.xqnqq.com/Article/4248.shtml
- http://http://map.mobile.xqnqq.com/Article/774793.shtml
- http://http://map.mobile.xqnqq.com/Article/934749.shtml
- http://http://map.read.usuhx.com/Article/741029.shtml
- http://http://map.mobile.xqnqq.com/Article/9145.shtml
- http://http://map.mobile.xqnqq.com/Article/8382.shtml
- http://http://map.mobile.xqnqq.com/Article/05506.shtml
- http://http://map.mobile.xqnqq.com/Article/4137337.shtml
- http://http://map.read.usuhx.com/Article/090753.shtml
- http://http://map.read.usuhx.com/Article/264885.shtml
- http://http://map.mobile.xqnqq.com/Article/2180769.shtml
- http://http://map.read.usuhx.com/Article/6694.shtml
- http://http://map.read.usuhx.com/Article/0230.shtml
- http://http://map.mobile.xqnqq.com/Article/3672122.shtml
- http://http://map.read.usuhx.com/Article/012838.shtml
- http://http://map.mobile.xqnqq.com/Article/899711.shtml
- http://http://map.read.usuhx.com/Article/590645.shtml
- http://http://map.mobile.xqnqq.com/Article/870475.shtml
- http://http://map.mobile.xqnqq.com/Article/229558.shtml
- http://http://map.mobile.xqnqq.com/Article/021599.shtml
- http://http://map.read.usuhx.com/Article/442557.shtml
- http://http://map.mobile.xqnqq.com/Article/94423.shtml
- http://http://map.read.usuhx.com/Article/29452.shtml

## 项目结构

```
linkmaster-pro/
├── manage.py                      # Django 项目入口管理脚本
├── requirements.txt               # Python 后端依赖列表
├── .env.example                   # 环境变量配置模板
├── docker-compose.yml             # 本地开发与测试用容器编排文件
├── docs/                          # 项目文档根目录
│   ├── user-guide/                # 用户操作手册，含截图与流程说明
│   ├── ops-guide/                 # 部署与运维指南，含监控与备份策略
│   ├── api-reference/             # RESTful API 详细文档，含请求响应示例
│   └── contributing/              # 贡献者指南，含代码规范与测试说明
├── src/                           # 核心源代码目录
│   ├── apps/                      # Django 应用模块
│   │   ├── core/                  # 核心数据模型：Link, Tag, CheckResult
│   │   ├── importer/              # 批量导入模块，支持 CSV/JSON/纯文本解析
│   │   ├── checker/               # 健康状态巡检模块，集成 Celery 任务
│   │   ├── exporter/              # 导出模块，支持 Markdown/JSON/HTML 格式
│   │   └── accounts/              # 用户认证与权限管理模块
│   ├── static/                    # 静态资源文件（CSS, JavaScript, 图片）
│   ├── templates/                 # Django 模板文件，含管理界面与仪表盘
│   └── utils/                     # 工具函数库，含 URL 解析、日志封装与验证器
├── tests/                         # 单元测试与集成测试目录
│   ├── test_models.py             # 数据模型层测试
│   ├── test_api.py                # API 端点测试
│   └── test_checker.py            # 巡检任务逻辑测试
├── scripts/                       # 运维辅助脚本
│   ├── backup_db.sh               # 数据库备份脚本
│   └── seed_data.py               # 初始示例数据填充脚本
└── config/                        # 部署配置文件
    ├── nginx.conf                 # Nginx 反向代理与静态资源服务配置
    └── gunicorn.conf.py           # Gunicorn WSGI 服务器启动参数配置
```

## 贡献指南

问题追踪与讨论：请在 GitHub Issues 中搜索是否已存在类似问题或功能请求。若未找到，请新建 Issue 并详细描述使用场景、预期行为与当前现象，标记合适的标签（bug、enhancement、question）。

代码分叉与本地开发：将本仓库 Fork 至个人账户后克隆到本地，建议在 dev 分支上开发。安装所有开发依赖（pip install -r requirements-dev.txt），并运行 pre-commit 钩子以自动检查代码风格。

编写测试用例：所有新增功能或修复必须包含对应的单元测试或集成测试，测试覆盖率不得低于 85%。在提交前执行 python manage.py test 确保全部测试通过。

提交变更与拉取请求：提交信息请遵循 Conventional Commits 格式（feat、fix、docs、style 等）。推送至远程分支后，向主仓库的 main 分支发起 Pull Request，描述中引用相关的 Issue 编号并附上变更摘要。

文档同步更新：若变更涉及用户操作或 API 行为，必须同步更新 /docs 目录下对应的 Markdown 文档。文档更新应与代码变更合并至同一个 Pull Request 中。

## 常见问题

系统支持最大管理多少条链接记录？

系统设计上对链接数量无硬性上限，实际承载能力取决于部署环境中的数据库性能与 Celery Worker 数量。在常规配置下（PostgreSQL 14、4 Core CPU、8GB RAM），单表记录数超过 100 万条时仍可保持正常的查询响应与巡检调度效率。建议定期通过健康报告清理无效链接以优化存储。

健康巡检任务是否会触发目标网站的反爬机制？

巡检模块默认采用单线程顺序请求，并设置 2 秒请求间隔与随机 User-Agent 轮换，同时遵循 robots.txt 规则。对于频繁巡检的站点，用户可在配置文件中自定义白名单与请求频率。系统不会执行 JavaScript 渲染或模拟登录行为，仅检查基础可达性与状态码。

如何将现有浏览器书签或第三方收藏夹导入系统？

系统提供通用的 CSV 与 JSON 导入模板，用户可将浏览器导出的 HTML 书签文件转换为模板格式后上传。对于 Chrome 或 Firefox 书签，社区维护了一个转换脚本（位于 /scripts/convert_bookmarks.py），可将 Netscape 格式书签直接映射为系统导入格式，具体用法参见运维手册中的导入章节。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
