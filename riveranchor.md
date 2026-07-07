# LinkMap 聚合导航系统

LinkMap 是一个面向技术研究者、数据运营人员和内容聚合者的轻量级外链资源导航系统。本项目定位于对分散在多个内容源（如移动端地图服务、行业资讯站点）中的深度文章链接进行结构化整理、分类标注与快速检索，解决信息碎片化导致的资源查找效率低下问题。LinkMap 不对原始内容做二次加工，仅提供清晰的索引视图与本地运行环境，适合需要快速启动一个外链门户或内部知识库导航的团队使用。

## 功能概览

- 多源链接统一入库：支持从不同域名和路径结构中批量导入链接，自动识别来源特征。
- 目录树式分类浏览：根据链接所属站点、栏目和文章编号自动生成层级目录，便于按业务线查找。
- 黑名单与去重机制：内置基于 URL 模式的去重引擎，避免同一资源在不同批次中重复收录。
- 本地全文检索：基于 SQLite FTS5 扩展，支持对文章标题、摘要和自定义标签的中文分词检索。
- 资源状态监控：定时检测已收录链接的可访问性（HTTP 状态码），标记失效或重定向资源。
- 批次管理能力：每批资源可独立标记批次号（如第 64/80 批），支持按批次筛选与导出。
- 只读静态导出：可一键生成全量链接的只读 HTML 目录页，适合发布到 CDN 或内部知识库。

## 应用场景

- 技术团队内部知识库构建：技术负责人可将团队订阅的行业分析文章、技术博客链接统一收录，LinkMap 提供快速检索与分类能力，替代零散的浏览器书签。
- 内容运营编辑选材：运营人员从多个移动端资讯源中筛选可转载或参考的文章，通过 LinkMap 按批次整理后分发给撰写团队，避免重复引用已处理内容。
- 数据分析师数据源管理：数据分析师需要定期访问特定站点的数据报表或案例文章，LinkMap 的目录结构支持按域名和业务主题组织，降低每次查找的时间成本。
- 开源项目文档资源站：开源社区可用 LinkMap 托管项目相关的教程、案例和第三方评测链接，以统一入口对外展示，提升社区资源聚合效率。

## 快速开始

以下步骤适用于 Linux / macOS / Windows WSL 环境，需提前安装 Git 与 Python 3.9 及以上版本。

```bash
# 克隆项目仓库
git clone https://github.com/linkmap-org/linkmap-nav.git
cd linkmap-nav

# 安装依赖（使用虚拟环境）
python3 -m venv venv
source venv/bin/activate  # Windows 下使用 venv\Scripts\activate
pip install -r requirements.txt

# 初始化数据库并导入当前批次资源
python manage.py initdb
python manage.py import --batch 64 --source data/batch_64.txt

# 启动本地开发服务器
python manage.py runserver --host 127.0.0.1 --port 8080
```

启动后访问 `http://127.0.0.1:8080` 即可浏览当前批次所有链接。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | >= 3.9, < 3.13 | 核心运行环境，推荐使用 3.11 |
| SQLite | >= 3.35.0 | 内置数据库，需支持 FTS5 全文检索扩展 |
| Git | >= 2.25 | 用于版本克隆与后续更新拉取 |
| requests | >= 2.28.0 | 用于资源状态监控与可访问性检测 |
| beautifulsoup4 | >= 4.11.0 | 用于解析链接所在页面的标题与元信息（可选） |
| pytest | >= 7.0.0 | 仅开发测试时使用，生产环境可不安装 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 入门 | docs/quickstart.md | 如何快速运行项目并导入第一批链接 |
| 操作 | docs/batch-management.md | 如何新增批次、合并去重、导出筛选结果 |
| 开发 | docs/api-reference.md | 各核心模块（导入器、检索器、监控器）的方法说明 |
| 运维 | docs/deployment-checklist.md | 生产环境部署前的检查项、日志配置与性能调优建议 |

## 资源列表

