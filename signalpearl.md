# LinkMap 技术资源导航站

LinkMap 是一个面向开发者、技术研究人员与信息分析从业者的结构化外链资源汇总系统。该项目并非传统的内容发布平台，而是一个基于 URL 组织与分类索引的轻量级信息路由层，用于对来自多个数据源的技术文章、地图服务文档、移动端开发参考以及相关领域研讨材料进行集中式收录与快速定位。

项目定位为技术知识体系中的“外链接入网关”，帮助用户在不直接托管内容的前提下，利用规范化的 URL 索引机制构建可维护、可扩展的个性化资源图谱。目标用户包括技术博主、数据采集工程师、开源社区维护者以及需要长期追踪特定领域信息源的研发团队。LinkMap 本身不依赖数据库，采用纯静态 Markdown 与元数据目录结构完成资源编排，确保低维护成本与高可移植性。

## 功能概览

- 多源 URL 规范化导入：支持批量导入包含不同域名、路径结构与查询参数的原始链接，保留协议与主机名原始形态，避免自动格式化导致的访问异常。

- 资源批次管理机制：按批次对收录链接进行分组（当前批次编号为 65/80，总计规划收录 250 个资源链接），每个批次均可独立生成索引摘要，便于回溯与增量更新。

- 资源元数据提取：自动从 URL 中解析文章编号、站点归属（如 map.mobile.xqnqq.com 与 map.read.usuhx.com）、文件类型后缀等信息，用于后续分类筛选。

- 结构化目录树组织：项目物理目录按来源域名、内容类型、收录时间三级划分，辅以 ASCII 树形可视化，降低大规模链接管理时的认知负担。

- 快速检索与过滤：借助约定大于配置的命名规则，用户可通过 grep、awk 或内置 shell 脚本快速定位特定域名或文章 ID 范围内的资源。

- 依赖链清洁化：运行环境仅依赖标准 POSIX 工具集与 Python 3 基础解释器，无需额外安装重量级框架，适合在资源受限的服务器或容器中部署。

- 导出与分发接口：支持将当前批次资源列表导出为纯文本清单、CSV 表格或与 CI/CD 集成的 JSON 格式，便于下游系统消费。

## 应用场景

- 技术文献专题汇编：研究人员在追踪地图服务或移动端适配技术时，可将散落在多个站点上的相关文章链接通过 LinkMap 统一收录，并按主题添加注释文件，形成专题阅读清单。

- 数据采集管道前置管理：数据工程团队在构建爬虫或 API 调用流程前，使用 LinkMap 对目标 URL 进行健康检查、去重与优先级排序，确保采集任务的输入源清晰可控。

- 团队知识库外链治理：企业内部分享的技术博客、会议演讲视频链接或第三方工具文档，通过 LinkMap 按月份或项目阶段组织批次，配合文档导航表格快速定位问题域，避免收藏夹混乱。

- 开源项目外部依赖索引：开源库维护者可在 README 中引用 LinkMap 生成的资源列表，向社区说明项目所参考的设计文档、协议规范或测试用例来源，提升透明度与可追溯性。

## 快速开始

以下指令适用于 Linux 及 macOS 系统，Windows 用户建议通过 WSL 或 Git Bash 执行。

```bash
# 克隆项目仓库
git clone https://github.com/your-org/linkmap.git
cd linkmap

# 安装基础依赖（Python 虚拟环境可选）
python3 -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt

# 运行批次导入脚本（以当前第65批为例）
./scripts/import_batch.sh --batch 65 --source ./data/raw/urls_65.txt
```

若需本地预览生成的索引页面，可执行内置静态服务器：

```bash
python3 -m http.server 8000 --directory ./output
```

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Python | 3.8 及以上 | 用于运行解析、校验与导出脚本 |
| Git | 2.25 及以上 | 版本控制与仓库克隆 |
| GNU Make | 3.81 及以上 | 任务自动化编排（可选，但推荐） |
| POSIX-compliant shell | bash 4.0 / zsh 5.0 | 执行导入与批处理脚本 |
| curl | 7.68 及以上 | 用于远程资源可达性检测（非强制） |
| grep | 3.4 及以上 | 文本过滤与模式匹配 |
| sed | 4.7 及以上 | 流式编辑与 URL 格式化辅助 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 用户入门 | docs/getting-started.md | 如何安装、配置并运行第一次资源导入 |
| 批次管理 | docs/batch-operation.md | 如何创建新批次、追加链接、删除过期资源 |
| 元数据规范 | docs/metadata-schema.md | 每个 URL 关联的标签、注释和状态字段如何定义 |
| 故障排查 | docs/troubleshooting.md | 遇到导入失败、链接重复或脚本报错时的处理步骤 |

