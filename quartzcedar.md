# Link Atlas

Link Atlas 是一个面向技术研究者、内容聚合者与信息归档从业者的开源外链资源归集与健康度监测系统。该项目不生产内容，而是提供一套标准化的外链资产管理框架，帮助用户将分散于各类站点、批次混乱、格式不统一的原始 URL 整理为可检索、可审计、可版本化的结构化数据集。Link Atlas 特别适用于需要长期维护大规模外链清单的文档团队、知识库运营者以及合规性审查人员，通过统一的项目模板与脚本工具，降低人工整理 URL 的出错率，提升多批次资源的管理效率。

## 功能概览

批量 URL 导入与去重 提供基于哈希的 URL 指纹去重机制，支持百万级链接的快速归并，自动识别协议变体与路径冗余。

结构化字段提取 自动解析 URL 中的域名、路径层级、文件扩展名及查询参数，生成可过滤的元数据表，便于后续分类与筛选。

健康状态探测 集成异步 HTTP 请求模块，支持对每个 URL 执行可达性检查、状态码记录与响应时间统计，输出健康度报表。

标签与分组管理 允许用户为每个链接添加自定义标签（如“技术文档”“视频源”“镜像站”），并基于标签或来源域名创建动态分组。

批次版本控制 内置批次管理功能，支持按导入时间、批次编号或来源文件对 URL 进行版本标记，便于回溯与增量更新。

导出格式适配 支持将整理后的链接列表导出为纯文本、CSV 表格或 JSON 结构化数据，兼容主流静态站点生成器与数据库导入工具。

配置化忽略规则 支持通过正则表达式配置忽略列表，自动过滤广告链接、临时会话参数或特定路径前缀，保持核心数据干净。

## 应用场景

文档站点外部链接审计 技术文档团队可使用 Link Atlas 定期扫描文档中嵌入的所有外链，生成断链报告，防止用户点击时遇到 404 页面，同时统计各域名下的链接分布情况，为迁移或替换决策提供数据依据。

学术研究参考文献清洗 研究人员在收集网络文献或数据源时，常面临数百个不同格式的 URL 记录。Link Atlas 可将这些 URL 标准化，提取主域名与路径结构，并按学科分类标签导出为引用清单，减少手工整理耗时。

企业合规性外链备案 法务或合规部门需要归档企业对外发布的所有引用链接。Link Atlas 的批次版本控制功能可记录每次更新时的链接集合，配合健康状态探测，确保对外公示的链接始终有效且内容合规。

开源项目资源镜像站维护 开源社区维护人员可将官方源、镜像源、备份地址等统一纳入 Link Atlas 管理，通过分组标签区分不同地域或服务商的资源，并在主站宕机时快速切换到备用链接。

## 快速开始

以下命令演示了 Link Atlas 的完整初始化流程，包括从仓库克隆、安装依赖以及运行基础整理任务。

```bash
# 克隆项目仓库
git clone https://github.com/link-atlas/link-atlas.git

# 进入项目目录
cd link-atlas

# 安装 Python 依赖（要求 Python 3.9 及以上）
pip install -r requirements.txt

# 运行示例整理任务（默认读取 data/raw/urls.txt，输出至 data/processed/）
python atlas.py --input data/raw/urls.txt --output data/processed/cleaned_urls.csv
```

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 或更高 | 核心运行环境，用于执行 URL 解析、去重与探测逻辑 |
| requests | 2.28 或更高 | 发送 HTTP 请求，用于链接健康状态探测 |
| pandas | 1.5 或更高 | 处理结构化数据表格，支持 CSV 与 JSON 读写 |
| pyyaml | 6.0 或更高 | 解析项目配置文件 config.yaml，管理忽略规则与标签映射 |
| pytest | 7.0 或更高 | 单元测试框架，用于验证 URL 解析与去重函数的正确性 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | docs/user_guide.md | 如何导入 URL 清单、如何设置忽略规则、如何导出不同格式的数据 |
| 配置参考 | docs/config_reference.md | config.yaml 中每个字段的含义、默认值及其对处理流程的影响 |
| API 文档 | docs/api_reference.md | 各核心模块（parser、deduper、checker）的函数签名与调用示例 |
| 设计概述 | docs/design_overview.md | 项目整体架构、数据流向、扩展点设计及性能优化策略 |

