# WebLink Navigator

WebLink Navigator 是一个面向技术研究者和信息分析人员的结构化外链资源聚合与导航系统。该项目通过人工筛选与自动化校验相结合的方式，对分散在多个内容源头的深度文章、技术文档及行业报告进行索引归类，旨在解决信息过载环境下高质量长尾内容难以被发现和回溯的问题。项目定位为轻量级的技术资料引用仓库，适用于需要快速定位特定编号文档或追溯信息原始出处的场景。

项目采用静态资源索引架构，不对原始内容进行转载或存贮，仅提供标准化的引用地址映射。所有收录的资源均按照采集批次、来源域名和文档编号进行规范化整理，确保每条链接具备可追溯性和唯一性。当前版本为核心索引库的第 28 批次，共计收录 250 个活跃资源链接。

## 功能概览

多源异构数据归一化：系统能够识别并标准化来自不同内容提供方的 URL 结构，将 mobile.xqnqq.com 与 read.usuhx.com 两类来源的文章链接统一纳入索引体系，屏蔽底层路径差异。

批次化资源管理：每批次资源以独立的清单文件形式存储，支持按批次编号（如 28/80）进行版本追溯和增量更新，便于长期维护和审计。

文档编号快速检索：基于文章路径中的数字 ID 构建倒排索引，用户可通过文档编号直接定位到对应的原始链接，无需遍历完整目录。

来源域名分类过滤：提供按来源域名（mobile.xqnqq.com 与 read.usuhx.com）筛选资源的功能，支持针对特定内容源头的聚焦阅读。

纯静态资源索引：系统不依赖数据库或后端服务，所有资源列表以 Markdown 或 JSON 格式存储于仓库中，可直接通过 HTTP 服务器进行访问。

链接存活状态标记：通过定期执行 HTTP HEAD 请求检测链接可用性，并在索引中标注失效链接，辅助用户判断资源的当前可访问状态。

原始链接直出模式：所有资源链接在输出时保持用户提交的原始格式，不添加协议前缀、不修改域名大小写、不附加尾部斜杠，确保引用路径的准确性和一致性。

## 应用场景

技术文档历史版本追溯：开发团队在查阅某项技术的早期设计文档时，可通过本项目的文档编号索引快速定位到存储在 read.usuhx.com 上的历史文章，避免在通用搜索引擎中面对大量无关结果。

移动端内容聚合阅读：内容运营人员需要汇总 mobile.xqnqq.com 上发布的系列技术解读文章时，可利用本项目的域名过滤功能一次性提取该来源的全部链接，形成定制化的阅读清单。

信息溯源与引用核查：学术研究者或技术博主在引用第三方资料时，可通过本项目的资源列表反向验证链接有效性，并获取标准化的引用格式，减少因链接变更导致的引用失效问题。

批量链接归档与备份规划：系统管理员在规划外部资源的本地镜像或备份策略时，可基于本项目输出的完整链接清单进行批量下载任务配置，提高归档操作的效率。

## 快速开始

以下指令可在 Linux 或 macOS 环境下完成项目的克隆、依赖安装与本地运行。

```bash
git clone https://github.com/weblink-navigator/weblink-navigator.git
cd weblink-navigator
pip install -r requirements.txt
python -m weblink_navigator.server --port 8080
```

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Python | 3.9 及以上 | 核心运行环境，用于提供静态文件服务与链接校验脚本 |
| pip | 22.0 及以上 | Python 包管理工具，用于安装项目依赖 |
| requests | 2.28.0 及以上 | 用于发送 HTTP 请求，执行链接存活状态检测 |
| markdown | 3.4.0 及以上 | 用于将资源索引的 Markdown 文件渲染为 HTML 页面 |
| click | 8.1.0 及以上 | 命令行接口框架，用于提供交互式管理命令 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 用户手册 | docs/user-guide.md | 如何使用本项目的索引功能进行资源检索与过滤 |
| 维护指南 | docs/maintainer-guide.md | 如何新增、更新或删除资源链接，以及如何管理批次 |
| 设计文档 | docs/architecture.md | 项目的整体架构设计、数据流转与扩展性考量 |
| 命令参考 | docs/commands.md | 所有 CLI 命令的详细参数说明与使用示例 |

## 资源列表