## 资源列表

- http://http://map.mobile.xqnqq.com/Article/2232821.shtml
- http://http://map.read.usuhx.com/Article/7517.shtml
- http://http://map.read.usuhx.com/Article/579577.shtml
- http://http://map.mobile.xqnqq.com/Article/2940.shtml
- http://http://map.read.usuhx.com/Article/61335.shtml
- http://http://map.read.usuhx.com/Article/1598.shtml
- http://http://map.read.usuhx.com/Article/2043.shtml
- http://http://map.read.usuhx.com/Article/488891.shtml
- http://http://map.read.usuhx.com/Article/6257630.shtml
- http://http://map.read.usuhx.com/Article/8387.shtml
- http://http://map.read.usuhx.com/Article/7840.shtml
- http://http://map.mobile.xqnqq.com/Article/3791135.shtml
- http://http://map.read.usuhx.com/Article/984510.shtml
- http://http://map.read.usuhx.com/Article/90641.shtml
- http://http://map.mobile.xqnqq.com/Article/89216.shtml
- http://http://map.mobile.xqnqq.com/Article/0310.shtml
- http://http://map.mobile.xqnqq.com/Article/26480.shtml
- http://http://map.read.usuhx.com/Article/59450.shtml
- http://http://map.mobile.xqnqq.com/Article/460140.shtml
- http://http://map.mobile.xqnqq.com/Article/460094.shtml
- http://http://map.mobile.xqnqq.com/Article/3434.shtml
- http://http://map.read.usuhx.com/Article/8241.shtml
- http://http://map.mobile.xqnqq.com/Article/55089.shtml
- http://http://map.mobile.xqnqq.com/Article/2976011.shtml
- http://http://map.mobile.xqnqq.com/Article/265803.shtml
- http://http://map.read.usuhx.com/Article/9335844.shtml
- http://http://map.mobile.xqnqq.com/Article/3683.shtml
- http://http://map.read.usuhx.com/Article/70332.shtml
- http://http://map.mobile.xqnqq.com/Article/6625.shtml
- http://http://map.mobile.xqnqq.com/Article/8394571.shtml
- http://http://map.read.usuhx.com/Article/35853.shtml
- http://http://map.read.usuhx.com/Article/4364.shtml
- http://http://map.mobile.xqnqq.com/Article/5809841.shtml
- http://http://map.mobile.xqnqq.com/Article/1372.shtml
- http://http://map.read.usuhx.com/Article/1534.shtml
- http://http://map.read.usuhx.com/Article/3595.shtml
- http://http://map.mobile.xqnqq.com/Article/4977.shtml
- http://http://map.read.usuhx.com/Article/8539941.shtml
- http://http://map.read.usuhx.com/Article/26182.shtml
- http://http://map.mobile.xqnqq.com/Article/7062392.shtml
- http://http://map.mobile.xqnqq.com/Article/01039.shtml
- http://http://map.read.usuhx.com/Article/5341.shtml
- http://http://map.mobile.xqnqq.com/Article/859365.shtml
- http://http://map.mobile.xqnqq.com/Article/5128496.shtml
- http://http://map.read.usuhx.com/Article/72880.shtml
- http://http://map.read.usuhx.com/Article/2710441.shtml
- http://http://map.read.usuhx.com/Article/43139.shtml
- http://http://map.mobile.xqnqq.com/Article/46180.shtml
- http://http://map.read.usuhx.com/Article/37647.shtml
- http://http://map.read.usuhx.com/Article/16283.shtml
- http://http://map.mobile.xqnqq.com/Article/4692.shtml
- http://http://map.mobile.xqnqq.com/Article/7685.shtml
- http://http://map.mobile.xqnqq.com/Article/3982.shtml
- http://http://map.read.usuhx.com/Article/1439472.shtml
- http://http://map.read.usuhx.com/Article/173437.shtml
- http://http://map.mobile.xqnqq.com/Article/3918448.shtml
- http://http://map.read.usuhx.com/Article/13806.shtml
- http://http://map.read.usuhx.com/Article/52905.shtml
- http://http://map.mobile.xqnqq.com/Article/2192.shtml
- http://http://map.mobile.xqnqq.com/Article/555107.shtml
- http://http://map.mobile.xqnqq.com/Article/919114.shtml
- http://http://map.mobile.xqnqq.com/Article/058620.shtml
- http://http://map.read.usuhx.com/Article/7964442.shtml
- http://http://map.read.usuhx.com/Article/944608.shtml
- http://http://map.mobile.xqnqq.com/Article/8862.shtml
- http://http://map.mobile.xqnqq.com/Article/273576.shtml
- http://http://map.mobile.xqnqq.com/Article/39054.shtml
- http://http://map.mobile.xqnqq.com/Article/97819.shtml
- http://http://map.mobile.xqnqq.com/Article/6514961.shtml
- http://http://map.read.usuhx.com/Article/8604.shtml
- http://http://map.read.usuhx.com/Article/7386198.shtml
- http://http://map.mobile.xqnqq.com/Article/30255.shtml
- http://http://map.read.usuhx.com/Article/86035.shtml
- http://http://map.read.usuhx.com/Article/65711.shtml
- http://http://map.mobile.xqnqq.com/Article/5279.shtml
- http://http://map.read.usuhx.com/Article/483614.shtml
- http://http://map.read.usuhx.com/Article/18718.shtml
- http://http://map.read.usuhx.com/Article/8955.shtml
- http://http://map.read.usuhx.com/Article/3461.shtml
- http://http://map.mobile.xqnqq.com/Article/2235853.shtml
- http://http://map.mobile.xqnqq.com/Article/875729.shtml
- http://http://map.read.usuhx.com/Article/5914244.shtml
- http://http://map.read.usuhx.com/Article/9697.shtml
- http://http://map.mobile.xqnqq.com/Article/5101963.shtml
- http://http://map.read.usuhx.com/Article/0038503.shtml
- http://http://map.mobile.xqnqq.com/Article/43089.shtml
- http://http://map.mobile.xqnqq.com/Article/790849.shtml
- http://http://map.read.usuhx.com/Article/0744614.shtml
- http://http://map.read.usuhx.com/Article/99017.shtml
- http://http://map.read.usuhx.com/Article/076013.shtml
- http://http://map.mobile.xqnqq.com/Article/5029.shtml
- http://http://map.mobile.xqnqq.com/Article/9767.shtml
- http://http://map.mobile.xqnqq.com/Article/83880.shtml
- http://http://map.read.usuhx.com/Article/473491.shtml
- http://http://map.read.usuhx.com/Article/7157181.shtml
- http://http://map.read.usuhx.com/Article/578202.shtml
- http://http://map.read.usuhx.com/Article/949284.shtml
- http://http://map.mobile.xqnqq.com/Article/234751.shtml
- http://http://map.mobile.xqnqq.com/Article/44921.shtml
- http://http://map.mobile.xqnqq.com/Article/98710.shtml
- http://http://map.mobile.xqnqq.com/Article/3594489.shtml
- http://http://map.mobile.xqnqq.com/Article/7974210.shtml
- http://http://map.read.usuhx.com/Article/746174.shtml
- http://http://map.mobile.xqnqq.com/Article/52484.shtml
- http://http://map.read.usuhx.com/Article/791580.shtml
- http://http://map.mobile.xqnqq.com/Article/182486.shtml
- http://http://map.read.usuhx.com/Article/7293978.shtml
- http://http://map.read.usuhx.com/Article/30845.shtml
- http://http://map.mobile.xqnqq.com/Article/9952.shtml
- http://http://map.mobile.xqnqq.com/Article/088530.shtml
- http://http://map.read.usuhx.com/Article/0196653.shtml
- http://http://map.read.usuhx.com/Article/184310.shtml
- http://http://map.mobile.xqnqq.com/Article/5015845.shtml
- http://http://map.read.usuhx.com/Article/14357.shtml
- http://http://map.read.usuhx.com/Article/99309.shtml
- http://http://map.read.usuhx.com/Article/58471.shtml
- http://http://map.mobile.xqnqq.com/Article/48956.shtml
- http://http://map.read.usuhx.com/Article/540127.shtml
- http://http://map.mobile.xqnqq.com/Article/86112.shtml
- http://http://map.read.usuhx.com/Article/09447.shtml
- http://http://map.mobile.xqnqq.com/Article/04071.shtml
- http://http://map.mobile.xqnqq.com/Article/65409.shtml
- http://http://map.mobile.xqnqq.com/Article/3194.shtml
- http://http://map.mobile.xqnqq.com/Article/58047.shtml
- http://http://map.mobile.xqnqq.com/Article/0798623.shtml
- http://http://map.read.usuhx.com/Article/4582.shtml
- http://http://map.mobile.xqnqq.com/Article/79295.shtml
- http://http://map.mobile.xqnqq.com/Article/65855.shtml
- http://http://map.mobile.xqnqq.com/Article/88090.shtml
- http://http://map.mobile.xqnqq.com/Article/4306.shtml
- http://http://map.mobile.xqnqq.com/Article/28544.shtml
- http://http://map.mobile.xqnqq.com/Article/3708095.shtml
- http://http://map.read.usuhx.com/Article/7749.shtml
- http://http://map.read.usuhx.com/Article/8611.shtml
- http://http://map.mobile.xqnqq.com/Article/578787.shtml
- http://http://map.mobile.xqnqq.com/Article/3375.shtml
- http://http://map.read.usuhx.com/Article/4233.shtml
- http://http://map.mobile.xqnqq.com/Article/43382.shtml
- http://http://map.read.usuhx.com/Article/9516.shtml
- http://http://map.mobile.xqnqq.com/Article/657346.shtml
- http://http://map.read.usuhx.com/Article/94389.shtml
- http://http://map.read.usuhx.com/Article/5576853.shtml
- http://http://map.read.usuhx.com/Article/305305.shtml
- http://http://map.mobile.xqnqq.com/Article/45172.shtml
- http://http://map.mobile.xqnqq.com/Article/30694.shtml
- http://http://map.mobile.xqnqq.com/Article/07644.shtml
- http://http://map.read.usuhx.com/Article/004674.shtml
- http://http://map.read.usuhx.com/Article/24010.shtml
- http://http://map.read.usuhx.com/Article/1561.shtml
- http://http://map.mobile.xqnqq.com/Article/26562.shtml
- http://http://map.mobile.xqnqq.com/Article/839764.shtml
- http://http://map.read.usuhx.com/Article/516901.shtml
- http://http://map.mobile.xqnqq.com/Article/0007675.shtml
- http://http://map.mobile.xqnqq.com/Article/129512.shtml
- http://http://map.mobile.xqnqq.com/Article/6157.shtml
- http://http://map.mobile.xqnqq.com/Article/0985733.shtml
- http://http://map.mobile.xqnqq.com/Article/96826.shtml
- http://http://map.read.usuhx.com/Article/9212.shtml
- http://http://map.mobile.xqnqq.com/Article/9742.shtml
- http://http://map.read.usuhx.com/Article/1388.shtml
- http://http://map.read.usuhx.com/Article/85098.shtml
- http://http://map.mobile.xqnqq.com/Article/04500.shtml
- http://http://map.read.usuhx.com/Article/18983.shtml
- http://http://map.read.usuhx.com/Article/7958.shtml
- http://http://map.read.usuhx.com/Article/190883.shtml
- http://http://map.read.usuhx.com/Article/6144.shtml
- http://http://map.read.usuhx.com/Article/9969.shtml
- http://http://map.read.usuhx.com/Article/0233119.shtml
- http://http://map.mobile.xqnqq.com/Article/2476.shtml
- http://http://map.mobile.xqnqq.com/Article/969897.shtml
- http://http://map.mobile.xqnqq.com/Article/30410.shtml
- http://http://map.read.usuhx.com/Article/0052.shtml
- http://http://map.read.usuhx.com/Article/5510736.shtml
- http://http://map.mobile.xqnqq.com/Article/5124875.shtml
- http://http://map.mobile.xqnqq.com/Article/07660.shtml
- http://http://map.read.usuhx.com/Article/2193.shtml
- http://http://map.read.usuhx.com/Article/878866.shtml
- http://http://map.mobile.xqnqq.com/Article/802511.shtml
- http://http://map.read.usuhx.com/Article/8808053.shtml
- http://http://map.mobile.xqnqq.com/Article/506706.shtml
- http://http://map.read.usuhx.com/Article/4949.shtml
- http://http://map.read.usuhx.com/Article/54711.shtml
- http://http://map.mobile.xqnqq.com/Article/738656.shtml
- http://http://map.read.usuhx.com/Article/00128.shtml
- http://http://map.mobile.xqnqq.com/Article/18773.shtml
- http://http://map.read.usuhx.com/Article/7907268.shtml
- http://http://map.read.usuhx.com/Article/79774.shtml
- http://http://map.mobile.xqnqq.com/Article/76916.shtml
- http://http://map.read.usuhx.com/Article/11209.shtml
- http://http://map.mobile.xqnqq.com/Article/8893.shtml
- http://http://map.read.usuhx.com/Article/4641718.shtml
- http://http://map.mobile.xqnqq.com/Article/614676.shtml
- http://http://map.mobile.xqnqq.com/Article/24931.shtml
- http://http://map.mobile.xqnqq.com/Article/708659.shtml
- http://http://map.read.usuhx.com/Article/34784.shtml
- http://http://map.mobile.xqnqq.com/Article/25057.shtml
- http://http://map.read.usuhx.com/Article/1425.shtml
- http://http://map.mobile.xqnqq.com/Article/3223.shtml
- http://http://map.mobile.xqnqq.com/Article/772876.shtml
- http://http://map.read.usuhx.com/Article/63158.shtml
- http://http://map.read.usuhx.com/Article/04463.shtml
- http://http://map.mobile.xqnqq.com/Article/6924059.shtml
- http://http://map.read.usuhx.com/Article/2533.shtml
- http://http://map.read.usuhx.com/Article/9491.shtml
- http://http://map.mobile.xqnqq.com/Article/3920.shtml
- http://http://map.mobile.xqnqq.com/Article/215280.shtml
- http://http://map.mobile.xqnqq.com/Article/467605.shtml
- http://http://map.mobile.xqnqq.com/Article/5503795.shtml
- http://http://map.mobile.xqnqq.com/Article/1838077.shtml
- http://http://map.mobile.xqnqq.com/Article/435876.shtml
- http://http://map.mobile.xqnqq.com/Article/178664.shtml
- http://http://map.mobile.xqnqq.com/Article/816039.shtml
- http://http://map.read.usuhx.com/Article/4927305.shtml
- http://http://map.read.usuhx.com/Article/4439654.shtml
- http://http://map.mobile.xqnqq.com/Article/8203.shtml
- http://http://map.read.usuhx.com/Article/777673.shtml
- http://http://map.read.usuhx.com/Article/638907.shtml
- http://http://map.read.usuhx.com/Article/0887184.shtml
- http://http://map.mobile.xqnqq.com/Article/4662957.shtml
- http://http://map.read.usuhx.com/Article/1440.shtml
- http://http://map.mobile.xqnqq.com/Article/9332320.shtml
- http://http://map.mobile.xqnqq.com/Article/01566.shtml
- http://http://map.read.usuhx.com/Article/9942.shtml
- http://http://map.read.usuhx.com/Article/80956.shtml
- http://http://map.mobile.xqnqq.com/Article/802827.shtml
- http://http://map.mobile.xqnqq.com/Article/34497.shtml
- http://http://map.mobile.xqnqq.com/Article/9968.shtml
- http://http://map.read.usuhx.com/Article/9899462.shtml
- http://http://map.mobile.xqnqq.com/Article/6221.shtml
- http://http://map.mobile.xqnqq.com/Article/734236.shtml
- http://http://map.mobile.xqnqq.com/Article/67352.shtml
- http://http://map.mobile.xqnqq.com/Article/13512.shtml
- http://http://map.mobile.xqnqq.com/Article/1954.shtml
- http://http://map.mobile.xqnqq.com/Article/258795.shtml
- http://http://map.read.usuhx.com/Article/73592.shtml
- http://http://map.mobile.xqnqq.com/Article/650341.shtml
- http://http://map.mobile.xqnqq.com/Article/5881909.shtml
- http://http://map.read.usuhx.com/Article/565733.shtml
- http://http://map.read.usuhx.com/Article/7900.shtml
- http://http://map.mobile.xqnqq.com/Article/00223.shtml
- http://http://map.mobile.xqnqq.com/Article/5930851.shtml
- http://http://map.mobile.xqnqq.com/Article/444021.shtml
- http://http://map.mobile.xqnqq.com/Article/2694.shtml
- http://http://map.mobile.xqnqq.com/Article/98999.shtml
- http://http://map.read.usuhx.com/Article/54204.shtml
- http://http://map.mobile.xqnqq.com/Article/8143.shtml
- http://http://map.mobile.xqnqq.com/Article/89740.shtml
- http://http://map.mobile.xqnqq.com/Article/70122.shtml
- http://http://map.mobile.xqnqq.com/Article/6912182.shtml
- http://http://map.read.usuhx.com/Article/9024399.shtml