- http://http://map.mobile.xqnqq.com/Article/615695.shtml
- http://http://map.read.usuhx.com/Article/4289.shtml
- http://http://map.mobile.xqnqq.com/Article/627222.shtml
- http://http://map.mobile.xqnqq.com/Article/41201.shtml
- http://http://map.read.usuhx.com/Article/2558162.shtml
- http://http://map.read.usuhx.com/Article/4929952.shtml
- http://http://map.mobile.xqnqq.com/Article/07815.shtml
- http://http://map.mobile.xqnqq.com/Article/4417669.shtml
- http://http://map.mobile.xqnqq.com/Article/680205.shtml
- http://http://map.mobile.xqnqq.com/Article/09748.shtml
- http://http://map.read.usuhx.com/Article/020643.shtml
- http://http://map.mobile.xqnqq.com/Article/4999.shtml
- http://http://map.mobile.xqnqq.com/Article/92946.shtml
- http://http://map.mobile.xqnqq.com/Article/78982.shtml
- http://http://map.mobile.xqnqq.com/Article/4389.shtml
- http://http://map.read.usuhx.com/Article/54050.shtml
- http://http://map.read.usuhx.com/Article/1436916.shtml
- http://http://map.mobile.xqnqq.com/Article/0665.shtml
- http://http://map.read.usuhx.com/Article/505023.shtml
- http://http://map.mobile.xqnqq.com/Article/6704057.shtml
- http://http://map.mobile.xqnqq.com/Article/3560.shtml
- http://http://map.mobile.xqnqq.com/Article/0422308.shtml
- http://http://map.mobile.xqnqq.com/Article/83165.shtml
- http://http://map.mobile.xqnqq.com/Article/29632.shtml
- http://http://map.read.usuhx.com/Article/2087795.shtml
- http://http://map.read.usuhx.com/Article/1565969.shtml
- http://http://map.mobile.xqnqq.com/Article/276158.shtml
- http://http://map.mobile.xqnqq.com/Article/6856612.shtml
- http://http://map.mobile.xqnqq.com/Article/766564.shtml
- http://http://map.read.usuhx.com/Article/8751.shtml
- http://http://map.read.usuhx.com/Article/99663.shtml
- http://http://map.mobile.xqnqq.com/Article/91211.shtml
- http://http://map.read.usuhx.com/Article/160235.shtml
- http://http://map.read.usuhx.com/Article/375355.shtml
- http://http://map.read.usuhx.com/Article/0253.shtml
- http://http://map.read.usuhx.com/Article/3791.shtml
- http://http://map.mobile.xqnqq.com/Article/21948.shtml
- http://http://map.mobile.xqnqq.com/Article/5980.shtml
- http://http://map.mobile.xqnqq.com/Article/67007.shtml
- http://http://map.read.usuhx.com/Article/491466.shtml
- http://http://map.read.usuhx.com/Article/2055.shtml
- http://http://map.read.usuhx.com/Article/91129.shtml
- http://http://map.mobile.xqnqq.com/Article/6656588.shtml
- http://http://map.read.usuhx.com/Article/962063.shtml
- http://http://map.mobile.xqnqq.com/Article/8136701.shtml
- http://http://map.read.usuhx.com/Article/31116.shtml
- http://http://map.mobile.xqnqq.com/Article/9704265.shtml
- http://http://map.read.usuhx.com/Article/42673.shtml
- http://http://map.mobile.xqnqq.com/Article/1285.shtml
- http://http://map.read.usuhx.com/Article/70057.shtml
- http://http://map.read.usuhx.com/Article/74669.shtml
- http://http://map.mobile.xqnqq.com/Article/4829.shtml
- http://http://map.mobile.xqnqq.com/Article/9250556.shtml
- http://http://map.read.usuhx.com/Article/0187131.shtml
- http://http://map.read.usuhx.com/Article/69049.shtml
- http://http://map.mobile.xqnqq.com/Article/1421.shtml
- http://http://map.mobile.xqnqq.com/Article/0161.shtml
- http://http://map.mobile.xqnqq.com/Article/944526.shtml
- http://http://map.mobile.xqnqq.com/Article/537519.shtml
- http://http://map.read.usuhx.com/Article/333467.shtml
- http://http://map.mobile.xqnqq.com/Article/1434.shtml
- http://http://map.mobile.xqnqq.com/Article/5971.shtml
- http://http://map.read.usuhx.com/Article/900435.shtml
- http://http://map.read.usuhx.com/Article/7461512.shtml
- http://http://map.read.usuhx.com/Article/43937.shtml
- http://http://map.read.usuhx.com/Article/5675761.shtml
- http://http://map.read.usuhx.com/Article/36190.shtml
- http://http://map.mobile.xqnqq.com/Article/85154.shtml
- http://http://map.read.usuhx.com/Article/77688.shtml
- http://http://map.mobile.xqnqq.com/Article/047360.shtml
- http://http://map.mobile.xqnqq.com/Article/695017.shtml
- http://http://map.mobile.xqnqq.com/Article/21120.shtml
- http://http://map.mobile.xqnqq.com/Article/88189.shtml
- http://http://map.read.usuhx.com/Article/8068.shtml
- http://http://map.read.usuhx.com/Article/67598.shtml
- http://http://map.mobile.xqnqq.com/Article/414030.shtml
- http://http://map.mobile.xqnqq.com/Article/3479.shtml
- http://http://map.read.usuhx.com/Article/43560.shtml
- http://http://map.mobile.xqnqq.com/Article/029000.shtml
- http://http://map.read.usuhx.com/Article/744812.shtml
- http://http://map.read.usuhx.com/Article/5158.shtml
- http://http://map.mobile.xqnqq.com/Article/40591.shtml
- http://http://map.read.usuhx.com/Article/6700.shtml
- http://http://map.mobile.xqnqq.com/Article/3532996.shtml
- http://http://map.read.usuhx.com/Article/8264925.shtml
- http://http://map.read.usuhx.com/Article/2431644.shtml
- http://http://map.read.usuhx.com/Article/009483.shtml
- http://http://map.read.usuhx.com/Article/420501.shtml
- http://http://map.mobile.xqnqq.com/Article/90803.shtml
- http://http://map.mobile.xqnqq.com/Article/6563.shtml
- http://http://map.mobile.xqnqq.com/Article/397279.shtml
- http://http://map.read.usuhx.com/Article/98726.shtml
- http://http://map.read.usuhx.com/Article/48918.shtml
- http://http://map.mobile.xqnqq.com/Article/5871855.shtml
- http://http://map.mobile.xqnqq.com/Article/351318.shtml
- http://http://map.mobile.xqnqq.com/Article/7604.shtml
- http://http://map.read.usuhx.com/Article/5603088.shtml
- http://http://map.mobile.xqnqq.com/Article/952213.shtml
- http://http://map.read.usuhx.com/Article/4737400.shtml
- http://http://map.mobile.xqnqq.com/Article/4342469.shtml
- http://http://map.read.usuhx.com/Article/268325.shtml
- http://http://map.mobile.xqnqq.com/Article/68105.shtml
- http://http://map.mobile.xqnqq.com/Article/0952674.shtml
- http://http://map.mobile.xqnqq.com/Article/0340.shtml
- http://http://map.read.usuhx.com/Article/14396.shtml
- http://http://map.read.usuhx.com/Article/614199.shtml
- http://http://map.read.usuhx.com/Article/459438.shtml
- http://http://map.read.usuhx.com/Article/2538221.shtml
- http://http://map.mobile.xqnqq.com/Article/45364.shtml
- http://http://map.mobile.xqnqq.com/Article/9695984.shtml
- http://http://map.read.usuhx.com/Article/99835.shtml
- http://http://map.mobile.xqnqq.com/Article/6357664.shtml
- http://http://map.read.usuhx.com/Article/6352.shtml
- http://http://map.mobile.xqnqq.com/Article/793489.shtml
- http://http://map.mobile.xqnqq.com/Article/8551.shtml
- http://http://map.read.usuhx.com/Article/393618.shtml
- http://http://map.mobile.xqnqq.com/Article/4786602.shtml
- http://http://map.mobile.xqnqq.com/Article/094125.shtml
- http://http://map.read.usuhx.com/Article/5320564.shtml
- http://http://map.read.usuhx.com/Article/8173.shtml
- http://http://map.mobile.xqnqq.com/Article/247415.shtml
- http://http://map.read.usuhx.com/Article/9880255.shtml
- http://http://map.read.usuhx.com/Article/6834.shtml
- http://http://map.read.usuhx.com/Article/5340319.shtml
- http://http://map.read.usuhx.com/Article/8066.shtml
- http://http://map.read.usuhx.com/Article/001979.shtml
- http://http://map.read.usuhx.com/Article/5907054.shtml
- http://http://map.read.usuhx.com/Article/2533586.shtml
- http://http://map.mobile.xqnqq.com/Article/639660.shtml
- http://http://map.read.usuhx.com/Article/4341.shtml
- http://http://map.mobile.xqnqq.com/Article/1737.shtml
- http://http://map.read.usuhx.com/Article/9231815.shtml
- http://http://map.read.usuhx.com/Article/2275.shtml
- http://http://map.mobile.xqnqq.com/Article/2934606.shtml
- http://http://map.read.usuhx.com/Article/98078.shtml
- http://http://map.mobile.xqnqq.com/Article/2640.shtml
- http://http://map.read.usuhx.com/Article/5701.shtml
- http://http://map.mobile.xqnqq.com/Article/013975.shtml
- http://http://map.read.usuhx.com/Article/46374.shtml
- http://http://map.read.usuhx.com/Article/9803961.shtml
- http://http://map.mobile.xqnqq.com/Article/137848.shtml
- http://http://map.mobile.xqnqq.com/Article/12600.shtml
- http://http://map.read.usuhx.com/Article/9959.shtml
- http://http://map.read.usuhx.com/Article/0293.shtml
- http://http://map.mobile.xqnqq.com/Article/031974.shtml
- http://http://map.read.usuhx.com/Article/5982.shtml
- http://http://map.mobile.xqnqq.com/Article/01495.shtml
- http://http://map.mobile.xqnqq.com/Article/940582.shtml
- http://http://map.mobile.xqnqq.com/Article/473228.shtml
- http://http://map.read.usuhx.com/Article/41784.shtml
- http://http://map.read.usuhx.com/Article/749335.shtml
- http://http://map.mobile.xqnqq.com/Article/8515.shtml
- http://http://map.read.usuhx.com/Article/3255373.shtml
- http://http://map.read.usuhx.com/Article/098695.shtml
- http://http://map.mobile.xqnqq.com/Article/791281.shtml
- http://http://map.read.usuhx.com/Article/5253657.shtml
- http://http://map.read.usuhx.com/Article/28939.shtml
- http://http://map.mobile.xqnqq.com/Article/798373.shtml
- http://http://map.mobile.xqnqq.com/Article/3866.shtml
- http://http://map.read.usuhx.com/Article/8695.shtml
- http://http://map.read.usuhx.com/Article/49257.shtml
- http://http://map.mobile.xqnqq.com/Article/863852.shtml
- http://http://map.mobile.xqnqq.com/Article/8417.shtml
- http://http://map.read.usuhx.com/Article/94867.shtml
- http://http://map.read.usuhx.com/Article/6307616.shtml
- http://http://map.read.usuhx.com/Article/0178819.shtml
- http://http://map.mobile.xqnqq.com/Article/477556.shtml
- http://http://map.mobile.xqnqq.com/Article/5396513.shtml
- http://http://map.mobile.xqnqq.com/Article/987305.shtml
- http://http://map.read.usuhx.com/Article/39134.shtml
- http://http://map.read.usuhx.com/Article/82927.shtml
- http://http://map.mobile.xqnqq.com/Article/5979479.shtml
- http://http://map.read.usuhx.com/Article/32517.shtml
- http://http://map.read.usuhx.com/Article/860116.shtml
- http://http://map.mobile.xqnqq.com/Article/4898833.shtml
- http://http://map.mobile.xqnqq.com/Article/2565037.shtml
- http://http://map.mobile.xqnqq.com/Article/44157.shtml
- http://http://map.read.usuhx.com/Article/59835.shtml
- http://http://map.mobile.xqnqq.com/Article/6637.shtml
- http://http://map.read.usuhx.com/Article/991800.shtml
- http://http://map.read.usuhx.com/Article/313897.shtml
- http://http://map.read.usuhx.com/Article/99260.shtml
- http://http://map.read.usuhx.com/Article/99898.shtml
- http://http://map.mobile.xqnqq.com/Article/6514080.shtml
- http://http://map.read.usuhx.com/Article/02500.shtml
- http://http://map.read.usuhx.com/Article/833956.shtml
- http://http://map.mobile.xqnqq.com/Article/124909.shtml
- http://http://map.mobile.xqnqq.com/Article/0426663.shtml
- http://http://map.read.usuhx.com/Article/134164.shtml
- http://http://map.read.usuhx.com/Article/20691.shtml
- http://http://map.mobile.xqnqq.com/Article/055039.shtml
- http://http://map.mobile.xqnqq.com/Article/915913.shtml
- http://http://map.mobile.xqnqq.com/Article/6164433.shtml
- http://http://map.mobile.xqnqq.com/Article/0785503.shtml
- http://http://map.mobile.xqnqq.com/Article/49540.shtml
- http://http://map.mobile.xqnqq.com/Article/088648.shtml
- http://http://map.read.usuhx.com/Article/776638.shtml
- http://http://map.mobile.xqnqq.com/Article/24358.shtml
- http://http://map.read.usuhx.com/Article/980188.shtml
- http://http://map.read.usuhx.com/Article/2869.shtml
- http://http://map.mobile.xqnqq.com/Article/9019576.shtml
- http://http://map.read.usuhx.com/Article/7139.shtml
- http://http://map.read.usuhx.com/Article/6240630.shtml
- http://http://map.read.usuhx.com/Article/34427.shtml
- http://http://map.mobile.xqnqq.com/Article/9528.shtml
- http://http://map.read.usuhx.com/Article/392029.shtml
- http://http://map.mobile.xqnqq.com/Article/3874371.shtml
- http://http://map.mobile.xqnqq.com/Article/8786799.shtml
- http://http://map.read.usuhx.com/Article/7628869.shtml
- http://http://map.mobile.xqnqq.com/Article/3680458.shtml
- http://http://map.read.usuhx.com/Article/0041602.shtml
- http://http://map.mobile.xqnqq.com/Article/3475.shtml
- http://http://map.mobile.xqnqq.com/Article/2844.shtml
- http://http://map.read.usuhx.com/Article/55784.shtml
- http://http://map.mobile.xqnqq.com/Article/62534.shtml
- http://http://map.read.usuhx.com/Article/2431.shtml
- http://http://map.read.usuhx.com/Article/8048.shtml
- http://http://map.mobile.xqnqq.com/Article/0799065.shtml
- http://http://map.mobile.xqnqq.com/Article/6832.shtml
- http://http://map.mobile.xqnqq.com/Article/49630.shtml
- http://http://map.mobile.xqnqq.com/Article/7657393.shtml
- http://http://map.mobile.xqnqq.com/Article/6390516.shtml
- http://http://map.mobile.xqnqq.com/Article/6315.shtml
- http://http://map.read.usuhx.com/Article/32904.shtml
- http://http://map.read.usuhx.com/Article/6624293.shtml
- http://http://map.read.usuhx.com/Article/05394.shtml
- http://http://map.read.usuhx.com/Article/7439.shtml
- http://http://map.mobile.xqnqq.com/Article/1229.shtml
- http://http://map.read.usuhx.com/Article/2886.shtml
- http://http://map.mobile.xqnqq.com/Article/6090.shtml
- http://http://map.read.usuhx.com/Article/5918.shtml
- http://http://map.read.usuhx.com/Article/106812.shtml
- http://http://map.mobile.xqnqq.com/Article/6865773.shtml
- http://http://map.read.usuhx.com/Article/3397.shtml
- http://http://map.mobile.xqnqq.com/Article/00384.shtml
- http://http://map.read.usuhx.com/Article/154654.shtml
- http://http://map.mobile.xqnqq.com/Article/46417.shtml
- http://http://map.read.usuhx.com/Article/86933.shtml
- http://http://map.read.usuhx.com/Article/399894.shtml
- http://http://map.read.usuhx.com/Article/291727.shtml
- http://http://map.read.usuhx.com/Article/962630.shtml
- http://http://map.mobile.xqnqq.com/Article/361850.shtml
- http://http://map.mobile.xqnqq.com/Article/1138106.shtml
- http://http://map.read.usuhx.com/Article/10873.shtml
- http://http://map.read.usuhx.com/Article/5439.shtml
- http://http://map.read.usuhx.com/Article/6653.shtml
- http://http://map.mobile.xqnqq.com/Article/247957.shtml
- http://http://map.read.usuhx.com/Article/044651.shtml
- http://http://map.read.usuhx.com/Article/420193.shtml
- http://http://map.mobile.xqnqq.com/Article/2784.shtml

