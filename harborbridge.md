# TechLink Archive

TechLink Archive 是一个面向技术研究者、开发者和信息分析人员的外链资源聚合与导航系统。本项目系统性地收录来自多个内容源的高价值技术文章链接，并按照主题域、内容类型和质量等级进行分类索引，旨在解决技术信息分散、优质内容难以追溯、跨源检索效率低下等问题。通过统一的资源清单和结构化的元数据描述，用户可以在本地环境中快速构建自己的技术阅读工作流，避免被商业推荐算法和信息噪音干扰。

本项目定位于轻量级、离线优先的链接管理工具，适合需要长期积累技术阅读素材、维护个人知识库、或在团队内部分享可信技术外链的工程团队和个人开发者。

## 功能概览

- 多源链接收录：支持从多个内容域名批量导入文章链接，保留原始 URL 和来源标记。
- 结构化索引：每条资源包含来源域、文章标识符和主题分类，便于后续检索与过滤。
- 批量导入机制：通过文本文件或标准输入批量添加链接，自动去重并校验 URL 格式。
- 标签化分类体系：内置技术领域标签（如后端、前端、运维、算法、安全），用户可自定义扩展。
- 质量评分标注：支持对链接进行 1-5 星质量评分，便于筛选高价值内容。
- 离线浏览辅助：提供链接清单导出功能，可配合离线阅读工具（如 Pocket、Wallabag）使用。
- Markdown 原生输出：所有资源列表以纯 Markdown 格式呈现，兼容主流文档平台和静态站点生成器。
- 轻量级依赖：仅需 Python 3.8+ 运行环境，无外部数据库依赖，数据以 JSON 和 Markdown 文件存储。

## 应用场景

1. 个人技术阅读队列管理：技术从业者可将每日发现的优质文章链接统一录入 Archive，利用标签和评分机制建立个人阅读优先级，避免在浏览器书签中积压大量未分类链接。

2. 团队技术周报素材收集：技术团队负责人或文档维护者可使用本项目汇总本周内团队关注的外部技术动态，生成结构化的外链周报，供内部评审和知识沉淀。

3. 开源项目文档外链索引：开源项目维护者可在项目 README 或 Wiki 中引用 Archive 生成的资源列表，为社区用户提供经过筛选的参考阅读材料，降低新手学习门槛。

4. 技术自媒体选题参考：技术博主或内容创作者可利用 Archive 的资源分类和趋势标签，快速定位近期热门技术话题，辅助选题策划和素材组织。

5. 离线知识库构建基础：结合自动化脚本，用户可定期拉取 Archive 中的链接列表，配合 wget 或离线阅读工具，构建个人专属的离线技术文库，适用于网络受限环境。

## 快速开始

以下步骤帮助您在本地环境中快速部署并运行 TechLink Archive。

```bash
# 克隆项目仓库至本地
git clone https://github.com/techlink-archive/techlink-archive.git

# 进入项目根目录
cd techlink-archive

# 安装 Python 依赖（推荐使用虚拟环境）
python3 -m venv venv
source venv/bin/activate  # Windows 用户使用 venv\Scripts\activate
pip install -r requirements.txt

# 执行导入脚本，将资源链接写入本地数据库
python scripts/import_links.py --input ./data/raw_links.txt

# 生成 Markdown 资源列表（输出至 ./output/resource_list.md）
python scripts/generate_markdown.py --output ./output/resource_list.md

# 启动本地静态预览服务（可选）
python -m http.server 8000 --directory ./output
```

## 安装要求

| 依赖项 | 必需版本 | 说明 |
|--------|----------|------|
| Python | 3.8 或更高 | 核心脚本运行环境，推荐 3.10+ |
| pip | 20.0 或更高 | Python 包管理工具，用于安装依赖库 |
| click | 8.0.0 或更高 | 命令行接口解析库，用于子命令管理 |
| markdown | 3.3.0 或更高 | 用于将结构化数据渲染为 Markdown 格式输出 |
| pytest | 7.0.0 或更高 | 单元测试框架（仅开发环境需要） |
| black | 22.0.0 或更高 | 代码格式化工具（仅开发环境需要） |
| 操作系统 | Linux / macOS / Windows | 跨平台支持，建议使用 Unix-like 系统以获得最佳性能 |
| 磁盘空间 | 至少 50 MB | 存储资源索引文件和输出文档，实际需求随链接数量线性增长 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 用户手册 | docs/user-guide.md | 如何导入链接、如何添加标签、如何导出不同格式的资源列表 |
| 配置说明 | docs/configuration.md | 如何修改分类规则、调整质量评分标准、自定义输出模板 |
| 开发指南 | docs/development.md | 如何扩展新的内容源解析器、如何贡献代码、如何运行测试套件 |
| 设计文档 | docs/design.md | 项目整体架构设计、数据模型定义、存储方案选型及权衡说明 |

