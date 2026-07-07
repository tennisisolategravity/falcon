# LinkMap 技术资源导航

LinkMap 是一个面向开发者、技术研究人员与运维工程师的分布式技术文档与文章聚合导航系统。该项目旨在解决技术资料分散、难以检索、缺乏结构化组织的问题，通过自动化的链接采集与分类机制，将散落在多个内容源的高质量技术文章进行统一归集与展示。LinkMap 本身不存储任何内容，仅作为技术外链的索引与导航层，帮助技术团队快速定位到特定领域的问题解答与实现参考。

项目定位为轻量级、只读化的技术资源网关，适用于个人开发者构建知识库、技术团队统一文档入口、以及运维人员快速查阅故障处理手册等场景。LinkMap 不依赖数据库，采用静态站点生成方式，所有链接索引基于配置文件与目录结构进行组织，支持通过 Nginx 或 Apache 直接部署，亦可集成至现有的 CI/CD 流水线中实现自动化更新。

## 功能概览

- 多源链接聚合：支持从多个内容域名自动采集文章链接，当前已接入 read.usuhx.com 与 mobile.xqnqq.com 两大技术文档源，覆盖运维、开发、网络工程等多个技术方向。

- 分类索引体系：基于文章 URL 路径与编号规则，自动生成按主题、按发布时间、按文章类型的三级索引目录，便于用户按需浏览。

- 全文检索支持：集成静态化全文检索能力，用户可通过关键词快速定位到包含特定术语或问题描述的文章链接。

- 链接状态检测：提供定期的链接可达性检测机制，自动标记不可访问的链接，确保导航资源的有效性与可靠性。

- 响应式展示层：前端展示层基于主流 CSS 框架构建，适配桌面端与移动端浏览，支持深色模式与字体缩放辅助功能。

- 批量导入导出：支持通过 CSV 或 YAML 格式批量导入链接清单，亦可一键导出当前全部索引为 Markdown 或 JSON 格式，便于与其他工具集成。

- 访问统计看板：内置基于日志分析的轻量级访问统计模块，展示热门文章、来源域名分布及每日请求趋势。

## 应用场景

- 技术团队内部知识库入口：技术 Leader 可将 LinkMap 部署为团队默认的文档起始页，将所有常用的技术手册、故障处理记录、架构设计文档的链接统一收录，新人入职时仅需记住一个入口地址即可获取全部参考资料。

- 运维故障排查快速通道：运维工程师在面对线上故障时，可通过 LinkMap 的检索功能快速查找历史相似问题的处理记录或官方文档说明，缩短故障恢复时间。系统支持按错误码、服务名称等关键词进行精确匹配。

- 个人技术博客聚合站：独立开发者或技术博主可使用 LinkMap 整理自己收藏的技术文章链接，按照编程语言、框架版本或技术领域进行分类，形成个人专属的技术资料库，便于日常回顾与学习。

- 离线文档分发辅助：对于网络受限的内部环境，LinkMap 可配合离线下载工具使用，运维人员先通过 LinkMap 筛选出需要的文章链接列表，再批量下载至内部服务器，实现文档的本地化分发。

## 快速开始

以下命令可在 Ubuntu 22.04 LTS 或 CentOS 9 Stream 环境下完成 LinkMap 的部署与启动。

```bash
# 克隆项目仓库
git clone https://github.com/linkmap/linkmap-core.git
cd linkmap-core

# 安装依赖（Node.js 18+ 与 npm 9+）
npm install

# 构建静态站点（生成 dist 目录）
npm run build

# 启动开发预览服务器（默认端口 3000）
npm run serve
```

