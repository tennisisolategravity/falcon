# WebLink Archive Gateway

WebLink Archive Gateway 是一个面向技术文档、历史文章与内容聚合场景的轻量级外链汇总与归档系统。项目定位于个人开发者、研究机构与内容运营团队，用于对分散在多个内容源的文章链接进行集中收录、结构化分类与快速检索。该项目不依赖外部数据库，以纯静态方式运行，适合部署在低成本服务器或对象存储平台上。

目标用户包括需要长期维护外链资源列表的技术博主、内部知识库管理人员、以及需要按批次组织大量内容链接的运营人员。WebLink Archive Gateway 解决了多源链接难以统一管理、缺乏分类标识、以及检索效率低下的问题，提供一套基于元数据映射的链接组织方案。

## 功能概览

- 批量链接导入解析：支持按批次导入大量文章链接，自动解析域名来源与文章ID。
- 双源数据聚合：当前版本内置对两个内容来源（read.usuhx.com 与 mobile.xqnqq.com）的链接聚合能力。
- 文章ID索引生成：从链接中提取文章编号，生成可用于快速定位的本地索引。
- 源站分类标签：根据链接所属域名自动添加分类标签，便于按来源筛选。
- 基础检索过滤：支持按域名来源、文章ID范围进行简单文本过滤。
- 静态导出机制：将链接列表导出为 Markdown 或 JSON 格式，便于集成到静态站点生成器。
- 项目状态仪表板：提供简单的命令行界面显示当前批次收录链接总数与来源分布统计。

## 应用场景

技术博客外链归档：技术作者在撰写年度总结或专题文章时，可将全年引用的外部链接统一存入 WebLink Archive Gateway，按批次生成结构化列表，避免链接散落在草稿文件中。

内部知识库链接治理：企业知识管理团队使用本系统对内部 Wiki、技术文档中引用的第三方文章链接进行集中登记，定期检查链接可用性，并在迁移文档时统一更新引用路径。

内容运营数据整理：内容运营人员针对特定营销活动或专题报道，收集大量相关报道链接，通过本系统按批次编号（如第63/80批）组织链接，方便团队协作与历史回溯。

开源项目外链资源站：开源社区维护项目周边资源列表时，利用本系统作为链接汇总工具，生成可直接嵌入 README 的资源导航区块。

## 快速开始

```bash
# 克隆代码仓库
git clone https://github.com/weblink-archive/weblink-archive-gateway.git

# 进入项目目录
cd weblink-archive-gateway

# 安装依赖（基于 Python 3.9+）
pip install -r requirements.txt

# 运行链接导入与索引生成
python cli.py import --batch 63 --source links_batch_63.txt

# 启动本地预览服务
python cli.py serve --port 8080
```

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
| :--- | :--- | :--- |
| Python | 3.9 及以上 | 核心运行环境，用于 CLI 工具与解析引擎 |
| pip | 21.0 及以上 | Python 包管理工具，用于安装依赖库 |
| beautifulsoup4 | 4.10.0 | HTML 解析库，用于未来扩展文章标题抓取功能 |
| lxml | 4.8.0 | 高性能 XML/HTML 解析器，beautifulsoup4 的后端 |
| requests | 2.27.0 | HTTP 客户端库，用于批量链接可用性检查（可选功能） |
| pytest | 7.0.0 | 单元测试框架，仅在开发环境中使用 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
| :--- | :--- | :--- |
| 入门 | docs/getting-started.md | 如何快速部署并使用本系统进行第一批链接导入 |
| 使用 | docs/batch-management.md | 如何管理多个批次的链接，如何进行增删改查操作 |
| 架构 | docs/architecture.md | 系统的模块划分、数据流与扩展点设计 |
| 扩展 | docs/custom-source.md | 如何添加新的内容源域名适配器，支持更多网站链接 |

## 资源列表

