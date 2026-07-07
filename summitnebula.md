# WebIndex 聚合导航系统

WebIndex 是一个面向技术调研、内容聚合与批量资源管理场景的轻量级外链汇总与导航系统。该项目定位于帮助开发者、研究员、运维人员以及内容策展人，将大量分散的 URL 资源以结构化方式收录、分类、检索与展示，解决海量链接难以整理、难以追溯、难以共享的痛点。

WebIndex 不依赖复杂前端框架，核心基于静态站点生成逻辑与 Markdown 驱动的数据管理方式，适合部署在任意 Web 服务器或对象存储上。项目自包含一套链接录入规范与索引模板，支持从原始 URL 列表自动生成带分类、标签、时间戳与快照状态的导航页面，同时保留完整原始链接以备跳转。

---

## 功能概览

批量导入与标准化存储：支持将原始 URL 列表直接录入系统，自动识别协议、域名、路径结构，按批次与序号生成永久索引记录。

多维度分类导航：基于 URL 来源域名、文章编号段、采集批次与时间维度自动生成分类视图，用户可快速筛选特定来源或特定编号区间的资源。

原始链接完整性保障：系统强制保留用户提交的每一个原始 URL 的完整字符串，不进行任何协议补全、域名规范化或路径改写，确保跳转目标与用户预期完全一致。

索引状态标记：每条记录包含收录时间、批次号、原始来源标记与有效性状态（有效/待验证/失效），便于后续批量检测与维护。

静态页面生成引擎：内置模板系统，可将所有收录链接渲染为纯静态 HTML 页面，无需数据库，直接部署即可访问。

命令行交互工具：提供 CLI 命令用于新增链接、批量导入、生成站点、验证链接可达性，适合集成进 CI/CD 或定时任务。

全文检索支持：集成轻量级倒排索引，支持按文章编号、域名片段、批次号进行快速检索，返回匹配记录列表。

---

## 应用场景

技术文档与资料归档：技术团队在撰写调研报告或收集竞品信息时，会产生大量参考链接。WebIndex 可将这些链接按批次录入，生成内部可共享的导航页面，避免链接散落在聊天记录或本地文档中无法统一管理。

内容聚合站点运营：个人博主或小型内容平台运营者，需要定期汇总外部引用来源或友情链接。WebIndex 的批次化管理能力可以按周或按月生成独立的链接清单页面，便于读者追溯原始信息来源。

运维监控与资源清单维护：运维人员需要记录各类监控面板、日志系统、管理后台的入口地址。WebIndex 支持批量录入和状态标记，可将所有内部系统入口汇总为统一导航页，配合链接可达性检测功能定期刷新状态。

数据采集与爬虫任务管理：数据采集工程师在爬取任务中会产生大量中间页 URL。WebIndex 可作为临时链接暂存与去重工具，帮助记录已采集和待采集的 URL，避免重复抓取或遗漏。

---

## 快速开始

以下命令适用于 Linux / macOS / WSL 环境，需提前安装 Git 与 Python 3.9 及以上版本。

```bash
git clone https://github.com/webindex/webindex.git
cd webindex
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
python manage.py init
python manage.py import --batch 4 --source urls.txt
python manage.py generate --output ./dist
```

执行完成后，所有静态页面将生成于 ./dist 目录，可直接使用任意 HTTP 服务器托管，例如：

```bash
python -m http.server 8080 --directory ./dist
```

---

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 及以上 | 核心运行环境，用于 CLI 工具与生成引擎 |
| Git | 2.25 及以上 | 用于克隆仓库与版本管理 |
| pip | 21.0 及以上 | Python 包依赖管理 |
| virtualenv 或 venv | 内置 | 推荐使用 Python 内置 venv 创建隔离环境 |
| Markdown 解析库 | markdown 3.4.1 | 用于将索引数据渲染为 HTML 内容块 |
| Jinja2 | 3.1.2 | 模板引擎，用于生成静态页面 |
| requests | 2.31.0 | 可选依赖，用于链接可达性检测功能 |
| pytest | 8.0.0 | 开发测试依赖，仅运行测试套件时需要 |

