# WebLink Hub

WebLink Hub 是一个面向技术研究人员、数据分析师和内容聚合者的结构化外链资源管理平台。该项目旨在解决分散在多个来源中的海量 URL 难以系统性整理、检索与复用的问题，通过统一的条目化存储和分类索引机制，将零散的链接转化为可审计、可追溯的知识资产。项目本身不生产内容，而是提供一套严谨的链接收录框架，适用于需要长期维护外部参考资源列表的工作流。

## 功能概览

- 批量链接导入：支持从纯文本、CSV 及 JSON 格式批量导入 URL 记录，自动去重并校验协议格式。
- 多维度标签分类：每条链接可绑定多个自定义标签，支持按项目、领域、优先级或来源站点进行精细分组。
- 原始字段保留：完整保存链接的原始 URL 字符串，不进行任何自动补全或规范化改写，确保与源数据绝对一致。
- 状态追踪与快照：记录每条链接的添加时间、最后访问状态码及响应时间，支持定期健康检查。
- 批次管理：按导入批次组织链接集合，当前批次编号为 6/80，便于大规模分发与增量更新。
- 只读镜像导出：生成纯 Markdown 格式的只读资源列表，可供静态站点或文档系统直接引用。
- 全文检索与过滤：基于 URL 路径关键词和标签组合进行快速筛选，支持正则表达式匹配模式。

## 应用场景

- 技术文档外部参考管理：技术写作团队在编写系统设计文档或 API 说明时，需要引用大量外部规范、标准或参考实现。WebLink Hub 可集中存放这些引用链接，并通过批次和标签关联到具体文档版本，避免参考链接失效或遗漏。
- 数据采集管道源头记录：数据工程团队在构建爬虫或采集任务时，需记录每个数据来源页面的原始 URL。WebLink Hub 提供严格的原始格式保留能力，确保溯源链路完整，便于数据审计和合规检查。
- 安全情报分析：安全研究员收集威胁情报报告、漏洞公告或恶意样本分析文章时，可利用本项目的标签系统按 CVE 编号、威胁组织或时间窗口对链接进行归类，支持快速检索与交叉引用。
- 开源项目 README 资源附录生成：开源项目维护者需要定期更新 README 中的“相关资源”或“参考资料”章节。WebLink Hub 可直接导出符合 Markdown 语法的资源列表，减少手动排版错误。
- 学术文献参考文献整理：研究人员在撰写综述或论文时，面对大量预印本、技术博客和官方文档链接，通过本项目的批次管理功能可区分不同草稿版本的引用集合。

## 快速开始

以下命令演示如何在本地环境中克隆代码仓库、安装依赖并启动开发服务。

```bash
git clone https://github.com/weblink-hub/weblink-hub.git
cd weblink-hub
npm install
npm run dev
```

执行上述命令后，开发服务器将运行在本地 3000 端口。访问 `http://localhost:3000` 可查看当前批次资源的管理界面。如需导入用户提供的原始链接数据，请将包含 URL 列表的文本文件放置于 `./data/import/` 目录下，随后执行 `npm run import` 命令。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Node.js | >= 18.0.0 | 运行时环境，支持 ES Modules 和 Fetch API |
| npm | >= 9.0.0 | 包管理器，用于安装项目依赖 |
| SQLite3 | 系统自带或手动安装 | 轻量级嵌入式数据库，用于存储链接元数据 |
| Git | >= 2.25.0 | 版本控制工具，用于克隆仓库和管理补丁 |
| TypeScript | >= 5.0.0 | 开发时类型检查，生产构建时需全局安装或使用 npx |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | /docs/user-guide/import-export.md | 如何从不同格式导入链接列表？导出时如何保留原始 URL 格式？ |
| 开发指南 | /docs/developer/architecture.md | 项目的模块划分和数据流是怎样的？新增标签处理器需要修改哪些文件？ |
| API 参考 | /docs/api/endpoints.md | 后端提供了哪些 REST 接口用于查询和更新链接记录？ |
| 运维手册 | /docs/operations/health-check.md | 如何配置定时任务对所有链接进行可用性探测？结果如何查看？ |

## 资源列表

