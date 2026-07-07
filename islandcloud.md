# WebMap 技术资源聚合索引

WebMap 是一个面向开发人员、技术研究人员与数据分析师的开源外链资源聚合与导航系统。该项目定位于对分散在多个内容源头的技术文章、数据报告、案例解析与工程实践文档进行系统性采集、分类与索引，帮助技术从业者快速定位特定主题下的高质量阅读材料。WebMap 本身不存储内容，仅提供指向原始来源的稳定引用链接，适用于构建个人或团队的知识库入口、技术周报素材池以及项目调研阶段的资料检索层。

## 功能概览

**多源资源聚合索引**：系统基于固定数据源结构，周期性整合来自多个内容分发节点的文章链接，形成统一的资源目录。

**按内容标识符检索**：每条资源均包含唯一内容编号与来源域名标识，支持基于编号或域名的快速定位与过滤。

**分类层级导航**：根据资源来源域名与路径结构，自动生成分类视图，区分移动端内容与通用阅读端内容。

**原始链接直出模式**：所有资源展示均保留原始 URL 字符串，不做自动跳转、短链替换或参数追加，确保引用可追溯。

**轻量级元数据标注**：每条资源附带基础元信息，包括来源域、文章编号及资源批次标记，便于后续扩展标签体系。

**无状态前端架构**：系统采用静态页面生成方式部署，无需后端数据库支持，所有链接数据以结构化文本形式维护。

**按批次管理资源集**：每批资源独立编号，当前批次为第 67/80 批，共收录 250 个链接，支持分批导出与归档。

## 应用场景

**技术团队内部知识周报编纂**：团队技术负责人或文档管理员可使用 WebMap 的聚合列表，快速筛选当周值得关注的技术文章链接，直接复制原始 URL 插入周报或团队 Wiki，无需重复收集分散的浏览器书签。

**项目调研阶段的资料采集**：在进行技术选型或竞品分析时，研究人员可通过 WebMap 按域名或编号范围检索相关文章，批量获取案例资料链接，建立调研素材池。

**个人技术阅读队列管理**：开发者可将 WebMap 作为每日阅读入口，浏览固定数据源的最新文章链接，将感兴趣的条目存入稍后阅读列表，避免使用社交平台或邮件订阅的信息干扰。

**静态站点内容迁移辅助**：当需要将外部文章引用迁移至新构建的文档站点时，WebMap 提供的纯链接列表可直接用于生成站点的外部引用章节，保持引用格式一致性与可验证性。

## 快速开始

以下命令用于克隆项目仓库、安装基础依赖并启动本地预览服务。

```bash
git clone https://github.com/webmap-index/webmap-resources.git
cd webmap-resources
npm install
npm run build
npm start
```

执行 `npm start` 后，本地服务默认监听 3000 端口，访问 http://localhost:3000 即可查看资源索引首页。资源列表数据位于 `data/resources_67_80.json`，可直接编辑该文件更新链接集合。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Node.js | 18.x 或 20.x LTS | 运行时环境，用于执行构建脚本与本地服务 |
| npm | 9.x 或更高 | 包管理器，用于安装项目依赖 |
| Git | 2.30 或更高 | 版本控制工具，用于克隆仓库与提交更新 |
| 静态站点生成器 | 无强制依赖 | 项目内置构建脚本，无需额外安装 Hexo 或 VuePress |
| 现代浏览器 | Chrome 90+ / Firefox 88+ | 用于预览索引页面，无特殊兼容性要求 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 用户层面 | `docs/user-guide.md` | 如何浏览资源列表、按域名或编号筛选链接、导出当前批次数据 |
| 维护者层面 | `docs/maintainer-guide.md` | 如何新增批次、更新链接列表、校验 URL 格式、提交变更请求 |
| 架构层面 | `docs/architecture.md` | 项目目录结构说明、数据流走向、构建流程与部署方案 |
| 贡献层面 | `CONTRIBUTING.md` | 提交资源补充或修正的完整流程、编码规范与审查标准 |

## 资源列表