---

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | /docs/user-guide.md | 如何新增链接、导入批次、生成站点、配置分类规则 |
| 管理员指南 | /docs/admin-guide.md | 如何部署到生产环境、配置 Nginx、设置定时检测任务 |
| 开发参考 | /docs/developer-guide.md | 模板系统如何扩展、数据存储格式说明、CLI 命令开发约定 |
| 常见任务 | /docs/recipes.md | 批量去重、链接状态批量更新、自定义页面模板示例 |

---

## 资源列表

- http://http://www.mobile.xqnqq.com/Article/027852.shtml
- http://http://www.mobile.xqnqq.com/Article/8147705.shtml
- http://http://www.mobile.xqnqq.com/Article/97281.shtml
- http://http://www.mobile.xqnqq.com/Article/6513866.shtml
- http://http://www.read.usuhx.com/Article/028541.shtml
- http://http://www.mobile.xqnqq.com/Article/420975.shtml
- http://http://www.mobile.xqnqq.com/Article/518656.shtml
- http://http://www.mobile.xqnqq.com/Article/5903.shtml
- http://http://www.mobile.xqnqq.com/Article/0487208.shtml
- http://http://www.mobile.xqnqq.com/Article/2756252.shtml
- http://http://www.mobile.xqnqq.com/Article/0292.shtml
- http://http://www.read.usuhx.com/Article/1578319.shtml
- http://http://www.mobile.xqnqq.com/Article/7693942.shtml
- http://http://www.read.usuhx.com/Article/5546.shtml
- http://http://www.mobile.xqnqq.com/Article/956817.shtml
- http://http://www.mobile.xqnqq.com/Article/949706.shtml
- http://http://www.mobile.xqnqq.com/Article/163883.shtml
- http://http://www.read.usuhx.com/Article/28089.shtml
- http://http://www.read.usuhx.com/Article/271340.shtml
- http://http://www.mobile.xqnqq.com/Article/383203.shtml
- http://http://www.mobile.xqnqq.com/Article/641162.shtml
- http://http://www.mobile.xqnqq.com/Article/4789200.shtml
- http://http://www.read.usuhx.com/Article/8140836.shtml
- http://http://www.mobile.xqnqq.com/Article/295608.shtml
- http://http://www.read.usuhx.com/Article/9192102.shtml
- http://http://www.read.usuhx.com/Article/1572903.shtml
- http://http://www.mobile.xqnqq.com/Article/9997107.shtml
- http://http://www.read.usuhx.com/Article/9755.shtml
- http://http://www.read.usuhx.com/Article/6875414.shtml
- http://http://www.mobile.xqnqq.com/Article/690590.shtml
- http://http://www.mobile.xqnqq.com/Article/08072.shtml
- http://http://www.read.usuhx.com/Article/37789.shtml
- http://http://www.mobile.xqnqq.com/Article/121593.shtml
- http://http://www.mobile.xqnqq.com/Article/49444.shtml
- http://http://www.read.usuhx.com/Article/7354.shtml
- http://http://www.mobile.xqnqq.com/Article/640418.shtml
- http://http://www.mobile.xqnqq.com/Article/69900.shtml
- http://http://www.mobile.xqnqq.com/Article/2727.shtml
- http://http://www.mobile.xqnqq.com/Article/4258743.shtml
- http://http://www.read.usuhx.com/Article/29407.shtml
- http://http://www.mobile.xqnqq.com/Article/34902.shtml
- http://http://www.read.usuhx.com/Article/554309.shtml
- http://http://www.read.usuhx.com/Article/9127554.shtml
- http://http://www.mobile.xqnqq.com/Article/824535.shtml
- http://http://www.mobile.xqnqq.com/Article/89571.shtml
- http://http://www.read.usuhx.com/Article/52165.shtml
- http://http://www.read.usuhx.com/Article/35343.shtml
- http://http://www.read.usuhx.com/Article/0434851.shtml
- http://http://www.mobile.xqnqq.com/Article/742038.shtml
- http://http://www.mobile.xqnqq.com/Article/34643.shtml
- http://http://www.read.usuhx.com/Article/135323.shtml
- http://http://www.mobile.xqnqq.com/Article/8911884.shtml
- http://http://www.mobile.xqnqq.com/Article/5708264.shtml
- http://http://www.mobile.xqnqq.com/Article/31531.shtml
- http://http://www.mobile.xqnqq.com/Article/9645481.shtml
- http://http://www.read.usuhx.com/Article/0547791.shtml
- http://http://www.read.usuhx.com/Article/7074799.shtml
- http://http://www.read.usuhx.com/Article/69941.shtml
- http://http://www.read.usuhx.com/Article/140427.shtml
- http://http://www.mobile.xqnqq.com/Article/5974.shtml
- http://http://www.mobile.xqnqq.com/Article/3643.shtml
- http://http://www.mobile.xqnqq.com/Article/5434.shtml
- http://http://www.read.usuhx.com/Article/3921232.shtml
- http://http://www.mobile.xqnqq.com/Article/50891.shtml
- http://http://www.read.usuhx.com/Article/44639.shtml
- http://http://www.mobile.xqnqq.com/Article/8451834.shtml
- http://http://www.read.usuhx.com/Article/189578.shtml
- http://http://www.mobile.xqnqq.com/Article/4444.shtml
- http://http://www.read.usuhx.com/Article/3038.shtml
- http://http://www.mobile.xqnqq.com/Article/090023.shtml
- http://http://www.read.usuhx.com/Article/3996.shtml
- http://http://www.read.usuhx.com/Article/5673.shtml
- http://http://www.read.usuhx.com/Article/100010.shtml
- http://http://www.mobile.xqnqq.com/Article/29867.shtml
- http://http://www.read.usuhx.com/Article/075784.shtml
- http://http://www.mobile.xqnqq.com/Article/90850.shtml
- http://http://www.mobile.xqnqq.com/Article/240486.shtml
- http://http://www.mobile.xqnqq.com/Article/77406.shtml
- http://http://www.read.usuhx.com/Article/309816.shtml
- http://http://www.read.usuhx.com/Article/1763629.shtml
- http://http://www.mobile.xqnqq.com/Article/4438.shtml
- http://http://www.mobile.xqnqq.com/Article/159657.shtml
- http://http://www.mobile.xqnqq.com/Article/6629663.shtml
- http://http://www.mobile.xqnqq.com/Article/508064.shtml
- http://http://www.mobile.xqnqq.com/Article/48140.shtml
- http://http://www.read.usuhx.com/Article/170311.shtml
- http://http://www.read.usuhx.com/Article/8750.shtml
- http://http://www.mobile.xqnqq.com/Article/3973.shtml
- http://http://www.mobile.xqnqq.com/Article/835066.shtml
- http://http://www.read.usuhx.com/Article/067255.shtml
- http://http://www.mobile.xqnqq.com/Article/45608.shtml
- http://http://www.read.usuhx.com/Article/2180012.shtml
- http://http://www.read.usuhx.com/Article/18456.shtml
- http://http://www.read.usuhx.com/Article/5420366.shtml
- http://http://www.read.usuhx.com/Article/0046.shtml
- http://http://www.mobile.xqnqq.com/Article/776415.shtml
- http://http://www.read.usuhx.com/Article/082365.shtml
- http://http://www.mobile.xqnqq.com/Article/80591.shtml
- http://http://www.mobile.xqnqq.com/Article/148297.shtml
- http://http://www.mobile.xqnqq.com/Article/1933388.shtml
- http://http://www.read.usuhx.com/Article/37287.shtml
- http://http://www.read.usuhx.com/Article/96195.shtml
- http://http://www.mobile.xqnqq.com/Article/69891.shtml
- http://http://www.mobile.xqnqq.com/Article/983591.shtml
- http://http://www.mobile.xqnqq.com/Article/3523039.shtml
- http://http://www.read.usuhx.com/Article/005978.shtml
- http://http://www.read.usuhx.com/Article/92971.shtml
- http://http://www.read.usuhx.com/Article/49276.shtml
- http://http://www.mobile.xqnqq.com/Article/937807.shtml
- http://http://www.mobile.xqnqq.com/Article/42741.shtml
- http://http://www.mobile.xqnqq.com/Article/4223173.shtml
- http://http://www.read.usuhx.com/Article/373665.shtml
- http://http://www.mobile.xqnqq.com/Article/1877.shtml
- http://http://www.read.usuhx.com/Article/6332496.shtml
- http://http://www.read.usuhx.com/Article/2786093.shtml
- http://http://www.read.usuhx.com/Article/2312.shtml
- http://http://www.read.usuhx.com/Article/789919.shtml
- http://http://www.read.usuhx.com/Article/2741.shtml
- http://http://www.mobile.xqnqq.com/Article/9131341.shtml
- http://http://www.read.usuhx.com/Article/7671609.shtml
- http://http://www.mobile.xqnqq.com/Article/5897.shtml
- http://http://www.mobile.xqnqq.com/Article/88848.shtml
- http://http://www.read.usuhx.com/Article/078789.shtml
- http://http://www.mobile.xqnqq.com/Article/6773352.shtml
- http://http://www.mobile.xqnqq.com/Article/4351910.shtml
- http://http://www.read.usuhx.com/Article/2125.shtml
- http://http://www.read.usuhx.com/Article/2435.shtml
- http://http://www.read.usuhx.com/Article/612465.shtml
- http://http://www.read.usuhx.com/Article/0732897.shtml
- http://http://www.read.usuhx.com/Article/1429.shtml
- http://http://www.read.usuhx.com/Article/57982.shtml
- http://http://www.read.usuhx.com/Article/26883.shtml
- http://http://www.read.usuhx.com/Article/284440.shtml
- http://http://www.read.usuhx.com/Article/292962.shtml
- http://http://www.mobile.xqnqq.com/Article/59302.shtml
- http://http://www.read.usuhx.com/Article/80475.shtml
- http://http://www.mobile.xqnqq.com/Article/7559667.shtml
- http://http://www.mobile.xqnqq.com/Article/03997.shtml
- http://http://www.mobile.xqnqq.com/Article/359639.shtml
- http://http://www.read.usuhx.com/Article/3200271.shtml
- http://http://www.read.usuhx.com/Article/41085.shtml
- http://http://www.read.usuhx.com/Article/812531.shtml
- http://http://www.mobile.xqnqq.com/Article/4983035.shtml
- http://http://www.read.usuhx.com/Article/43528.shtml
- http://http://www.read.usuhx.com/Article/68248.shtml
- http://http://www.mobile.xqnqq.com/Article/766848.shtml
- http://http://www.mobile.xqnqq.com/Article/3012.shtml
- http://http://www.mobile.xqnqq.com/Article/8722675.shtml
- http://http://www.mobile.xqnqq.com/Article/04254.shtml
- http://http://www.read.usuhx.com/Article/7664.shtml
- http://http://www.mobile.xqnqq.com/Article/20085.shtml
- http://http://www.mobile.xqnqq.com/Article/7340156.shtml
- http://http://www.read.usuhx.com/Article/1404513.shtml
- http://http://www.read.usuhx.com/Article/807629.shtml
- http://http://www.mobile.xqnqq.com/Article/1486431.shtml
- http://http://www.read.usuhx.com/Article/3098.shtml
- http://http://www.mobile.xqnqq.com/Article/186431.shtml
- http://http://www.mobile.xqnqq.com/Article/4093.shtml
- http://http://www.mobile.xqnqq.com/Article/42372.shtml
- http://http://www.mobile.xqnqq.com/Article/294354.shtml
- http://http://www.mobile.xqnqq.com/Article/057269.shtml
- http://http://www.read.usuhx.com/Article/4622898.shtml
- http://http://www.read.usuhx.com/Article/39371.shtml
- http://http://www.read.usuhx.com/Article/838080.shtml
- http://http://www.read.usuhx.com/Article/34348.shtml
- http://http://www.read.usuhx.com/Article/786414.shtml
- http://http://www.mobile.xqnqq.com/Article/74893.shtml
- http://http://www.read.usuhx.com/Article/102101.shtml
- http://http://www.read.usuhx.com/Article/461632.shtml
- http://http://www.mobile.xqnqq.com/Article/058263.shtml
- http://http://www.read.usuhx.com/Article/7811.shtml
- http://http://www.read.usuhx.com/Article/74547.shtml
- http://http://www.read.usuhx.com/Article/9677.shtml
- http://http://www.read.usuhx.com/Article/68193.shtml
- http://http://www.mobile.xqnqq.com/Article/785445.shtml
- http://http://www.mobile.xqnqq.com/Article/675494.shtml
- http://http://www.read.usuhx.com/Article/91905.shtml
- http://http://www.mobile.xqnqq.com/Article/2196941.shtml
- http://http://www.mobile.xqnqq.com/Article/09127.shtml
- http://http://www.read.usuhx.com/Article/913689.shtml
- http://http://www.read.usuhx.com/Article/53849.shtml
- http://http://www.mobile.xqnqq.com/Article/4809.shtml
- http://http://www.read.usuhx.com/Article/43251.shtml
- http://http://www.read.usuhx.com/Article/343750.shtml
- http://http://www.read.usuhx.com/Article/4505.shtml
- http://http://www.mobile.xqnqq.com/Article/1056777.shtml
- http://http://www.read.usuhx.com/Article/7463.shtml
- http://http://www.read.usuhx.com/Article/380249.shtml
- http://http://www.read.usuhx.com/Article/48437.shtml
- http://http://www.mobile.xqnqq.com/Article/1408.shtml
- http://http://www.mobile.xqnqq.com/Article/1364419.shtml
- http://http://www.read.usuhx.com/Article/385607.shtml
- http://http://www.mobile.xqnqq.com/Article/938246.shtml
- http://http://www.read.usuhx.com/Article/1500.shtml
- http://http://www.read.usuhx.com/Article/7088046.shtml
- http://http://www.read.usuhx.com/Article/287994.shtml
- http://http://www.read.usuhx.com/Article/501887.shtml
- http://http://www.read.usuhx.com/Article/141284.shtml
- http://http://www.mobile.xqnqq.com/Article/7324.shtml
- http://http://www.mobile.xqnqq.com/Article/05285.shtml
- http://http://www.mobile.xqnqq.com/Article/7852811.shtml
- http://http://www.mobile.xqnqq.com/Article/945997.shtml
- http://http://www.mobile.xqnqq.com/Article/167320.shtml
- http://http://www.read.usuhx.com/Article/18370.shtml
- http://http://www.mobile.xqnqq.com/Article/991529.shtml
- http://http://www.read.usuhx.com/Article/545117.shtml
- http://http://www.read.usuhx.com/Article/147186.shtml
- http://http://www.mobile.xqnqq.com/Article/66679.shtml
- http://http://www.read.usuhx.com/Article/18845.shtml
- http://http://www.read.usuhx.com/Article/86995.shtml
- http://http://www.read.usuhx.com/Article/286957.shtml
- http://http://www.read.usuhx.com/Article/89111.shtml
- http://http://www.read.usuhx.com/Article/082388.shtml
- http://http://www.read.usuhx.com/Article/0984628.shtml
- http://http://www.read.usuhx.com/Article/0612.shtml
- http://http://www.mobile.xqnqq.com/Article/50850.shtml
- http://http://www.mobile.xqnqq.com/Article/014254.shtml
- http://http://www.mobile.xqnqq.com/Article/4302366.shtml
- http://http://www.read.usuhx.com/Article/833289.shtml
- http://http://www.mobile.xqnqq.com/Article/770829.shtml
- http://http://www.read.usuhx.com/Article/8891080.shtml
- http://http://www.read.usuhx.com/Article/4027170.shtml
- http://http://www.mobile.xqnqq.com/Article/67886.shtml
- http://http://www.mobile.xqnqq.com/Article/756066.shtml
- http://http://www.mobile.xqnqq.com/Article/25110.shtml
- http://http://www.read.usuhx.com/Article/8989946.shtml
- http://http://www.mobile.xqnqq.com/Article/64346.shtml
- http://http://www.read.usuhx.com/Article/7287.shtml
- http://http://www.mobile.xqnqq.com/Article/0439746.shtml
- http://http://www.read.usuhx.com/Article/711381.shtml
- http://http://www.read.usuhx.com/Article/0506940.shtml
- http://http://www.read.usuhx.com/Article/45011.shtml
- http://http://www.read.usuhx.com/Article/8948.shtml
- http://http://www.mobile.xqnqq.com/Article/627284.shtml
- http://http://www.read.usuhx.com/Article/2460.shtml
- http://http://www.read.usuhx.com/Article/00886.shtml
- http://http://www.read.usuhx.com/Article/6934872.shtml
- http://http://www.mobile.xqnqq.com/Article/137186.shtml
- http://http://www.read.usuhx.com/Article/4859.shtml
- http://http://www.read.usuhx.com/Article/38915.shtml
- http://http://www.mobile.xqnqq.com/Article/6393.shtml
- http://http://www.read.usuhx.com/Article/475668.shtml
- http://http://www.read.usuhx.com/Article/93783.shtml
- http://http://www.read.usuhx.com/Article/51347.shtml
- http://http://www.read.usuhx.com/Article/1363.shtml
- http://http://www.mobile.xqnqq.com/Article/6960609.shtml
- http://http://www.read.usuhx.com/Article/4636343.shtml
- http://http://www.mobile.xqnqq.com/Article/7113.shtml
- http://http://www.read.usuhx.com/Article/8951308.shtml
- http://http://www.mobile.xqnqq.com/Article/422648.shtml