- http://http://www.read.usuhx.com/Article/7210166.shtml
- http://http://www.mobile.xqnqq.com/Article/60859.shtml
- http://http://www.mobile.xqnqq.com/Article/8307620.shtml
- http://http://www.read.usuhx.com/Article/474838.shtml
- http://http://www.mobile.xqnqq.com/Article/7767.shtml
- http://http://www.mobile.xqnqq.com/Article/5482835.shtml
- http://http://www.read.usuhx.com/Article/159959.shtml
- http://http://www.mobile.xqnqq.com/Article/8948.shtml
- http://http://www.read.usuhx.com/Article/118953.shtml
- http://http://www.read.usuhx.com/Article/653041.shtml
- http://http://www.mobile.xqnqq.com/Article/6582512.shtml
- http://http://www.read.usuhx.com/Article/33529.shtml
- http://http://www.read.usuhx.com/Article/91284.shtml
- http://http://www.mobile.xqnqq.com/Article/9598.shtml
- http://http://www.read.usuhx.com/Article/010766.shtml
- http://http://www.mobile.xqnqq.com/Article/7886.shtml
- http://http://www.read.usuhx.com/Article/744642.shtml
- http://http://www.read.usuhx.com/Article/1097340.shtml
- http://http://www.read.usuhx.com/Article/5549217.shtml
- http://http://www.mobile.xqnqq.com/Article/90402.shtml
- http://http://www.read.usuhx.com/Article/164800.shtml
- http://http://www.mobile.xqnqq.com/Article/250044.shtml
- http://http://www.mobile.xqnqq.com/Article/061369.shtml
- http://http://www.mobile.xqnqq.com/Article/923946.shtml
- http://http://www.mobile.xqnqq.com/Article/932298.shtml
- http://http://www.mobile.xqnqq.com/Article/9693.shtml
- http://http://www.read.usuhx.com/Article/338712.shtml
- http://http://www.read.usuhx.com/Article/69897.shtml
- http://http://www.read.usuhx.com/Article/122775.shtml
- http://http://www.mobile.xqnqq.com/Article/3379.shtml
- http://http://www.read.usuhx.com/Article/1326.shtml
- http://http://www.read.usuhx.com/Article/8957.shtml
- http://http://www.mobile.xqnqq.com/Article/9110852.shtml
- http://http://www.read.usuhx.com/Article/29379.shtml
- http://http://www.mobile.xqnqq.com/Article/3135495.shtml
- http://http://www.mobile.xqnqq.com/Article/10407.shtml
- http://http://www.mobile.xqnqq.com/Article/62746.shtml
- http://http://www.mobile.xqnqq.com/Article/02244.shtml
- http://http://www.mobile.xqnqq.com/Article/9669.shtml
- http://http://www.read.usuhx.com/Article/4432154.shtml
- http://http://www.read.usuhx.com/Article/3512247.shtml
- http://http://www.read.usuhx.com/Article/47658.shtml
- http://http://www.read.usuhx.com/Article/3462.shtml
- http://http://www.mobile.xqnqq.com/Article/5317.shtml
- http://http://www.read.usuhx.com/Article/6871783.shtml
- http://http://www.read.usuhx.com/Article/056771.shtml
- http://http://www.read.usuhx.com/Article/819952.shtml
- http://http://www.mobile.xqnqq.com/Article/281774.shtml
- http://http://www.read.usuhx.com/Article/0080.shtml
- http://http://www.mobile.xqnqq.com/Article/2134801.shtml
- http://http://www.mobile.xqnqq.com/Article/86513.shtml
- http://http://www.mobile.xqnqq.com/Article/936730.shtml
- http://http://www.mobile.xqnqq.com/Article/381705.shtml
- http://http://www.mobile.xqnqq.com/Article/1171316.shtml
- http://http://www.mobile.xqnqq.com/Article/7564.shtml
- http://http://www.mobile.xqnqq.com/Article/3400.shtml
- http://http://www.mobile.xqnqq.com/Article/7276897.shtml
- http://http://www.read.usuhx.com/Article/2813018.shtml
- http://http://www.mobile.xqnqq.com/Article/468989.shtml
- http://http://www.mobile.xqnqq.com/Article/8381.shtml
- http://http://www.mobile.xqnqq.com/Article/86169.shtml
- http://http://www.read.usuhx.com/Article/588530.shtml
- http://http://www.mobile.xqnqq.com/Article/550590.shtml
- http://http://www.read.usuhx.com/Article/4997.shtml
- http://http://www.mobile.xqnqq.com/Article/7089.shtml
- http://http://www.mobile.xqnqq.com/Article/511751.shtml
- http://http://www.read.usuhx.com/Article/1160.shtml
- http://http://www.read.usuhx.com/Article/9110.shtml
- http://http://www.mobile.xqnqq.com/Article/01471.shtml
- http://http://www.read.usuhx.com/Article/217148.shtml
- http://http://www.mobile.xqnqq.com/Article/760342.shtml
- http://http://www.mobile.xqnqq.com/Article/0065179.shtml
- http://http://www.read.usuhx.com/Article/64384.shtml
- http://http://www.mobile.xqnqq.com/Article/13911.shtml
- http://http://www.mobile.xqnqq.com/Article/809638.shtml
- http://http://www.mobile.xqnqq.com/Article/4309457.shtml
- http://http://www.read.usuhx.com/Article/3326139.shtml
- http://http://www.mobile.xqnqq.com/Article/633571.shtml
- http://http://www.read.usuhx.com/Article/6092.shtml
- http://http://www.read.usuhx.com/Article/2399498.shtml
- http://http://www.read.usuhx.com/Article/21700.shtml
- http://http://www.read.usuhx.com/Article/75393.shtml
- http://http://www.read.usuhx.com/Article/70406.shtml
- http://http://www.read.usuhx.com/Article/9416904.shtml
- http://http://www.read.usuhx.com/Article/1578746.shtml
- http://http://www.read.usuhx.com/Article/83167.shtml
- http://http://www.mobile.xqnqq.com/Article/3970.shtml
- http://http://www.mobile.xqnqq.com/Article/4721261.shtml
- http://http://www.mobile.xqnqq.com/Article/4032.shtml
- http://http://www.mobile.xqnqq.com/Article/88160.shtml
- http://http://www.mobile.xqnqq.com/Article/635743.shtml
- http://http://www.read.usuhx.com/Article/499575.shtml
- http://http://www.read.usuhx.com/Article/8357.shtml
- http://http://www.read.usuhx.com/Article/2559263.shtml
- http://http://www.mobile.xqnqq.com/Article/4080740.shtml
- http://http://www.mobile.xqnqq.com/Article/2296811.shtml
- http://http://www.mobile.xqnqq.com/Article/67017.shtml
- http://http://www.mobile.xqnqq.com/Article/700379.shtml
- http://http://www.mobile.xqnqq.com/Article/7175420.shtml
- http://http://www.mobile.xqnqq.com/Article/7394.shtml
- http://http://www.read.usuhx.com/Article/9864.shtml
- http://http://www.mobile.xqnqq.com/Article/01489.shtml
- http://http://www.read.usuhx.com/Article/23163.shtml
- http://http://www.mobile.xqnqq.com/Article/38140.shtml
- http://http://www.read.usuhx.com/Article/5535.shtml
- http://http://www.read.usuhx.com/Article/27106.shtml
- http://http://www.read.usuhx.com/Article/5082091.shtml
- http://http://www.mobile.xqnqq.com/Article/717531.shtml
- http://http://www.mobile.xqnqq.com/Article/848693.shtml
- http://http://www.mobile.xqnqq.com/Article/571077.shtml
- http://http://www.mobile.xqnqq.com/Article/3282.shtml
- http://http://www.read.usuhx.com/Article/254579.shtml
- http://http://www.read.usuhx.com/Article/455562.shtml
- http://http://www.mobile.xqnqq.com/Article/85170.shtml
- http://http://www.mobile.xqnqq.com/Article/87583.shtml
- http://http://www.read.usuhx.com/Article/86982.shtml
- http://http://www.read.usuhx.com/Article/0358315.shtml
- http://http://www.read.usuhx.com/Article/323910.shtml
- http://http://www.read.usuhx.com/Article/69180.shtml
- http://http://www.read.usuhx.com/Article/85467.shtml
- http://http://www.mobile.xqnqq.com/Article/4514.shtml
- http://http://www.mobile.xqnqq.com/Article/2503.shtml
- http://http://www.mobile.xqnqq.com/Article/58571.shtml
- http://http://www.mobile.xqnqq.com/Article/14486.shtml
- http://http://www.read.usuhx.com/Article/7775171.shtml
- http://http://www.mobile.xqnqq.com/Article/3635.shtml
- http://http://www.read.usuhx.com/Article/683692.shtml
- http://http://www.read.usuhx.com/Article/373695.shtml
- http://http://www.mobile.xqnqq.com/Article/25587.shtml
- http://http://www.mobile.xqnqq.com/Article/8820.shtml
- http://http://www.mobile.xqnqq.com/Article/392227.shtml
- http://http://www.mobile.xqnqq.com/Article/2589.shtml
- http://http://www.read.usuhx.com/Article/72204.shtml
- http://http://www.read.usuhx.com/Article/073324.shtml
- http://http://www.mobile.xqnqq.com/Article/1422600.shtml
- http://http://www.read.usuhx.com/Article/356414.shtml
- http://http://www.read.usuhx.com/Article/2559.shtml
- http://http://www.mobile.xqnqq.com/Article/6802105.shtml
- http://http://www.mobile.xqnqq.com/Article/21256.shtml
- http://http://www.mobile.xqnqq.com/Article/2940998.shtml
- http://http://www.read.usuhx.com/Article/816790.shtml
- http://http://www.mobile.xqnqq.com/Article/67408.shtml
- http://http://www.read.usuhx.com/Article/56482.shtml
- http://http://www.mobile.xqnqq.com/Article/96480.shtml
- http://http://www.read.usuhx.com/Article/63916.shtml
- http://http://www.mobile.xqnqq.com/Article/7915812.shtml
- http://http://www.read.usuhx.com/Article/39387.shtml
- http://http://www.read.usuhx.com/Article/2118042.shtml
- http://http://www.read.usuhx.com/Article/12795.shtml
- http://http://www.mobile.xqnqq.com/Article/42542.shtml
- http://http://www.mobile.xqnqq.com/Article/7733406.shtml
- http://http://www.read.usuhx.com/Article/0833.shtml
- http://http://www.read.usuhx.com/Article/04684.shtml
- http://http://www.read.usuhx.com/Article/52066.shtml
- http://http://www.mobile.xqnqq.com/Article/53932.shtml
- http://http://www.read.usuhx.com/Article/67047.shtml
- http://http://www.read.usuhx.com/Article/0203816.shtml
- http://http://www.mobile.xqnqq.com/Article/884615.shtml
- http://http://www.read.usuhx.com/Article/253242.shtml
- http://http://www.mobile.xqnqq.com/Article/111069.shtml
- http://http://www.read.usuhx.com/Article/28235.shtml
- http://http://www.read.usuhx.com/Article/564937.shtml
- http://http://www.mobile.xqnqq.com/Article/5167.shtml
- http://http://www.read.usuhx.com/Article/7944.shtml
- http://http://www.mobile.xqnqq.com/Article/822636.shtml
- http://http://www.read.usuhx.com/Article/077521.shtml
- http://http://www.mobile.xqnqq.com/Article/89413.shtml
- http://http://www.mobile.xqnqq.com/Article/7293367.shtml
- http://http://www.read.usuhx.com/Article/5958754.shtml
- http://http://www.mobile.xqnqq.com/Article/05965.shtml
- http://http://www.read.usuhx.com/Article/577451.shtml
- http://http://www.read.usuhx.com/Article/754351.shtml
- http://http://www.read.usuhx.com/Article/039787.shtml
- http://http://www.mobile.xqnqq.com/Article/7559859.shtml
- http://http://www.read.usuhx.com/Article/062218.shtml
- http://http://www.read.usuhx.com/Article/8823589.shtml
- http://http://www.read.usuhx.com/Article/0040.shtml
- http://http://www.read.usuhx.com/Article/64822.shtml
- http://http://www.mobile.xqnqq.com/Article/0558.shtml
- http://http://www.mobile.xqnqq.com/Article/56798.shtml
- http://http://www.mobile.xqnqq.com/Article/1987.shtml
- http://http://www.mobile.xqnqq.com/Article/0443205.shtml
- http://http://www.mobile.xqnqq.com/Article/1491088.shtml
- http://http://www.read.usuhx.com/Article/42133.shtml
- http://http://www.read.usuhx.com/Article/2038.shtml
- http://http://www.read.usuhx.com/Article/4583935.shtml
- http://http://www.read.usuhx.com/Article/5583902.shtml
- http://http://www.mobile.xqnqq.com/Article/0084.shtml
- http://http://www.mobile.xqnqq.com/Article/144681.shtml
- http://http://www.read.usuhx.com/Article/221760.shtml
- http://http://www.read.usuhx.com/Article/9138.shtml
- http://http://www.mobile.xqnqq.com/Article/059402.shtml
- http://http://www.mobile.xqnqq.com/Article/1006.shtml
- http://http://www.mobile.xqnqq.com/Article/8158913.shtml
- http://http://www.read.usuhx.com/Article/877985.shtml
- http://http://www.read.usuhx.com/Article/03895.shtml
- http://http://www.read.usuhx.com/Article/9103.shtml
- http://http://www.read.usuhx.com/Article/7985.shtml
- http://http://www.read.usuhx.com/Article/6438977.shtml
- http://http://www.mobile.xqnqq.com/Article/1252.shtml
- http://http://www.mobile.xqnqq.com/Article/2357.shtml
- http://http://www.read.usuhx.com/Article/62413.shtml
- http://http://www.mobile.xqnqq.com/Article/796774.shtml
- http://http://www.read.usuhx.com/Article/54687.shtml
- http://http://www.mobile.xqnqq.com/Article/083819.shtml
- http://http://www.mobile.xqnqq.com/Article/8125.shtml
- http://http://www.mobile.xqnqq.com/Article/165603.shtml
- http://http://www.mobile.xqnqq.com/Article/6746.shtml
- http://http://www.read.usuhx.com/Article/1520046.shtml
- http://http://www.read.usuhx.com/Article/889226.shtml
- http://http://www.read.usuhx.com/Article/7466227.shtml
- http://http://www.read.usuhx.com/Article/3503.shtml
- http://http://www.mobile.xqnqq.com/Article/5571.shtml
- http://http://www.read.usuhx.com/Article/8984623.shtml
- http://http://www.mobile.xqnqq.com/Article/1028410.shtml
- http://http://www.mobile.xqnqq.com/Article/1090002.shtml
- http://http://www.read.usuhx.com/Article/128405.shtml
- http://http://www.mobile.xqnqq.com/Article/487217.shtml
- http://http://www.mobile.xqnqq.com/Article/83268.shtml
- http://http://www.read.usuhx.com/Article/1404356.shtml
- http://http://www.mobile.xqnqq.com/Article/963459.shtml
- http://http://www.read.usuhx.com/Article/424996.shtml
- http://http://www.read.usuhx.com/Article/2292701.shtml
- http://http://www.read.usuhx.com/Article/528206.shtml
- http://http://www.read.usuhx.com/Article/10137.shtml
- http://http://www.read.usuhx.com/Article/589950.shtml
- http://http://www.read.usuhx.com/Article/519820.shtml
- http://http://www.mobile.xqnqq.com/Article/3602.shtml
- http://http://www.mobile.xqnqq.com/Article/893795.shtml
- http://http://www.mobile.xqnqq.com/Article/2261312.shtml
- http://http://www.mobile.xqnqq.com/Article/945384.shtml
- http://http://www.mobile.xqnqq.com/Article/79994.shtml
- http://http://www.mobile.xqnqq.com/Article/588697.shtml
- http://http://www.read.usuhx.com/Article/0448681.shtml
- http://http://www.read.usuhx.com/Article/8897768.shtml
- http://http://www.read.usuhx.com/Article/94887.shtml
- http://http://www.mobile.xqnqq.com/Article/339832.shtml
- http://http://www.mobile.xqnqq.com/Article/026234.shtml
- http://http://www.mobile.xqnqq.com/Article/93659.shtml
- http://http://www.mobile.xqnqq.com/Article/317476.shtml
- http://http://www.read.usuhx.com/Article/6585795.shtml
- http://http://www.read.usuhx.com/Article/28766.shtml
- http://http://www.read.usuhx.com/Article/75797.shtml
- http://http://www.mobile.xqnqq.com/Article/4710.shtml
- http://http://www.mobile.xqnqq.com/Article/7811.shtml
- http://http://www.mobile.xqnqq.com/Article/0706.shtml
- http://http://www.read.usuhx.com/Article/2470.shtml
- http://http://www.mobile.xqnqq.com/Article/21767.shtml
- http://http://www.mobile.xqnqq.com/Article/7297705.shtml
- http://http://www.mobile.xqnqq.com/Article/11804.shtml

