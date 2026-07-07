# LinkMap 技术资源导航站

LinkMap 是一个面向开发者、技术研究人员与运维工程师的轻量级技术资源外链汇总与导航系统。该项目定位于对分散于多个内容源站点的技术文章、文档与案例进行统一收录与分类索引，帮助技术团队和个人快速检索到特定领域的高质量外链内容，降低信息查找成本，提升研发与故障排查效率。

LinkMap 不提供内容存储或转发服务，仅作为 URL 元信息整理与检索层，所有实际内容均指向原始发布站点。项目核心适用于需要持续跟踪多个技术内容源、构建内部知识索引体系或进行技术文章聚合分析的场景。

## 功能概览

- 多源外链统一收录：支持将来自不同域名、不同路径结构的技术文章链接按统一格式导入系统，自动解析 URL 组成部分并生成基础索引记录。

- 链接分类与标签标注：允许为每条外链记录添加自定义分类标签、技术领域标识和内容摘要备注，便于后续按主题筛选。

- 批量导入与去重检测：提供基于 URL 完整路径的 MD5 哈希去重机制，防止重复录入相同文章链接，支持 CSV 和纯文本列表两种批量导入方式。

- 基础检索与过滤：支持按来源域名、URL 关键词、收录时间范围进行简单检索与过滤，返回匹配的外链列表及基础元信息。

- 状态可用性监控：内置周期性 HTTP HEAD 请求检测机制，自动标记访问异常的链接并记录不可用时间戳，辅助维护链接库健康度。

- 导出与分享：支持将筛选后的链接列表导出为纯文本格式或 Markdown 列表格式，便于嵌入技术文档、周报或知识库。

## 应用场景

- 技术团队内部知识库构建：研发团队可将日常参考的官方文档、技术博客、故障排查案例链接统一收录至 LinkMap，形成团队共享的外链资源库，新人入职时可快速获取高质量学习资料列表。

- 技术内容聚合与周报生成：技术编辑或社区运营人员可利用 LinkMap 的批量导入与导出功能，定期从多个内容源站点收集最新技术文章链接，整理后生成带分类标注的链接清单，用于技术周报或月刊素材编排。

- 个人技术书签管理与迁移：开发者可将浏览器中分散存储的技术书签导出为链接列表，批量导入 LinkMap 进行集中管理，通过状态监控功能定期检测书签有效性，避免因站点迁移或页面删除导致书签失效。

- 技术调研与竞品分析：进行技术选型或竞品分析时，可使用 LinkMap 快速收集并归类相关的技术文档、产品公告与社区讨论链接，通过统一界面进行横向对比与资料梳理。

## 快速开始

以下步骤可在本地环境快速启动 LinkMap 服务。

```bash
# 克隆项目仓库至本地
git clone https://github.com/your-org/linkmap.git

# 进入项目根目录
cd linkmap

# 安装项目依赖（基于 Python 3.10 + pip）
pip install -r requirements.txt

# 初始化本地 SQLite 数据库表结构
python manage.py migrate

# 启动开发服务器，默认监听 127.0.0.1:8000
python manage.py runserver
```

访问 http://127.0.0.1:8000 即可进入 LinkMap 管理界面，开始导入和管理技术资源外链。

## 安装要求

| 依赖项 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.10 及以上 | 核心运行环境，建议使用 3.11 或 3.12 以获得更好性能 |
| pip | 22.0 及以上 | Python 包管理工具，用于安装项目依赖库 |
| SQLite | 3.35 及以上 | 默认内置数据库，用于存储链接索引和元信息，无需额外安装 |
| Django | 4.2.x LTS | Web 框架，提供 ORM、管理界面和基础请求处理能力 |
| requests | 2.31.x | 用于链接可用性检测时发送 HTTP HEAD 请求 |
| python-dotenv | 1.0.x | 管理环境变量配置，支持 .env 文件加载 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | /docs/user-guide/ | 如何批量导入链接、如何设置分类标签、如何查看可用性监控结果 |
| 管理员指南 | /docs/admin-guide/ | 如何配置周期性检测任务、如何清理失效链接、如何备份索引数据库 |
| API 参考 | /docs/api-reference/ | 如何通过 REST API 进行链接的增删改查、如何集成外部脚本批量操作 |
| 开发指南 | /docs/development/ | 如何二次开发扩展分类体系、如何替换检测逻辑、如何贡献代码 |

## 资源列表

