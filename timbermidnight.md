# WebLink Collective

WebLink Collective 是一个面向技术研究者、内容聚合者与信息分析人员的高质量外链资源汇总项目。本项目基于分布式数据采集与结构化存储方案，对来自多个内容源的技术文章、行业资讯及深度报道进行系统性整理与索引。项目定位为技术资源导航中间层，不直接存储原始内容，而是通过标准化链接映射机制，为开发者提供可追溯、可验证、可扩展的外部信息入口。

WebLink Collective 适用于需要批量访问特定域名下技术文章链接的自动化脚本、内容推荐系统的数据预热、搜索引擎爬虫的种子库构建，以及人工审阅场景下的快速跳转需求。项目内置分级标签体系与初步去重策略，支持按来源域名、文章编号与批次进行快速筛选。当前批次为第 10/80 批，共计收录 250 个有效外链资源，覆盖双域名下的多类目技术内容。

## 功能概览

批量外链导入与标准化清洗：接收原始 URL 列表，自动去除多余协议前缀与空白字符，统一为可访问的 HTTP 链接格式，保留原始路径与查询参数。

多源域名聚合管理：支持同时处理来自不同根域名的链接资源，本项目当前覆盖 mobile.xqnqq.com 与 read.usuhx.com 两个主要域名，各自独立维护文章编号映射表。

结构化元数据提取：从 URL 路径中解析 Article 目录后的数字编号，作为该资源的唯一业务主键，便于后续去重、排序与关联查询。

链接可用性预检：对每个录入链接执行基础 HTTP 状态码探测（可选开关），标记异常状态（4xx/5xx/超时），辅助用户判断资源存活情况。

批次进度追踪：记录当前批次序号（10/80）、总资源数、已处理数与通过率，支持断点续传与增量导入。

原始数据保留与导出：所有 URL 严格按用户原始输入格式存储，导出时保持原样，不添加协议补全、不修改大小写、不附加尾部斜杠。

标签关联与全文检索：为每个链接关联自动生成的关键词标签（基于路径与编号规律），支持通过标签组合快速定位特定批次或域名的资源。

RESTful API 接口：提供 `/api/v1/links` 端点，支持分页查询、按域名过滤、按批次筛选，返回 JSON 格式数据，便于集成至外部工具链。

## 应用场景

技术资讯聚合平台的种子链接采集。内容聚合系统每日需从固定源站抓取最新文章，WebLink Collective 提供结构化的初始链接池，调度器可依据本项目的资源列表进行差异化抓取频率配置，避免重复爬取与遗漏。

外链健康度定期巡检。运维团队可利用本项目的链接列表，配合第三方监控工具，对两个域名下的文章链接进行周期性可达性检测，及时发现源站删除或迁移导致的失效链接，更新内部书签库。

数据分析脚本的测试数据集。数据科学家在构建 URL 解析模型或文本分类器时，需要大量真实 URL 样本进行训练与验证。本项目提供的 250 个真实外链可作为基准测试集，评估解析器的准确率与鲁棒性。

人工内容审阅的快速导航目录。内容编辑或法务审核人员需定期抽查外部引用来源，本项目按批次组织的资源列表可直接作为工作清单，每行一个链接，复制至浏览器即可访问，提高审阅效率。

SEO 反向链路分析的前端数据源。SEO 工程师可利用本项目导出的 URL 列表，配合外链分析工具，评估两个域名的反向链接分布、锚文本多样性及页面权重传递特征。

## 快速开始

以下命令演示了如何从 GitHub 克隆本项目、安装基础依赖并运行本地预览服务。

```bash
# 克隆项目仓库
git clone https://github.com/weblink-collective/weblink-collective.git

# 进入项目目录
cd weblink-collective

# 安装 Node.js 依赖（适用于 API 服务与前端面板）
npm install

# 运行开发服务器，默认监听 3000 端口
npm run dev
```

访问 `http://localhost:3000` 可查看当前批次的资源列表与统计面板。若需仅导出纯文本链接列表，可执行以下命令：

