# WebMap 技术文章索引集

WebMap 是一个面向开发者和技术研究人员的结构化外链与技术文章资源汇总项目。该项目系统性地收录来自 map.mobile.xqnqq.com 与 map.read.usuhx.com 两个技术内容源的文章链接，按照文章编号与来源域名进行规范化归集，形成可检索、可扩展的技术文献索引库。WebMap 适用于需要快速定位特定技术文章、进行批量链接整理、以及构建自定义技术阅读列表的场景。项目本身不存储文章内容，仅提供链接索引与分类框架，便于团队内部共享或集成至自动化内容采集流水线。

## 功能概览

**链接按来源域名自动分组** 项目将全部收录链接按照 map.mobile.xqnqq.com 与 map.read.usuhx.com 两个域名分别归类，便于用户按站点进行定向浏览。

**文章编号快速检索** 每条链接均保留原始 URL 中的文章编号（Article/ 后的数字序列），支持通过编号进行精确匹配与定位。

**批量链接导出能力** 提供完整的链接清单，可一键复制用于批量下载、内容抓取或外链分析工具导入。

**无冗余存储设计** 项目仅维护 URL 索引，不缓存文章正文或资源文件，保持仓库轻量且避免版权风险。

**Markdown 纯文本格式** 所有文档采用标准 Markdown 书写，兼容 GitHub、GitLab、Gitee 等主流代码托管平台渲染。

**定期更新占位机制** 项目结构预留新增链接的插入位置，支持通过脚本自动追加最新文章链接。

**文档导航分层体系** 从入门概览到深度配置提供四层文档索引，覆盖不同使用深度的需求。

**ASCII 目录树清晰展示** 项目根目录与子目录结构以树形图呈现，每个目录附带功能注释，降低新贡献者上手成本。

## 应用场景

技术团队内部知识库构建。团队可将 WebMap 作为基础索引，定期从两个源站点抓取新文章链接，结合内部标签系统形成定制化技术文库。

个人开发者批量阅读管理。开发者可通过本项目的链接清单，一次性导出所有文章地址，导入至 Pocket、Instapaper 或 Wallabag 等稍后阅读工具，实现集中式技术阅读规划。

自动化内容采集管道前置环节。数据工程团队可将本项目链接清单作为爬虫任务输入，按域名和编号分批抓取文章元数据（标题、发布时间、正文摘要），用于后续的文本分析或推荐系统训练。

## 快速开始

```bash
# 克隆仓库到本地
git clone https://github.com/webmap-index/webmap.git

# 进入项目根目录
cd webmap

# 安装依赖（项目仅需 Python 3 标准库 + pandas）
pip install pandas

# 运行链接整理脚本，生成分类 CSV 与更新 README 资源列表
python scripts/build_index.py --input sources/raw_links.txt --output dist/

# 启动本地静态预览服务（可选）
python -m http.server 8000
```

## 安装要求

| 依赖项 | 必需版本 | 说明 |
|--------|----------|------|
| Python | 3.8 及以上 | 用于运行链接整理与校验脚本 |
| pandas | 1.5.0 及以上 | 处理链接表格去重与排序 |
| git | 2.25 及以上 | 克隆仓库与提交更新 |
| 操作系统 | Linux / macOS / Windows | 跨平台支持，路径分隔符已做兼容 |
| 网络连接 | 任意公网环境 | 用于访问原始文章链接，非本地运行必需 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 入门 | docs/quick_start.md | 项目是什么、如何快速获取所有链接、如何导出清单 |
| 操作 | docs/usage_guide.md | 如何按域名筛选、如何按编号查找、如何导入第三方阅读工具 |
| 进阶 | docs/contribution_workflow.md | 如何新增链接、如何更新索引、如何提交拉取请求 |
| 配置 | docs/configuration.md | 如何调整排序规则、如何修改输出格式（CSV / JSON / Markdown） |

## 资源列表