## 资源列表

- http://http://www.mobile.xqnqq.com/Article/2421764.shtml
- http://http://www.read.usuhx.com/Article/4602.shtml
- http://http://www.read.usuhx.com/Article/5738460.shtml
- http://http://www.mobile.xqnqq.com/Article/4057717.shtml
- http://http://www.mobile.xqnqq.com/Article/1641.shtml
- http://http://www.read.usuhx.com/Article/96104.shtml
- http://http://www.mobile.xqnqq.com/Article/59235.shtml
- http://http://www.mobile.xqnqq.com/Article/769051.shtml
- http://http://www.mobile.xqnqq.com/Article/9937.shtml
- http://http://www.read.usuhx.com/Article/201815.shtml
- http://http://www.read.usuhx.com/Article/5154782.shtml
- http://http://www.mobile.xqnqq.com/Article/18723.shtml
- http://http://www.read.usuhx.com/Article/3413.shtml
- http://http://www.mobile.xqnqq.com/Article/908396.shtml
- http://http://www.mobile.xqnqq.com/Article/4305.shtml
- http://http://www.mobile.xqnqq.com/Article/809415.shtml
- http://http://www.read.usuhx.com/Article/48837.shtml
- http://http://www.read.usuhx.com/Article/6756.shtml
- http://http://www.mobile.xqnqq.com/Article/8036335.shtml
- http://http://www.read.usuhx.com/Article/5030830.shtml
- http://http://www.mobile.xqnqq.com/Article/8290.shtml
- http://http://www.mobile.xqnqq.com/Article/285994.shtml
- http://http://www.read.usuhx.com/Article/285667.shtml
- http://http://www.read.usuhx.com/Article/3584.shtml
- http://http://www.read.usuhx.com/Article/880712.shtml
- http://http://www.read.usuhx.com/Article/328045.shtml
- http://http://www.mobile.xqnqq.com/Article/279354.shtml
- http://http://www.mobile.xqnqq.com/Article/8893340.shtml
- http://http://www.mobile.xqnqq.com/Article/044460.shtml
- http://http://www.mobile.xqnqq.com/Article/26857.shtml
- http://http://www.read.usuhx.com/Article/1425178.shtml
- http://http://www.read.usuhx.com/Article/6179.shtml
- http://http://www.mobile.xqnqq.com/Article/0618584.shtml
- http://http://www.read.usuhx.com/Article/24862.shtml
- http://http://www.read.usuhx.com/Article/464862.shtml
- http://http://www.mobile.xqnqq.com/Article/36128.shtml
- http://http://www.mobile.xqnqq.com/Article/49277.shtml
- http://http://www.mobile.xqnqq.com/Article/044993.shtml
- http://http://www.mobile.xqnqq.com/Article/6988039.shtml
- http://http://www.read.usuhx.com/Article/4103.shtml
- http://http://www.read.usuhx.com/Article/2343958.shtml
- http://http://www.mobile.xqnqq.com/Article/371224.shtml
- http://http://www.mobile.xqnqq.com/Article/2118380.shtml
- http://http://www.mobile.xqnqq.com/Article/6239.shtml
- http://http://www.mobile.xqnqq.com/Article/644309.shtml
- http://http://www.read.usuhx.com/Article/10348.shtml
- http://http://www.read.usuhx.com/Article/057328.shtml
- http://http://www.read.usuhx.com/Article/459976.shtml
- http://http://www.mobile.xqnqq.com/Article/540782.shtml
- http://http://www.read.usuhx.com/Article/64960.shtml
- http://http://www.read.usuhx.com/Article/4082.shtml
- http://http://www.mobile.xqnqq.com/Article/32390.shtml
- http://http://www.mobile.xqnqq.com/Article/1141422.shtml
- http://http://www.mobile.xqnqq.com/Article/444229.shtml
- http://http://www.mobile.xqnqq.com/Article/828424.shtml
- http://http://www.mobile.xqnqq.com/Article/39298.shtml
- http://http://www.mobile.xqnqq.com/Article/2518.shtml
- http://http://www.mobile.xqnqq.com/Article/570669.shtml
- http://http://www.mobile.xqnqq.com/Article/5563.shtml
- http://http://www.mobile.xqnqq.com/Article/9474.shtml
- http://http://www.read.usuhx.com/Article/09039.shtml
- http://http://www.mobile.xqnqq.com/Article/4171165.shtml
- http://http://www.mobile.xqnqq.com/Article/5341120.shtml
- http://http://www.mobile.xqnqq.com/Article/1315.shtml
- http://http://www.read.usuhx.com/Article/6692952.shtml
- http://http://www.read.usuhx.com/Article/06642.shtml
- http://http://www.read.usuhx.com/Article/457435.shtml
- http://http://www.mobile.xqnqq.com/Article/5474513.shtml
- http://http://www.read.usuhx.com/Article/6092711.shtml
- http://http://www.read.usuhx.com/Article/314785.shtml
- http://http://www.read.usuhx.com/Article/2211772.shtml
- http://http://www.mobile.xqnqq.com/Article/688444.shtml
- http://http://www.read.usuhx.com/Article/330677.shtml
- http://http://www.mobile.xqnqq.com/Article/21982.shtml
- http://http://www.mobile.xqnqq.com/Article/04255.shtml
- http://http://www.read.usuhx.com/Article/82430.shtml
- http://http://www.read.usuhx.com/Article/04434.shtml
- http://http://www.read.usuhx.com/Article/064322.shtml
- http://http://www.read.usuhx.com/Article/5902280.shtml
- http://http://www.mobile.xqnqq.com/Article/3038901.shtml
- http://http://www.mobile.xqnqq.com/Article/0550.shtml
- http://http://www.read.usuhx.com/Article/8996.shtml
- http://http://www.read.usuhx.com/Article/59971.shtml
- http://http://www.mobile.xqnqq.com/Article/5004883.shtml
- http://http://www.mobile.xqnqq.com/Article/3674.shtml
- http://http://www.read.usuhx.com/Article/395923.shtml
- http://http://www.read.usuhx.com/Article/148341.shtml
- http://http://www.mobile.xqnqq.com/Article/7223.shtml
- http://http://www.read.usuhx.com/Article/71384.shtml
- http://http://www.mobile.xqnqq.com/Article/79072.shtml
- http://http://www.mobile.xqnqq.com/Article/5523125.shtml
- http://http://www.read.usuhx.com/Article/874082.shtml
- http://http://www.read.usuhx.com/Article/919929.shtml
- http://http://www.mobile.xqnqq.com/Article/1700983.shtml
- http://http://www.mobile.xqnqq.com/Article/3524.shtml
- http://http://www.read.usuhx.com/Article/993812.shtml
- http://http://www.mobile.xqnqq.com/Article/02663.shtml
- http://http://www.read.usuhx.com/Article/42893.shtml
- http://http://www.mobile.xqnqq.com/Article/03756.shtml
- http://http://www.mobile.xqnqq.com/Article/49959.shtml
- http://http://www.mobile.xqnqq.com/Article/15540.shtml
- http://http://www.read.usuhx.com/Article/40849.shtml
- http://http://www.mobile.xqnqq.com/Article/5343.shtml
- http://http://www.read.usuhx.com/Article/770597.shtml
- http://http://www.read.usuhx.com/Article/28654.shtml
- http://http://www.read.usuhx.com/Article/60109.shtml
- http://http://www.read.usuhx.com/Article/531877.shtml
- http://http://www.read.usuhx.com/Article/4862441.shtml
- http://http://www.read.usuhx.com/Article/254196.shtml
- http://http://www.read.usuhx.com/Article/0724114.shtml
- http://http://www.read.usuhx.com/Article/30903.shtml
- http://http://www.mobile.xqnqq.com/Article/84017.shtml
- http://http://www.mobile.xqnqq.com/Article/7775.shtml
- http://http://www.read.usuhx.com/Article/093581.shtml
- http://http://www.read.usuhx.com/Article/7316090.shtml
- http://http://www.read.usuhx.com/Article/6644935.shtml
- http://http://www.mobile.xqnqq.com/Article/99565.shtml
- http://http://www.mobile.xqnqq.com/Article/2635.shtml
- http://http://www.mobile.xqnqq.com/Article/05525.shtml
- http://http://www.mobile.xqnqq.com/Article/285099.shtml
- http://http://www.mobile.xqnqq.com/Article/89815.shtml
- http://http://www.read.usuhx.com/Article/453030.shtml
- http://http://www.mobile.xqnqq.com/Article/41333.shtml
- http://http://www.mobile.xqnqq.com/Article/2631645.shtml
- http://http://www.read.usuhx.com/Article/8078371.shtml
- http://http://www.read.usuhx.com/Article/0239303.shtml
- http://http://www.read.usuhx.com/Article/0207554.shtml
- http://http://www.mobile.xqnqq.com/Article/8811481.shtml
- http://http://www.mobile.xqnqq.com/Article/532351.shtml
- http://http://www.read.usuhx.com/Article/55481.shtml
- http://http://www.read.usuhx.com/Article/87444.shtml
- http://http://www.read.usuhx.com/Article/145159.shtml
- http://http://www.mobile.xqnqq.com/Article/6410416.shtml
- http://http://www.read.usuhx.com/Article/5415.shtml
- http://http://www.read.usuhx.com/Article/58747.shtml
- http://http://www.mobile.xqnqq.com/Article/4883.shtml
- http://http://www.read.usuhx.com/Article/341407.shtml
- http://http://www.mobile.xqnqq.com/Article/6354.shtml
- http://http://www.read.usuhx.com/Article/32167.shtml
- http://http://www.read.usuhx.com/Article/436320.shtml
- http://http://www.mobile.xqnqq.com/Article/0636.shtml
- http://http://www.read.usuhx.com/Article/4851369.shtml
- http://http://www.read.usuhx.com/Article/1831.shtml
- http://http://www.mobile.xqnqq.com/Article/46690.shtml
- http://http://www.read.usuhx.com/Article/219173.shtml
- http://http://www.mobile.xqnqq.com/Article/84330.shtml
- http://http://www.read.usuhx.com/Article/3010.shtml
- http://http://www.read.usuhx.com/Article/7583.shtml
- http://http://www.mobile.xqnqq.com/Article/87464.shtml
- http://http://www.mobile.xqnqq.com/Article/0005.shtml
- http://http://www.mobile.xqnqq.com/Article/236826.shtml
- http://http://www.mobile.xqnqq.com/Article/2783.shtml
- http://http://www.read.usuhx.com/Article/3057.shtml
- http://http://www.read.usuhx.com/Article/0397394.shtml
- http://http://www.mobile.xqnqq.com/Article/16617.shtml
- http://http://www.mobile.xqnqq.com/Article/842379.shtml
- http://http://www.read.usuhx.com/Article/54564.shtml
- http://http://www.read.usuhx.com/Article/73203.shtml
- http://http://www.read.usuhx.com/Article/672801.shtml
- http://http://www.read.usuhx.com/Article/51802.shtml
- http://http://www.read.usuhx.com/Article/6920909.shtml
- http://http://www.mobile.xqnqq.com/Article/7508319.shtml
- http://http://www.read.usuhx.com/Article/29092.shtml
- http://http://www.mobile.xqnqq.com/Article/5970372.shtml
- http://http://www.mobile.xqnqq.com/Article/7400.shtml
- http://http://www.read.usuhx.com/Article/72907.shtml
- http://http://www.read.usuhx.com/Article/9484589.shtml
- http://http://www.read.usuhx.com/Article/7342.shtml
- http://http://www.read.usuhx.com/Article/50488.shtml
- http://http://www.read.usuhx.com/Article/891271.shtml
- http://http://www.read.usuhx.com/Article/55332.shtml
- http://http://www.read.usuhx.com/Article/49928.shtml
- http://http://www.mobile.xqnqq.com/Article/81097.shtml
- http://http://www.read.usuhx.com/Article/891897.shtml
- http://http://www.mobile.xqnqq.com/Article/92899.shtml
- http://http://www.mobile.xqnqq.com/Article/3432.shtml
- http://http://www.mobile.xqnqq.com/Article/4694047.shtml
- http://http://www.mobile.xqnqq.com/Article/6369878.shtml
- http://http://www.read.usuhx.com/Article/73690.shtml
- http://http://www.mobile.xqnqq.com/Article/601086.shtml
- http://http://www.mobile.xqnqq.com/Article/0157.shtml
- http://http://www.read.usuhx.com/Article/199235.shtml
- http://http://www.mobile.xqnqq.com/Article/1755.shtml
- http://http://www.mobile.xqnqq.com/Article/615849.shtml
- http://http://www.read.usuhx.com/Article/424114.shtml
- http://http://www.read.usuhx.com/Article/013461.shtml
- http://http://www.mobile.xqnqq.com/Article/118467.shtml
- http://http://www.mobile.xqnqq.com/Article/2318.shtml
- http://http://www.mobile.xqnqq.com/Article/5257211.shtml
- http://http://www.read.usuhx.com/Article/5269.shtml
- http://http://www.mobile.xqnqq.com/Article/56585.shtml
- http://http://www.read.usuhx.com/Article/8358819.shtml
- http://http://www.read.usuhx.com/Article/0784.shtml
- http://http://www.mobile.xqnqq.com/Article/815616.shtml
- http://http://www.read.usuhx.com/Article/724551.shtml
- http://http://www.read.usuhx.com/Article/37353.shtml
- http://http://www.mobile.xqnqq.com/Article/8480.shtml
- http://http://www.mobile.xqnqq.com/Article/66237.shtml
- http://http://www.read.usuhx.com/Article/47842.shtml
- http://http://www.read.usuhx.com/Article/45861.shtml
- http://http://www.mobile.xqnqq.com/Article/808672.shtml
- http://http://www.read.usuhx.com/Article/302280.shtml
- http://http://www.mobile.xqnqq.com/Article/057156.shtml
- http://http://www.read.usuhx.com/Article/8560.shtml
- http://http://www.mobile.xqnqq.com/Article/834922.shtml
- http://http://www.mobile.xqnqq.com/Article/7148567.shtml
- http://http://www.mobile.xqnqq.com/Article/75973.shtml
- http://http://www.mobile.xqnqq.com/Article/15644.shtml
- http://http://www.read.usuhx.com/Article/89457.shtml
- http://http://www.mobile.xqnqq.com/Article/80220.shtml
- http://http://www.mobile.xqnqq.com/Article/95473.shtml
- http://http://www.read.usuhx.com/Article/5039266.shtml
- http://http://www.mobile.xqnqq.com/Article/55542.shtml
- http://http://www.read.usuhx.com/Article/0633629.shtml
- http://http://www.mobile.xqnqq.com/Article/214283.shtml
- http://http://www.mobile.xqnqq.com/Article/63221.shtml
- http://http://www.mobile.xqnqq.com/Article/7109117.shtml
- http://http://www.mobile.xqnqq.com/Article/026904.shtml
- http://http://www.mobile.xqnqq.com/Article/029715.shtml
- http://http://www.mobile.xqnqq.com/Article/831286.shtml
- http://http://www.mobile.xqnqq.com/Article/489427.shtml
- http://http://www.mobile.xqnqq.com/Article/2732.shtml
- http://http://www.mobile.xqnqq.com/Article/7810.shtml
- http://http://www.mobile.xqnqq.com/Article/45290.shtml
- http://http://www.read.usuhx.com/Article/57600.shtml
- http://http://www.read.usuhx.com/Article/4735.shtml
- http://http://www.read.usuhx.com/Article/9075930.shtml
- http://http://www.mobile.xqnqq.com/Article/522549.shtml
- http://http://www.mobile.xqnqq.com/Article/6124.shtml
- http://http://www.mobile.xqnqq.com/Article/279417.shtml
- http://http://www.read.usuhx.com/Article/847295.shtml
- http://http://www.mobile.xqnqq.com/Article/3226.shtml
- http://http://www.mobile.xqnqq.com/Article/870482.shtml
- http://http://www.mobile.xqnqq.com/Article/750645.shtml
- http://http://www.read.usuhx.com/Article/0130.shtml
- http://http://www.mobile.xqnqq.com/Article/90272.shtml
- http://http://www.read.usuhx.com/Article/10999.shtml
- http://http://www.mobile.xqnqq.com/Article/160264.shtml
- http://http://www.mobile.xqnqq.com/Article/9617.shtml
- http://http://www.mobile.xqnqq.com/Article/037811.shtml
- http://http://www.read.usuhx.com/Article/75500.shtml
- http://http://www.mobile.xqnqq.com/Article/387937.shtml
- http://http://www.mobile.xqnqq.com/Article/9610380.shtml
- http://http://www.mobile.xqnqq.com/Article/3838.shtml
- http://http://www.read.usuhx.com/Article/3646355.shtml
- http://http://www.mobile.xqnqq.com/Article/5645439.shtml
- http://http://www.mobile.xqnqq.com/Article/380088.shtml
- http://http://www.read.usuhx.com/Article/443774.shtml
- http://http://www.mobile.xqnqq.com/Article/6348840.shtml
- http://http://www.mobile.xqnqq.com/Article/6751.shtml

