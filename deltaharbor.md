# IndexHub

IndexHub 是一个面向技术研究者与内容聚合场景的轻量级外链资源归集系统。该项目定位于对分散在多个内容源头的文章、文档与技术笔记进行结构化索引，并通过统一的目录体系与标签映射，帮助用户快速定位高价值信息。IndexHub 不存储原始内容，仅提供规范的引用链路与状态监测能力，适用于个人知识库辅助、团队技术周报素材收集以及自动化外链巡检等场景。

## 功能概览

- 多源链接归一化收录：支持将来自不同域名的文章链接按原始地址精确录入，保留完整协议与路径信息，避免二次跳转或协议改写。
- 批次化资源管理：按批次对链接进行分组，每批次可记录收录时间、来源特征与校验状态，便于后续批量更新与过期检测。
- 基础可用性探测：对已收录链接提供 HTTP 状态码检查与响应时间记录，协助识别失效或重定向资源。
- 标签与分类映射：允许用户为每个链接附加自定义标签（如「前端」「性能优化」「架构」），并基于标签生成快速筛选视图。
- 只读只删数据策略：不对链接指向的原始内容做任何缓存或代理，严格遵守源站版权与访问策略，仅保留元数据与引用关系。
- 结构化的文档输出：内置 README 与文档模板生成器，可自动产出包含资源列表、依赖说明与目录树的维护文档，降低项目维护成本。
- 轻量级部署：无外部数据库依赖，核心服务基于文件系统与内存缓存，可在低配服务器或本地开发环境中快速运行。

## 应用场景

1. 技术团队内部周报素材整理：团队技术负责人每周需要汇总多篇社区文章作为周报参考。IndexHub 可预先收录候选链接，并添加「周报」「前端」「后端」等标签，周报撰写时直接按标签导出列表，无需重复搜索。

2. 个人知识库外链索引构建：个人博客或笔记系统（如 Obsidian、Logseq）中常需要管理大量外部引用。IndexHub 可作为独立服务运行，为本地笔记提供可查询的外链目录，并定期检查链接有效性，避免笔记中积累过多死链。

3. 自动化内容聚合系统的前置过滤层：在构建技术新闻聚合器或 RSS 增强服务时，IndexHub 可作为链接准入校验模块，先对原始链接进行格式规范化与去重，再交由下游爬虫或渲染服务处理，降低异常 URL 对主流程的干扰。

4. 开源项目文档的外部参考管理：开源项目维护者需要在 README 或 Wiki 中列出大量外部参考链接。IndexHub 提供批次化导入与模板输出能力，能够将零散的链接整理为符合项目规范的外部资源章节，并自动生成 Markdown 格式列表。

## 快速开始

以下步骤适用于 Linux 与 macOS 环境，Windows 用户可通过 WSL 或 Git Bash 执行。

```bash
# 克隆代码仓库
git clone https://github.com/your-org/indexhub.git
cd indexhub

# 安装依赖（使用 pip 管理 Python 后端）
pip install -r requirements.txt

# 构建前端静态资源（若启用 Web UI）
cd webui && npm install && npm run build && cd ..

# 初始化本地数据库与配置
python scripts/init_db.py --env development

# 启动开发服务器（默认监听 127.0.0.1:8000）
python app.py
```

启动后访问 `http://127.0.0.1:8000` 可进入索引管理界面。首次启动将自动创建 `data/` 目录用于存放链接元数据文件。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Python | 3.9 及以上 | 核心服务运行时环境 |
| pip | 22.0 及以上 | Python 包管理工具 |
| Node.js | 18.0 及以上 | 仅当构建 Web UI 时需要 |
| npm | 9.0 及以上 | 前端资源构建工具 |
| Git | 2.25 及以上 | 用于克隆仓库与版本管理 |
| 磁盘空间 | 至少 200 MB | 存放元数据与日志文件 |
| 内存 | 至少 512 MB | 支持单进程运行与缓存 |
| 操作系统 | Linux / macOS / Windows WSL | 生产环境推荐 Ubuntu 20.04 LTS |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 入门指南 | docs/getting-started.md | 如何安装、配置并运行 IndexHub 的第一个实例？ |
| 链接管理 | docs/link-management.md | 如何批量添加链接、更新标签以及删除失效资源？ |
| 批次操作 | docs/batch-operations.md | 如何创建新批次、切换批次以及导出批次报告？ |
| 可用性检测 | docs/health-check.md | 如何配置定时检测、解读检测结果以及处理异常链接？ |
| API 参考 | docs/api-reference.md | 服务端提供了哪些 RESTful 接口，请求与响应格式是什么？ |
| 模板生成 | docs/template-generation.md | 如何自定义 README 与资源列表的输出模板？ |