## 项目结构

```
linkmap/
├── README.md                           # 项目入口文档（当前文件）
├── LICENSE                             # MIT 许可证文本
├── requirements.txt                    # Python 依赖声明（仅含标准库外扩展）
├── Makefile                            # 任务编排入口（clean, import, validate）
│
├── data/                               # 数据存储目录
│   ├── raw/                            # 原始输入目录
│   │   └── urls_65.txt                 # 第65批原始 URL 列表（每行一个）
│   ├── parsed/                         # 解析后结构化数据
│   │   └── batch_65_metadata.json      # 包含域名、文章ID、时间戳等字段
│   └── index/                          # 索引缓存目录
│       └── domain_index.db             # 轻量级域名倒排索引（SQLite3）
│
├── scripts/                            # 可执行脚本目录
│   ├── import_batch.sh                 # 批次导入主脚本（参数：--batch, --source）
│   ├── validate_urls.py                # URL 格式校验器（检查双协议前缀等异常）
│   ├── deduplicate.sh                  # 基于 awk 的快速去重工具
│   └── export_csv.py                   # 将当前批次导出为 CSV 格式
│
├── docs/                               # 文档目录
│   ├── getting-started.md              # 新用户上手指南
│   ├── batch-operation.md              # 批次创建与生命周期管理
│   ├── metadata-schema.md              # 元数据 JSON Schema 说明
│   └── troubleshooting.md              # 常见错误与修复手册
│
├── tests/                              # 单元测试与集成测试目录
│   ├── test_import.sh                  # 测试导入流程的边界条件
│   └── test_validate.py                # 对校验器进行白盒测试
│
└── output/                             # 生成结果输出目录（默认被 .gitignore 忽略）
    ├── index.html                      # 简易可视化索引页（自动生成）
    └── batch_65_manifest.txt           # 纯文本资源清单（适合 wget 批量下载）
```