- http://http://map.mobile.xqnqq.com/Article/2421764.shtml
- http://http://map.read.usuhx.com/Article/4602.shtml
- http://http://map.read.usuhx.com/Article/5738460.shtml
- http://http://map.mobile.xqnqq.com/Article/4057717.shtml
- http://http://map.mobile.xqnqq.com/Article/1641.shtml
- http://http://map.read.usuhx.com/Article/96104.shtml
- http://http://map.mobile.xqnqq.com/Article/59235.shtml
- http://http://map.mobile.xqnqq.com/Article/769051.shtml
- http://http://map.mobile.xqnqq.com/Article/9937.shtml
- http://http://map.read.usuhx.com/Article/201815.shtml
- http://http://map.read.usuhx.com/Article/5154782.shtml
- http://http://map.mobile.xqnqq.com/Article/18723.shtml
- http://http://map.read.usuhx.com/Article/3413.shtml
- http://http://map.mobile.xqnqq.com/Article/908396.shtml
- http://http://map.mobile.xqnqq.com/Article/4305.shtml
- http://http://map.mobile.xqnqq.com/Article/809415.shtml
- http://http://map.read.usuhx.com/Article/48837.shtml
- http://http://map.read.usuhx.com/Article/6756.shtml
- http://http://map.mobile.xqnqq.com/Article/8036335.shtml
- http://http://map.read.usuhx.com/Article/5030830.shtml
- http://http://map.mobile.xqnqq.com/Article/8290.shtml
- http://http://map.mobile.xqnqq.com/Article/285994.shtml
- http://http://map.read.usuhx.com/Article/285667.shtml
- http://http://map.read.usuhx.com/Article/3584.shtml
- http://http://map.read.usuhx.com/Article/880712.shtml
- http://http://map.read.usuhx.com/Article/328045.shtml
- http://http://map.mobile.xqnqq.com/Article/279354.shtml
- http://http://map.mobile.xqnqq.com/Article/8893340.shtml
- http://http://map.mobile.xqnqq.com/Article/044460.shtml
- http://http://map.mobile.xqnqq.com/Article/26857.shtml
- http://http://map.read.usuhx.com/Article/1425178.shtml
- http://http://map.read.usuhx.com/Article/6179.shtml
- http://http://map.mobile.xqnqq.com/Article/0618584.shtml
- http://http://map.read.usuhx.com/Article/24862.shtml
- http://http://map.read.usuhx.com/Article/464862.shtml
- http://http://map.mobile.xqnqq.com/Article/36128.shtml
- http://http://map.mobile.xqnqq.com/Article/49277.shtml
- http://http://map.mobile.xqnqq.com/Article/044993.shtml
- http://http://map.mobile.xqnqq.com/Article/6988039.shtml
- http://http://map.read.usuhx.com/Article/4103.shtml
- http://http://map.read.usuhx.com/Article/2343958.shtml
- http://http://map.mobile.xqnqq.com/Article/371224.shtml
- http://http://map.mobile.xqnqq.com/Article/2118380.shtml
- http://http://map.mobile.xqnqq.com/Article/6239.shtml
- http://http://map.mobile.xqnqq.com/Article/644309.shtml
- http://http://map.read.usuhx.com/Article/10348.shtml
- http://http://map.read.usuhx.com/Article/057328.shtml
- http://http://map.read.usuhx.com/Article/459976.shtml
- http://http://map.mobile.xqnqq.com/Article/540782.shtml
- http://http://map.read.usuhx.com/Article/64960.shtml
- http://http://map.read.usuhx.com/Article/4082.shtml
- http://http://map.mobile.xqnqq.com/Article/32390.shtml
- http://http://map.mobile.xqnqq.com/Article/1141422.shtml
- http://http://map.mobile.xqnqq.com/Article/444229.shtml
- http://http://map.mobile.xqnqq.com/Article/828424.shtml
- http://http://map.mobile.xqnqq.com/Article/39298.shtml
- http://http://map.mobile.xqnqq.com/Article/2518.shtml
- http://http://map.mobile.xqnqq.com/Article/570669.shtml
- http://http://map.mobile.xqnqq.com/Article/5563.shtml
- http://http://map.mobile.xqnqq.com/Article/9474.shtml
- http://http://map.read.usuhx.com/Article/09039.shtml
- http://http://map.mobile.xqnqq.com/Article/4171165.shtml
- http://http://map.mobile.xqnqq.com/Article/5341120.shtml
- http://http://map.mobile.xqnqq.com/Article/1315.shtml
- http://http://map.read.usuhx.com/Article/6692952.shtml
- http://http://map.read.usuhx.com/Article/06642.shtml
- http://http://map.read.usuhx.com/Article/457435.shtml
- http://http://map.mobile.xqnqq.com/Article/5474513.shtml
- http://http://map.read.usuhx.com/Article/6092711.shtml
- http://http://map.read.usuhx.com/Article/314785.shtml
- http://http://map.read.usuhx.com/Article/2211772.shtml
- http://http://map.mobile.xqnqq.com/Article/688444.shtml
- http://http://map.read.usuhx.com/Article/330677.shtml
- http://http://map.mobile.xqnqq.com/Article/21982.shtml
- http://http://map.mobile.xqnqq.com/Article/04255.shtml
- http://http://map.read.usuhx.com/Article/82430.shtml
- http://http://map.read.usuhx.com/Article/04434.shtml
- http://http://map.read.usuhx.com/Article/064322.shtml
- http://http://map.read.usuhx.com/Article/5902280.shtml
- http://http://map.mobile.xqnqq.com/Article/3038901.shtml
- http://http://map.mobile.xqnqq.com/Article/0550.shtml
- http://http://map.read.usuhx.com/Article/8996.shtml
- http://http://map.read.usuhx.com/Article/59971.shtml
- http://http://map.mobile.xqnqq.com/Article/5004883.shtml
- http://http://map.mobile.xqnqq.com/Article/3674.shtml
- http://http://map.read.usuhx.com/Article/395923.shtml
- http://http://map.read.usuhx.com/Article/148341.shtml
- http://http://map.mobile.xqnqq.com/Article/7223.shtml
- http://http://map.read.usuhx.com/Article/71384.shtml
- http://http://map.mobile.xqnqq.com/Article/79072.shtml
- http://http://map.mobile.xqnqq.com/Article/5523125.shtml
- http://http://map.read.usuhx.com/Article/874082.shtml
- http://http://map.read.usuhx.com/Article/919929.shtml
- http://http://map.mobile.xqnqq.com/Article/1700983.shtml
- http://http://map.mobile.xqnqq.com/Article/3524.shtml
- http://http://map.read.usuhx.com/Article/993812.shtml
- http://http://map.mobile.xqnqq.com/Article/02663.shtml
- http://http://map.read.usuhx.com/Article/42893.shtml
- http://http://map.mobile.xqnqq.com/Article/03756.shtml
- http://http://map.mobile.xqnqq.com/Article/49959.shtml
- http://http://map.mobile.xqnqq.com/Article/15540.shtml
- http://http://map.read.usuhx.com/Article/40849.shtml
- http://http://map.mobile.xqnqq.com/Article/5343.shtml
- http://http://map.read.usuhx.com/Article/770597.shtml
- http://http://map.read.usuhx.com/Article/28654.shtml
- http://http://map.read.usuhx.com/Article/60109.shtml
- http://http://map.read.usuhx.com/Article/531877.shtml
- http://http://map.read.usuhx.com/Article/4862441.shtml
- http://http://map.read.usuhx.com/Article/254196.shtml
- http://http://map.read.usuhx.com/Article/0724114.shtml
- http://http://map.read.usuhx.com/Article/30903.shtml
- http://http://map.mobile.xqnqq.com/Article/84017.shtml
- http://http://map.mobile.xqnqq.com/Article/7775.shtml
- http://http://map.read.usuhx.com/Article/093581.shtml
- http://http://map.read.usuhx.com/Article/7316090.shtml
- http://http://map.read.usuhx.com/Article/6644935.shtml
- http://http://map.mobile.xqnqq.com/Article/99565.shtml
- http://http://map.mobile.xqnqq.com/Article/2635.shtml
- http://http://map.mobile.xqnqq.com/Article/05525.shtml
- http://http://map.mobile.xqnqq.com/Article/285099.shtml
- http://http://map.mobile.xqnqq.com/Article/89815.shtml
- http://http://map.read.usuhx.com/Article/453030.shtml
- http://http://map.mobile.xqnqq.com/Article/41333.shtml
- http://http://map.mobile.xqnqq.com/Article/2631645.shtml
- http://http://map.read.usuhx.com/Article/8078371.shtml
- http://http://map.read.usuhx.com/Article/0239303.shtml
- http://http://map.read.usuhx.com/Article/0207554.shtml
- http://http://map.mobile.xqnqq.com/Article/8811481.shtml
- http://http://map.mobile.xqnqq.com/Article/532351.shtml
- http://http://map.read.usuhx.com/Article/55481.shtml
- http://http://map.read.usuhx.com/Article/87444.shtml
- http://http://map.read.usuhx.com/Article/145159.shtml
- http://http://map.mobile.xqnqq.com/Article/6410416.shtml
- http://http://map.read.usuhx.com/Article/5415.shtml
- http://http://map.read.usuhx.com/Article/58747.shtml
- http://http://map.mobile.xqnqq.com/Article/4883.shtml
- http://http://map.read.usuhx.com/Article/341407.shtml
- http://http://map.mobile.xqnqq.com/Article/6354.shtml
- http://http://map.read.usuhx.com/Article/32167.shtml
- http://http://map.read.usuhx.com/Article/436320.shtml
- http://http://map.mobile.xqnqq.com/Article/0636.shtml
- http://http://map.read.usuhx.com/Article/4851369.shtml
- http://http://map.read.usuhx.com/Article/1831.shtml
- http://http://map.mobile.xqnqq.com/Article/46690.shtml
- http://http://map.read.usuhx.com/Article/219173.shtml
- http://http://map.mobile.xqnqq.com/Article/84330.shtml
- http://http://map.read.usuhx.com/Article/3010.shtml
- http://http://map.read.usuhx.com/Article/7583.shtml
- http://http://map.mobile.xqnqq.com/Article/87464.shtml
- http://http://map.mobile.xqnqq.com/Article/0005.shtml
- http://http://map.mobile.xqnqq.com/Article/236826.shtml
- http://http://map.mobile.xqnqq.com/Article/2783.shtml
- http://http://map.read.usuhx.com/Article/3057.shtml
- http://http://map.read.usuhx.com/Article/0397394.shtml
- http://http://map.mobile.xqnqq.com/Article/16617.shtml
- http://http://map.mobile.xqnqq.com/Article/842379.shtml
- http://http://map.read.usuhx.com/Article/54564.shtml
- http://http://map.read.usuhx.com/Article/73203.shtml
- http://http://map.read.usuhx.com/Article/672801.shtml
- http://http://map.read.usuhx.com/Article/51802.shtml
- http://http://map.read.usuhx.com/Article/6920909.shtml
- http://http://map.mobile.xqnqq.com/Article/7508319.shtml
- http://http://map.read.usuhx.com/Article/29092.shtml
- http://http://map.mobile.xqnqq.com/Article/5970372.shtml
- http://http://map.mobile.xqnqq.com/Article/7400.shtml
- http://http://map.read.usuhx.com/Article/72907.shtml
- http://http://map.read.usuhx.com/Article/9484589.shtml
- http://http://map.read.usuhx.com/Article/7342.shtml
- http://http://map.read.usuhx.com/Article/50488.shtml
- http://http://map.read.usuhx.com/Article/891271.shtml
- http://http://map.read.usuhx.com/Article/55332.shtml
- http://http://map.read.usuhx.com/Article/49928.shtml
- http://http://map.mobile.xqnqq.com/Article/81097.shtml
- http://http://map.read.usuhx.com/Article/891897.shtml
- http://http://map.mobile.xqnqq.com/Article/92899.shtml
- http://http://map.mobile.xqnqq.com/Article/3432.shtml
- http://http://map.mobile.xqnqq.com/Article/4694047.shtml
- http://http://map.mobile.xqnqq.com/Article/6369878.shtml
- http://http://map.read.usuhx.com/Article/73690.shtml
- http://http://map.mobile.xqnqq.com/Article/601086.shtml
- http://http://map.mobile.xqnqq.com/Article/0157.shtml
- http://http://map.read.usuhx.com/Article/199235.shtml
- http://http://map.mobile.xqnqq.com/Article/1755.shtml
- http://http://map.mobile.xqnqq.com/Article/615849.shtml
- http://http://map.read.usuhx.com/Article/424114.shtml
- http://http://map.read.usuhx.com/Article/013461.shtml
- http://http://map.mobile.xqnqq.com/Article/118467.shtml
- http://http://map.mobile.xqnqq.com/Article/2318.shtml
- http://http://map.mobile.xqnqq.com/Article/5257211.shtml
- http://http://map.read.usuhx.com/Article/5269.shtml
- http://http://map.mobile.xqnqq.com/Article/56585.shtml
- http://http://map.read.usuhx.com/Article/8358819.shtml
- http://http://map.read.usuhx.com/Article/0784.shtml
- http://http://map.mobile.xqnqq.com/Article/815616.shtml
- http://http://map.read.usuhx.com/Article/724551.shtml
- http://http://map.read.usuhx.com/Article/37353.shtml
- http://http://map.mobile.xqnqq.com/Article/8480.shtml
- http://http://map.mobile.xqnqq.com/Article/66237.shtml
- http://http://map.read.usuhx.com/Article/47842.shtml
- http://http://map.read.usuhx.com/Article/45861.shtml
- http://http://map.mobile.xqnqq.com/Article/808672.shtml
- http://http://map.read.usuhx.com/Article/302280.shtml
- http://http://map.mobile.xqnqq.com/Article/057156.shtml
- http://http://map.read.usuhx.com/Article/8560.shtml
- http://http://map.mobile.xqnqq.com/Article/834922.shtml
- http://http://map.mobile.xqnqq.com/Article/7148567.shtml
- http://http://map.mobile.xqnqq.com/Article/75973.shtml
- http://http://map.mobile.xqnqq.com/Article/15644.shtml
- http://http://map.read.usuhx.com/Article/89457.shtml
- http://http://map.mobile.xqnqq.com/Article/80220.shtml
- http://http://map.mobile.xqnqq.com/Article/95473.shtml
- http://http://map.read.usuhx.com/Article/5039266.shtml
- http://http://map.mobile.xqnqq.com/Article/55542.shtml
- http://http://map.read.usuhx.com/Article/0633629.shtml
- http://http://map.mobile.xqnqq.com/Article/214283.shtml
- http://http://map.mobile.xqnqq.com/Article/63221.shtml
- http://http://map.mobile.xqnqq.com/Article/7109117.shtml
- http://http://map.mobile.xqnqq.com/Article/026904.shtml
- http://http://map.mobile.xqnqq.com/Article/029715.shtml
- http://http://map.mobile.xqnqq.com/Article/831286.shtml
- http://http://map.mobile.xqnqq.com/Article/489427.shtml
- http://http://map.mobile.xqnqq.com/Article/2732.shtml
- http://http://map.mobile.xqnqq.com/Article/7810.shtml
- http://http://map.mobile.xqnqq.com/Article/45290.shtml
- http://http://map.read.usuhx.com/Article/57600.shtml
- http://http://map.read.usuhx.com/Article/4735.shtml
- http://http://map.read.usuhx.com/Article/9075930.shtml
- http://http://map.mobile.xqnqq.com/Article/522549.shtml
- http://http://map.mobile.xqnqq.com/Article/6124.shtml
- http://http://map.mobile.xqnqq.com/Article/279417.shtml
- http://http://map.read.usuhx.com/Article/847295.shtml
- http://http://map.mobile.xqnqq.com/Article/3226.shtml
- http://http://map.mobile.xqnqq.com/Article/870482.shtml
- http://http://map.mobile.xqnqq.com/Article/750645.shtml
- http://http://map.read.usuhx.com/Article/0130.shtml
- http://http://map.mobile.xqnqq.com/Article/90272.shtml
- http://http://map.read.usuhx.com/Article/10999.shtml
- http://http://map.mobile.xqnqq.com/Article/160264.shtml
- http://http://map.mobile.xqnqq.com/Article/9617.shtml
- http://http://map.mobile.xqnqq.com/Article/037811.shtml
- http://http://map.read.usuhx.com/Article/75500.shtml
- http://http://map.mobile.xqnqq.com/Article/387937.shtml
- http://http://map.mobile.xqnqq.com/Article/9610380.shtml
- http://http://map.mobile.xqnqq.com/Article/3838.shtml
- http://http://map.read.usuhx.com/Article/3646355.shtml
- http://http://map.mobile.xqnqq.com/Article/5645439.shtml
- http://http://map.mobile.xqnqq.com/Article/380088.shtml
- http://http://map.read.usuhx.com/Article/443774.shtml
- http://http://map.mobile.xqnqq.com/Article/6348840.shtml
- http://http://map.mobile.xqnqq.com/Article/6751.shtml