```bash
npm run export:links -- --batch=10 --format=markdown
```

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|----------|----------|------|
| Node.js | 16.x 或更高 | 运行时环境，用于执行 API 服务与构建脚本 |
| npm | 8.x 或更高 | 包管理器，用于安装项目依赖 |
| SQLite3 | 3.32.0 或更高 | 嵌入式数据库，存储链接元数据与批次信息 |
| Git | 2.25.0 或更高 | 版本控制，用于克隆仓库与提交更新 |
| curl | 7.68.0 或更高 | 可选，用于链接可用性预检的 HTTP 探测 |
| 操作系统 | Linux / macOS / Windows WSL2 | 项目未针对原生 Windows 命令行做全面适配 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 入门指南 | `docs/getting-started.md` | 如何快速获取当前批次的所有链接并开始使用？ |
| API 参考 | `docs/api-reference.md` | 如何通过 RESTful 接口查询、过滤与导出链接数据？ |
| 数据格式 | `docs/data-format.md` | URL 的存储结构、字段定义与扩展字段如何设计？ |
| 贡献手册 | `docs/contributing.md` | 如何提交新批次的数据、修复失效链接或改进解析逻辑？ |

## 资源列表

- http://http://www.mobile.xqnqq.com/Article/7876873.shtml
- http://http://www.mobile.xqnqq.com/Article/15808.shtml
- http://http://www.mobile.xqnqq.com/Article/58990.shtml
- http://http://www.mobile.xqnqq.com/Article/7249.shtml
- http://http://www.read.usuhx.com/Article/727828.shtml
- http://http://www.read.usuhx.com/Article/7721202.shtml
- http://http://www.mobile.xqnqq.com/Article/2116715.shtml
- http://http://www.mobile.xqnqq.com/Article/91333.shtml
- http://http://www.mobile.xqnqq.com/Article/05395.shtml
- http://http://www.mobile.xqnqq.com/Article/79159.shtml
- http://http://www.mobile.xqnqq.com/Article/3845.shtml
- http://http://www.read.usuhx.com/Article/67229.shtml
- http://http://www.mobile.xqnqq.com/Article/635958.shtml
- http://http://www.mobile.xqnqq.com/Article/96532.shtml
- http://http://www.read.usuhx.com/Article/0769.shtml
- http://http://www.read.usuhx.com/Article/96537.shtml
- http://http://www.read.usuhx.com/Article/1273619.shtml
- http://http://www.mobile.xqnqq.com/Article/6801.shtml
- http://http://www.mobile.xqnqq.com/Article/40075.shtml
- http://http://www.mobile.xqnqq.com/Article/10732.shtml
- http://http://www.read.usuhx.com/Article/13508.shtml
- http://http://www.read.usuhx.com/Article/991122.shtml
- http://http://www.read.usuhx.com/Article/837994.shtml
- http://http://www.read.usuhx.com/Article/4374.shtml
- http://http://www.mobile.xqnqq.com/Article/8506301.shtml
- http://http://www.read.usuhx.com/Article/77053.shtml
- http://http://www.mobile.xqnqq.com/Article/4872.shtml
- http://http://www.mobile.xqnqq.com/Article/844482.shtml
- http://http://www.mobile.xqnqq.com/Article/3724.shtml
- http://http://www.read.usuhx.com/Article/6859586.shtml
- http://http://www.mobile.xqnqq.com/Article/82902.shtml
- http://http://www.read.usuhx.com/Article/8281420.shtml
- http://http://www.read.usuhx.com/Article/78355.shtml
- http://http://www.read.usuhx.com/Article/6830974.shtml
- http://http://www.mobile.xqnqq.com/Article/54965.shtml
- http://http://www.mobile.xqnqq.com/Article/056935.shtml
- http://http://www.read.usuhx.com/Article/9590.shtml
- http://http://www.read.usuhx.com/Article/5273941.shtml
- http://http://www.read.usuhx.com/Article/4756802.shtml
- http://http://www.mobile.xqnqq.com/Article/6586207.shtml
- http://http://www.read.usuhx.com/Article/0928.shtml
- http://http://www.mobile.xqnqq.com/Article/001879.shtml
- http://http://www.read.usuhx.com/Article/80090.shtml
- http://http://www.mobile.xqnqq.com/Article/119813.shtml
- http://http://www.read.usuhx.com/Article/1618064.shtml
- http://http://www.read.usuhx.com/Article/03368.shtml
- http://http://www.mobile.xqnqq.com/Article/928013.shtml
- http://http://www.mobile.xqnqq.com/Article/2521.shtml
- http://http://www.mobile.xqnqq.com/Article/4492.shtml
- http://http://www.mobile.xqnqq.com/Article/7382121.shtml
- http://http://www.mobile.xqnqq.com/Article/27878.shtml
- http://http://www.read.usuhx.com/Article/598219.shtml
- http://http://www.read.usuhx.com/Article/8912.shtml
- http://http://www.mobile.xqnqq.com/Article/6891133.shtml
- http://http://www.mobile.xqnqq.com/Article/049587.shtml
- http://http://www.read.usuhx.com/Article/15375.shtml
- http://http://www.read.usuhx.com/Article/17187.shtml
- http://http://www.mobile.xqnqq.com/Article/2622464.shtml
- http://http://www.read.usuhx.com/Article/9357954.shtml
- http://http://www.mobile.xqnqq.com/Article/8695.shtml
- http://http://www.read.usuhx.com/Article/8146349.shtml
- http://http://www.read.usuhx.com/Article/9641.shtml
- http://http://www.mobile.xqnqq.com/Article/6454.shtml
- http://http://www.read.usuhx.com/Article/5598525.shtml
- http://http://www.mobile.xqnqq.com/Article/326180.shtml
- http://http://www.read.usuhx.com/Article/8501318.shtml
- http://http://www.mobile.xqnqq.com/Article/632926.shtml
- http://http://www.read.usuhx.com/Article/4782.shtml
- http://http://www.read.usuhx.com/Article/4394.shtml
- http://http://www.mobile.xqnqq.com/Article/9480936.shtml
- http://http://www.read.usuhx.com/Article/64669.shtml
- http://http://www.read.usuhx.com/Article/281873.shtml
- http://http://www.mobile.xqnqq.com/Article/22888.shtml
- http://http://www.mobile.xqnqq.com/Article/183953.shtml
- http://http://www.mobile.xqnqq.com/Article/25357.shtml
- http://http://www.mobile.xqnqq.com/Article/997179.shtml
- http://http://www.read.usuhx.com/Article/1284999.shtml
- http://http://www.read.usuhx.com/Article/1083587.shtml
- http://http://www.read.usuhx.com/Article/65971.shtml
- http://http://www.mobile.xqnqq.com/Article/4044.shtml
- http://http://www.read.usuhx.com/Article/26598.shtml
- http://http://www.mobile.xqnqq.com/Article/7950.shtml
- http://http://www.read.usuhx.com/Article/56969.shtml
- http://http://www.mobile.xqnqq.com/Article/22611.shtml
- http://http://www.read.usuhx.com/Article/94772.shtml
- http://http://www.read.usuhx.com/Article/4425.shtml
- http://http://www.mobile.xqnqq.com/Article/682839.shtml
- http://http://www.read.usuhx.com/Article/6083894.shtml
- http://http://www.read.usuhx.com/Article/6629767.shtml
- http://http://www.mobile.xqnqq.com/Article/4328.shtml
- http://http://www.mobile.xqnqq.com/Article/1059.shtml
- http://http://www.mobile.xqnqq.com/Article/457410.shtml
- http://http://www.mobile.xqnqq.com/Article/4405182.shtml
- http://http://www.mobile.xqnqq.com/Article/361123.shtml
- http://http://www.read.usuhx.com/Article/19151.shtml
- http://http://www.mobile.xqnqq.com/Article/455026.shtml
- http://http://www.mobile.xqnqq.com/Article/8855296.shtml
- http://http://www.read.usuhx.com/Article/6032.shtml
- http://http://www.mobile.xqnqq.com/Article/61197.shtml
- http://http://www.mobile.xqnqq.com/Article/381265.shtml
- http://http://www.read.usuhx.com/Article/86341.shtml
- http://http://www.read.usuhx.com/Article/3864.shtml
- http://http://www.read.usuhx.com/Article/450530.shtml
- http://http://www.read.usuhx.com/Article/049774.shtml
- http://http://www.read.usuhx.com/Article/07823.shtml
- http://http://www.read.usuhx.com/Article/5378882.shtml
- http://http://www.mobile.xqnqq.com/Article/481921.shtml
- http://http://www.read.usuhx.com/Article/664771.shtml
- http://http://www.mobile.xqnqq.com/Article/1836543.shtml
- http://http://www.read.usuhx.com/Article/944083.shtml
- http://http://www.mobile.xqnqq.com/Article/1980.shtml
- http://http://www.mobile.xqnqq.com/Article/1222.shtml
- http://http://www.read.usuhx.com/Article/0206.shtml
- http://http://www.read.usuhx.com/Article/4893.shtml
- http://http://www.read.usuhx.com/Article/916448.shtml
- http://http://www.read.usuhx.com/Article/463517.shtml
- http://http://www.mobile.xqnqq.com/Article/5023.shtml
- http://http://www.read.usuhx.com/Article/35392.shtml
- http://http://www.read.usuhx.com/Article/14117.shtml
- http://http://www.mobile.xqnqq.com/Article/656050.shtml
- http://http://www.mobile.xqnqq.com/Article/17701.shtml
- http://http://www.mobile.xqnqq.com/Article/404864.shtml
- http://http://www.read.usuhx.com/Article/8227.shtml
- http://http://www.mobile.xqnqq.com/Article/26018.shtml
- http://http://www.mobile.xqnqq.com/Article/22490.shtml
- http://http://www.read.usuhx.com/Article/9518561.shtml
- http://http://www.mobile.xqnqq.com/Article/46258.shtml
- http://http://www.mobile.xqnqq.com/Article/9469.shtml
- http://http://www.mobile.xqnqq.com/Article/93399.shtml
- http://http://www.read.usuhx.com/Article/494681.shtml
- http://http://www.mobile.xqnqq.com/Article/74924.shtml
- http://http://www.read.usuhx.com/Article/678355.shtml
- http://http://www.read.usuhx.com/Article/9031.shtml
- http://http://www.mobile.xqnqq.com/Article/298975.shtml
- http://http://www.read.usuhx.com/Article/993304.shtml
- http://http://www.mobile.xqnqq.com/Article/721682.shtml
- http://http://www.read.usuhx.com/Article/92164.shtml
- http://http://www.read.usuhx.com/Article/0304595.shtml
- http://http://www.mobile.xqnqq.com/Article/40327.shtml
- http://http://www.read.usuhx.com/Article/616790.shtml
- http://http://www.mobile.xqnqq.com/Article/764456.shtml
- http://http://www.mobile.xqnqq.com/Article/9240.shtml
- http://http://www.read.usuhx.com/Article/1482029.shtml
- http://http://www.mobile.xqnqq.com/Article/9891.shtml
- http://http://www.read.usuhx.com/Article/509799.shtml
- http://http://www.read.usuhx.com/Article/788564.shtml
- http://http://www.mobile.xqnqq.com/Article/6245.shtml
- http://http://www.mobile.xqnqq.com/Article/1461116.shtml
- http://http://www.read.usuhx.com/Article/782023.shtml
- http://http://www.mobile.xqnqq.com/Article/18683.shtml
- http://http://www.read.usuhx.com/Article/5043.shtml
- http://http://www.mobile.xqnqq.com/Article/6857658.shtml
- http://http://www.read.usuhx.com/Article/1613.shtml
- http://http://www.mobile.xqnqq.com/Article/7777755.shtml
- http://http://www.read.usuhx.com/Article/1945590.shtml
- http://http://www.read.usuhx.com/Article/1409.shtml
- http://http://www.read.usuhx.com/Article/6180.shtml
- http://http://www.read.usuhx.com/Article/452085.shtml
- http://http://www.mobile.xqnqq.com/Article/7662893.shtml
- http://http://www.read.usuhx.com/Article/755408.shtml
- http://http://www.mobile.xqnqq.com/Article/8935441.shtml
- http://http://www.mobile.xqnqq.com/Article/4050586.shtml
- http://http://www.read.usuhx.com/Article/13572.shtml
- http://http://www.mobile.xqnqq.com/Article/6249720.shtml
- http://http://www.mobile.xqnqq.com/Article/56697.shtml
- http://http://www.read.usuhx.com/Article/4216133.shtml
- http://http://www.mobile.xqnqq.com/Article/4454.shtml
- http://http://www.mobile.xqnqq.com/Article/4997953.shtml
- http://http://www.read.usuhx.com/Article/37871.shtml
- http://http://www.mobile.xqnqq.com/Article/084525.shtml
- http://http://www.mobile.xqnqq.com/Article/47571.shtml
- http://http://www.read.usuhx.com/Article/73790.shtml
- http://http://www.mobile.xqnqq.com/Article/65742.shtml
- http://http://www.mobile.xqnqq.com/Article/4761.shtml
- http://http://www.read.usuhx.com/Article/135298.shtml
- http://http://www.mobile.xqnqq.com/Article/55015.shtml
- http://http://www.read.usuhx.com/Article/42895.shtml
- http://http://www.read.usuhx.com/Article/3221.shtml
- http://http://www.read.usuhx.com/Article/5266660.shtml
- http://http://www.mobile.xqnqq.com/Article/495419.shtml
- http://http://www.mobile.xqnqq.com/Article/3611.shtml
- http://http://www.read.usuhx.com/Article/9687.shtml
- http://http://www.read.usuhx.com/Article/7882104.shtml
- http://http://www.mobile.xqnqq.com/Article/8577607.shtml
- http://http://www.read.usuhx.com/Article/9877.shtml
- http://http://www.mobile.xqnqq.com/Article/81533.shtml
- http://http://www.mobile.xqnqq.com/Article/9002534.shtml
- http://http://www.read.usuhx.com/Article/3891.shtml
- http://http://www.mobile.xqnqq.com/Article/470870.shtml
- http://http://www.mobile.xqnqq.com/Article/3232138.shtml
- http://http://www.mobile.xqnqq.com/Article/693791.shtml
- http://http://www.mobile.xqnqq.com/Article/421180.shtml
- http://http://www.mobile.xqnqq.com/Article/165473.shtml
- http://http://www.read.usuhx.com/Article/1381786.shtml
- http://http://www.mobile.xqnqq.com/Article/4639.shtml
- http://http://www.mobile.xqnqq.com/Article/9397.shtml
- http://http://www.mobile.xqnqq.com/Article/09579.shtml
- http://http://www.read.usuhx.com/Article/2593.shtml
- http://http://www.mobile.xqnqq.com/Article/3769.shtml
- http://http://www.read.usuhx.com/Article/0727.shtml
- http://http://www.read.usuhx.com/Article/5795587.shtml
- http://http://www.mobile.xqnqq.com/Article/624764.shtml
- http://http://www.read.usuhx.com/Article/5389.shtml
- http://http://www.read.usuhx.com/Article/1967764.shtml
- http://http://www.mobile.xqnqq.com/Article/383045.shtml
- http://http://www.mobile.xqnqq.com/Article/8569.shtml
- http://http://www.mobile.xqnqq.com/Article/8528275.shtml
- http://http://www.mobile.xqnqq.com/Article/6644039.shtml
- http://http://www.mobile.xqnqq.com/Article/528662.shtml
- http://http://www.read.usuhx.com/Article/939138.shtml
- http://http://www.read.usuhx.com/Article/4007.shtml
- http://http://www.mobile.xqnqq.com/Article/73227.shtml
- http://http://www.read.usuhx.com/Article/69945.shtml
- http://http://www.mobile.xqnqq.com/Article/1124906.shtml
- http://http://www.read.usuhx.com/Article/338776.shtml
- http://http://www.mobile.xqnqq.com/Article/94232.shtml
- http://http://www.mobile.xqnqq.com/Article/8360093.shtml
- http://http://www.mobile.xqnqq.com/Article/1671602.shtml
- http://http://www.mobile.xqnqq.com/Article/921795.shtml
- http://http://www.mobile.xqnqq.com/Article/438431.shtml
- http://http://www.mobile.xqnqq.com/Article/81651.shtml
- http://http://www.read.usuhx.com/Article/4820071.shtml
- http://http://www.mobile.xqnqq.com/Article/823906.shtml
- http://http://www.read.usuhx.com/Article/51382.shtml
- http://http://www.read.usuhx.com/Article/279526.shtml
- http://http://www.mobile.xqnqq.com/Article/7091206.shtml
- http://http://www.mobile.xqnqq.com/Article/531407.shtml
- http://http://www.mobile.xqnqq.com/Article/73402.shtml
- http://http://www.mobile.xqnqq.com/Article/5296427.shtml
- http://http://www.mobile.xqnqq.com/Article/32553.shtml
- http://http://www.mobile.xqnqq.com/Article/0825.shtml
- http://http://www.mobile.xqnqq.com/Article/961135.shtml
- http://http://www.read.usuhx.com/Article/276564.shtml
- http://http://www.mobile.xqnqq.com/Article/72881.shtml
- http://http://www.mobile.xqnqq.com/Article/89432.shtml
- http://http://www.read.usuhx.com/Article/0618754.shtml
- http://http://www.read.usuhx.com/Article/6323536.shtml
- http://http://www.read.usuhx.com/Article/254538.shtml
- http://http://www.mobile.xqnqq.com/Article/147234.shtml
- http://http://www.read.usuhx.com/Article/9965.shtml
- http://http://www.read.usuhx.com/Article/1682.shtml
- http://http://www.mobile.xqnqq.com/Article/7374571.shtml
- http://http://www.read.usuhx.com/Article/03106.shtml
- http://http://www.read.usuhx.com/Article/52365.shtml
- http://http://www.read.usuhx.com/Article/90031.shtml
- http://http://www.read.usuhx.com/Article/7503226.shtml
- http://http://www.mobile.xqnqq.com/Article/05079.shtml
- http://http://www.read.usuhx.com/Article/16997.shtml
- http://http://www.mobile.xqnqq.com/Article/779031.shtml
- http://http://www.mobile.xqnqq.com/Article/2325328.shtml