## 项目结构

```
weblink-navigator/
├── src/                                  # 核心源代码目录
│   ├── weblink_navigator/                # 主包目录
│   │   ├── __init__.py                   # 包初始化与版本声明
│   │   ├── server.py                     # 内置HTTP服务入口，提供静态资源浏览
│   │   ├── indexer.py                    # 资源索引构建模块，负责解析清单并生成检索结构
│   │   ├── validator.py                  # 链接有效性校验模块，执行并发HEAD请求检测
│   │   └── cli.py                        # 命令行交互层，暴露管理命令
│   └── tests/                            # 单元测试与集成测试目录
│       ├── test_indexer.py               # 索引构建逻辑的测试用例
│       └── test_validator.py             # 链接校验功能的测试套件
├── data/                                 # 数据存储目录
│   ├── batches/                          # 批次资源清单存放处
│   │   ├── batch_028.json                # 第28批次结构化数据（JSON格式）
│   │   └── batch_028.md                  # 第28批次Markdown可读版本
│   └── cache/                            # 校验结果缓存目录
│       └── status_cache.db               # SQLite数据库，存储链接最近一次校验状态
├── docs/                                 # 项目文档目录
│   ├── user-guide.md                     # 用户使用手册
│   ├── maintainer-guide.md               # 维护者操作指南
│   ├── architecture.md                   # 系统架构设计文档
│   └── commands.md                       # CLI命令完整参考
├── scripts/                              # 辅助运维脚本目录
│   ├── validate_all.sh                   # 批量校验所有批次链接的Shell脚本
│   └── generate_index.sh                 # 重新生成静态索引页面的脚本
├── config/                               # 配置文件目录
│   └── settings.yaml                     # 全局配置（服务端口、校验超时、缓存策略等）
├── requirements.txt                      # Python依赖清单
├── setup.py                              # 项目安装与分发配置文件
└── README.md                             # 项目首页说明文档（本文件）
```