- http://http://www.mobile.xqnqq.com/Article/9224.shtml
- http://http://www.mobile.xqnqq.com/Article/095744.shtml
- http://http://www.read.usuhx.com/Article/4858393.shtml
- http://http://www.mobile.xqnqq.com/Article/28499.shtml
- http://http://www.read.usuhx.com/Article/322144.shtml
- http://http://www.mobile.xqnqq.com/Article/4683.shtml
- http://http://www.mobile.xqnqq.com/Article/3960.shtml
- http://http://www.mobile.xqnqq.com/Article/1637386.shtml
- http://http://www.read.usuhx.com/Article/3529080.shtml
- http://http://www.read.usuhx.com/Article/1725935.shtml
- http://http://www.mobile.xqnqq.com/Article/16832.shtml
- http://http://www.mobile.xqnqq.com/Article/712077.shtml
- http://http://www.mobile.xqnqq.com/Article/8995936.shtml
- http://http://www.mobile.xqnqq.com/Article/415500.shtml
- http://http://www.read.usuhx.com/Article/439062.shtml
- http://http://www.mobile.xqnqq.com/Article/6574.shtml
- http://http://www.read.usuhx.com/Article/2921032.shtml
- http://http://www.read.usuhx.com/Article/3822760.shtml
- http://http://www.mobile.xqnqq.com/Article/60103.shtml
- http://http://www.read.usuhx.com/Article/757405.shtml
- http://http://www.mobile.xqnqq.com/Article/30377.shtml
- http://http://www.mobile.xqnqq.com/Article/225779.shtml
- http://http://www.read.usuhx.com/Article/0381.shtml
- http://http://www.read.usuhx.com/Article/981227.shtml
- http://http://www.read.usuhx.com/Article/1899500.shtml
- http://http://www.read.usuhx.com/Article/3012571.shtml
- http://http://www.mobile.xqnqq.com/Article/0277920.shtml
- http://http://www.mobile.xqnqq.com/Article/8181788.shtml
- http://http://www.read.usuhx.com/Article/088386.shtml
- http://http://www.read.usuhx.com/Article/9635.shtml
- http://http://www.read.usuhx.com/Article/3639.shtml
- http://http://www.read.usuhx.com/Article/727966.shtml
- http://http://www.read.usuhx.com/Article/0280.shtml
- http://http://www.mobile.xqnqq.com/Article/304662.shtml
- http://http://www.mobile.xqnqq.com/Article/8288.shtml
- http://http://www.read.usuhx.com/Article/2271.shtml
- http://http://www.mobile.xqnqq.com/Article/12541.shtml
- http://http://www.read.usuhx.com/Article/782418.shtml
- http://http://www.mobile.xqnqq.com/Article/113486.shtml
- http://http://www.mobile.xqnqq.com/Article/6570.shtml
- http://http://www.read.usuhx.com/Article/43341.shtml
- http://http://www.mobile.xqnqq.com/Article/8320283.shtml
- http://http://www.mobile.xqnqq.com/Article/28029.shtml
- http://http://www.read.usuhx.com/Article/9967206.shtml
- http://http://www.read.usuhx.com/Article/660350.shtml
- http://http://www.read.usuhx.com/Article/1306348.shtml
- http://http://www.mobile.xqnqq.com/Article/22121.shtml
- http://http://www.mobile.xqnqq.com/Article/3434676.shtml
- http://http://www.read.usuhx.com/Article/00527.shtml
- http://http://www.read.usuhx.com/Article/06826.shtml
- http://http://www.mobile.xqnqq.com/Article/8497045.shtml
- http://http://www.mobile.xqnqq.com/Article/971182.shtml
- http://http://www.mobile.xqnqq.com/Article/7128.shtml
- http://http://www.mobile.xqnqq.com/Article/2033224.shtml
- http://http://www.mobile.xqnqq.com/Article/33474.shtml
- http://http://www.mobile.xqnqq.com/Article/13162.shtml
- http://http://www.mobile.xqnqq.com/Article/04177.shtml
- http://http://www.mobile.xqnqq.com/Article/575434.shtml
- http://http://www.read.usuhx.com/Article/8838371.shtml
- http://http://www.mobile.xqnqq.com/Article/0190451.shtml
- http://http://www.mobile.xqnqq.com/Article/53718.shtml
- http://http://www.mobile.xqnqq.com/Article/3412771.shtml
- http://http://www.mobile.xqnqq.com/Article/627177.shtml
- http://http://www.read.usuhx.com/Article/883253.shtml
- http://http://www.read.usuhx.com/Article/236338.shtml
- http://http://www.read.usuhx.com/Article/046867.shtml
- http://http://www.mobile.xqnqq.com/Article/3250.shtml
- http://http://www.read.usuhx.com/Article/375799.shtml
- http://http://www.mobile.xqnqq.com/Article/761115.shtml
- http://http://www.read.usuhx.com/Article/1598299.shtml
- http://http://www.mobile.xqnqq.com/Article/6649791.shtml
- http://http://www.mobile.xqnqq.com/Article/34875.shtml
- http://http://www.mobile.xqnqq.com/Article/12925.shtml
- http://http://www.mobile.xqnqq.com/Article/44591.shtml
- http://http://www.mobile.xqnqq.com/Article/15647.shtml
- http://http://www.mobile.xqnqq.com/Article/576571.shtml
- http://http://www.read.usuhx.com/Article/46166.shtml
- http://http://www.read.usuhx.com/Article/01022.shtml
- http://http://www.mobile.xqnqq.com/Article/0654.shtml
- http://http://www.mobile.xqnqq.com/Article/75619.shtml
- http://http://www.mobile.xqnqq.com/Article/219937.shtml
- http://http://www.mobile.xqnqq.com/Article/947084.shtml
- http://http://www.mobile.xqnqq.com/Article/0062.shtml
- http://http://www.read.usuhx.com/Article/128173.shtml
- http://http://www.mobile.xqnqq.com/Article/9168501.shtml
- http://http://www.mobile.xqnqq.com/Article/4177.shtml
- http://http://www.read.usuhx.com/Article/9191252.shtml
- http://http://www.mobile.xqnqq.com/Article/4561.shtml
- http://http://www.mobile.xqnqq.com/Article/0343662.shtml
- http://http://www.read.usuhx.com/Article/20946.shtml
- http://http://www.mobile.xqnqq.com/Article/8870.shtml
- http://http://www.mobile.xqnqq.com/Article/13523.shtml
- http://http://www.mobile.xqnqq.com/Article/4125912.shtml
- http://http://www.mobile.xqnqq.com/Article/7216.shtml
- http://http://www.mobile.xqnqq.com/Article/714537.shtml
- http://http://www.mobile.xqnqq.com/Article/1982.shtml
- http://http://www.read.usuhx.com/Article/134595.shtml
- http://http://www.mobile.xqnqq.com/Article/4266055.shtml
- http://http://www.mobile.xqnqq.com/Article/72052.shtml
- http://http://www.mobile.xqnqq.com/Article/6515748.shtml
- http://http://www.read.usuhx.com/Article/6305544.shtml
- http://http://www.mobile.xqnqq.com/Article/0809.shtml
- http://http://www.mobile.xqnqq.com/Article/2069389.shtml
- http://http://www.read.usuhx.com/Article/6935.shtml
- http://http://www.mobile.xqnqq.com/Article/4033.shtml
- http://http://www.mobile.xqnqq.com/Article/2171420.shtml
- http://http://www.read.usuhx.com/Article/4410.shtml
- http://http://www.mobile.xqnqq.com/Article/6325105.shtml
- http://http://www.read.usuhx.com/Article/998756.shtml
- http://http://www.read.usuhx.com/Article/673821.shtml
- http://http://www.mobile.xqnqq.com/Article/8484.shtml
- http://http://www.read.usuhx.com/Article/0443400.shtml
- http://http://www.read.usuhx.com/Article/575752.shtml
- http://http://www.read.usuhx.com/Article/5215276.shtml
- http://http://www.mobile.xqnqq.com/Article/6013600.shtml
- http://http://www.mobile.xqnqq.com/Article/3100.shtml
- http://http://www.read.usuhx.com/Article/5373.shtml
- http://http://www.read.usuhx.com/Article/9730368.shtml
- http://http://www.mobile.xqnqq.com/Article/2046.shtml
- http://http://www.read.usuhx.com/Article/14120.shtml
- http://http://www.mobile.xqnqq.com/Article/3888605.shtml
- http://http://www.mobile.xqnqq.com/Article/96284.shtml
- http://http://www.mobile.xqnqq.com/Article/930312.shtml
- http://http://www.read.usuhx.com/Article/901066.shtml
- http://http://www.read.usuhx.com/Article/619365.shtml
- http://http://www.mobile.xqnqq.com/Article/659896.shtml
- http://http://www.read.usuhx.com/Article/778558.shtml
- http://http://www.read.usuhx.com/Article/37829.shtml
- http://http://www.read.usuhx.com/Article/531984.shtml
- http://http://www.mobile.xqnqq.com/Article/417675.shtml
- http://http://www.mobile.xqnqq.com/Article/21713.shtml
- http://http://www.mobile.xqnqq.com/Article/993781.shtml
- http://http://www.mobile.xqnqq.com/Article/3323.shtml
- http://http://www.read.usuhx.com/Article/32270.shtml
- http://http://www.mobile.xqnqq.com/Article/4966764.shtml
- http://http://www.mobile.xqnqq.com/Article/0925506.shtml
- http://http://www.mobile.xqnqq.com/Article/3312.shtml
- http://http://www.mobile.xqnqq.com/Article/4378.shtml
- http://http://www.mobile.xqnqq.com/Article/2578.shtml
- http://http://www.mobile.xqnqq.com/Article/459312.shtml
- http://http://www.mobile.xqnqq.com/Article/5023696.shtml
- http://http://www.read.usuhx.com/Article/6355.shtml
- http://http://www.read.usuhx.com/Article/0692384.shtml
- http://http://www.read.usuhx.com/Article/9406129.shtml
- http://http://www.read.usuhx.com/Article/562267.shtml
- http://http://www.mobile.xqnqq.com/Article/7924789.shtml
- http://http://www.mobile.xqnqq.com/Article/738545.shtml
- http://http://www.read.usuhx.com/Article/2534809.shtml
- http://http://www.read.usuhx.com/Article/2448.shtml
- http://http://www.read.usuhx.com/Article/5540.shtml
- http://http://www.mobile.xqnqq.com/Article/13246.shtml
- http://http://www.mobile.xqnqq.com/Article/651060.shtml
- http://http://www.mobile.xqnqq.com/Article/4939056.shtml
- http://http://www.read.usuhx.com/Article/16156.shtml
- http://http://www.mobile.xqnqq.com/Article/0197031.shtml
- http://http://www.mobile.xqnqq.com/Article/649700.shtml
- http://http://www.read.usuhx.com/Article/10170.shtml
- http://http://www.read.usuhx.com/Article/25251.shtml
- http://http://www.read.usuhx.com/Article/53657.shtml
- http://http://www.mobile.xqnqq.com/Article/598219.shtml
- http://http://www.read.usuhx.com/Article/7560.shtml
- http://http://www.read.usuhx.com/Article/21986.shtml
- http://http://www.mobile.xqnqq.com/Article/688049.shtml
- http://http://www.mobile.xqnqq.com/Article/41458.shtml
- http://http://www.mobile.xqnqq.com/Article/557285.shtml
- http://http://www.mobile.xqnqq.com/Article/59778.shtml
- http://http://www.mobile.xqnqq.com/Article/25131.shtml
- http://http://www.read.usuhx.com/Article/3087.shtml
- http://http://www.read.usuhx.com/Article/1170.shtml
- http://http://www.read.usuhx.com/Article/857287.shtml
- http://http://www.read.usuhx.com/Article/352712.shtml
- http://http://www.mobile.xqnqq.com/Article/9231827.shtml
- http://http://www.read.usuhx.com/Article/078408.shtml
- http://http://www.read.usuhx.com/Article/58849.shtml
- http://http://www.mobile.xqnqq.com/Article/56171.shtml
- http://http://www.read.usuhx.com/Article/2351303.shtml
- http://http://www.mobile.xqnqq.com/Article/036653.shtml
- http://http://www.read.usuhx.com/Article/532317.shtml
- http://http://www.read.usuhx.com/Article/7081288.shtml
- http://http://www.mobile.xqnqq.com/Article/1702.shtml
- http://http://www.read.usuhx.com/Article/622565.shtml
- http://http://www.mobile.xqnqq.com/Article/11783.shtml
- http://http://www.mobile.xqnqq.com/Article/05362.shtml
- http://http://www.read.usuhx.com/Article/040488.shtml
- http://http://www.mobile.xqnqq.com/Article/3878.shtml
- http://http://www.mobile.xqnqq.com/Article/786536.shtml
- http://http://www.read.usuhx.com/Article/76375.shtml
- http://http://www.read.usuhx.com/Article/9089053.shtml
- http://http://www.read.usuhx.com/Article/4965.shtml
- http://http://www.mobile.xqnqq.com/Article/66961.shtml
- http://http://www.read.usuhx.com/Article/278055.shtml
- http://http://www.read.usuhx.com/Article/9765.shtml
- http://http://www.read.usuhx.com/Article/2270882.shtml
- http://http://www.read.usuhx.com/Article/71591.shtml
- http://http://www.mobile.xqnqq.com/Article/585854.shtml
- http://http://www.read.usuhx.com/Article/6311987.shtml
- http://http://www.read.usuhx.com/Article/65293.shtml
- http://http://www.read.usuhx.com/Article/77205.shtml
- http://http://www.read.usuhx.com/Article/5270.shtml
- http://http://www.mobile.xqnqq.com/Article/9432725.shtml
- http://http://www.read.usuhx.com/Article/2040364.shtml
- http://http://www.read.usuhx.com/Article/61344.shtml
- http://http://www.read.usuhx.com/Article/4510.shtml
- http://http://www.mobile.xqnqq.com/Article/3974.shtml
- http://http://www.read.usuhx.com/Article/24936.shtml
- http://http://www.mobile.xqnqq.com/Article/0060.shtml
- http://http://www.mobile.xqnqq.com/Article/80070.shtml
- http://http://www.read.usuhx.com/Article/5486920.shtml
- http://http://www.read.usuhx.com/Article/13045.shtml
- http://http://www.mobile.xqnqq.com/Article/1748.shtml
- http://http://www.read.usuhx.com/Article/6536.shtml
- http://http://www.mobile.xqnqq.com/Article/2393.shtml
- http://http://www.read.usuhx.com/Article/26836.shtml
- http://http://www.mobile.xqnqq.com/Article/091230.shtml
- http://http://www.mobile.xqnqq.com/Article/9398.shtml
- http://http://www.read.usuhx.com/Article/17050.shtml
- http://http://www.mobile.xqnqq.com/Article/084696.shtml
- http://http://www.mobile.xqnqq.com/Article/3613741.shtml
- http://http://www.mobile.xqnqq.com/Article/77240.shtml
- http://http://www.read.usuhx.com/Article/6503.shtml
- http://http://www.read.usuhx.com/Article/7582.shtml
- http://http://www.read.usuhx.com/Article/9376410.shtml
- http://http://www.mobile.xqnqq.com/Article/793533.shtml
- http://http://www.mobile.xqnqq.com/Article/7582861.shtml
- http://http://www.read.usuhx.com/Article/4971241.shtml
- http://http://www.mobile.xqnqq.com/Article/22067.shtml
- http://http://www.read.usuhx.com/Article/3246337.shtml
- http://http://www.mobile.xqnqq.com/Article/2183580.shtml
- http://http://www.read.usuhx.com/Article/8529.shtml
- http://http://www.read.usuhx.com/Article/742336.shtml
- http://http://www.read.usuhx.com/Article/5210176.shtml
- http://http://www.mobile.xqnqq.com/Article/26510.shtml
- http://http://www.read.usuhx.com/Article/0671.shtml
- http://http://www.mobile.xqnqq.com/Article/4459.shtml
- http://http://www.read.usuhx.com/Article/66485.shtml
- http://http://www.mobile.xqnqq.com/Article/1857.shtml
- http://http://www.read.usuhx.com/Article/741719.shtml
- http://http://www.mobile.xqnqq.com/Article/7033.shtml
- http://http://www.mobile.xqnqq.com/Article/1292839.shtml
- http://http://www.read.usuhx.com/Article/757287.shtml
- http://http://www.read.usuhx.com/Article/6843551.shtml
- http://http://www.mobile.xqnqq.com/Article/9846.shtml
- http://http://www.mobile.xqnqq.com/Article/7469.shtml
- http://http://www.read.usuhx.com/Article/94930.shtml
- http://http://www.mobile.xqnqq.com/Article/6759860.shtml
- http://http://www.read.usuhx.com/Article/113569.shtml
- http://http://www.read.usuhx.com/Article/50164.shtml
- http://http://www.mobile.xqnqq.com/Article/8413.shtml
- http://http://www.mobile.xqnqq.com/Article/9020546.shtml
- http://http://www.mobile.xqnqq.com/Article/8920923.shtml