- http://http://map.mobile.xqnqq.com/Article/9224.shtml
- http://http://map.mobile.xqnqq.com/Article/095744.shtml
- http://http://map.read.usuhx.com/Article/4858393.shtml
- http://http://map.mobile.xqnqq.com/Article/28499.shtml
- http://http://map.read.usuhx.com/Article/322144.shtml
- http://http://map.mobile.xqnqq.com/Article/4683.shtml
- http://http://map.mobile.xqnqq.com/Article/3960.shtml
- http://http://map.mobile.xqnqq.com/Article/1637386.shtml
- http://http://map.read.usuhx.com/Article/3529080.shtml
- http://http://map.read.usuhx.com/Article/1725935.shtml
- http://http://map.mobile.xqnqq.com/Article/16832.shtml
- http://http://map.mobile.xqnqq.com/Article/712077.shtml
- http://http://map.mobile.xqnqq.com/Article/8995936.shtml
- http://http://map.mobile.xqnqq.com/Article/415500.shtml
- http://http://map.read.usuhx.com/Article/439062.shtml
- http://http://map.mobile.xqnqq.com/Article/6574.shtml
- http://http://map.read.usuhx.com/Article/2921032.shtml
- http://http://map.read.usuhx.com/Article/3822760.shtml
- http://http://map.mobile.xqnqq.com/Article/60103.shtml
- http://http://map.read.usuhx.com/Article/757405.shtml
- http://http://map.mobile.xqnqq.com/Article/30377.shtml
- http://http://map.mobile.xqnqq.com/Article/225779.shtml
- http://http://map.read.usuhx.com/Article/0381.shtml
- http://http://map.read.usuhx.com/Article/981227.shtml
- http://http://map.read.usuhx.com/Article/1899500.shtml
- http://http://map.read.usuhx.com/Article/3012571.shtml
- http://http://map.mobile.xqnqq.com/Article/0277920.shtml
- http://http://map.mobile.xqnqq.com/Article/8181788.shtml
- http://http://map.read.usuhx.com/Article/088386.shtml
- http://http://map.read.usuhx.com/Article/9635.shtml
- http://http://map.read.usuhx.com/Article/3639.shtml
- http://http://map.read.usuhx.com/Article/727966.shtml
- http://http://map.read.usuhx.com/Article/0280.shtml
- http://http://map.mobile.xqnqq.com/Article/304662.shtml
- http://http://map.mobile.xqnqq.com/Article/8288.shtml
- http://http://map.read.usuhx.com/Article/2271.shtml
- http://http://map.mobile.xqnqq.com/Article/12541.shtml
- http://http://map.read.usuhx.com/Article/782418.shtml
- http://http://map.mobile.xqnqq.com/Article/113486.shtml
- http://http://map.mobile.xqnqq.com/Article/6570.shtml
- http://http://map.read.usuhx.com/Article/43341.shtml
- http://http://map.mobile.xqnqq.com/Article/8320283.shtml
- http://http://map.mobile.xqnqq.com/Article/28029.shtml
- http://http://map.read.usuhx.com/Article/9967206.shtml
- http://http://map.read.usuhx.com/Article/660350.shtml
- http://http://map.read.usuhx.com/Article/1306348.shtml
- http://http://map.mobile.xqnqq.com/Article/22121.shtml
- http://http://map.mobile.xqnqq.com/Article/3434676.shtml
- http://http://map.read.usuhx.com/Article/00527.shtml
- http://http://map.read.usuhx.com/Article/06826.shtml
- http://http://map.mobile.xqnqq.com/Article/8497045.shtml
- http://http://map.mobile.xqnqq.com/Article/971182.shtml
- http://http://map.mobile.xqnqq.com/Article/7128.shtml
- http://http://map.mobile.xqnqq.com/Article/2033224.shtml
- http://http://map.mobile.xqnqq.com/Article/33474.shtml
- http://http://map.mobile.xqnqq.com/Article/13162.shtml
- http://http://map.mobile.xqnqq.com/Article/04177.shtml
- http://http://map.mobile.xqnqq.com/Article/575434.shtml
- http://http://map.read.usuhx.com/Article/8838371.shtml
- http://http://map.mobile.xqnqq.com/Article/0190451.shtml
- http://http://map.mobile.xqnqq.com/Article/53718.shtml
- http://http://map.mobile.xqnqq.com/Article/3412771.shtml
- http://http://map.mobile.xqnqq.com/Article/627177.shtml
- http://http://map.read.usuhx.com/Article/883253.shtml
- http://http://map.read.usuhx.com/Article/236338.shtml
- http://http://map.read.usuhx.com/Article/046867.shtml
- http://http://map.mobile.xqnqq.com/Article/3250.shtml
- http://http://map.read.usuhx.com/Article/375799.shtml
- http://http://map.mobile.xqnqq.com/Article/761115.shtml
- http://http://map.read.usuhx.com/Article/1598299.shtml
- http://http://map.mobile.xqnqq.com/Article/6649791.shtml
- http://http://map.mobile.xqnqq.com/Article/34875.shtml
- http://http://map.mobile.xqnqq.com/Article/12925.shtml
- http://http://map.mobile.xqnqq.com/Article/44591.shtml
- http://http://map.mobile.xqnqq.com/Article/15647.shtml
- http://http://map.mobile.xqnqq.com/Article/576571.shtml
- http://http://map.read.usuhx.com/Article/46166.shtml
- http://http://map.read.usuhx.com/Article/01022.shtml
- http://http://map.mobile.xqnqq.com/Article/0654.shtml
- http://http://map.mobile.xqnqq.com/Article/75619.shtml
- http://http://map.mobile.xqnqq.com/Article/219937.shtml
- http://http://map.mobile.xqnqq.com/Article/947084.shtml
- http://http://map.mobile.xqnqq.com/Article/0062.shtml
- http://http://map.read.usuhx.com/Article/128173.shtml
- http://http://map.mobile.xqnqq.com/Article/9168501.shtml
- http://http://map.mobile.xqnqq.com/Article/4177.shtml
- http://http://map.read.usuhx.com/Article/9191252.shtml
- http://http://map.mobile.xqnqq.com/Article/4561.shtml
- http://http://map.mobile.xqnqq.com/Article/0343662.shtml
- http://http://map.read.usuhx.com/Article/20946.shtml
- http://http://map.mobile.xqnqq.com/Article/8870.shtml
- http://http://map.mobile.xqnqq.com/Article/13523.shtml
- http://http://map.mobile.xqnqq.com/Article/4125912.shtml
- http://http://map.mobile.xqnqq.com/Article/7216.shtml
- http://http://map.mobile.xqnqq.com/Article/714537.shtml
- http://http://map.mobile.xqnqq.com/Article/1982.shtml
- http://http://map.read.usuhx.com/Article/134595.shtml
- http://http://map.mobile.xqnqq.com/Article/4266055.shtml
- http://http://map.mobile.xqnqq.com/Article/72052.shtml
- http://http://map.mobile.xqnqq.com/Article/6515748.shtml
- http://http://map.read.usuhx.com/Article/6305544.shtml
- http://http://map.mobile.xqnqq.com/Article/0809.shtml
- http://http://map.mobile.xqnqq.com/Article/2069389.shtml
- http://http://map.read.usuhx.com/Article/6935.shtml
- http://http://map.mobile.xqnqq.com/Article/4033.shtml
- http://http://map.mobile.xqnqq.com/Article/2171420.shtml
- http://http://map.read.usuhx.com/Article/4410.shtml
- http://http://map.mobile.xqnqq.com/Article/6325105.shtml
- http://http://map.read.usuhx.com/Article/998756.shtml
- http://http://map.read.usuhx.com/Article/673821.shtml
- http://http://map.mobile.xqnqq.com/Article/8484.shtml
- http://http://map.read.usuhx.com/Article/0443400.shtml
- http://http://map.read.usuhx.com/Article/575752.shtml
- http://http://map.read.usuhx.com/Article/5215276.shtml
- http://http://map.mobile.xqnqq.com/Article/6013600.shtml
- http://http://map.mobile.xqnqq.com/Article/3100.shtml
- http://http://map.read.usuhx.com/Article/5373.shtml
- http://http://map.read.usuhx.com/Article/9730368.shtml
- http://http://map.mobile.xqnqq.com/Article/2046.shtml
- http://http://map.read.usuhx.com/Article/14120.shtml
- http://http://map.mobile.xqnqq.com/Article/3888605.shtml
- http://http://map.mobile.xqnqq.com/Article/96284.shtml
- http://http://map.mobile.xqnqq.com/Article/930312.shtml
- http://http://map.read.usuhx.com/Article/901066.shtml
- http://http://map.read.usuhx.com/Article/619365.shtml
- http://http://map.mobile.xqnqq.com/Article/659896.shtml
- http://http://map.read.usuhx.com/Article/778558.shtml
- http://http://map.read.usuhx.com/Article/37829.shtml
- http://http://map.read.usuhx.com/Article/531984.shtml
- http://http://map.mobile.xqnqq.com/Article/417675.shtml
- http://http://map.mobile.xqnqq.com/Article/21713.shtml
- http://http://map.mobile.xqnqq.com/Article/993781.shtml
- http://http://map.mobile.xqnqq.com/Article/3323.shtml
- http://http://map.read.usuhx.com/Article/32270.shtml
- http://http://map.mobile.xqnqq.com/Article/4966764.shtml
- http://http://map.mobile.xqnqq.com/Article/0925506.shtml
- http://http://map.mobile.xqnqq.com/Article/3312.shtml
- http://http://map.mobile.xqnqq.com/Article/4378.shtml
- http://http://map.mobile.xqnqq.com/Article/2578.shtml
- http://http://map.mobile.xqnqq.com/Article/459312.shtml
- http://http://map.mobile.xqnqq.com/Article/5023696.shtml
- http://http://map.read.usuhx.com/Article/6355.shtml
- http://http://map.read.usuhx.com/Article/0692384.shtml
- http://http://map.read.usuhx.com/Article/9406129.shtml
- http://http://map.read.usuhx.com/Article/562267.shtml
- http://http://map.mobile.xqnqq.com/Article/7924789.shtml
- http://http://map.mobile.xqnqq.com/Article/738545.shtml
- http://http://map.read.usuhx.com/Article/2534809.shtml
- http://http://map.read.usuhx.com/Article/2448.shtml
- http://http://map.read.usuhx.com/Article/5540.shtml
- http://http://map.mobile.xqnqq.com/Article/13246.shtml
- http://http://map.mobile.xqnqq.com/Article/651060.shtml
- http://http://map.mobile.xqnqq.com/Article/4939056.shtml
- http://http://map.read.usuhx.com/Article/16156.shtml
- http://http://map.mobile.xqnqq.com/Article/0197031.shtml
- http://http://map.mobile.xqnqq.com/Article/649700.shtml
- http://http://map.read.usuhx.com/Article/10170.shtml
- http://http://map.read.usuhx.com/Article/25251.shtml
- http://http://map.read.usuhx.com/Article/53657.shtml
- http://http://map.mobile.xqnqq.com/Article/598219.shtml
- http://http://map.read.usuhx.com/Article/7560.shtml
- http://http://map.read.usuhx.com/Article/21986.shtml
- http://http://map.mobile.xqnqq.com/Article/688049.shtml
- http://http://map.mobile.xqnqq.com/Article/41458.shtml
- http://http://map.mobile.xqnqq.com/Article/557285.shtml
- http://http://map.mobile.xqnqq.com/Article/59778.shtml
- http://http://map.mobile.xqnqq.com/Article/25131.shtml
- http://http://map.read.usuhx.com/Article/3087.shtml
- http://http://map.read.usuhx.com/Article/1170.shtml
- http://http://map.read.usuhx.com/Article/857287.shtml
- http://http://map.read.usuhx.com/Article/352712.shtml
- http://http://map.mobile.xqnqq.com/Article/9231827.shtml
- http://http://map.read.usuhx.com/Article/078408.shtml
- http://http://map.read.usuhx.com/Article/58849.shtml
- http://http://map.mobile.xqnqq.com/Article/56171.shtml
- http://http://map.read.usuhx.com/Article/2351303.shtml
- http://http://map.mobile.xqnqq.com/Article/036653.shtml
- http://http://map.read.usuhx.com/Article/532317.shtml
- http://http://map.read.usuhx.com/Article/7081288.shtml
- http://http://map.mobile.xqnqq.com/Article/1702.shtml
- http://http://map.read.usuhx.com/Article/622565.shtml
- http://http://map.mobile.xqnqq.com/Article/11783.shtml
- http://http://map.mobile.xqnqq.com/Article/05362.shtml
- http://http://map.read.usuhx.com/Article/040488.shtml
- http://http://map.mobile.xqnqq.com/Article/3878.shtml
- http://http://map.mobile.xqnqq.com/Article/786536.shtml
- http://http://map.read.usuhx.com/Article/76375.shtml
- http://http://map.read.usuhx.com/Article/9089053.shtml
- http://http://map.read.usuhx.com/Article/4965.shtml
- http://http://map.mobile.xqnqq.com/Article/66961.shtml
- http://http://map.read.usuhx.com/Article/278055.shtml
- http://http://map.read.usuhx.com/Article/9765.shtml
- http://http://map.read.usuhx.com/Article/2270882.shtml
- http://http://map.read.usuhx.com/Article/71591.shtml
- http://http://map.mobile.xqnqq.com/Article/585854.shtml
- http://http://map.read.usuhx.com/Article/6311987.shtml
- http://http://map.read.usuhx.com/Article/65293.shtml
- http://http://map.read.usuhx.com/Article/77205.shtml
- http://http://map.read.usuhx.com/Article/5270.shtml
- http://http://map.mobile.xqnqq.com/Article/9432725.shtml
- http://http://map.read.usuhx.com/Article/2040364.shtml
- http://http://map.read.usuhx.com/Article/61344.shtml
- http://http://map.read.usuhx.com/Article/4510.shtml
- http://http://map.mobile.xqnqq.com/Article/3974.shtml
- http://http://map.read.usuhx.com/Article/24936.shtml
- http://http://map.mobile.xqnqq.com/Article/0060.shtml
- http://http://map.mobile.xqnqq.com/Article/80070.shtml
- http://http://map.read.usuhx.com/Article/5486920.shtml
- http://http://map.read.usuhx.com/Article/13045.shtml
- http://http://map.mobile.xqnqq.com/Article/1748.shtml
- http://http://map.read.usuhx.com/Article/6536.shtml
- http://http://map.mobile.xqnqq.com/Article/2393.shtml
- http://http://map.read.usuhx.com/Article/26836.shtml
- http://http://map.mobile.xqnqq.com/Article/091230.shtml
- http://http://map.mobile.xqnqq.com/Article/9398.shtml
- http://http://map.read.usuhx.com/Article/17050.shtml
- http://http://map.mobile.xqnqq.com/Article/084696.shtml
- http://http://map.mobile.xqnqq.com/Article/3613741.shtml
- http://http://map.mobile.xqnqq.com/Article/77240.shtml
- http://http://map.read.usuhx.com/Article/6503.shtml
- http://http://map.read.usuhx.com/Article/7582.shtml
- http://http://map.read.usuhx.com/Article/9376410.shtml
- http://http://map.mobile.xqnqq.com/Article/793533.shtml
- http://http://map.mobile.xqnqq.com/Article/7582861.shtml
- http://http://map.read.usuhx.com/Article/4971241.shtml
- http://http://map.mobile.xqnqq.com/Article/22067.shtml
- http://http://map.read.usuhx.com/Article/3246337.shtml
- http://http://map.mobile.xqnqq.com/Article/2183580.shtml
- http://http://map.read.usuhx.com/Article/8529.shtml
- http://http://map.read.usuhx.com/Article/742336.shtml
- http://http://map.read.usuhx.com/Article/5210176.shtml
- http://http://map.mobile.xqnqq.com/Article/26510.shtml
- http://http://map.read.usuhx.com/Article/0671.shtml
- http://http://map.mobile.xqnqq.com/Article/4459.shtml
- http://http://map.read.usuhx.com/Article/66485.shtml
- http://http://map.mobile.xqnqq.com/Article/1857.shtml
- http://http://map.read.usuhx.com/Article/741719.shtml
- http://http://map.mobile.xqnqq.com/Article/7033.shtml
- http://http://map.mobile.xqnqq.com/Article/1292839.shtml
- http://http://map.read.usuhx.com/Article/757287.shtml
- http://http://map.read.usuhx.com/Article/6843551.shtml
- http://http://map.mobile.xqnqq.com/Article/9846.shtml
- http://http://map.mobile.xqnqq.com/Article/7469.shtml
- http://http://map.read.usuhx.com/Article/94930.shtml
- http://http://map.mobile.xqnqq.com/Article/6759860.shtml
- http://http://map.read.usuhx.com/Article/113569.shtml
- http://http://map.read.usuhx.com/Article/50164.shtml
- http://http://map.mobile.xqnqq.com/Article/8413.shtml
- http://http://map.mobile.xqnqq.com/Article/9020546.shtml
- http://http://map.mobile.xqnqq.com/Article/8920923.shtml