- http://http://map.mobile.xqnqq.com/Article/3304791.shtml
- http://http://map.read.usuhx.com/Article/4215.shtml
- http://http://map.read.usuhx.com/Article/44498.shtml
- http://http://map.mobile.xqnqq.com/Article/79751.shtml
- http://http://map.read.usuhx.com/Article/7768989.shtml
- http://http://map.mobile.xqnqq.com/Article/8707.shtml
- http://http://map.mobile.xqnqq.com/Article/8252.shtml
- http://http://map.read.usuhx.com/Article/4939.shtml
- http://http://map.read.usuhx.com/Article/01858.shtml
- http://http://map.mobile.xqnqq.com/Article/2280327.shtml
- http://http://map.mobile.xqnqq.com/Article/5790.shtml
- http://http://map.mobile.xqnqq.com/Article/956242.shtml
- http://http://map.read.usuhx.com/Article/24736.shtml
- http://http://map.read.usuhx.com/Article/78168.shtml
- http://http://map.read.usuhx.com/Article/74036.shtml
- http://http://map.read.usuhx.com/Article/0756979.shtml
- http://http://map.read.usuhx.com/Article/562115.shtml
- http://http://map.read.usuhx.com/Article/17077.shtml
- http://http://map.mobile.xqnqq.com/Article/4661.shtml
- http://http://map.mobile.xqnqq.com/Article/0774300.shtml
- http://http://map.read.usuhx.com/Article/91773.shtml
- http://http://map.read.usuhx.com/Article/512795.shtml
- http://http://map.read.usuhx.com/Article/919286.shtml
- http://http://map.mobile.xqnqq.com/Article/1957.shtml
- http://http://map.read.usuhx.com/Article/27109.shtml
- http://http://map.read.usuhx.com/Article/5642031.shtml
- http://http://map.read.usuhx.com/Article/011447.shtml
- http://http://map.mobile.xqnqq.com/Article/80612.shtml
- http://http://map.mobile.xqnqq.com/Article/44406.shtml
- http://http://map.read.usuhx.com/Article/44115.shtml
- http://http://map.read.usuhx.com/Article/6652.shtml
- http://http://map.read.usuhx.com/Article/31172.shtml
- http://http://map.read.usuhx.com/Article/27899.shtml
- http://http://map.mobile.xqnqq.com/Article/708599.shtml
- http://http://map.mobile.xqnqq.com/Article/15885.shtml
- http://http://map.read.usuhx.com/Article/6590.shtml
- http://http://map.mobile.xqnqq.com/Article/20802.shtml
- http://http://map.mobile.xqnqq.com/Article/92451.shtml
- http://http://map.mobile.xqnqq.com/Article/578867.shtml
- http://http://map.mobile.xqnqq.com/Article/565693.shtml
- http://http://map.mobile.xqnqq.com/Article/47798.shtml
- http://http://map.read.usuhx.com/Article/5888.shtml
- http://http://map.read.usuhx.com/Article/9818388.shtml
- http://http://map.read.usuhx.com/Article/9403165.shtml
- http://http://map.read.usuhx.com/Article/605097.shtml
- http://http://map.mobile.xqnqq.com/Article/9788.shtml
- http://http://map.read.usuhx.com/Article/1985.shtml
- http://http://map.read.usuhx.com/Article/19401.shtml
- http://http://map.mobile.xqnqq.com/Article/2151.shtml
- http://http://map.mobile.xqnqq.com/Article/0350618.shtml
- http://http://map.mobile.xqnqq.com/Article/0189.shtml
- http://http://map.mobile.xqnqq.com/Article/0335.shtml
- http://http://map.mobile.xqnqq.com/Article/66494.shtml
- http://http://map.mobile.xqnqq.com/Article/0731404.shtml
- http://http://map.mobile.xqnqq.com/Article/0852.shtml
- http://http://map.mobile.xqnqq.com/Article/561169.shtml
- http://http://map.read.usuhx.com/Article/22156.shtml
- http://http://map.read.usuhx.com/Article/2692320.shtml
- http://http://map.read.usuhx.com/Article/05551.shtml
- http://http://map.read.usuhx.com/Article/244215.shtml
- http://http://map.mobile.xqnqq.com/Article/81626.shtml
- http://http://map.mobile.xqnqq.com/Article/4516263.shtml
- http://http://map.mobile.xqnqq.com/Article/64966.shtml
- http://http://map.read.usuhx.com/Article/0857.shtml
- http://http://map.read.usuhx.com/Article/0111.shtml
- http://http://map.read.usuhx.com/Article/20084.shtml
- http://http://map.read.usuhx.com/Article/78049.shtml
- http://http://map.read.usuhx.com/Article/04833.shtml
- http://http://map.mobile.xqnqq.com/Article/21394.shtml
- http://http://map.read.usuhx.com/Article/00399.shtml
- http://http://map.read.usuhx.com/Article/506084.shtml
- http://http://map.mobile.xqnqq.com/Article/23149.shtml
- http://http://map.mobile.xqnqq.com/Article/4707869.shtml
- http://http://map.mobile.xqnqq.com/Article/8383.shtml
- http://http://map.read.usuhx.com/Article/9765361.shtml
- http://http://map.read.usuhx.com/Article/750002.shtml
- http://http://map.mobile.xqnqq.com/Article/0688296.shtml
- http://http://map.mobile.xqnqq.com/Article/554492.shtml
- http://http://map.read.usuhx.com/Article/5576.shtml
- http://http://map.read.usuhx.com/Article/568373.shtml
- http://http://map.read.usuhx.com/Article/8183629.shtml
- http://http://map.read.usuhx.com/Article/942689.shtml
- http://http://map.mobile.xqnqq.com/Article/8654584.shtml
- http://http://map.read.usuhx.com/Article/1041.shtml
- http://http://map.mobile.xqnqq.com/Article/55798.shtml
- http://http://map.mobile.xqnqq.com/Article/0483.shtml
- http://http://map.read.usuhx.com/Article/3565.shtml
- http://http://map.read.usuhx.com/Article/9214929.shtml
- http://http://map.mobile.xqnqq.com/Article/8853.shtml
- http://http://map.mobile.xqnqq.com/Article/5000714.shtml
- http://http://map.mobile.xqnqq.com/Article/899765.shtml
- http://http://map.mobile.xqnqq.com/Article/5845.shtml
- http://http://map.mobile.xqnqq.com/Article/8795888.shtml
- http://http://map.mobile.xqnqq.com/Article/71612.shtml
- http://http://map.mobile.xqnqq.com/Article/2998872.shtml
- http://http://map.mobile.xqnqq.com/Article/46977.shtml
- http://http://map.mobile.xqnqq.com/Article/501274.shtml
- http://http://map.mobile.xqnqq.com/Article/6726780.shtml
- http://http://map.mobile.xqnqq.com/Article/011785.shtml
- http://http://map.read.usuhx.com/Article/234307.shtml
- http://http://map.read.usuhx.com/Article/685906.shtml
- http://http://map.mobile.xqnqq.com/Article/4555283.shtml
- http://http://map.read.usuhx.com/Article/37068.shtml
- http://http://map.mobile.xqnqq.com/Article/4733.shtml
- http://http://map.read.usuhx.com/Article/9661.shtml
- http://http://map.mobile.xqnqq.com/Article/0311.shtml
- http://http://map.mobile.xqnqq.com/Article/670639.shtml
- http://http://map.mobile.xqnqq.com/Article/885133.shtml
- http://http://map.read.usuhx.com/Article/72452.shtml
- http://http://map.read.usuhx.com/Article/6370.shtml
- http://http://map.read.usuhx.com/Article/97403.shtml
- http://http://map.read.usuhx.com/Article/20044.shtml
- http://http://map.mobile.xqnqq.com/Article/4286.shtml
- http://http://map.mobile.xqnqq.com/Article/215720.shtml
- http://http://map.read.usuhx.com/Article/340030.shtml
- http://http://map.mobile.xqnqq.com/Article/1111789.shtml
- http://http://map.mobile.xqnqq.com/Article/52121.shtml
- http://http://map.mobile.xqnqq.com/Article/350288.shtml
- http://http://map.mobile.xqnqq.com/Article/0822718.shtml
- http://http://map.read.usuhx.com/Article/7837548.shtml
- http://http://map.read.usuhx.com/Article/68284.shtml
- http://http://map.mobile.xqnqq.com/Article/183147.shtml
- http://http://map.read.usuhx.com/Article/5630821.shtml
- http://http://map.read.usuhx.com/Article/6073.shtml
- http://http://map.mobile.xqnqq.com/Article/144954.shtml
- http://http://map.mobile.xqnqq.com/Article/88933.shtml
- http://http://map.mobile.xqnqq.com/Article/1819.shtml
- http://http://map.mobile.xqnqq.com/Article/8349099.shtml
- http://http://map.mobile.xqnqq.com/Article/550533.shtml
- http://http://map.mobile.xqnqq.com/Article/3883.shtml
- http://http://map.mobile.xqnqq.com/Article/88048.shtml
- http://http://map.read.usuhx.com/Article/2140.shtml
- http://http://map.mobile.xqnqq.com/Article/4600275.shtml
- http://http://map.mobile.xqnqq.com/Article/8322.shtml
- http://http://map.read.usuhx.com/Article/7081.shtml
- http://http://map.read.usuhx.com/Article/1983158.shtml
- http://http://map.mobile.xqnqq.com/Article/92609.shtml
- http://http://map.read.usuhx.com/Article/873482.shtml
- http://http://map.mobile.xqnqq.com/Article/43375.shtml
- http://http://map.read.usuhx.com/Article/1803.shtml
- http://http://map.mobile.xqnqq.com/Article/8077.shtml
- http://http://map.mobile.xqnqq.com/Article/017701.shtml
- http://http://map.read.usuhx.com/Article/17039.shtml
- http://http://map.mobile.xqnqq.com/Article/888172.shtml
- http://http://map.read.usuhx.com/Article/2350.shtml
- http://http://map.read.usuhx.com/Article/36519.shtml
- http://http://map.read.usuhx.com/Article/7558.shtml
- http://http://map.read.usuhx.com/Article/243245.shtml
- http://http://map.mobile.xqnqq.com/Article/4474.shtml
- http://http://map.read.usuhx.com/Article/5220.shtml
- http://http://map.mobile.xqnqq.com/Article/2067545.shtml
- http://http://map.mobile.xqnqq.com/Article/7731134.shtml
- http://http://map.read.usuhx.com/Article/71533.shtml
- http://http://map.mobile.xqnqq.com/Article/15098.shtml
- http://http://map.mobile.xqnqq.com/Article/842294.shtml
- http://http://map.mobile.xqnqq.com/Article/71594.shtml
- http://http://map.mobile.xqnqq.com/Article/945960.shtml
- http://http://map.mobile.xqnqq.com/Article/0981.shtml
- http://http://map.mobile.xqnqq.com/Article/0845121.shtml
- http://http://map.mobile.xqnqq.com/Article/3501.shtml
- http://http://map.mobile.xqnqq.com/Article/06885.shtml
- http://http://map.read.usuhx.com/Article/58394.shtml
- http://http://map.read.usuhx.com/Article/794108.shtml
- http://http://map.mobile.xqnqq.com/Article/67995.shtml
- http://http://map.mobile.xqnqq.com/Article/418221.shtml
- http://http://map.mobile.xqnqq.com/Article/8060.shtml
- http://http://map.mobile.xqnqq.com/Article/08570.shtml
- http://http://map.mobile.xqnqq.com/Article/3728.shtml
- http://http://map.mobile.xqnqq.com/Article/297505.shtml
- http://http://map.mobile.xqnqq.com/Article/9011812.shtml
- http://http://map.read.usuhx.com/Article/6765.shtml
- http://http://map.read.usuhx.com/Article/486589.shtml
- http://http://map.mobile.xqnqq.com/Article/876200.shtml
- http://http://map.read.usuhx.com/Article/5355063.shtml
- http://http://map.read.usuhx.com/Article/08765.shtml
- http://http://map.read.usuhx.com/Article/228632.shtml
- http://http://map.read.usuhx.com/Article/81060.shtml
- http://http://map.mobile.xqnqq.com/Article/561004.shtml
- http://http://map.read.usuhx.com/Article/659498.shtml
- http://http://map.read.usuhx.com/Article/87392.shtml
- http://http://map.read.usuhx.com/Article/333853.shtml
- http://http://map.read.usuhx.com/Article/3138.shtml
- http://http://map.read.usuhx.com/Article/8791599.shtml
- http://http://map.mobile.xqnqq.com/Article/5966211.shtml
- http://http://map.mobile.xqnqq.com/Article/20968.shtml
- http://http://map.mobile.xqnqq.com/Article/1259379.shtml
- http://http://map.mobile.xqnqq.com/Article/4198961.shtml
- http://http://map.mobile.xqnqq.com/Article/6101148.shtml
- http://http://map.read.usuhx.com/Article/9882782.shtml
- http://http://map.read.usuhx.com/Article/5911637.shtml
- http://http://map.mobile.xqnqq.com/Article/6369.shtml
- http://http://map.read.usuhx.com/Article/10808.shtml
- http://http://map.mobile.xqnqq.com/Article/379664.shtml
- http://http://map.read.usuhx.com/Article/455658.shtml
- http://http://map.mobile.xqnqq.com/Article/8989.shtml
- http://http://map.mobile.xqnqq.com/Article/1740.shtml
- http://http://map.read.usuhx.com/Article/1705.shtml
- http://http://map.read.usuhx.com/Article/7471297.shtml
- http://http://map.read.usuhx.com/Article/20573.shtml
- http://http://map.mobile.xqnqq.com/Article/38652.shtml
- http://http://map.mobile.xqnqq.com/Article/95037.shtml
- http://http://map.read.usuhx.com/Article/6828575.shtml
- http://http://map.read.usuhx.com/Article/6839067.shtml
- http://http://map.read.usuhx.com/Article/9063.shtml
- http://http://map.read.usuhx.com/Article/6459.shtml
- http://http://map.read.usuhx.com/Article/544813.shtml
- http://http://map.mobile.xqnqq.com/Article/0624.shtml
- http://http://map.mobile.xqnqq.com/Article/7593063.shtml
- http://http://map.read.usuhx.com/Article/1496.shtml
- http://http://map.mobile.xqnqq.com/Article/090943.shtml
- http://http://map.mobile.xqnqq.com/Article/817245.shtml
- http://http://map.mobile.xqnqq.com/Article/542016.shtml
- http://http://map.mobile.xqnqq.com/Article/8745.shtml
- http://http://map.mobile.xqnqq.com/Article/5441001.shtml
- http://http://map.mobile.xqnqq.com/Article/87178.shtml
- http://http://map.read.usuhx.com/Article/0883451.shtml
- http://http://map.mobile.xqnqq.com/Article/797360.shtml
- http://http://map.read.usuhx.com/Article/031901.shtml
- http://http://map.mobile.xqnqq.com/Article/1044785.shtml
- http://http://map.mobile.xqnqq.com/Article/7311.shtml
- http://http://map.mobile.xqnqq.com/Article/597368.shtml
- http://http://map.read.usuhx.com/Article/02081.shtml
- http://http://map.mobile.xqnqq.com/Article/0853.shtml
- http://http://map.mobile.xqnqq.com/Article/7652.shtml
- http://http://map.read.usuhx.com/Article/2667.shtml
- http://http://map.mobile.xqnqq.com/Article/569266.shtml
- http://http://map.read.usuhx.com/Article/529414.shtml
- http://http://map.mobile.xqnqq.com/Article/01734.shtml
- http://http://map.read.usuhx.com/Article/9929890.shtml
- http://http://map.read.usuhx.com/Article/9406863.shtml
- http://http://map.mobile.xqnqq.com/Article/337624.shtml
- http://http://map.mobile.xqnqq.com/Article/87565.shtml
- http://http://map.read.usuhx.com/Article/39684.shtml
- http://http://map.read.usuhx.com/Article/1273899.shtml
- http://http://map.mobile.xqnqq.com/Article/1523.shtml
- http://http://map.read.usuhx.com/Article/8030.shtml
- http://http://map.mobile.xqnqq.com/Article/66879.shtml
- http://http://map.mobile.xqnqq.com/Article/458051.shtml
- http://http://map.mobile.xqnqq.com/Article/7134608.shtml
- http://http://map.mobile.xqnqq.com/Article/909144.shtml
- http://http://map.read.usuhx.com/Article/292142.shtml
- http://http://map.mobile.xqnqq.com/Article/3329.shtml
- http://http://map.read.usuhx.com/Article/96214.shtml
- http://http://map.mobile.xqnqq.com/Article/85986.shtml
- http://http://map.read.usuhx.com/Article/7686797.shtml
- http://http://map.mobile.xqnqq.com/Article/1586.shtml
- http://http://map.read.usuhx.com/Article/98139.shtml
- http://http://map.mobile.xqnqq.com/Article/011424.shtml
- http://http://map.mobile.xqnqq.com/Article/2576.shtml
- http://http://map.mobile.xqnqq.com/Article/8174494.shtml