## 资源列表

- http://http://map.mobile.xqnqq.com/Article/027852.shtml
- http://http://map.mobile.xqnqq.com/Article/8147705.shtml
- http://http://map.mobile.xqnqq.com/Article/97281.shtml
- http://http://map.mobile.xqnqq.com/Article/6513866.shtml
- http://http://map.read.usuhx.com/Article/028541.shtml
- http://http://map.mobile.xqnqq.com/Article/420975.shtml
- http://http://map.mobile.xqnqq.com/Article/518656.shtml
- http://http://map.mobile.xqnqq.com/Article/5903.shtml
- http://http://map.mobile.xqnqq.com/Article/0487208.shtml
- http://http://map.mobile.xqnqq.com/Article/2756252.shtml
- http://http://map.mobile.xqnqq.com/Article/0292.shtml
- http://http://map.read.usuhx.com/Article/1578319.shtml
- http://http://map.mobile.xqnqq.com/Article/7693942.shtml
- http://http://map.read.usuhx.com/Article/5546.shtml
- http://http://map.mobile.xqnqq.com/Article/956817.shtml
- http://http://map.mobile.xqnqq.com/Article/949706.shtml
- http://http://map.mobile.xqnqq.com/Article/163883.shtml
- http://http://map.read.usuhx.com/Article/28089.shtml
- http://http://map.read.usuhx.com/Article/271340.shtml
- http://http://map.mobile.xqnqq.com/Article/383203.shtml
- http://http://map.mobile.xqnqq.com/Article/641162.shtml
- http://http://map.mobile.xqnqq.com/Article/4789200.shtml
- http://http://map.read.usuhx.com/Article/8140836.shtml
- http://http://map.mobile.xqnqq.com/Article/295608.shtml
- http://http://map.read.usuhx.com/Article/9192102.shtml
- http://http://map.read.usuhx.com/Article/1572903.shtml
- http://http://map.mobile.xqnqq.com/Article/9997107.shtml
- http://http://map.read.usuhx.com/Article/9755.shtml
- http://http://map.read.usuhx.com/Article/6875414.shtml
- http://http://map.mobile.xqnqq.com/Article/690590.shtml
- http://http://map.mobile.xqnqq.com/Article/08072.shtml
- http://http://map.read.usuhx.com/Article/37789.shtml
- http://http://map.mobile.xqnqq.com/Article/121593.shtml
- http://http://map.mobile.xqnqq.com/Article/49444.shtml
- http://http://map.read.usuhx.com/Article/7354.shtml
- http://http://map.mobile.xqnqq.com/Article/640418.shtml
- http://http://map.mobile.xqnqq.com/Article/69900.shtml
- http://http://map.mobile.xqnqq.com/Article/2727.shtml
- http://http://map.mobile.xqnqq.com/Article/4258743.shtml
- http://http://map.read.usuhx.com/Article/29407.shtml
- http://http://map.mobile.xqnqq.com/Article/34902.shtml
- http://http://map.read.usuhx.com/Article/554309.shtml
- http://http://map.read.usuhx.com/Article/9127554.shtml
- http://http://map.mobile.xqnqq.com/Article/824535.shtml
- http://http://map.mobile.xqnqq.com/Article/89571.shtml
- http://http://map.read.usuhx.com/Article/52165.shtml
- http://http://map.read.usuhx.com/Article/35343.shtml
- http://http://map.read.usuhx.com/Article/0434851.shtml
- http://http://map.mobile.xqnqq.com/Article/742038.shtml
- http://http://map.mobile.xqnqq.com/Article/34643.shtml
- http://http://map.read.usuhx.com/Article/135323.shtml
- http://http://map.mobile.xqnqq.com/Article/8911884.shtml
- http://http://map.mobile.xqnqq.com/Article/5708264.shtml
- http://http://map.mobile.xqnqq.com/Article/31531.shtml
- http://http://map.mobile.xqnqq.com/Article/9645481.shtml
- http://http://map.read.usuhx.com/Article/0547791.shtml
- http://http://map.read.usuhx.com/Article/7074799.shtml
- http://http://map.read.usuhx.com/Article/69941.shtml
- http://http://map.read.usuhx.com/Article/140427.shtml
- http://http://map.mobile.xqnqq.com/Article/5974.shtml
- http://http://map.mobile.xqnqq.com/Article/3643.shtml
- http://http://map.mobile.xqnqq.com/Article/5434.shtml
- http://http://map.read.usuhx.com/Article/3921232.shtml
- http://http://map.mobile.xqnqq.com/Article/50891.shtml
- http://http://map.read.usuhx.com/Article/44639.shtml
- http://http://map.mobile.xqnqq.com/Article/8451834.shtml
- http://http://map.read.usuhx.com/Article/189578.shtml
- http://http://map.mobile.xqnqq.com/Article/4444.shtml
- http://http://map.read.usuhx.com/Article/3038.shtml
- http://http://map.mobile.xqnqq.com/Article/090023.shtml
- http://http://map.read.usuhx.com/Article/3996.shtml
- http://http://map.read.usuhx.com/Article/5673.shtml
- http://http://map.read.usuhx.com/Article/100010.shtml
- http://http://map.mobile.xqnqq.com/Article/29867.shtml
- http://http://map.read.usuhx.com/Article/075784.shtml
- http://http://map.mobile.xqnqq.com/Article/90850.shtml
- http://http://map.mobile.xqnqq.com/Article/240486.shtml
- http://http://map.mobile.xqnqq.com/Article/77406.shtml
- http://http://map.read.usuhx.com/Article/309816.shtml
- http://http://map.read.usuhx.com/Article/1763629.shtml
- http://http://map.mobile.xqnqq.com/Article/4438.shtml
- http://http://map.mobile.xqnqq.com/Article/159657.shtml
- http://http://map.mobile.xqnqq.com/Article/6629663.shtml
- http://http://map.mobile.xqnqq.com/Article/508064.shtml
- http://http://map.mobile.xqnqq.com/Article/48140.shtml
- http://http://map.read.usuhx.com/Article/170311.shtml
- http://http://map.read.usuhx.com/Article/8750.shtml
- http://http://map.mobile.xqnqq.com/Article/3973.shtml
- http://http://map.mobile.xqnqq.com/Article/835066.shtml
- http://http://map.read.usuhx.com/Article/067255.shtml
- http://http://map.mobile.xqnqq.com/Article/45608.shtml
- http://http://map.read.usuhx.com/Article/2180012.shtml
- http://http://map.read.usuhx.com/Article/18456.shtml
- http://http://map.read.usuhx.com/Article/5420366.shtml
- http://http://map.read.usuhx.com/Article/0046.shtml
- http://http://map.mobile.xqnqq.com/Article/776415.shtml
- http://http://map.read.usuhx.com/Article/082365.shtml
- http://http://map.mobile.xqnqq.com/Article/80591.shtml
- http://http://map.mobile.xqnqq.com/Article/148297.shtml
- http://http://map.mobile.xqnqq.com/Article/1933388.shtml
- http://http://map.read.usuhx.com/Article/37287.shtml
- http://http://map.read.usuhx.com/Article/96195.shtml
- http://http://map.mobile.xqnqq.com/Article/69891.shtml
- http://http://map.mobile.xqnqq.com/Article/983591.shtml
- http://http://map.mobile.xqnqq.com/Article/3523039.shtml
- http://http://map.read.usuhx.com/Article/005978.shtml
- http://http://map.read.usuhx.com/Article/92971.shtml
- http://http://map.read.usuhx.com/Article/49276.shtml
- http://http://map.mobile.xqnqq.com/Article/937807.shtml
- http://http://map.mobile.xqnqq.com/Article/42741.shtml
- http://http://map.mobile.xqnqq.com/Article/4223173.shtml
- http://http://map.read.usuhx.com/Article/373665.shtml
- http://http://map.mobile.xqnqq.com/Article/1877.shtml
- http://http://map.read.usuhx.com/Article/6332496.shtml
- http://http://map.read.usuhx.com/Article/2786093.shtml
- http://http://map.read.usuhx.com/Article/2312.shtml
- http://http://map.read.usuhx.com/Article/789919.shtml
- http://http://map.read.usuhx.com/Article/2741.shtml
- http://http://map.mobile.xqnqq.com/Article/9131341.shtml
- http://http://map.read.usuhx.com/Article/7671609.shtml
- http://http://map.mobile.xqnqq.com/Article/5897.shtml
- http://http://map.mobile.xqnqq.com/Article/88848.shtml
- http://http://map.read.usuhx.com/Article/078789.shtml
- http://http://map.mobile.xqnqq.com/Article/6773352.shtml
- http://http://map.mobile.xqnqq.com/Article/4351910.shtml
- http://http://map.read.usuhx.com/Article/2125.shtml
- http://http://map.read.usuhx.com/Article/2435.shtml
- http://http://map.read.usuhx.com/Article/612465.shtml
- http://http://map.read.usuhx.com/Article/0732897.shtml
- http://http://map.read.usuhx.com/Article/1429.shtml
- http://http://map.read.usuhx.com/Article/57982.shtml
- http://http://map.read.usuhx.com/Article/26883.shtml
- http://http://map.read.usuhx.com/Article/284440.shtml
- http://http://map.read.usuhx.com/Article/292962.shtml
- http://http://map.mobile.xqnqq.com/Article/59302.shtml
- http://http://map.read.usuhx.com/Article/80475.shtml
- http://http://map.mobile.xqnqq.com/Article/7559667.shtml
- http://http://map.mobile.xqnqq.com/Article/03997.shtml
- http://http://map.mobile.xqnqq.com/Article/359639.shtml
- http://http://map.read.usuhx.com/Article/3200271.shtml
- http://http://map.read.usuhx.com/Article/41085.shtml
- http://http://map.read.usuhx.com/Article/812531.shtml
- http://http://map.mobile.xqnqq.com/Article/4983035.shtml
- http://http://map.read.usuhx.com/Article/43528.shtml
- http://http://map.read.usuhx.com/Article/68248.shtml
- http://http://map.mobile.xqnqq.com/Article/766848.shtml
- http://http://map.mobile.xqnqq.com/Article/3012.shtml
- http://http://map.mobile.xqnqq.com/Article/8722675.shtml
- http://http://map.mobile.xqnqq.com/Article/04254.shtml
- http://http://map.read.usuhx.com/Article/7664.shtml
- http://http://map.mobile.xqnqq.com/Article/20085.shtml
- http://http://map.mobile.xqnqq.com/Article/7340156.shtml
- http://http://map.read.usuhx.com/Article/1404513.shtml
- http://http://map.read.usuhx.com/Article/807629.shtml
- http://http://map.mobile.xqnqq.com/Article/1486431.shtml
- http://http://map.read.usuhx.com/Article/3098.shtml
- http://http://map.mobile.xqnqq.com/Article/186431.shtml
- http://http://map.mobile.xqnqq.com/Article/4093.shtml
- http://http://map.mobile.xqnqq.com/Article/42372.shtml
- http://http://map.mobile.xqnqq.com/Article/294354.shtml
- http://http://map.mobile.xqnqq.com/Article/057269.shtml
- http://http://map.read.usuhx.com/Article/4622898.shtml
- http://http://map.read.usuhx.com/Article/39371.shtml
- http://http://map.read.usuhx.com/Article/838080.shtml
- http://http://map.read.usuhx.com/Article/34348.shtml
- http://http://map.read.usuhx.com/Article/786414.shtml
- http://http://map.mobile.xqnqq.com/Article/74893.shtml
- http://http://map.read.usuhx.com/Article/102101.shtml
- http://http://map.read.usuhx.com/Article/461632.shtml
- http://http://map.mobile.xqnqq.com/Article/058263.shtml
- http://http://map.read.usuhx.com/Article/7811.shtml
- http://http://map.read.usuhx.com/Article/74547.shtml
- http://http://map.read.usuhx.com/Article/9677.shtml
- http://http://map.read.usuhx.com/Article/68193.shtml
- http://http://map.mobile.xqnqq.com/Article/785445.shtml
- http://http://map.mobile.xqnqq.com/Article/675494.shtml
- http://http://map.read.usuhx.com/Article/91905.shtml
- http://http://map.mobile.xqnqq.com/Article/2196941.shtml
- http://http://map.mobile.xqnqq.com/Article/09127.shtml
- http://http://map.read.usuhx.com/Article/913689.shtml
- http://http://map.read.usuhx.com/Article/53849.shtml
- http://http://map.mobile.xqnqq.com/Article/4809.shtml
- http://http://map.read.usuhx.com/Article/43251.shtml
- http://http://map.read.usuhx.com/Article/343750.shtml
- http://http://map.read.usuhx.com/Article/4505.shtml
- http://http://map.mobile.xqnqq.com/Article/1056777.shtml
- http://http://map.read.usuhx.com/Article/7463.shtml
- http://http://map.read.usuhx.com/Article/380249.shtml
- http://http://map.read.usuhx.com/Article/48437.shtml
- http://http://map.mobile.xqnqq.com/Article/1408.shtml
- http://http://map.mobile.xqnqq.com/Article/1364419.shtml
- http://http://map.read.usuhx.com/Article/385607.shtml
- http://http://map.mobile.xqnqq.com/Article/938246.shtml
- http://http://map.read.usuhx.com/Article/1500.shtml
- http://http://map.read.usuhx.com/Article/7088046.shtml
- http://http://map.read.usuhx.com/Article/287994.shtml
- http://http://map.read.usuhx.com/Article/501887.shtml
- http://http://map.read.usuhx.com/Article/141284.shtml
- http://http://map.mobile.xqnqq.com/Article/7324.shtml
- http://http://map.mobile.xqnqq.com/Article/05285.shtml
- http://http://map.mobile.xqnqq.com/Article/7852811.shtml
- http://http://map.mobile.xqnqq.com/Article/945997.shtml
- http://http://map.mobile.xqnqq.com/Article/167320.shtml
- http://http://map.read.usuhx.com/Article/18370.shtml
- http://http://map.mobile.xqnqq.com/Article/991529.shtml
- http://http://map.read.usuhx.com/Article/545117.shtml
- http://http://map.read.usuhx.com/Article/147186.shtml
- http://http://map.mobile.xqnqq.com/Article/66679.shtml
- http://http://map.read.usuhx.com/Article/18845.shtml
- http://http://map.read.usuhx.com/Article/86995.shtml
- http://http://map.read.usuhx.com/Article/286957.shtml
- http://http://map.read.usuhx.com/Article/89111.shtml
- http://http://map.read.usuhx.com/Article/082388.shtml
- http://http://map.read.usuhx.com/Article/0984628.shtml
- http://http://map.read.usuhx.com/Article/0612.shtml
- http://http://map.mobile.xqnqq.com/Article/50850.shtml
- http://http://map.mobile.xqnqq.com/Article/014254.shtml
- http://http://map.mobile.xqnqq.com/Article/4302366.shtml
- http://http://map.read.usuhx.com/Article/833289.shtml
- http://http://map.mobile.xqnqq.com/Article/770829.shtml
- http://http://map.read.usuhx.com/Article/8891080.shtml
- http://http://map.read.usuhx.com/Article/4027170.shtml
- http://http://map.mobile.xqnqq.com/Article/67886.shtml
- http://http://map.mobile.xqnqq.com/Article/756066.shtml
- http://http://map.mobile.xqnqq.com/Article/25110.shtml
- http://http://map.read.usuhx.com/Article/8989946.shtml
- http://http://map.mobile.xqnqq.com/Article/64346.shtml
- http://http://map.read.usuhx.com/Article/7287.shtml
- http://http://map.mobile.xqnqq.com/Article/0439746.shtml
- http://http://map.read.usuhx.com/Article/711381.shtml
- http://http://map.read.usuhx.com/Article/0506940.shtml
- http://http://map.read.usuhx.com/Article/45011.shtml
- http://http://map.read.usuhx.com/Article/8948.shtml
- http://http://map.mobile.xqnqq.com/Article/627284.shtml
- http://http://map.read.usuhx.com/Article/2460.shtml
- http://http://map.read.usuhx.com/Article/00886.shtml
- http://http://map.read.usuhx.com/Article/6934872.shtml
- http://http://map.mobile.xqnqq.com/Article/137186.shtml
- http://http://map.read.usuhx.com/Article/4859.shtml
- http://http://map.read.usuhx.com/Article/38915.shtml
- http://http://map.mobile.xqnqq.com/Article/6393.shtml
- http://http://map.read.usuhx.com/Article/475668.shtml
- http://http://map.read.usuhx.com/Article/93783.shtml
- http://http://map.read.usuhx.com/Article/51347.shtml
- http://http://map.read.usuhx.com/Article/1363.shtml
- http://http://map.mobile.xqnqq.com/Article/6960609.shtml
- http://http://map.read.usuhx.com/Article/4636343.shtml
- http://http://map.mobile.xqnqq.com/Article/7113.shtml
- http://http://map.read.usuhx.com/Article/8951308.shtml
- http://http://map.mobile.xqnqq.com/Article/422648.shtml