## 资源列表

- http://http://www.read.usuhx.com/Article/93635.shtml
- http://http://www.mobile.xqnqq.com/Article/24355.shtml
- http://http://www.read.usuhx.com/Article/3076.shtml
- http://http://www.mobile.xqnqq.com/Article/356355.shtml
- http://http://www.read.usuhx.com/Article/3206385.shtml
- http://http://www.mobile.xqnqq.com/Article/8384.shtml
- http://http://www.mobile.xqnqq.com/Article/27376.shtml
- http://http://www.read.usuhx.com/Article/187058.shtml
- http://http://www.read.usuhx.com/Article/971306.shtml
- http://http://www.mobile.xqnqq.com/Article/03147.shtml
- http://http://www.read.usuhx.com/Article/63212.shtml
- http://http://www.mobile.xqnqq.com/Article/055594.shtml
- http://http://www.mobile.xqnqq.com/Article/953194.shtml
- http://http://www.read.usuhx.com/Article/04130.shtml
- http://http://www.read.usuhx.com/Article/044828.shtml
- http://http://www.read.usuhx.com/Article/8402.shtml
- http://http://www.read.usuhx.com/Article/7481.shtml
- http://http://www.read.usuhx.com/Article/66874.shtml
- http://http://www.mobile.xqnqq.com/Article/396111.shtml
- http://http://www.read.usuhx.com/Article/232092.shtml
- http://http://www.mobile.xqnqq.com/Article/7911773.shtml
- http://http://www.read.usuhx.com/Article/8472057.shtml
- http://http://www.mobile.xqnqq.com/Article/554568.shtml
- http://http://www.read.usuhx.com/Article/616646.shtml
- http://http://www.mobile.xqnqq.com/Article/2598137.shtml
- http://http://www.mobile.xqnqq.com/Article/2490.shtml
- http://http://www.read.usuhx.com/Article/1560510.shtml
- http://http://www.mobile.xqnqq.com/Article/93544.shtml
- http://http://www.mobile.xqnqq.com/Article/2076.shtml
- http://http://www.mobile.xqnqq.com/Article/695503.shtml
- http://http://www.mobile.xqnqq.com/Article/0179983.shtml
- http://http://www.read.usuhx.com/Article/804423.shtml
- http://http://www.read.usuhx.com/Article/2263.shtml
- http://http://www.mobile.xqnqq.com/Article/5407004.shtml
- http://http://www.mobile.xqnqq.com/Article/1154755.shtml
- http://http://www.mobile.xqnqq.com/Article/2717.shtml
- http://http://www.mobile.xqnqq.com/Article/4689782.shtml
- http://http://www.read.usuhx.com/Article/3586479.shtml
- http://http://www.read.usuhx.com/Article/966868.shtml
- http://http://www.read.usuhx.com/Article/6050.shtml
- http://http://www.read.usuhx.com/Article/1226811.shtml
- http://http://www.read.usuhx.com/Article/84151.shtml
- http://http://www.read.usuhx.com/Article/863761.shtml
- http://http://www.read.usuhx.com/Article/19892.shtml
- http://http://www.mobile.xqnqq.com/Article/165137.shtml
- http://http://www.mobile.xqnqq.com/Article/2271986.shtml
- http://http://www.mobile.xqnqq.com/Article/4516.shtml
- http://http://www.read.usuhx.com/Article/705369.shtml
- http://http://www.read.usuhx.com/Article/2386.shtml
- http://http://www.mobile.xqnqq.com/Article/39795.shtml
- http://http://www.mobile.xqnqq.com/Article/8022.shtml
- http://http://www.mobile.xqnqq.com/Article/8016273.shtml
- http://http://www.mobile.xqnqq.com/Article/868099.shtml
- http://http://www.read.usuhx.com/Article/7134.shtml
- http://http://www.read.usuhx.com/Article/3459173.shtml
- http://http://www.read.usuhx.com/Article/4922.shtml
- http://http://www.read.usuhx.com/Article/195393.shtml
- http://http://www.mobile.xqnqq.com/Article/3044.shtml
- http://http://www.read.usuhx.com/Article/592203.shtml
- http://http://www.read.usuhx.com/Article/339545.shtml
- http://http://www.read.usuhx.com/Article/7404.shtml
- http://http://www.read.usuhx.com/Article/2509.shtml
- http://http://www.read.usuhx.com/Article/39841.shtml
- http://http://www.mobile.xqnqq.com/Article/146684.shtml
- http://http://www.mobile.xqnqq.com/Article/820624.shtml
- http://http://www.read.usuhx.com/Article/6430.shtml
- http://http://www.read.usuhx.com/Article/69979.shtml
- http://http://www.read.usuhx.com/Article/22116.shtml
- http://http://www.mobile.xqnqq.com/Article/743895.shtml
- http://http://www.mobile.xqnqq.com/Article/969366.shtml
- http://http://www.mobile.xqnqq.com/Article/5348948.shtml
- http://http://www.read.usuhx.com/Article/370795.shtml
- http://http://www.mobile.xqnqq.com/Article/6436508.shtml
- http://http://www.mobile.xqnqq.com/Article/050690.shtml
- http://http://www.mobile.xqnqq.com/Article/1889.shtml
- http://http://www.mobile.xqnqq.com/Article/9708.shtml
- http://http://www.read.usuhx.com/Article/33099.shtml
- http://http://www.read.usuhx.com/Article/9467221.shtml
- http://http://www.mobile.xqnqq.com/Article/68897.shtml
- http://http://www.read.usuhx.com/Article/6025.shtml
- http://http://www.read.usuhx.com/Article/50975.shtml
- http://http://www.mobile.xqnqq.com/Article/66205.shtml
- http://http://www.mobile.xqnqq.com/Article/8786.shtml
- http://http://www.mobile.xqnqq.com/Article/2835174.shtml
- http://http://www.mobile.xqnqq.com/Article/000595.shtml
- http://http://www.read.usuhx.com/Article/4688.shtml
- http://http://www.mobile.xqnqq.com/Article/894301.shtml
- http://http://www.read.usuhx.com/Article/3399417.shtml
- http://http://www.read.usuhx.com/Article/33305.shtml
- http://http://www.read.usuhx.com/Article/82799.shtml
- http://http://www.mobile.xqnqq.com/Article/517775.shtml
- http://http://www.read.usuhx.com/Article/2299016.shtml
- http://http://www.read.usuhx.com/Article/76120.shtml
- http://http://www.mobile.xqnqq.com/Article/0173.shtml
- http://http://www.mobile.xqnqq.com/Article/93356.shtml
- http://http://www.mobile.xqnqq.com/Article/0038522.shtml
- http://http://www.mobile.xqnqq.com/Article/1314694.shtml
- http://http://www.mobile.xqnqq.com/Article/0602543.shtml
- http://http://www.mobile.xqnqq.com/Article/0918025.shtml
- http://http://www.read.usuhx.com/Article/3626838.shtml
- http://http://www.mobile.xqnqq.com/Article/0652958.shtml
- http://http://www.read.usuhx.com/Article/9387745.shtml
- http://http://www.read.usuhx.com/Article/994673.shtml
- http://http://www.read.usuhx.com/Article/198597.shtml
- http://http://www.mobile.xqnqq.com/Article/247208.shtml
- http://http://www.read.usuhx.com/Article/946255.shtml
- http://http://www.mobile.xqnqq.com/Article/8520576.shtml
- http://http://www.mobile.xqnqq.com/Article/231593.shtml
- http://http://www.read.usuhx.com/Article/15239.shtml
- http://http://www.mobile.xqnqq.com/Article/1289571.shtml
- http://http://www.read.usuhx.com/Article/01974.shtml
- http://http://www.mobile.xqnqq.com/Article/50422.shtml
- http://http://www.read.usuhx.com/Article/31607.shtml
- http://http://www.read.usuhx.com/Article/2438541.shtml
- http://http://www.mobile.xqnqq.com/Article/655465.shtml
- http://http://www.mobile.xqnqq.com/Article/5500.shtml
- http://http://www.read.usuhx.com/Article/3168498.shtml
- http://http://www.read.usuhx.com/Article/30767.shtml
- http://http://www.read.usuhx.com/Article/82999.shtml
- http://http://www.read.usuhx.com/Article/4862.shtml
- http://http://www.mobile.xqnqq.com/Article/0532.shtml
- http://http://www.mobile.xqnqq.com/Article/1878.shtml
- http://http://www.mobile.xqnqq.com/Article/863706.shtml
- http://http://www.read.usuhx.com/Article/15595.shtml
- http://http://www.mobile.xqnqq.com/Article/78434.shtml
- http://http://www.mobile.xqnqq.com/Article/5307.shtml
- http://http://www.mobile.xqnqq.com/Article/74643.shtml
- http://http://www.read.usuhx.com/Article/001024.shtml
- http://http://www.mobile.xqnqq.com/Article/9195.shtml
- http://http://www.read.usuhx.com/Article/6646602.shtml
- http://http://www.mobile.xqnqq.com/Article/421410.shtml
- http://http://www.read.usuhx.com/Article/9988857.shtml
- http://http://www.mobile.xqnqq.com/Article/104340.shtml
- http://http://www.read.usuhx.com/Article/69654.shtml
- http://http://www.mobile.xqnqq.com/Article/66897.shtml
- http://http://www.read.usuhx.com/Article/843775.shtml
- http://http://www.mobile.xqnqq.com/Article/64105.shtml
- http://http://www.read.usuhx.com/Article/9931440.shtml
- http://http://www.mobile.xqnqq.com/Article/9104292.shtml
- http://http://www.mobile.xqnqq.com/Article/039488.shtml
- http://http://www.read.usuhx.com/Article/146494.shtml
- http://http://www.mobile.xqnqq.com/Article/5818121.shtml
- http://http://www.read.usuhx.com/Article/492649.shtml
- http://http://www.mobile.xqnqq.com/Article/96510.shtml
- http://http://www.read.usuhx.com/Article/9450.shtml
- http://http://www.read.usuhx.com/Article/8867.shtml
- http://http://www.mobile.xqnqq.com/Article/825913.shtml
- http://http://www.mobile.xqnqq.com/Article/07488.shtml
- http://http://www.mobile.xqnqq.com/Article/4840351.shtml
- http://http://www.read.usuhx.com/Article/0518384.shtml
- http://http://www.read.usuhx.com/Article/3608168.shtml
- http://http://www.read.usuhx.com/Article/3342.shtml
- http://http://www.mobile.xqnqq.com/Article/2202004.shtml
- http://http://www.mobile.xqnqq.com/Article/5946359.shtml
- http://http://www.read.usuhx.com/Article/61882.shtml
- http://http://www.mobile.xqnqq.com/Article/7933.shtml
- http://http://www.mobile.xqnqq.com/Article/764682.shtml
- http://http://www.mobile.xqnqq.com/Article/887978.shtml
- http://http://www.read.usuhx.com/Article/7655.shtml
- http://http://www.mobile.xqnqq.com/Article/7229330.shtml
- http://http://www.mobile.xqnqq.com/Article/9157626.shtml
- http://http://www.mobile.xqnqq.com/Article/6526.shtml
- http://http://www.read.usuhx.com/Article/4807563.shtml
- http://http://www.read.usuhx.com/Article/54475.shtml
- http://http://www.read.usuhx.com/Article/2299.shtml
- http://http://www.mobile.xqnqq.com/Article/1759.shtml
- http://http://www.mobile.xqnqq.com/Article/581273.shtml
- http://http://www.mobile.xqnqq.com/Article/09169.shtml
- http://http://www.read.usuhx.com/Article/68886.shtml
- http://http://www.mobile.xqnqq.com/Article/04109.shtml
- http://http://www.read.usuhx.com/Article/6913277.shtml
- http://http://www.read.usuhx.com/Article/4009732.shtml
- http://http://www.mobile.xqnqq.com/Article/869229.shtml
- http://http://www.read.usuhx.com/Article/1912912.shtml
- http://http://www.read.usuhx.com/Article/80750.shtml
- http://http://www.read.usuhx.com/Article/5139486.shtml
- http://http://www.read.usuhx.com/Article/651643.shtml
- http://http://www.mobile.xqnqq.com/Article/5390262.shtml
- http://http://www.read.usuhx.com/Article/8054.shtml
- http://http://www.mobile.xqnqq.com/Article/9138322.shtml
- http://http://www.mobile.xqnqq.com/Article/14426.shtml
- http://http://www.mobile.xqnqq.com/Article/4636886.shtml
- http://http://www.mobile.xqnqq.com/Article/45306.shtml
- http://http://www.read.usuhx.com/Article/66533.shtml
- http://http://www.read.usuhx.com/Article/489072.shtml
- http://http://www.mobile.xqnqq.com/Article/0062497.shtml
- http://http://www.read.usuhx.com/Article/34300.shtml
- http://http://www.mobile.xqnqq.com/Article/38234.shtml
- http://http://www.read.usuhx.com/Article/645740.shtml
- http://http://www.mobile.xqnqq.com/Article/9190259.shtml
- http://http://www.read.usuhx.com/Article/3600394.shtml
- http://http://www.read.usuhx.com/Article/06931.shtml
- http://http://www.read.usuhx.com/Article/754174.shtml
- http://http://www.mobile.xqnqq.com/Article/925587.shtml
- http://http://www.mobile.xqnqq.com/Article/2997665.shtml
- http://http://www.mobile.xqnqq.com/Article/3178609.shtml
- http://http://www.read.usuhx.com/Article/443173.shtml
- http://http://www.read.usuhx.com/Article/4591.shtml
- http://http://www.mobile.xqnqq.com/Article/36294.shtml
- http://http://www.mobile.xqnqq.com/Article/334174.shtml
- http://http://www.mobile.xqnqq.com/Article/43629.shtml
- http://http://www.read.usuhx.com/Article/8482.shtml
- http://http://www.read.usuhx.com/Article/6825553.shtml
- http://http://www.mobile.xqnqq.com/Article/937598.shtml
- http://http://www.mobile.xqnqq.com/Article/939788.shtml
- http://http://www.read.usuhx.com/Article/0751449.shtml
- http://http://www.read.usuhx.com/Article/22744.shtml
- http://http://www.mobile.xqnqq.com/Article/30036.shtml
- http://http://www.read.usuhx.com/Article/75357.shtml
- http://http://www.read.usuhx.com/Article/7876.shtml
- http://http://www.mobile.xqnqq.com/Article/899879.shtml
- http://http://www.mobile.xqnqq.com/Article/8639.shtml
- http://http://www.read.usuhx.com/Article/5863260.shtml
- http://http://www.read.usuhx.com/Article/47435.shtml
- http://http://www.mobile.xqnqq.com/Article/8629012.shtml
- http://http://www.mobile.xqnqq.com/Article/7084.shtml
- http://http://www.mobile.xqnqq.com/Article/3796.shtml
- http://http://www.read.usuhx.com/Article/7953.shtml
- http://http://www.mobile.xqnqq.com/Article/1580782.shtml
- http://http://www.read.usuhx.com/Article/18299.shtml
- http://http://www.mobile.xqnqq.com/Article/8148846.shtml
- http://http://www.mobile.xqnqq.com/Article/83863.shtml
- http://http://www.mobile.xqnqq.com/Article/58613.shtml
- http://http://www.read.usuhx.com/Article/3327343.shtml
- http://http://www.mobile.xqnqq.com/Article/982089.shtml
- http://http://www.read.usuhx.com/Article/204881.shtml
- http://http://www.mobile.xqnqq.com/Article/176924.shtml
- http://http://www.read.usuhx.com/Article/420867.shtml
- http://http://www.mobile.xqnqq.com/Article/0226243.shtml
- http://http://www.mobile.xqnqq.com/Article/5706588.shtml
- http://http://www.read.usuhx.com/Article/45043.shtml
- http://http://www.mobile.xqnqq.com/Article/19307.shtml
- http://http://www.read.usuhx.com/Article/14973.shtml
- http://http://www.read.usuhx.com/Article/7235.shtml
- http://http://www.read.usuhx.com/Article/527880.shtml
- http://http://www.mobile.xqnqq.com/Article/4410510.shtml
- http://http://www.read.usuhx.com/Article/08109.shtml
- http://http://www.mobile.xqnqq.com/Article/1312811.shtml
- http://http://www.read.usuhx.com/Article/9341255.shtml
- http://http://www.read.usuhx.com/Article/63521.shtml
- http://http://www.mobile.xqnqq.com/Article/6045856.shtml
- http://http://www.mobile.xqnqq.com/Article/0514851.shtml
- http://http://www.read.usuhx.com/Article/76358.shtml
- http://http://www.mobile.xqnqq.com/Article/0775.shtml
- http://http://www.read.usuhx.com/Article/13401.shtml
- http://http://www.read.usuhx.com/Article/6558.shtml
- http://http://www.mobile.xqnqq.com/Article/688477.shtml
- http://http://www.read.usuhx.com/Article/43871.shtml
- http://http://www.mobile.xqnqq.com/Article/8175782.shtml
- http://http://www.read.usuhx.com/Article/95629.shtml