## 项目结构

```
webmap/
├── README.md                       # 项目首页与完整链接清单
├── LICENSE                         # MIT 许可证文件
├── .gitignore                      # 忽略构建产物与临时文件
├── sources/                        # 原始数据输入目录
│   └── raw_links.txt               # 人工或脚本收集的原始链接列表
├── scripts/                        # 可执行工具脚本目录
│   ├── build_index.py              # 主构建脚本，生成分类索引与统计
│   ├── validator.py                # URL 格式校验与去重模块
│   └── exporter.py                 # 导出为 CSV / JSON / HTML 的转换器
├── dist/                           # 构建输出目录（不纳入版本控制）
│   ├── index.csv                   # 按域名和编号排序的表格数据
│   ├── index.json                  # 结构化 JSON 格式索引
│   └── summary.txt                 # 链接总数与域名分布统计摘要
├── docs/                           # 详细文档目录
│   ├── quick_start.md              # 5 分钟快速上手指南
│   ├── usage_guide.md              # 日常使用操作说明
│   ├── contribution_workflow.md    # 贡献者提交流程规范
│   └── configuration.md            # 脚本参数与输出格式定制
└── tests/                          # 单元测试与集成测试目录
    ├── test_validator.py           # 链接校验逻辑测试
    └── test_exporter.py            # 导出格式正确性测试
```