## 项目结构

```
techlink-archive/
├── data/                                   # 数据存储目录，存放所有源链接和元数据
│   ├── raw_links.txt                       # 原始链接导入文件，每行一个 URL
│   ├── indexed_links.json                  # 去重并标准化后的链接索引，JSON 格式
│   └── tags.json                           # 标签定义及与链接的映射关系
├── scripts/                                # 核心脚本目录，包含所有可执行程序
│   ├── import_links.py                     # 链接导入脚本，支持去重和格式校验
│   ├── generate_markdown.py                # Markdown 输出生成器，用于导出资源列表
│   └── tag_manager.py                      # 标签管理工具，支持增删改查操作
├── docs/                                   # 项目文档目录，包含用户手册和开发指南
│   ├── user-guide.md                       # 用户手册，详细说明安装与日常使用流程
│   ├── development.md                      # 开发指南，涵盖贡献规范和测试流程
│   └── design.md                           # 设计文档，描述架构选型和数据模型
├── tests/                                  # 单元测试目录，用于保证核心功能正确性
│   ├── test_import.py                      # 导入功能测试用例
│   ├── test_generate.py                    # 生成功能测试用例
│   └── test_tags.py                        # 标签管理测试用例
├── output/                                 # 输出目录，存放生成的 Markdown 文档和报告
│   ├── resource_list.md                    # 完整的资源列表输出文件
│   └── stats_report.md                     # 统计报告，包含链接总数和来源分布
├── config/                                 # 配置文件目录，存放用户自定义设置
│   ├── settings.yaml                       # 主配置文件，定义分类规则和输出格式
│   └── categories.yaml                     # 分类映射表，用于自动标注主题域
├── requirements.txt                        # Python 依赖列表，用于快速安装所需库
├── README.md                               # 项目说明文档，即当前文件
└── LICENSE                                 # MIT 许可证文件
```