## 项目结构

```
webmap-resources/
├── data/
│   ├── resources_67_80.json        # 当前批次资源列表（250 条）
│   ├── schemas/
│   │   └── resource.schema.json    # 资源条目 JSON Schema 校验文件
│   └── archives/
│       └── batch_66.json           # 历史批次归档示例
├── src/
│   ├── core/
│   │   ├── indexer.js              # 资源索引生成核心逻辑
│   │   └── validator.js            # URL 格式与重复性校验器
│   ├── generators/
│   │   ├── static.js               # 静态 HTML 页面生成器
│   │   └── rss.js                  # RSS 订阅源生成器
│   ├── filters/
│   │   ├── domain.js               # 按域名过滤资源
│   │   └── batch.js                # 按批次号过滤资源
│   └── utils/
│       ├── logger.js               # 日志工具
│       └── config.js               # 全局配置加载
├── public/
│   ├── index.html                  # 生成后的首页
│   ├── styles/
│   │   └── main.css                # 基础样式表
│   └── scripts/
│       └── filter.js               # 前端过滤交互脚本
├── tests/
│   ├── unit/
│   │   └── validator.test.js       # 校验器单元测试
│   └── integration/
│       └── generator.test.js       # 生成器集成测试
├── docs/                           # 文档目录（详见文档导航）
├── .github/
│   └── workflows/
│       └── build.yml               # CI 构建流水线配置
├── package.json                    # npm 项目配置
├── README.md                       # 本文件
└── LICENSE                         # MIT 许可证
```