## 项目结构

```
linkmap-nav/
├── data/                           # 批次数据目录
│   ├── batch_64.txt                # 第64批原始链接列表（当前导入）
│   ├── batch_63.txt                # 历史批次示例
│   └── schema/                     # 数据格式定义
├── src/                            # 核心源码
│   ├── importer/                   # 链接导入模块
│   │   ├── parser.py               # 解析原始URL，提取域名与文章ID
│   │   └── dedup.py                # 基于布隆过滤器的轻量去重
│   ├── storage/                    # 存储层
│   │   ├── db.py                   # SQLite连接与表结构初始化
│   │   └── models.py               # ORM映射（文章、批次、标签）
│   ├── search/                     # 检索模块
│   │   ├── fts.py                  # FTS5虚拟表管理与查询构造
│   │   └── tokenizer.py            # 中文分词适配器
│   ├── monitor/                    # 状态监控
│   │   ├── checker.py              # 并发HTTP HEAD请求检测
│   │   └── reporter.py             # 失效链接报表生成
│   └── web/                        # Web服务层
│       ├── app.py                  # Flask应用主入口
│       ├── templates/              # Jinja2模板目录
│       └── static/                 # CSS与前端JavaScript资源
├── tests/                          # 单元测试与集成测试
│   ├── test_importer.py
│   ├── test_dedup.py
│   └── test_monitor.py
├── scripts/                        # 运维辅助脚本
│   ├── export_static.py            # 静态HTML导出工具
│   └── migrate_db.py               # 数据库版本迁移
├── docs/                           # 完整文档（见文档导航章节）
├── requirements.txt                # Python依赖列表（含版本锁定）
├── setup.py                        # 项目打包配置
└── README.md                       # 本文件
```