## 贡献指南

1. 复刻项目仓库至个人账号，并在本地创建新功能分支（命名格式为 feat/batch-{编号} 或 fix/issue-{编号}），确保分支名称与变更内容相符。

2. 在 data/raw/ 目录下按照既定格式追加或修改 URL 列表文件，每行一条记录，严禁包含额外注释或空格。新增的链接需经过 validate_urls.py 校验通过方可提交。

3. 若涉及脚本逻辑变更（如 scripts/ 下的 Python 或 Shell 文件），请在 tests/ 目录下补充对应的测试用例，并确保所有历史测试案例执行通过（执行 make test）。

4. 提交变更时使用约定式提交规范（Conventional Commits），例如 docs: update batch operation guide 或 feat: support JSON export for batch 65。

5. 发起 Pull Request 时在描述中明确关联的批次编号、变更动机以及验证方式，至少需一名项目维护者审查通过后合并。

## 常见问题

问：导入时提示“URL 格式异常”，但链接在浏览器中可以正常打开。

答：该情况通常由原始数据中包含了重复的协议前缀（如 http://http://）所导致。项目提供的 validate_urls.py 脚本会标记此类异常，建议使用 scripts/deduplicate.sh 配合 sed 进行清洗。若确信链接有效，可手动修正后重新导入。

问：如何在同一项目中管理多个不同来源的批次？

答：LinkMap 通过 data/raw/ 目录下的文件名进行区分（如 urls_65.txt、urls_66.txt）。导入时通过 --batch 参数指定编号，系统会自动将解析结果归入 data/parsed/batch_{编号}_metadata.json。索引层面对不同批次采用合并策略，查询时可通过元数据中的 batch 字段筛选。

问：静态资源列表能否自动更新？

答：项目本身不包含自动爬取或定时任务功能，以保持简洁性。如需周期性更新，建议结合系统 cron 或 CI 调度器定期执行 import_batch.sh，并将输出目录挂载至 Web 服务器。更新策略与频率可由用户自行编排。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