- http://http://map.read.usuhx.com/Article/5382.shtml
- http://http://map.read.usuhx.com/Article/3598110.shtml
- http://http://map.mobile.xqnqq.com/Article/5369.shtml
- http://http://map.read.usuhx.com/Article/792869.shtml
- http://http://map.mobile.xqnqq.com/Article/097705.shtml
- http://http://map.mobile.xqnqq.com/Article/87546.shtml
- http://http://map.read.usuhx.com/Article/962987.shtml
- http://http://map.mobile.xqnqq.com/Article/28287.shtml
- http://http://map.read.usuhx.com/Article/56994.shtml
- http://http://map.read.usuhx.com/Article/592694.shtml
- http://http://map.read.usuhx.com/Article/6571.shtml
- http://http://map.mobile.xqnqq.com/Article/563125.shtml
- http://http://map.mobile.xqnqq.com/Article/8053151.shtml
- http://http://map.mobile.xqnqq.com/Article/1224.shtml
- http://http://map.mobile.xqnqq.com/Article/165423.shtml
- http://http://map.mobile.xqnqq.com/Article/1913919.shtml
- http://http://map.mobile.xqnqq.com/Article/23264.shtml
- http://http://map.mobile.xqnqq.com/Article/3128684.shtml
- http://http://map.mobile.xqnqq.com/Article/9883034.shtml
- http://http://map.mobile.xqnqq.com/Article/82143.shtml
- http://http://map.read.usuhx.com/Article/9116.shtml
- http://http://map.mobile.xqnqq.com/Article/222384.shtml
- http://http://map.read.usuhx.com/Article/4967968.shtml
- http://http://map.mobile.xqnqq.com/Article/4931.shtml
- http://http://map.mobile.xqnqq.com/Article/377864.shtml
- http://http://map.read.usuhx.com/Article/56081.shtml
- http://http://map.read.usuhx.com/Article/5707.shtml
- http://http://map.mobile.xqnqq.com/Article/6327948.shtml
- http://http://map.mobile.xqnqq.com/Article/065060.shtml
- http://http://map.mobile.xqnqq.com/Article/697421.shtml
- http://http://map.read.usuhx.com/Article/49764.shtml
- http://http://map.mobile.xqnqq.com/Article/962147.shtml
- http://http://map.mobile.xqnqq.com/Article/4445.shtml
- http://http://map.mobile.xqnqq.com/Article/8818839.shtml
- http://http://map.mobile.xqnqq.com/Article/2971.shtml
- http://http://map.mobile.xqnqq.com/Article/3476440.shtml
- http://http://map.read.usuhx.com/Article/9412808.shtml
- http://http://map.mobile.xqnqq.com/Article/7304021.shtml
- http://http://map.mobile.xqnqq.com/Article/278014.shtml
- http://http://map.mobile.xqnqq.com/Article/0912046.shtml
- http://http://map.read.usuhx.com/Article/355103.shtml
- http://http://map.mobile.xqnqq.com/Article/3507043.shtml
- http://http://map.mobile.xqnqq.com/Article/9456927.shtml
- http://http://map.mobile.xqnqq.com/Article/86702.shtml
- http://http://map.read.usuhx.com/Article/8209.shtml
- http://http://map.mobile.xqnqq.com/Article/9958162.shtml
- http://http://map.mobile.xqnqq.com/Article/461531.shtml
- http://http://map.mobile.xqnqq.com/Article/351888.shtml
- http://http://map.read.usuhx.com/Article/837704.shtml
- http://http://map.read.usuhx.com/Article/518792.shtml
- http://http://map.read.usuhx.com/Article/720757.shtml
- http://http://map.read.usuhx.com/Article/99531.shtml
- http://http://map.mobile.xqnqq.com/Article/216180.shtml
- http://http://map.read.usuhx.com/Article/355039.shtml
- http://http://map.mobile.xqnqq.com/Article/3734893.shtml
- http://http://map.mobile.xqnqq.com/Article/85477.shtml
- http://http://map.mobile.xqnqq.com/Article/335056.shtml
- http://http://map.read.usuhx.com/Article/898355.shtml
- http://http://map.mobile.xqnqq.com/Article/747701.shtml
- http://http://map.mobile.xqnqq.com/Article/1743.shtml
- http://http://map.mobile.xqnqq.com/Article/99002.shtml
- http://http://map.mobile.xqnqq.com/Article/31536.shtml
- http://http://map.read.usuhx.com/Article/380138.shtml
- http://http://map.mobile.xqnqq.com/Article/93490.shtml
- http://http://map.read.usuhx.com/Article/233951.shtml
- http://http://map.read.usuhx.com/Article/5296089.shtml
- http://http://map.mobile.xqnqq.com/Article/35543.shtml
- http://http://map.mobile.xqnqq.com/Article/704851.shtml
- http://http://map.read.usuhx.com/Article/4943022.shtml
- http://http://map.mobile.xqnqq.com/Article/6911.shtml
- http://http://map.read.usuhx.com/Article/4937.shtml
- http://http://map.mobile.xqnqq.com/Article/3469.shtml
- http://http://map.read.usuhx.com/Article/74932.shtml
- http://http://map.read.usuhx.com/Article/06216.shtml
- http://http://map.read.usuhx.com/Article/9214.shtml
- http://http://map.read.usuhx.com/Article/81898.shtml
- http://http://map.mobile.xqnqq.com/Article/5446725.shtml
- http://http://map.read.usuhx.com/Article/0555726.shtml
- http://http://map.mobile.xqnqq.com/Article/021274.shtml
- http://http://map.mobile.xqnqq.com/Article/126323.shtml
- http://http://map.read.usuhx.com/Article/83341.shtml
- http://http://map.mobile.xqnqq.com/Article/9750949.shtml
- http://http://map.mobile.xqnqq.com/Article/07504.shtml
- http://http://map.mobile.xqnqq.com/Article/588509.shtml
- http://http://map.read.usuhx.com/Article/284816.shtml
- http://http://map.read.usuhx.com/Article/00587.shtml
- http://http://map.mobile.xqnqq.com/Article/773178.shtml
- http://http://map.mobile.xqnqq.com/Article/3604154.shtml
- http://http://map.read.usuhx.com/Article/88939.shtml
- http://http://map.read.usuhx.com/Article/06289.shtml
- http://http://map.read.usuhx.com/Article/741534.shtml
- http://http://map.read.usuhx.com/Article/75005.shtml
- http://http://map.mobile.xqnqq.com/Article/46136.shtml
- http://http://map.read.usuhx.com/Article/058592.shtml
- http://http://map.read.usuhx.com/Article/52108.shtml
- http://http://map.read.usuhx.com/Article/78682.shtml
- http://http://map.mobile.xqnqq.com/Article/552057.shtml
- http://http://map.mobile.xqnqq.com/Article/671793.shtml
- http://http://map.read.usuhx.com/Article/029256.shtml
- http://http://map.mobile.xqnqq.com/Article/8145.shtml
- http://http://map.mobile.xqnqq.com/Article/23568.shtml
- http://http://map.read.usuhx.com/Article/973736.shtml
- http://http://map.read.usuhx.com/Article/86219.shtml
- http://http://map.mobile.xqnqq.com/Article/7703.shtml
- http://http://map.read.usuhx.com/Article/8643.shtml
- http://http://map.read.usuhx.com/Article/4791951.shtml
- http://http://map.read.usuhx.com/Article/6534.shtml
- http://http://map.mobile.xqnqq.com/Article/556660.shtml
- http://http://map.mobile.xqnqq.com/Article/5432372.shtml
- http://http://map.read.usuhx.com/Article/865079.shtml
- http://http://map.mobile.xqnqq.com/Article/15315.shtml
- http://http://map.mobile.xqnqq.com/Article/271720.shtml
- http://http://map.read.usuhx.com/Article/6847342.shtml
- http://http://map.read.usuhx.com/Article/458989.shtml
- http://http://map.read.usuhx.com/Article/2287149.shtml
- http://http://map.mobile.xqnqq.com/Article/80637.shtml
- http://http://map.mobile.xqnqq.com/Article/0324.shtml
- http://http://map.mobile.xqnqq.com/Article/93666.shtml
- http://http://map.mobile.xqnqq.com/Article/73972.shtml
- http://http://map.mobile.xqnqq.com/Article/3261.shtml
- http://http://map.read.usuhx.com/Article/9858434.shtml
- http://http://map.mobile.xqnqq.com/Article/717609.shtml
- http://http://map.mobile.xqnqq.com/Article/98339.shtml
- http://http://map.mobile.xqnqq.com/Article/250675.shtml
- http://http://map.mobile.xqnqq.com/Article/1287120.shtml
- http://http://map.mobile.xqnqq.com/Article/2172887.shtml
- http://http://map.mobile.xqnqq.com/Article/25597.shtml
- http://http://map.mobile.xqnqq.com/Article/5840.shtml
- http://http://map.read.usuhx.com/Article/33551.shtml
- http://http://map.read.usuhx.com/Article/2599623.shtml
- http://http://map.mobile.xqnqq.com/Article/2709111.shtml
- http://http://map.mobile.xqnqq.com/Article/67922.shtml
- http://http://map.mobile.xqnqq.com/Article/8799.shtml
- http://http://map.read.usuhx.com/Article/1796570.shtml
- http://http://map.mobile.xqnqq.com/Article/091617.shtml
- http://http://map.mobile.xqnqq.com/Article/6768725.shtml
- http://http://map.read.usuhx.com/Article/151224.shtml
- http://http://map.mobile.xqnqq.com/Article/98215.shtml
- http://http://map.read.usuhx.com/Article/25641.shtml
- http://http://map.read.usuhx.com/Article/96054.shtml
- http://http://map.mobile.xqnqq.com/Article/0686667.shtml
- http://http://map.mobile.xqnqq.com/Article/968659.shtml
- http://http://map.read.usuhx.com/Article/1086.shtml
- http://http://map.read.usuhx.com/Article/584013.shtml
- http://http://map.mobile.xqnqq.com/Article/2630.shtml
- http://http://map.mobile.xqnqq.com/Article/8401951.shtml
- http://http://map.read.usuhx.com/Article/2704.shtml
- http://http://map.mobile.xqnqq.com/Article/29408.shtml
- http://http://map.read.usuhx.com/Article/412053.shtml
- http://http://map.read.usuhx.com/Article/0413909.shtml
- http://http://map.mobile.xqnqq.com/Article/812844.shtml
- http://http://map.read.usuhx.com/Article/2543.shtml
- http://http://map.read.usuhx.com/Article/8215022.shtml
- http://http://map.mobile.xqnqq.com/Article/530381.shtml
- http://http://map.mobile.xqnqq.com/Article/4161.shtml
- http://http://map.mobile.xqnqq.com/Article/4066.shtml
- http://http://map.mobile.xqnqq.com/Article/4398.shtml
- http://http://map.read.usuhx.com/Article/2803734.shtml
- http://http://map.read.usuhx.com/Article/1337356.shtml
- http://http://map.read.usuhx.com/Article/0258646.shtml
- http://http://map.mobile.xqnqq.com/Article/36253.shtml
- http://http://map.read.usuhx.com/Article/26010.shtml
- http://http://map.read.usuhx.com/Article/602695.shtml
- http://http://map.read.usuhx.com/Article/7021.shtml
- http://http://map.read.usuhx.com/Article/139586.shtml
- http://http://map.read.usuhx.com/Article/4421.shtml
- http://http://map.mobile.xqnqq.com/Article/8936620.shtml
- http://http://map.mobile.xqnqq.com/Article/8100.shtml
- http://http://map.mobile.xqnqq.com/Article/7376.shtml
- http://http://map.mobile.xqnqq.com/Article/13274.shtml
- http://http://map.mobile.xqnqq.com/Article/0551.shtml
- http://http://map.mobile.xqnqq.com/Article/217937.shtml
- http://http://map.read.usuhx.com/Article/9132.shtml
- http://http://map.read.usuhx.com/Article/222037.shtml
- http://http://map.read.usuhx.com/Article/3105.shtml
- http://http://map.read.usuhx.com/Article/030682.shtml
- http://http://map.mobile.xqnqq.com/Article/387247.shtml
- http://http://map.mobile.xqnqq.com/Article/1824.shtml
- http://http://map.read.usuhx.com/Article/89096.shtml
- http://http://map.mobile.xqnqq.com/Article/6424362.shtml
- http://http://map.read.usuhx.com/Article/1211.shtml
- http://http://map.mobile.xqnqq.com/Article/996517.shtml
- http://http://map.mobile.xqnqq.com/Article/137197.shtml
- http://http://map.read.usuhx.com/Article/796180.shtml
- http://http://map.read.usuhx.com/Article/14814.shtml
- http://http://map.read.usuhx.com/Article/0564243.shtml
- http://http://map.read.usuhx.com/Article/1603.shtml
- http://http://map.mobile.xqnqq.com/Article/30588.shtml
- http://http://map.mobile.xqnqq.com/Article/1222731.shtml
- http://http://map.mobile.xqnqq.com/Article/561253.shtml
- http://http://map.mobile.xqnqq.com/Article/5849.shtml
- http://http://map.mobile.xqnqq.com/Article/4608.shtml
- http://http://map.mobile.xqnqq.com/Article/5769.shtml
- http://http://map.read.usuhx.com/Article/8647362.shtml
- http://http://map.mobile.xqnqq.com/Article/0912600.shtml
- http://http://map.read.usuhx.com/Article/86709.shtml
- http://http://map.read.usuhx.com/Article/85912.shtml
- http://http://map.read.usuhx.com/Article/6321.shtml
- http://http://map.read.usuhx.com/Article/9652.shtml
- http://http://map.mobile.xqnqq.com/Article/409254.shtml
- http://http://map.read.usuhx.com/Article/602902.shtml
- http://http://map.read.usuhx.com/Article/4860.shtml
- http://http://map.mobile.xqnqq.com/Article/35706.shtml
- http://http://map.mobile.xqnqq.com/Article/897737.shtml
- http://http://map.mobile.xqnqq.com/Article/069629.shtml
- http://http://map.read.usuhx.com/Article/4691.shtml
- http://http://map.read.usuhx.com/Article/26881.shtml
- http://http://map.mobile.xqnqq.com/Article/85474.shtml
- http://http://map.read.usuhx.com/Article/0203.shtml
- http://http://map.mobile.xqnqq.com/Article/4216.shtml
- http://http://map.mobile.xqnqq.com/Article/321869.shtml
- http://http://map.mobile.xqnqq.com/Article/80145.shtml
- http://http://map.read.usuhx.com/Article/1676.shtml
- http://http://map.mobile.xqnqq.com/Article/2922078.shtml
- http://http://map.mobile.xqnqq.com/Article/954661.shtml
- http://http://map.mobile.xqnqq.com/Article/6119378.shtml
- http://http://map.read.usuhx.com/Article/71429.shtml
- http://http://map.mobile.xqnqq.com/Article/2202.shtml
- http://http://map.mobile.xqnqq.com/Article/69430.shtml
- http://http://map.read.usuhx.com/Article/5662.shtml
- http://http://map.mobile.xqnqq.com/Article/870378.shtml
- http://http://map.read.usuhx.com/Article/46248.shtml
- http://http://map.mobile.xqnqq.com/Article/9295732.shtml
- http://http://map.mobile.xqnqq.com/Article/2762.shtml
- http://http://map.mobile.xqnqq.com/Article/816612.shtml
- http://http://map.read.usuhx.com/Article/2691.shtml
- http://http://map.mobile.xqnqq.com/Article/123029.shtml
- http://http://map.mobile.xqnqq.com/Article/5276668.shtml
- http://http://map.read.usuhx.com/Article/0934845.shtml
- http://http://map.mobile.xqnqq.com/Article/3351.shtml
- http://http://map.mobile.xqnqq.com/Article/8416.shtml
- http://http://map.read.usuhx.com/Article/4054.shtml
- http://http://map.mobile.xqnqq.com/Article/3958078.shtml
- http://http://map.mobile.xqnqq.com/Article/0352592.shtml
- http://http://map.mobile.xqnqq.com/Article/31651.shtml
- http://http://map.read.usuhx.com/Article/3059.shtml
- http://http://map.read.usuhx.com/Article/5719159.shtml
- http://http://map.read.usuhx.com/Article/7316.shtml
- http://http://map.mobile.xqnqq.com/Article/317200.shtml
- http://http://map.read.usuhx.com/Article/60051.shtml
- http://http://map.mobile.xqnqq.com/Article/721368.shtml
- http://http://map.read.usuhx.com/Article/788522.shtml
- http://http://map.read.usuhx.com/Article/790637.shtml
- http://http://map.read.usuhx.com/Article/183796.shtml
- http://http://map.read.usuhx.com/Article/46874.shtml
- http://http://map.mobile.xqnqq.com/Article/0442661.shtml
- http://http://map.mobile.xqnqq.com/Article/65685.shtml
- http://http://map.read.usuhx.com/Article/96798.shtml
- http://http://map.read.usuhx.com/Article/2862.shtml
- http://http://map.mobile.xqnqq.com/Article/1610109.shtml