## 项目结构

```
link-atlas/
├── atlas.py                  # 命令行入口，协调解析、去重、探测与导出流程
├── config.yaml               # 全局配置文件，定义忽略规则、标签别名与请求超时参数
├── requirements.txt          # Python 依赖清单，锁定各库版本号
├── data/
│   ├── raw/                  # 存放用户导入的原始 URL 清单，每行一个 URL
│   ├── processed/            # 输出清洗后的结构化数据，包含元数据与状态标记
│   └── cache/                # 缓存健康探测结果，避免重复请求同一 URL
├── src/
│   ├── parser.py             # URL 解析模块，提取协议、域名、路径、查询参数
│   ├── deduper.py            # 基于 SHA-256 的指纹去重与合并逻辑
│   ├── checker.py            # 异步 HTTP 健康检查，支持重试与超时控制
│   ├── exporter.py           # 导出为 CSV、JSON、纯文本等格式的适配器
│   └── utils.py              # 公共辅助函数，如日志记录、文件读写与时间格式化
├── tests/
│   ├── test_parser.py        # 针对 parser.py 的单元测试用例
│   ├── test_deduper.py       # 验证去重算法在重复与相似 URL 上的表现
│   └── test_checker.py       # 模拟 HTTP 响应，测试探测模块的容错性
└── docs/
    ├── user_guide.md         # 面向用户的完整操作手册
    ├── config_reference.md   # 配置项逐条说明与范例
    ├── api_reference.md      # 各模块函数签名、参数类型与返回值说明
    └── design_overview.md    # 项目架构图、数据流描述与扩展插件指南
```