生产环境部署建议执行 `npm run build` 后将 `dist` 目录下的所有文件复制到 Web 服务器的根目录下，并配置路由回退至 `index.html`。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Node.js | 18.x LTS 或更高 | 用于构建工具链与本地开发服务器，不支持 16.x 及以下版本 |
| npm | 9.x 或更高 | 包管理器，用于安装项目依赖与执行构建脚本 |
| 操作系统 | Linux x86_64 / macOS 13+ | 支持 Windows WSL2，但生产部署推荐 Linux 环境 |
| 网络访问 | 出站 80/443 端口可达 | 用于构建时检测外部链接可用性，内网部署可关闭该功能 |
| 磁盘空间 | 至少 200 MB | 用于存放构建产物及缓存索引文件，建议预留 500 MB |
| 内存 | 至少 1 GB | 构建过程中需加载全部链接元数据，大型索引建议 2 GB 以上 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | /docs/user-guide/ | 如何使用 LinkMap 进行链接检索、分类浏览及收藏管理 |
| 管理员指南 | /docs/admin-guide/ | 如何配置数据源、调整索引更新频率及设置访问权限 |
| 开发者文档 | /docs/developer-guide/ | 如何二次开发、自定义主题样式或扩展新的链接采集器 |
| API 参考 | /docs/api-reference/ | LinkMap 提供的静态数据接口格式说明，用于与其他系统集成 |
| 部署运维 | /docs/deployment/ | 在 Docker、Kubernetes 或传统虚拟机上的详细部署步骤 |
| 常见问题 | /docs/faq/ | 汇总了社区反馈的典型问题及对应的解决方案与配置示例 |

## 资源列表