## 贡献指南

欢迎提交 Pull Request 或 Issue。请遵循以下流程以确保代码质量和项目一致性。

1. 阅读项目行为准则（CODE_OF_CONDUCT.md）并签署贡献者许可协议（CLA）。
2. 在 issue 列表中查找未被指派的待办项，或新建 issue 描述您要修复的问题或新增的功能，等待核心维护者标注 `accepted` 标签。
3. Fork 本仓库，在您的个人分支上基于 `dev` 分支进行开发，提交信息请遵循 Conventional Commits 规范（如 `feat: add batch export endpoint`）。
4. 编写或更新对应的单元测试，确保所有测试用例通过（`pytest tests/`），且覆盖率不低于 85%。
5. 提交 Pull Request 到 `dev` 分支，在 PR 描述中关联对应的 issue 编号，并附上手动测试截屏或日志片段（如有 UI 变动）。

## 常见问题

Q: 导入链接时提示“重复条目”，如何绕过去重机制强制导入？

A: 去重基于 URL 完整字符串与文章 ID 双重校验。如需强制导入，可在导入命令后添加 `--force` 参数：`python manage.py import --batch 64 --source file.txt --force`。此操作会跳过去重检查，但可能产生重复记录，建议仅在数据修复时使用。

Q: 静态导出生成的 HTML 页面不支持中文搜索，如何解决？

A: 静态导出模式仅用于只读浏览，不包含动态搜索功能。如需中文检索，请启动本地 Web 服务（`runserver`）或在生产环境部署带 FTS5 支持的 SQLite 后端。若使用云数据库，请确保已启用 SQLite 的 FTS5 扩展（编译时需开启 `-DSQLITE_ENABLE_FTS5`）。

Q: 监控模块报告大量链接超时，但浏览器可以正常访问，如何调整检测参数？

A: 默认超时时间为 3 秒，并发数为 10。您可在 `src/monitor/checker.py` 中调整 `TIMEOUT` 和 `MAX_WORKERS` 常量。对于移动端站点，建议将超时放宽至 5-8 秒，并减少并发数以避免触发对方防火墙策略。

## 许可证

MIT License

Copyright (c) 2026 LinkMap Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