## 贡献指南

1. 复刻本仓库至个人账户，克隆复刻后的仓库到本地开发环境，配置上游远程分支以便同步主仓库更新。

2. 在 sources/raw_links.txt 末尾追加新增链接，每行一个 URL，确保链接不重复且属于两个指定域名之一。若添加批量链接，建议先运行 validator.py 进行格式检查。

3. 执行 scripts/build_index.py 脚本，观察控制台输出无错误，确认 dist/ 目录下的 CSV 与 JSON 文件正确反映了新增链接。

4. 提交变更并推送至复刻仓库，提交信息格式建议为 "feat: add N new links from [domain]" 或 "fix: correct malformed URL for Article/xxxxx"。

5. 通过 GitHub 或 Gitee 平台发起拉取请求至主仓库的 main 分支，等待项目维护者审核合并。合并前需确保拉取请求不引入重复链接且文档章节同步更新。

## 常见问题

Q: 项目是否存储文章正文或图片资源？
A: 不存储。WebMap 仅维护文章链接索引，不缓存任何正文、图片、PDF 或其他附属资源。用户访问链接时直接跳转至原始来源站点。

Q: 如何快速查找特定文章编号对应的完整链接？
A: 可使用 grep 命令在 README.md 或 sources/raw_links.txt 中搜索编号，例如 grep "3304791" README.md。亦可在 dist/index.csv 中使用 Excel 或 pandas 进行筛选。

Q: 如果原始链接失效或返回 404，项目会如何处理？
A: 项目本身不检测链接可用性。建议贡献者定期运行 scripts/validator.py 并配合第三方链接检查工具（如 wget --spider）扫描全部链接，发现失效链接后通过拉取请求将其从列表中移除或标注为失效状态。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