- http://http://map.read.usuhx.com/Article/809921.shtml
- http://http://map.mobile.xqnqq.com/Article/958320.shtml
- http://http://map.read.usuhx.com/Article/8664402.shtml
- http://http://map.read.usuhx.com/Article/97936.shtml
- http://http://map.read.usuhx.com/Article/3993.shtml
- http://http://map.mobile.xqnqq.com/Article/6985.shtml
- http://http://map.mobile.xqnqq.com/Article/38194.shtml
- http://http://map.mobile.xqnqq.com/Article/45179.shtml
- http://http://map.mobile.xqnqq.com/Article/6761.shtml
- http://http://map.read.usuhx.com/Article/867307.shtml
- http://http://map.read.usuhx.com/Article/5575199.shtml
- http://http://map.read.usuhx.com/Article/6335.shtml
- http://http://map.mobile.xqnqq.com/Article/85839.shtml
- http://http://map.mobile.xqnqq.com/Article/6117.shtml
- http://http://map.read.usuhx.com/Article/17778.shtml
- http://http://map.mobile.xqnqq.com/Article/32242.shtml
- http://http://map.read.usuhx.com/Article/2606.shtml
- http://http://map.read.usuhx.com/Article/5692.shtml
- http://http://map.mobile.xqnqq.com/Article/946677.shtml
- http://http://map.mobile.xqnqq.com/Article/111611.shtml
- http://http://map.read.usuhx.com/Article/65554.shtml
- http://http://map.mobile.xqnqq.com/Article/001248.shtml
- http://http://map.read.usuhx.com/Article/315076.shtml
- http://http://map.read.usuhx.com/Article/118799.shtml
- http://http://map.read.usuhx.com/Article/2630990.shtml
- http://http://map.mobile.xqnqq.com/Article/3409269.shtml
- http://http://map.mobile.xqnqq.com/Article/63303.shtml
- http://http://map.read.usuhx.com/Article/8840.shtml
- http://http://map.read.usuhx.com/Article/790529.shtml
- http://http://map.mobile.xqnqq.com/Article/73165.shtml
- http://http://map.read.usuhx.com/Article/62800.shtml
- http://http://map.mobile.xqnqq.com/Article/7581048.shtml
- http://http://map.mobile.xqnqq.com/Article/87743.shtml
- http://http://map.mobile.xqnqq.com/Article/222849.shtml
- http://http://map.read.usuhx.com/Article/56058.shtml
- http://http://map.mobile.xqnqq.com/Article/7180049.shtml
- http://http://map.read.usuhx.com/Article/678260.shtml
- http://http://map.mobile.xqnqq.com/Article/392050.shtml
- http://http://map.mobile.xqnqq.com/Article/912527.shtml
- http://http://map.read.usuhx.com/Article/31560.shtml
- http://http://map.mobile.xqnqq.com/Article/598480.shtml
- http://http://map.mobile.xqnqq.com/Article/6969962.shtml
- http://http://map.read.usuhx.com/Article/88043.shtml
- http://http://map.read.usuhx.com/Article/5566006.shtml
- http://http://map.read.usuhx.com/Article/393595.shtml
- http://http://map.mobile.xqnqq.com/Article/4419523.shtml
- http://http://map.read.usuhx.com/Article/0488320.shtml
- http://http://map.mobile.xqnqq.com/Article/162595.shtml
- http://http://map.mobile.xqnqq.com/Article/026435.shtml
- http://http://map.read.usuhx.com/Article/313773.shtml
- http://http://map.read.usuhx.com/Article/152628.shtml
- http://http://map.mobile.xqnqq.com/Article/88142.shtml
- http://http://map.mobile.xqnqq.com/Article/6292869.shtml
- http://http://map.read.usuhx.com/Article/6963.shtml
- http://http://map.read.usuhx.com/Article/627690.shtml
- http://http://map.mobile.xqnqq.com/Article/8833097.shtml
- http://http://map.read.usuhx.com/Article/734445.shtml
- http://http://map.read.usuhx.com/Article/0089.shtml
- http://http://map.read.usuhx.com/Article/491939.shtml
- http://http://map.mobile.xqnqq.com/Article/23668.shtml
- http://http://map.mobile.xqnqq.com/Article/7181632.shtml
- http://http://map.read.usuhx.com/Article/475269.shtml
- http://http://map.read.usuhx.com/Article/3753.shtml
- http://http://map.mobile.xqnqq.com/Article/3789188.shtml
- http://http://map.mobile.xqnqq.com/Article/119736.shtml
- http://http://map.mobile.xqnqq.com/Article/70692.shtml
- http://http://map.read.usuhx.com/Article/0861792.shtml
- http://http://map.read.usuhx.com/Article/53571.shtml
- http://http://map.read.usuhx.com/Article/738227.shtml
- http://http://map.read.usuhx.com/Article/6909821.shtml
- http://http://map.read.usuhx.com/Article/83650.shtml
- http://http://map.mobile.xqnqq.com/Article/0729.shtml
- http://http://map.read.usuhx.com/Article/49240.shtml
- http://http://map.mobile.xqnqq.com/Article/8820566.shtml
- http://http://map.read.usuhx.com/Article/2388.shtml
- http://http://map.read.usuhx.com/Article/895893.shtml
- http://http://map.mobile.xqnqq.com/Article/309365.shtml
- http://http://map.mobile.xqnqq.com/Article/209653.shtml
- http://http://map.read.usuhx.com/Article/826187.shtml
- http://http://map.read.usuhx.com/Article/17063.shtml
- http://http://map.mobile.xqnqq.com/Article/5970970.shtml
- http://http://map.read.usuhx.com/Article/3202.shtml
- http://http://map.mobile.xqnqq.com/Article/7182060.shtml
- http://http://map.mobile.xqnqq.com/Article/315558.shtml
- http://http://map.read.usuhx.com/Article/7024.shtml
- http://http://map.mobile.xqnqq.com/Article/56845.shtml
- http://http://map.read.usuhx.com/Article/6292.shtml
- http://http://map.mobile.xqnqq.com/Article/23055.shtml
- http://http://map.mobile.xqnqq.com/Article/74541.shtml
- http://http://map.mobile.xqnqq.com/Article/0641.shtml
- http://http://map.mobile.xqnqq.com/Article/8086.shtml
- http://http://map.mobile.xqnqq.com/Article/34423.shtml
- http://http://map.mobile.xqnqq.com/Article/922498.shtml
- http://http://map.mobile.xqnqq.com/Article/7916809.shtml
- http://http://map.read.usuhx.com/Article/2279875.shtml
- http://http://map.read.usuhx.com/Article/716426.shtml
- http://http://map.mobile.xqnqq.com/Article/492856.shtml
- http://http://map.read.usuhx.com/Article/08625.shtml
- http://http://map.mobile.xqnqq.com/Article/772221.shtml
- http://http://map.mobile.xqnqq.com/Article/1353.shtml
- http://http://map.read.usuhx.com/Article/47106.shtml
- http://http://map.read.usuhx.com/Article/788482.shtml
- http://http://map.read.usuhx.com/Article/765249.shtml
- http://http://map.mobile.xqnqq.com/Article/6913776.shtml
- http://http://map.read.usuhx.com/Article/3490159.shtml
- http://http://map.mobile.xqnqq.com/Article/624982.shtml
- http://http://map.read.usuhx.com/Article/437637.shtml
- http://http://map.mobile.xqnqq.com/Article/3725.shtml
- http://http://map.mobile.xqnqq.com/Article/136229.shtml
- http://http://map.read.usuhx.com/Article/5034865.shtml
- http://http://map.mobile.xqnqq.com/Article/2740.shtml
- http://http://map.read.usuhx.com/Article/4318.shtml
- http://http://map.read.usuhx.com/Article/1144.shtml
- http://http://map.read.usuhx.com/Article/9585.shtml
- http://http://map.read.usuhx.com/Article/229852.shtml
- http://http://map.mobile.xqnqq.com/Article/8191.shtml
- http://http://map.mobile.xqnqq.com/Article/5292.shtml
- http://http://map.mobile.xqnqq.com/Article/5957.shtml
- http://http://map.read.usuhx.com/Article/1295353.shtml
- http://http://map.read.usuhx.com/Article/2566838.shtml
- http://http://map.read.usuhx.com/Article/9196509.shtml
- http://http://map.read.usuhx.com/Article/2369.shtml
- http://http://map.read.usuhx.com/Article/19895.shtml
- http://http://map.read.usuhx.com/Article/86002.shtml
- http://http://map.read.usuhx.com/Article/120125.shtml
- http://http://map.read.usuhx.com/Article/6078655.shtml
- http://http://map.mobile.xqnqq.com/Article/938116.shtml
- http://http://map.read.usuhx.com/Article/3030.shtml
- http://http://map.mobile.xqnqq.com/Article/4031.shtml
- http://http://map.read.usuhx.com/Article/000265.shtml
- http://http://map.read.usuhx.com/Article/538358.shtml
- http://http://map.read.usuhx.com/Article/086348.shtml
- http://http://map.mobile.xqnqq.com/Article/8067.shtml
- http://http://map.read.usuhx.com/Article/933994.shtml
- http://http://map.read.usuhx.com/Article/25907.shtml
- http://http://map.read.usuhx.com/Article/140446.shtml
- http://http://map.read.usuhx.com/Article/0637639.shtml
- http://http://map.mobile.xqnqq.com/Article/7524.shtml
- http://http://map.read.usuhx.com/Article/6987363.shtml
- http://http://map.read.usuhx.com/Article/25701.shtml
- http://http://map.mobile.xqnqq.com/Article/7569404.shtml
- http://http://map.mobile.xqnqq.com/Article/5558032.shtml
- http://http://map.read.usuhx.com/Article/9306.shtml
- http://http://map.mobile.xqnqq.com/Article/616269.shtml
- http://http://map.read.usuhx.com/Article/093060.shtml
- http://http://map.mobile.xqnqq.com/Article/7736672.shtml
- http://http://map.mobile.xqnqq.com/Article/68480.shtml
- http://http://map.mobile.xqnqq.com/Article/33212.shtml
- http://http://map.read.usuhx.com/Article/0664.shtml
- http://http://map.read.usuhx.com/Article/0930.shtml
- http://http://map.read.usuhx.com/Article/18478.shtml
- http://http://map.read.usuhx.com/Article/0225.shtml
- http://http://map.read.usuhx.com/Article/5424.shtml
- http://http://map.mobile.xqnqq.com/Article/32392.shtml
- http://http://map.mobile.xqnqq.com/Article/7800153.shtml
- http://http://map.read.usuhx.com/Article/32189.shtml
- http://http://map.mobile.xqnqq.com/Article/4833535.shtml
- http://http://map.mobile.xqnqq.com/Article/3531.shtml
- http://http://map.read.usuhx.com/Article/346821.shtml
- http://http://map.read.usuhx.com/Article/3943.shtml
- http://http://map.read.usuhx.com/Article/34429.shtml
- http://http://map.read.usuhx.com/Article/008912.shtml
- http://http://map.read.usuhx.com/Article/125792.shtml
- http://http://map.read.usuhx.com/Article/2852.shtml
- http://http://map.mobile.xqnqq.com/Article/007865.shtml
- http://http://map.mobile.xqnqq.com/Article/3553.shtml
- http://http://map.read.usuhx.com/Article/1108.shtml
- http://http://map.mobile.xqnqq.com/Article/8667.shtml
- http://http://map.read.usuhx.com/Article/81771.shtml
- http://http://map.read.usuhx.com/Article/8644298.shtml
- http://http://map.read.usuhx.com/Article/1569.shtml
- http://http://map.read.usuhx.com/Article/2012444.shtml
- http://http://map.read.usuhx.com/Article/112915.shtml
- http://http://map.mobile.xqnqq.com/Article/2335228.shtml
- http://http://map.read.usuhx.com/Article/84571.shtml
- http://http://map.mobile.xqnqq.com/Article/469487.shtml
- http://http://map.read.usuhx.com/Article/4954.shtml
- http://http://map.mobile.xqnqq.com/Article/341782.shtml
- http://http://map.read.usuhx.com/Article/845988.shtml
- http://http://map.read.usuhx.com/Article/08415.shtml
- http://http://map.mobile.xqnqq.com/Article/2790651.shtml
- http://http://map.read.usuhx.com/Article/3109.shtml
- http://http://map.mobile.xqnqq.com/Article/168971.shtml
- http://http://map.read.usuhx.com/Article/1934273.shtml
- http://http://map.read.usuhx.com/Article/9216861.shtml
- http://http://map.read.usuhx.com/Article/44668.shtml
- http://http://map.mobile.xqnqq.com/Article/034336.shtml
- http://http://map.read.usuhx.com/Article/071212.shtml
- http://http://map.mobile.xqnqq.com/Article/284118.shtml
- http://http://map.read.usuhx.com/Article/2986323.shtml
- http://http://map.mobile.xqnqq.com/Article/36852.shtml
- http://http://map.read.usuhx.com/Article/6616.shtml
- http://http://map.mobile.xqnqq.com/Article/8911.shtml
- http://http://map.read.usuhx.com/Article/7577.shtml
- http://http://map.mobile.xqnqq.com/Article/748590.shtml
- http://http://map.read.usuhx.com/Article/0943290.shtml
- http://http://map.mobile.xqnqq.com/Article/477452.shtml
- http://http://map.mobile.xqnqq.com/Article/34225.shtml
- http://http://map.mobile.xqnqq.com/Article/58132.shtml
- http://http://map.read.usuhx.com/Article/63374.shtml
- http://http://map.read.usuhx.com/Article/1217.shtml
- http://http://map.mobile.xqnqq.com/Article/2337184.shtml
- http://http://map.read.usuhx.com/Article/7806413.shtml
- http://http://map.mobile.xqnqq.com/Article/2729790.shtml
- http://http://map.read.usuhx.com/Article/4334903.shtml
- http://http://map.read.usuhx.com/Article/2339660.shtml
- http://http://map.read.usuhx.com/Article/370387.shtml
- http://http://map.mobile.xqnqq.com/Article/1336320.shtml
- http://http://map.read.usuhx.com/Article/0574052.shtml
- http://http://map.read.usuhx.com/Article/990517.shtml
- http://http://map.read.usuhx.com/Article/5769085.shtml
- http://http://map.read.usuhx.com/Article/069274.shtml
- http://http://map.read.usuhx.com/Article/649813.shtml
- http://http://map.mobile.xqnqq.com/Article/4928520.shtml
- http://http://map.mobile.xqnqq.com/Article/581910.shtml
- http://http://map.read.usuhx.com/Article/69147.shtml
- http://http://map.read.usuhx.com/Article/45459.shtml
- http://http://map.mobile.xqnqq.com/Article/7100.shtml
- http://http://map.read.usuhx.com/Article/2528487.shtml
- http://http://map.mobile.xqnqq.com/Article/1665.shtml
- http://http://map.mobile.xqnqq.com/Article/7941028.shtml
- http://http://map.mobile.xqnqq.com/Article/60672.shtml
- http://http://map.read.usuhx.com/Article/0705.shtml
- http://http://map.read.usuhx.com/Article/7238969.shtml
- http://http://map.read.usuhx.com/Article/62788.shtml
- http://http://map.read.usuhx.com/Article/59584.shtml
- http://http://map.mobile.xqnqq.com/Article/1725.shtml
- http://http://map.read.usuhx.com/Article/42089.shtml
- http://http://map.read.usuhx.com/Article/2042457.shtml
- http://http://map.mobile.xqnqq.com/Article/37794.shtml
- http://http://map.mobile.xqnqq.com/Article/4934.shtml
- http://http://map.read.usuhx.com/Article/9524.shtml
- http://http://map.read.usuhx.com/Article/6578.shtml
- http://http://map.mobile.xqnqq.com/Article/2639.shtml
- http://http://map.mobile.xqnqq.com/Article/9070313.shtml
- http://http://map.mobile.xqnqq.com/Article/049258.shtml
- http://http://map.mobile.xqnqq.com/Article/863697.shtml
- http://http://map.read.usuhx.com/Article/0526.shtml
- http://http://map.read.usuhx.com/Article/02206.shtml
- http://http://map.read.usuhx.com/Article/49252.shtml
- http://http://map.read.usuhx.com/Article/387784.shtml
- http://http://map.read.usuhx.com/Article/2684684.shtml
- http://http://map.mobile.xqnqq.com/Article/6384.shtml
- http://http://map.read.usuhx.com/Article/4286.shtml
- http://http://map.read.usuhx.com/Article/23441.shtml
- http://http://map.mobile.xqnqq.com/Article/5236865.shtml
- http://http://map.mobile.xqnqq.com/Article/7624627.shtml
- http://http://map.mobile.xqnqq.com/Article/4570440.shtml
- http://http://map.mobile.xqnqq.com/Article/5480674.shtml
- http://http://map.read.usuhx.com/Article/66589.shtml