## 贡献指南

1. 在 GitHub 上 Fork 本仓库，并在本地克隆您的 Fork 版本。请确保使用最新的 main 分支作为基础，避免在旧版本上引入冲突。

2. 新增或修改功能前，请先在 issues 列表中查找是否已有相关讨论。若无对应议题，请新建一个 issue 描述您要解决的问题或拟新增的功能，等待维护者确认后再开始编码。

3. 所有代码变更需在本地通过完整的测试套件（pytest）并保持代码格式符合 black 规范。提交前请运行 `black .` 和 `pytest tests/` 确保无格式警告和测试失败。

4. 提交 Pull Request 时请附上清晰的变更说明，包括修改目的、实现方式以及测试覆盖情况。若为新增功能，请同步更新 docs/ 目录下的对应文档。

5. 对于资源链接的增删改请求，请同时更新 data/raw_links.txt 文件并在 PR 中说明来源和筛选依据，以便维护者审核链接质量和合规性。

## 常见问题

Q: 导入链接时提示 URL 格式无效，但链接在浏览器中可以正常打开，是什么原因？

A: 导入脚本默认执行严格的协议和域名校验，要求每条链接必须包含明确的协议头（http:// 或 https://）。如果您的链接包含重复协议头（如 http://http://）或缺少协议头，脚本会拒绝导入。建议使用脚本提供的 --fix 参数尝试自动修复常见格式错误，或手动编辑 raw_links.txt 文件修正链接格式后再执行导入。

Q: 如何更新已导入链接的标签或评分信息？

A: 您可以直接编辑 data/indexed_links.json 文件，找到对应链接的条目，修改 tags 或 rating 字段的值。修改完成后，重新运行 generate_markdown.py 脚本即可生成更新后的资源列表。为避免手动编辑导致的 JSON 格式错误，建议使用 tag_manager.py 命令行工具进行标签操作，例如 `python scripts/tag_manager.py --add --url "http://example.com" --tag "backend"`。

Q: 生成的 resource_list.md 文件包含所有链接，但我想只导出某个标签下的链接，应该如何操作？

A: 您可以在运行 generate_markdown.py 时指定 --tag 参数，例如 `python scripts/generate_markdown.py --tag "backend" --output ./output/backend_list.md`。该命令将仅输出包含指定标签的链接。如果不指定标签，则默认导出全部链接。该功能同样支持多个标签的与或逻辑组合，详细用法请参考 docs/user-guide.md 中的高级过滤章节。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