## 项目结构

```
weblink-archive-gateway/
├── cli.py                      # 命令行入口，整合导入、索引、服务启动功能
├── requirements.txt            # Python 依赖清单
├── README.md                   # 项目说明文档
├── LICENSE                     # MIT 许可证文件
├── config/
│   ├── settings.py             # 全局配置项（批次编号、数据目录、服务端口）
│   └── sources.py              # 内容源适配器注册表（定义可解析的域名列表）
├── core/
│   ├── __init__.py
│   ├── parser.py               # 链接解析器，提取域名与文章ID
│   ├── indexer.py              # 索引生成器，构建内存索引与统计信息
│   ├── loader.py               # 批量加载器，支持从文本文件或直接列表导入
│   └── exporter.py             # 导出器，将链接列表输出为 Markdown / JSON
├── adapters/
│   ├── __init__.py
│   ├── base.py                 # 适配器基类，定义标准化接口
│   ├── usuhx.py                # map.read.usuhx.com 域名适配器
│   └── xqnqq.py                # map.mobile.xqnqq.com 域名适配器
├── data/
│   ├── batches/                # 按批次存储原始链接数据
│   │   └── batch_63.txt        # 第63批次原始链接文件
│   └── indices/                # 生成的索引缓存
│       └── batch_63_index.json # 第63批次索引数据
├── tests/
│   ├── test_parser.py          # 解析器单元测试
│   ├── test_indexer.py         # 索引器单元测试
│   └── test_adapters.py        # 适配器集成测试
└── docs/
    ├── getting-started.md      # 快速入门指南
    ├── batch-management.md     # 批次管理操作说明
    ├── architecture.md         # 系统架构设计文档
    └── custom-source.md        # 自定义内容源扩展指南
```