## 项目结构

```
weblink-collective/
├── src/                                # 核心源代码目录
│   ├── api/                            # RESTful API 路由与控制器
│   │   ├── v1/                         # API v1 版本实现
│   │   │   ├── links.js                # 链接查询与过滤接口
│   │   │   └── batches.js              # 批次信息与进度接口
│   ├── core/                           # 业务逻辑核心模块
│   │   ├── importer.js                 # 原始 URL 导入与清洗引擎
│   │   ├── deduper.js                  # 基于文章编号的去重策略
│   │   └── validator.js                # 链接格式校验与协议修正
│   ├── db/                             # 数据库操作层
│   │   ├── migrations/                 # SQLite 表结构迁移脚本
│   │   │   └── 001_initial_schema.sql  # 初始化建表语句
│   │   ├── seed.js                     # 种子数据填充（含当前批次）
│   │   └── client.js                   # 数据库连接与查询封装
│   └── utils/                          # 通用工具函数
│       ├── logger.js                   # 日志记录（按日切分）
│       └── httpChecker.js              # 链接存活探测（依赖 curl）
├── docs/                               # 完整文档目录
│   ├── getting-started.md              # 入门指南
│   ├── api-reference.md                # API 详细参考
│   ├── data-format.md                  # 数据格式规范
│   └── contributing.md                 # 贡献指南
├── scripts/                            # 辅助运维脚本
│   ├── export-links.sh                 # 批量导出链接为纯文本
│   └── health-check.sh                 # 批量探测所有链接状态
├── config/                             # 环境配置
│   ├── default.json                    # 默认配置（端口、超时等）
│   └── production.json                 # 生产环境覆盖配置
├── tests/                              # 单元测试与集成测试
│   ├── importer.test.js                # 导入引擎测试
│   └── validator.test.js               # 校验器测试
├── .gitignore                          # Git 忽略文件列表
├── package.json                        # Node.js 项目清单与依赖
├── README.md                           # 项目主文档（本文件）
└── LICENSE                             # MIT 许可证文件
```