## 项目结构

```
linkmap/
├── manage.py                 # Django 项目管理入口，用于启动服务、执行迁移与创建超级用户
├── requirements.txt          # Python 依赖声明文件，包含所有必需第三方库及版本锁定
├── .env.example              # 环境变量配置模板，包含 SECRET_KEY、DEBUG 模式等敏感参数
├── linkmap/                  # 项目全局配置目录
│   ├── __init__.py
│   ├── settings.py           # 主配置文件，包含数据库、中间件、静态文件与日志等设置
│   ├── urls.py               # 根路由配置，映射到各子应用的路由入口
│   └── wsgi.py               # WSGI 网关接口，用于生产环境部署
├── apps/                     # 所有自定义应用存放目录
│   ├── links/                # 链接管理核心应用
│   │   ├── models.py         # Link 数据模型定义，包含 URL、来源域名、收录时间、状态等字段
│   │   ├── views.py          # 链接列表、导入、检索、导出等视图函数
│   │   ├── admin.py          # Django 管理后台定制，支持按域名、状态筛选链接记录
│   │   └── utils.py          # URL 解析、去重哈希计算、HTTP 状态检测等工具函数
│   ├── monitor/              # 周期性健康检查应用
│   │   ├── tasks.py          # 定时任务定义，调用检测逻辑并更新链接状态
│   │   └── scheduler.py      # 基于 APScheduler 的任务调度配置
│   └── api/                  # REST API 应用，提供外部系统集成接口
│       ├── serializers.py    # 链接数据的序列化与反序列化定义
│       └── viewsets.py       # API 视图集，支持 CRUD 操作
├── static/                   # 静态资源目录，包含 CSS、JavaScript 和图片文件
├── templates/                # HTML 模板目录，包含管理界面和列表展示页面
└── docs/                     # 项目文档目录
    ├── user-guide.md
    ├── admin-guide.md
    ├── api-reference.md
    └── development.md
```