## 项目结构

```
webindex/
├── cli/                                 # 命令行工具模块
│   ├── commands/                        # 子命令实现
│   │   ├── import.py                    # 导入批次链接
│   │   ├── generate.py                  # 生成静态站点
│   │   ├── verify.py                    # 链接可达性检测
│   │   └── list.py                      # 列出已收录记录
│   ├── main.py                          # CLI 入口
│   └── config.py                        # 配置加载与校验
├── core/                                # 核心数据模型与逻辑
│   ├── models/                          # 数据模型定义
│   │   ├── record.py                    # 单条链接记录模型
│   │   ├── batch.py                     # 批次元数据模型
│   │   └── index.py                     # 索引结构模型
│   ├── storage/                         # 存储后端
│   │   ├── file_backend.py              # 基于 JSON 文件的存储实现
│   │   └── schema.py                    # 存储结构定义
│   └── parser/                          # URL 解析与规范化
│       ├── extractor.py                 # 域名、路径、编号提取
│       └── validator.py                 # 格式校验
├── templates/                           # 静态页面模板
│   ├── base.html                        # 基础布局模板
│   ├── index.html                       # 首页导航模板
│   ├── batch.html                       # 批次详情页
│   └── detail.html                      # 单条链接详情页
├── static/                              # 静态资源
│   ├── css/                             # 样式文件
│   │   └── style.css                    # 主样式表
│   └── js/                              # 前端脚本
│       └── search.js                    # 本地检索功能
├── tests/                               # 单元测试与集成测试
│   ├── test_models.py                   # 数据模型测试
│   ├── test_storage.py                  # 存储层测试
│   └── test_cli.py                      # 命令行功能测试
├── docs/                                # 文档目录
│   ├── user-guide.md                    # 用户手册
│   ├── admin-guide.md                   # 管理员指南
│   ├── developer-guide.md               # 开发参考
│   └── recipes.md                       # 常见任务与配方
├── data/                                # 数据存储目录
│   ├── batches/                         # 按批次存储的原始数据
│   └── index.json                       # 全局索引文件
├── scripts/                             # 辅助脚本
│   ├── batch_check.sh                   # 批量检测链接状态
│   └── deploy.sh                        # 一键部署至服务器
├── .env.example                         # 环境变量模板
├── requirements.txt                     # Python 依赖清单
├── setup.py                             # 安装脚本
└── README.md                            # 项目说明文档
```