## 贡献指南

提交新批次数据：在 `src/db/seed.js` 中按现有格式追加新的 URL 数组，确保每个链接符合原始输入规范（不补协议、不改大小写），随后运行 `npm run db:migrate` 更新本地数据库。

修复失效链接：若发现资源列表中存在无法访问的链接，请先在 `docs/contributing.md` 中查阅失效链接处理流程，然后通过 Issue 提交具体的 URL 与 HTTP 状态码，或直接发起 Pull Request 在 `data/` 目录下标记失效记录。

改进解析逻辑：对 URL 解析器或去重算法的优化，需在 `tests/` 目录下补充对应的单元测试用例，确保改动不破坏现有功能，并提交带有测试覆盖的 Pull Request。

完善文档：文档更新应同步修改 `docs/` 目录下的对应 Markdown 文件，并在 Pull Request 描述中注明文档变更范围，便于审阅者快速定位。

报告安全问题：若发现本项目输出的链接指向恶意或钓鱼站点，请通过邮件联系安全响应团队（地址见 `docs/contributing.md`），勿在公开 Issue 中披露具体 URL。

## 常见问题

问题：为什么资源列表中的链接都带有 `http://http://` 重复前缀？这是否为错误？

回答：本项目严格遵循原始数据录入原则，所有 URL 均按用户提供的原始字符串原样存储与展示。重复前缀属于输入数据的原始特征，项目未做自动修正，以保证数据可追溯性与审计合规性。使用者可在脚本层面自行进行字符串替换处理。

问题：如何仅导出当前批次中属于 `mobile.xqnqq.com` 域名的链接？

回答：可通过 API 过滤参数 `?domain=mobile.xqnqq.com` 进行查询，或使用命令行工具 `npm run export:links -- --domain=mobile.xqnqq.com` 导出。前端面板也提供按域名的筛选下拉框。

问题：项目是否支持 HTTPS 链接的自动升级？

回答：不支持。出于数据完整性考量，项目不自动将 HTTP 改写为 HTTPS。用户如需使用 HTTPS 访问，应在消费数据时自行替换协议头，或通过配置反向代理实现升级。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