## 项目结构

```
weblink-hub/
├── src/
│   ├── core/                     # 核心数据模型与业务逻辑
│   │   ├── Link.ts               # Link 实体类，包含原始 URL 字段与状态
│   │   └── BatchManager.ts       # 批次管理，当前批次 6/80 的计数器与元数据
│   ├── importers/                # 不同格式的导入器实现
│   │   ├── TextImporter.ts       # 纯文本按行导入，每行一个 URL
│   │   └── CsvImporter.ts        # CSV 解析，支持自定义列映射
│   ├── exporters/                # 导出器，负责生成 Markdown 资源列表
│   │   └── MarkdownExporter.ts   # 严格按一行一个 URL 格式输出
│   ├── storage/                  # 持久化层
│   │   ├── Database.ts           # SQLite3 连接与表初始化
│   │   └── Migration.ts          # 批次字段与标签表的迁移脚本
│   ├── server/                   # HTTP 服务层
│   │   ├── routes/               # API 路由定义
│   │   └── middleware/           # 请求日志与错误处理中间件
│   └── cli/                      # 命令行入口
│       └── commands/             # import / export / check 子命令
├── tests/                        # 单元测试与集成测试用例
│   ├── importers.test.ts
│   └── exporters.test.ts
├── docs/                         # 完整文档目录
│   ├── user-guide/
│   └── developer/
├── data/                         # 数据目录
│   ├── imports/                  # 待导入的原始文件存放处
│   └── exports/                  # 导出的 Markdown 文件输出目录
├── config/                       # 环境配置
│   ├── default.yaml              # 默认端口、数据库路径、批次号
│   └── production.yaml           # 生产环境覆盖配置
├── .github/                      # GitHub 工作流
│   └── workflows/                # CI 与 定时健康检查任务
├── package.json
├── tsconfig.json
└── README.md
```