## 项目结构

```
linkmap-core/
├── config/                                   # 全局配置目录
│   ├── sources.yaml                          # 数据源定义（包含域名、采集间隔、过滤规则）
│   └── categories.yaml                       # 分类映射表（URL 模式到分类名称的对应关系）
├── src/                                      # 核心源代码目录
│   ├── core/                                 # 核心逻辑模块
│   │   ├── collector.js                      # 链接采集器，负责从数据源拉取文章列表
│   │   ├── indexer.js                        # 索引生成器，构建倒排索引与分类索引
│   │   └── validator.js                      # 链接校验器，检测 URL 可达性与内容类型
│   ├── cli/                                  # 命令行工具入口
│   │   ├── build.js                          # 构建命令实现
│   │   └── serve.js                          # 本地预览服务实现
│   └── templates/                            # 静态页面模板
│       ├── layout.ejs                        # 基础布局模板
│       └── components/                       # 可复用 UI 组件模板
├── public/                                   # 静态资源目录（不经过构建流程）
│   ├── css/                                  # 样式表文件
│   │   ├── main.css                          # 主样式文件
│   │   └── dark.css                          # 深色模式样式覆盖
│   └── js/                                   # 前端 JavaScript 脚本
│       ├── search.js                         # 全文检索前端实现
│       └── stats.js                          # 访问统计图表渲染
├── dist/                                     # 构建输出目录（由 npm run build 生成）
│   ├── index.html                            # 首页
│   ├── search.html                           # 检索结果页
│   └── categories/                           # 分类视图子目录
├── tests/                                    # 单元测试与集成测试
│   ├── collector.test.js                     # 采集器单元测试
│   └── validator.test.js                     # 校验器单元测试
├── docs/                                     # 项目文档（用户手册、API 参考等）
├── scripts/                                  # 辅助运维脚本
│   ├── update-index.sh                       # 手动触发索引更新的 Shell 脚本
│   └── health-check.sh                       # 链接健康状态检查脚本
├── .env.example                              # 环境变量配置范例
├── package.json                              # npm 包配置及依赖声明
├── README.md                                 # 项目说明文档（即本文档）
└── LICENSE                                   # MIT 许可证文件
```