## 贡献指南

1. 资源新增提交流程：在 data/batches/ 目录下找到对应批次的 JSON 文件，按照现有对象结构添加新的链接条目，并确保文档编号在批次内唯一。提交 Pull Request 前需运行 scripts/validate_all.sh 进行本地校验。

2. 链接失效处理规范：若发现资源列表中存在无法访问的链接，请在对应条目的 status 字段中标记为 inactive，并在 notes 字段中记录检测时间与HTTP状态码。不直接删除链接，以保持历史索引的完整性。

3. 文档更新要求：任何对核心功能（索引构建、链接校验、服务启动）的代码修改，必须同步更新 docs/ 目录下的对应文档，并在 Pull Request 描述中指明文档变更范围。

4. 提交信息格式：Commit 消息需遵循语义化提交规范，使用 feat:、fix:、docs:、chore: 等前缀，并在正文中简要描述变更目的与影响范围。Pull Request 标题需包含关联的批次编号或功能模块名称。

5. 测试覆盖标准：新增或修改的代码需在 src/tests/ 目录下补充对应的单元测试用例，确保核心函数的行覆盖率不低于百分之八十。CI 流水线将自动执行测试套件。

## 常见问题

Q: 资源列表中的链接为什么包含 http://http:// 这样的重复协议前缀？
A: 这是用户提交数据时携带的原始格式。本项目遵循严格原样输出原则，不对链接进行任何格式修正，以保证与用户提供的数据完全一致。使用这些链接时，建议手动去除多余的 http:// 前缀，或使用浏览器的自动地址补全功能。

Q: 如何快速查找某个特定文档编号对应的链接？
A: 可以使用 grep 命令行工具在资源列表中进行搜索，例如 grep "7210166" README.md。也可以通过 data/batches/batch_028.json 文件中的数字ID字段进行程序化检索。

Q: 项目的链接有效性校验频率是多久？
A: 默认配置下，scripts/validate_all.sh 脚本每日凌晨执行一次全量校验。结果缓存于 data/cache/status_cache.db 中，可通过运行 python -m weblink_navigator.cli show-status 命令查看最新的各链接状态汇总。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