## 贡献指南

1. 查阅项目 Issue 列表，选择未被认领的 bug 修复或功能增强任务。对于新功能建议，请先创建讨论 Issue 与维护者沟通设计思路。

2. Fork 本仓库，在本地开发分支上完成代码修改。提交前请确保所有现有单元测试通过，并为新增代码编写对应的测试用例。

3. 遵循 PEP 8 代码风格规范，提交信息采用语义化格式（类型: 简短描述），类型包括 feat、fix、docs、refactor、test 等。

4. 发起 Pull Request 至 main 分支，在 PR 描述中清晰说明变更内容、影响范围以及测试覆盖情况。PR 需获得至少一位维护者的代码审核批准。

5. 若涉及新增内容源适配器，请同时更新 docs/custom-source.md 文档，提供新适配器的配置示例与使用说明。

## 常见问题

Q: 系统是否可以处理非 shtml 后缀的链接，例如普通 html 或 php 页面？

A: 当前版本的链接解析器仅针对 shtml 后缀进行默认匹配，但适配器接口允许覆盖匹配规则。用户可通过继承 base.py 中的 BaseAdapter 类，重写 match 方法以支持其他后缀格式。后续版本将提供更灵活的正则表达式配置。

Q: 导入大批量链接时，系统性能如何？

A: 单批次设计容量为 500 条链接以内，第63批次共250条链接属于常规规模。解析与索引生成过程为纯内存操作，通常在毫秒级完成。若需处理万级链接，建议分批导入并利用 exporter 模块生成静态文件，避免一次性加载全部数据。

Q: 如何更新已导入批次的链接信息？

A: 系统当前不支持直接更新已导入批次中的单条链接。如需修正，建议重新生成批次文件并执行导入覆盖操作（使用 --force 选项）。更细粒度的编辑功能已在后续版本规划中。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