## 贡献指南

1. 报告问题或建议新功能前，请先查阅文档导航中的常见问题部分以及 GitHub Issues 列表，确认该问题未被重复提交或已标记为下一个版本的修复计划。

2. 提交代码变更时，请从 `main` 分支创建新的特性分支，命名格式为 `feature/简要描述` 或 `fix/问题编号`，确保分支名称清晰反映变更内容。

3. 所有新增功能或修复必须附带对应的单元测试或集成测试用例，测试覆盖率不得低于现有主干分支的水平，提交前需执行 `npm test` 确认全部测试通过。

4. 提交 Pull Request 时，请填写标准的 PR 模板，包含变更动机、实现方案、测试结果以及影响范围说明，并至少请求一位项目维护者进行代码审查。

5. 文档类贡献（包括但不限于 README 更新、用户手册补充、API 文档修正）可直接提交至 `docs/` 目录，无需附带测试，但需确保 Markdown 格式符合规范且无拼写错误。

## 常见问题

Q: 构建时提示 "Connection timeout" 错误，无法完成链接采集，应如何处理？

A: 该错误通常是由于网络环境限制导致无法访问外部数据源。解决方案有两种：其一，检查主机的出站防火墙规则，确保对 `map.read.usuhx.com` 和 `map.mobile.xqnqq.com` 的 80 端口访问未被阻断；其二，在 `config/sources.yaml` 中将 `timeout` 参数调整为 30000 毫秒（30 秒），并启用 `retry` 重试机制。若处于完全离线环境，可预先将链接列表以 CSV 格式导入至 `data/` 目录，并设置 `offline_mode: true` 跳过网络采集。

Q: 如何自定义 LinkMap 的前端展示主题，例如修改配色方案或布局结构？

A: 主题自定义通过覆盖 `public/css/main.css` 中的 CSS 变量实现。所有可调用的变量定义在 `:root` 伪类中，包括 `--primary-color`、`--background-color`、`--font-family` 等。若需深度定制布局，可修改 `src/templates/layout.ejs` 中的 HTML 结构，并在 `src/templates/components/` 目录下调整相应组件的模板文件。修改完成后执行 `npm run build` 重新生成静态页面，无需重启服务。

Q: LinkMap 的链接索引更新频率是多少，是否支持增量更新？

A: 默认配置下，LinkMap 在每次构建时全量拉取所有数据源的文章列表并重新生成索引。对于大型数据源，可通过配置 `incremental_update: true` 启用增量模式，该模式会对比本地缓存的文章编号与远程最新编号，仅新增或移除变更的条目，大幅缩短构建时间。增量更新功能依赖本地 `cache/` 目录存储上一次构建的状态快照，请确保该目录具有读写权限。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