## 贡献指南

1. 复刻项目仓库至个人账号，克隆到本地开发环境，确保 Python 3.10 及以上版本已安装。创建新的功能分支，分支命名遵循 `feature/描述` 或 `fix/描述` 格式。

2. 在本地安装开发依赖，包括测试框架和代码检查工具。执行 `pip install -r requirements-dev.txt` 安装额外开发依赖，并运行 `pre-commit install` 启用代码风格自动检查。

3. 实现功能或修复缺陷后，编写或更新相应的单元测试，确保测试覆盖核心逻辑。运行 `python manage.py test` 验证所有测试用例通过，同时保证原有功能未受影响。

4. 更新文档目录下对应的文档文件，若新增功能涉及用户可感知的变化，需在 `docs/user-guide.md` 或 `docs/api-reference.md` 中添加相关说明段落。

5. 提交变更并推送到复刻仓库，向主仓库的 `main` 分支发起 Pull Request。请求描述中需明确说明变更目的、实现方式及测试结果摘要，等待项目维护者审核。

## 常见问题

Q: 导入大量链接时出现超时或内存占用过高如何处理？

A: 建议将单次导入的链接数量控制在 500 条以内，使用分批导入策略。可通过管理界面分批次上传 CSV 文件，或使用 API 接口逐批提交。对于超过 2000 条的批量导入，推荐在服务器端使用 `python manage.py import_links --file links.txt --batch-size 200` 命令行方式进行导入，该方式绕过了 HTTP 请求超时限制。

Q: 链接可用性检测显示大量链接状态异常，但实际浏览器中可以正常访问，原因是什么？

A: 可用性检测默认使用 HTTP HEAD 方法，部分站点可能不支持 HEAD 请求或对 HEAD 请求返回非标准状态码。此外，某些站点会校验 User-Agent 或要求携带特定 Cookie。如需更准确的检测结果，可在配置文件中将检测方法修改为 GET，并设置合适的请求头。检测超时时间默认设置为 5 秒，若目标站点响应较慢可适当调大该值。

Q: 如何将现有浏览器书签批量导入 LinkMap？

A: 主流浏览器支持将书签导出为 HTML 文件或 CSV 格式。首先从浏览器导出书签文件，然后使用项目提供的转换脚本 `scripts/convert_bookmarks.py` 将书签文件转换为 LinkMap 兼容的 CSV 格式。转换后生成的 CSV 包含 URL 和标题两列，通过管理界面的批量导入功能上传该 CSV 文件即可完成导入。若浏览器导出格式为 JSON，可使用 `scripts/convert_json.py` 进行转换。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