## 贡献指南

确认现有 Issue 与 Pull Request 列表，避免重复提交。若发现新的需求或缺陷，请先创建一个 Issue 描述问题背景、复现步骤与预期行为。

Fork 本仓库至个人账户，并在本地新建一个功能分支，分支命名采用 feature/简短描述 或 fix/问题编号 的格式，以便追踪变更目的。

编写或更新与变更相关的单元测试，确保所有测试用例通过。对于新增的配置项或导出格式，需同步更新 docs 目录下的对应文档。

提交前运行完整的测试套件与代码风格检查（flake8 或 black），保证代码风格一致且无回归错误。提交信息使用简洁的英文，说明变更类型与影响范围。

发起 Pull Request 至主仓库的 develop 分支，并在描述中关联相关的 Issue 编号。核心维护者将在三个工作日内进行审查，提出修改意见或合并变更。

## 常见问题

执行 atlas.py 时提示 ModuleNotFoundError: No module named 'requests'，应如何解决？

该错误表示 Python 环境中缺少 requests 库。请先确认已按照安装要求正确执行 pip install -r requirements.txt。若仍然失败，可手动执行 pip install requests==2.28.2 安装指定版本。建议使用虚拟环境（如 venv 或 conda）隔离项目依赖，避免与其他项目发生版本冲突。

处理包含大量 URL 的文件时，程序运行缓慢或内存占用过高，有何优化建议？

对于超过十万条记录的输入文件，建议使用 --chunk-size 参数分批处理，该参数控制每批次加载的记录数量，默认值为 5000。可根据机器内存大小调整至 2000 或 10000。此外，可启用 --no-check 选项跳过健康探测阶段，仅执行解析与去重，以加速前期清洗流程。若需完整探测，建议使用 --workers 参数增加并发线程数，但需注意目标服务器的访问频率限制。

导出的 CSV 文件中，某些 URL 的 status 列显示为 TIMEOUT 或 404，这些链接是否被自动移除？

Link Atlas 默认保留所有原始 URL，不会自动删除任何链接。健康探测结果仅作为附加元数据写入输出文件，用户可根据 status 列自行筛选或处理异常链接。若希望过滤掉特定状态码的链接，可在配置文件的 ignore_rules 部分添加状态码过滤正则，或在使用 pandas 二次处理时按条件剔除。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