## 贡献指南

1. 查阅 issue 列表或新建 issue 描述您希望修复的问题或新增的功能，等待维护者确认方向。
2. 从 `main` 分支切出新的特性分支，分支名称采用 `feat/` 或 `fix/` 前缀，后接简短英文描述。
3. 编写代码并确保所有现有单元测试通过，新增功能需附带对应的测试用例。
4. 提交前运行 `npm run lint` 和 `npm run format` 统一代码风格。
5. 发起 Pull Request，描述变更内容、测试结果以及对用户文档的影响，至少一位维护者批准后方可合并。

## 常见问题

问：导入链接时，项目是否会修改我提供的原始 URL 字符串？

答：不会。WebLink Hub 的设计原则之一就是绝对保留用户输入的原始 URL 字符串。无论是协议前缀、域名大小写还是路径中的特殊字符，系统都会原样存储。导出时同样直接读取原始字段，不进行任何自动补全或规范化操作。

问：如何对已导入的链接进行标签批量更新？

答：当前版本支持通过 CSV 文件批量更新标签。您需要准备包含 `id` 或 `url` 列以及 `tags` 列的文件，在管理界面选择“批量更新”功能上传。标签字段支持用逗号或分号分隔多个标签。若标签不存在，系统会自动创建。

问：健康检查功能会对每个链接发起 HTTP 请求吗？频率如何控制？

答：是的。健康检查模块会使用 Node.js 的 `fetch` 对每个链接发送 HEAD 或 GET 请求（可配置）。默认频率为每周日凌晨 2:00 执行一次，超时时间设为 5 秒。您可以在 `config/default.yaml` 中调整 `healthCheck.cron` 和 `healthCheck.timeout` 参数。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