---

## 贡献指南

提交 Issue 报告缺陷或功能请求：使用 GitHub Issues 提交详细描述，包含运行环境、Python 版本、复现步骤与期望结果。缺陷报告需附带最小化测试用例或相关日志片段。

创建 Pull Request 进行代码贡献：从 main 分支创建新的特性分支，确保代码通过全部单元测试（pytest 覆盖率不低于 85%），并在 PR 描述中明确关联对应的 Issue 编号。

完善文档与翻译：欢迎对用户手册、管理员指南或开发者参考进行补充与修订。文档采用 Markdown 格式，遵循中文技术文档写作规范，修正错别字、优化示例、补充遗漏步骤均可。

新增链接批次数据：如果您有大量公开可用的技术资源链接，可以按照 data/sample.json 格式整理后提交至 data/contrib/ 目录，经审核后合并入官方索引库。

反馈使用体验与改进建议：在 GitHub Discussions 中分享您的使用场景、部署方式与改进建议，帮助项目更好地匹配实际需求。

---

## 常见问题

Q：导入链接时提示 "invalid URL format"，但链接在浏览器中可以正常打开。是什么原因？

A：WebIndex 对 URL 格式校验较为严格，要求必须包含协议头。您提交的链接中若存在以 "http://http://" 开头的写法，会被解析器视为双重协议而拒绝。请在导入前将链接统一修正为以 "http://" 或 "https://" 单次开头。如果您的原始数据确实包含此类格式，可在导入时使用 --strict=false 参数关闭严格校验模式，系统将保留原始字符串不做解析。

Q：生成的静态页面中，链接跳转后显示 404，但手动复制链接到地址栏可以正常访问。如何解决？

A：该问题通常由静态页面中的链接自动补全行为导致。WebIndex 在生成页面时严格使用原始 URL 字符串作为 href 属性值，不进行任何自动补全。如果您的原始 URL 为 "http://http://..." 格式，浏览器会将其解析为 "http://http://..." 并尝试访问，这可能与您手动访问时的实际地址不一致。建议在导入前检查并修正原始数据。如果无法修改原始数据，可启用 raw_output 模式，系统将链接以纯文本形式展示而非可点击的超链接。

Q：如何批量更新已有链接的状态标记？

A：使用 verify 命令配合 --batch 参数可重新检测特定批次内所有链接的可达性，并自动更新状态字段。例如：python manage.py verify --batch 4 --timeout 5 --retry 2。检测完成后，重新执行 generate 命令即可刷新静态页面中的状态显示。如需手动更新单条记录的状态，可使用 update 命令：python manage.py update --id <record_id> --status verified。

---

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