## 项目结构

```
indexhub/
├── app.py                     # 主服务入口，初始化 Flask 应用与路由
├── requirements.txt           # Python 依赖列表 (Flask, requests, python-dotenv)
├── config/
│   ├── __init__.py            # 配置模块初始化
│   ├── settings.py            # 环境变量与默认配置 (端口、日志级别、缓存策略)
│   └── batch_config.yaml      # 批次定义文件 (批次编号、名称、收录阈值)
├── core/
│   ├── __init__.py
│   ├── link_manager.py        # 链接增删改查与标签管理核心逻辑
│   ├── batch_engine.py        # 批次创建、切换与状态维护
│   ├── health_checker.py      # 异步 HTTP 可用性检测与结果持久化
│   └── template_renderer.py   # README / 资源列表模板渲染器
├── data/
│   ├── links/                 # 按批次存储链接元数据 (JSON 格式)
│   ├── checks/                # 检测历史记录 (按日期分片)
│   └── tags/                  # 标签索引文件 (标签 -> 链接 ID 映射)
├── webui/
│   ├── src/                   # React 前端源代码
│   ├── public/                # 静态资源入口
│   └── build/                 # 构建输出目录 (生产环境)
├── scripts/
│   ├── init_db.py             # 初始化数据目录与默认配置
│   ├── import_links.py        # 批量导入链接 (支持 CSV / 纯文本列表)
│   └── export_report.py       # 导出批次报告 (Markdown / JSON)
├── tests/
│   ├── unit/                  # 单元测试 (核心模块)
│   └── integration/           # 集成测试 (API 与文件系统交互)
├── docs/                      # 详细文档 (入门指南、API 参考、部署说明)
└── README.md                  # 项目概览与快速入口 (即本文档)
```