## 贡献指南

1. 复刻仓库至个人账号下，在本地创建功能分支，分支命名格式为 `feat/resource-update-batch-67` 或 `fix/url-correction`。

2. 编辑 `data/resources_67_80.json` 文件，新增或修正资源链接。每个链接必须为完整字符串，保留原始协议与域名格式，不得添加额外包装。

3. 运行 `npm run validate` 执行链接格式校验与重复性检查，确保所有 URL 符合基本格式要求且无重复条目。

4. 提交变更并推送到远程分支，通过 GitHub 界面发起 Pull Request 至主仓库的 `main` 分支，在 PR 描述中注明本次变更涉及的批次号与变更类型（新增 / 修正 / 删除）。

5. 等待项目维护者进行审查，审查通过后合并至主分支，合并后 CI 流水线将自动重新生成静态页面并部署。

## 常见问题

**问：为什么部分链接看起来包含重复的 http:// 前缀？**

答：所有链接均按来源数据原始格式原样收录，未做任何归一化处理。用户访问时应以实际字符串为准，若浏览器无法解析，请手动核对链接格式。项目方不负责对原始数据进行格式修正，以保持数据溯源的真实性。

**问：如何快速查找特定域名的所有资源？**

答：可使用浏览器页面内搜索功能（Ctrl+F / Cmd+F）输入域名关键词，例如 `mobile.xqnqq.com` 或 `read.usuhx.com`，即可在当前资源列表中高亮所有匹配条目。后续版本将增加前端域名过滤下拉菜单。

**问：项目是否提供 RSS 订阅或 API 接口？**

答：当前版本支持通过 `npm run generate-rss` 生成静态 RSS 文件，输出路径为 `public/feed.xml`。API 接口暂未开放，但所有数据以 JSON 格式存储在 `data/` 目录下，开发者可直接读取该文件用于二次开发。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