## 贡献指南

1. 查阅议题与项目看板：访问 GitHub Issues 与 Projects 页面，了解当前计划中的功能与待修复缺陷。选择未被认领的议题，或提出新的改进建议。

2. 派生仓库并创建特性分支：将主仓库派生至个人账户，然后克隆派生仓库到本地。新建分支时使用 `feat/` 或 `fix/` 前缀，例如 `feat/batch-export-csv`。

3. 编写代码与测试：遵循项目根目录下的 `.flake8` 与 `.pre-commit-config.yaml` 规范。所有新功能需包含对应的单元测试，测试覆盖率不低于 80%。

4. 提交变更并推送分支：提交信息采用 Conventional Commits 格式，如 `feat(link): add batch delete endpoint`。推送分支后，在 GitHub 上发起 Pull Request 并填写变更说明模板。

5. 接受代码审查与合并：至少一名维护者将审查代码，检查功能完整性、测试通过性以及文档更新情况。审查通过后由维护者执行合并操作。

## 常见问题

Q: IndexHub 是否会缓存或代理原始链接的内容？
A: 不会。IndexHub 仅存储链接的元数据（URL、标题、标签、收录时间、检测状态），不请求或保存原始页面的正文内容。可用性检测仅通过 HEAD 或 GET 请求获取状态码与响应头，不进行深度内容抓取。

Q: 如何迁移已收录的链接数据到另一台服务器？
A: 复制整个 `data/` 目录到新服务器的相同相对路径下即可。所有数据以 JSON 文件形式存储，无外部数据库依赖。迁移后需确保新服务器的时间戳与时区设置与原环境一致，以免影响检测记录排序。

Q: 单个批次最多可以收录多少条链接？
A: 系统本身未设置硬性上限，但建议单个批次不超过 5000 条链接，以保持内存缓存与文件读取的性能稳定。若需管理更大规模的资源集合，可拆分为多个批次并按时间或主题分类。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
