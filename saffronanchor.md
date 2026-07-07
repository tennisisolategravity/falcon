# LinkBridge 技术资源导航站

LinkBridge 是一个面向开发者、技术研究人员与开源爱好者的外链资源聚合与导航工具。该项目旨在解决技术阅读中优质外链分散、难以追溯、分类模糊的问题，通过结构化索引与轻量级元数据标注，帮助用户快速定位高价值技术文章、案例分析和工程实践参考。LinkBridge 本身不存储或修改任何外部内容，仅提供链接的整理、标签化与基础校验服务，适用于个人知识管理、团队技术文库建设以及社区资源共建等场景。

## 功能概览

批量外链导入与去重校验 系统支持从文本文件、CSV 或剪贴板批量导入 URL，自动执行语法校验与重复项过滤，减少人工整理成本。

多级标签分类体系 用户可为每条链接添加自定义标签（如“性能优化”“微服务”“前端工程”），并支持标签组合检索，实现精细化的资源筛选。

链接可用性健康检查 后台定时任务对已收录的 URL 发起 HEAD 请求，检测响应状态码与重定向链，标记失效链接并生成异常报告。

全文检索与字段过滤 基于链接标题、来源域名、标签集合和摘要描述进行关键词检索，同时支持按域名、状态码、更新时间等字段过滤结果。

公开只读 API 接口 提供符合 RESTful 风格的 JSON API，允许第三方系统批量获取资源列表、标签树和单条详情，便于集成到其他文档平台。

用户自定义收藏夹 注册用户可将感兴趣的资源链接加入个人收藏夹，并添加私有备注，实现个性化资源管理。

数据导出与订阅 支持将筛选后的资源列表导出为 Markdown、JSON 或 CSV 格式，同时提供 RSS 订阅功能，实时跟踪指定标签下的新增链接。

## 应用场景

技术团队内部文档共建 开发团队可将日常遇到的优秀外链统一收录至 LinkBridge，并标注关联业务模块，形成可持续积累的团队技术文库，减少重复搜索时间。

开源项目参考附录管理 开源项目维护者使用 LinkBridge 整理相关技术规范、生态工具和案例实现，作为项目 README 或官方文档的外部参考附录，提升文档完整度。

技术博客与 Newsletter 素材池 技术博主或资讯编辑利用 LinkBridge 分类存储潜在写作素材，结合标签检索快速组织主题稿件，提高内容产出效率。

个人学习路径资源归档 学习者按技能领域（如数据库内核、分布式系统、网络编程）建立独立收藏集合，配合失效检测功能及时更新过时参考，保障学习资料的可用性。

## 快速开始

以下操作指引您在本地环境部署 LinkBridge 服务。

```bash
git clone https://github.com/linkbridge/linkbridge.git
cd linkbridge
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver 0.0.0.0:8000
```

访问 http://localhost:8000 即可进入管理控制台，首次启动会提示创建管理员账户。使用 `python manage.py createsuperuser` 按提示完成管理员创建。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---------|---------|------|
| Python | 3.9 及以上 | 核心运行环境，推荐使用 3.11 |
| PostgreSQL | 13.0 及以上 | 主数据库，用于存储链接元数据与用户信息 |
| Redis | 6.2 及以上 | 缓存与消息队列后端，用于异步任务 |
| Celery | 5.3 及以上 | 异步任务调度框架，执行健康检查与导出 |
| Nginx | 1.22 及以上 | 生产环境反向代理与静态资源服务（可选） |
| Node.js | 18.0 及以上 | 仅用于前端资产构建（开发模式可选） |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|-----------|
| 用户手册 | /docs/user-guide/ | 如何注册、导入链接、使用标签和收藏功能 |
| 管理员指南 | /docs/admin-guide/ | 如何配置健康检查策略、管理用户权限、调整系统参数 |
| API 参考 | /docs/api-reference/ | 所有公开接口的请求参数、响应格式与错误码说明 |
| 部署运维 | /docs/deployment/ | 生产环境容器化部署、高可用配置与监控方案 |

## 资源列表

- http://http://www.mobile.xqnqq.com/Article/612316.shtml
- http://http://www.read.usuhx.com/Article/1042.shtml
- http://http://www.mobile.xqnqq.com/Article/009607.shtml
- http://http://www.mobile.xqnqq.com/Article/492706.shtml
- http://http://www.mobile.xqnqq.com/Article/5221110.shtml
- http://http://www.read.usuhx.com/Article/2423.shtml
- http://http://www.read.usuhx.com/Article/1355319.shtml
- http://http://www.mobile.xqnqq.com/Article/4655853.shtml
- http://http://www.read.usuhx.com/Article/99068.shtml
- http://http://www.mobile.xqnqq.com/Article/428466.shtml
- http://http://www.read.usuhx.com/Article/96651.shtml
- http://http://www.read.usuhx.com/Article/9820.shtml
- http://http://www.read.usuhx.com/Article/189115.shtml
- http://http://www.read.usuhx.com/Article/57316.shtml
- http://http://www.read.usuhx.com/Article/17686.shtml
- http://http://www.mobile.xqnqq.com/Article/685380.shtml
- http://http://www.mobile.xqnqq.com/Article/31685.shtml
- http://http://www.read.usuhx.com/Article/41356.shtml
- http://http://www.read.usuhx.com/Article/1968.shtml
- http://http://www.read.usuhx.com/Article/5027534.shtml
- http://http://www.mobile.xqnqq.com/Article/6561.shtml
- http://http://www.mobile.xqnqq.com/Article/1128.shtml
- http://http://www.mobile.xqnqq.com/Article/6952.shtml
- http://http://www.read.usuhx.com/Article/57275.shtml
- http://http://www.read.usuhx.com/Article/03737.shtml
- http://http://www.read.usuhx.com/Article/63504.shtml
- http://http://www.mobile.xqnqq.com/Article/7610.shtml
- http://http://www.read.usuhx.com/Article/925682.shtml
- http://http://www.mobile.xqnqq.com/Article/085705.shtml
- http://http://www.mobile.xqnqq.com/Article/0336.shtml
- http://http://www.mobile.xqnqq.com/Article/4591198.shtml
- http://http://www.mobile.xqnqq.com/Article/4008089.shtml
- http://http://www.mobile.xqnqq.com/Article/42211.shtml
- http://http://www.mobile.xqnqq.com/Article/0205298.shtml
- http://http://www.read.usuhx.com/Article/93614.shtml
- http://http://www.read.usuhx.com/Article/335995.shtml
- http://http://www.mobile.xqnqq.com/Article/974982.shtml
- http://http://www.mobile.xqnqq.com/Article/1461.shtml
- http://http://www.mobile.xqnqq.com/Article/297703.shtml
- http://http://www.read.usuhx.com/Article/4258354.shtml
- http://http://www.mobile.xqnqq.com/Article/8026.shtml
- http://http://www.read.usuhx.com/Article/889035.shtml
- http://http://www.mobile.xqnqq.com/Article/8885.shtml
- http://http://www.mobile.xqnqq.com/Article/408271.shtml
- http://http://www.mobile.xqnqq.com/Article/345133.shtml
- http://http://www.mobile.xqnqq.com/Article/618729.shtml
- http://http://www.mobile.xqnqq.com/Article/92841.shtml
- http://http://www.mobile.xqnqq.com/Article/7354069.shtml
- http://http://www.mobile.xqnqq.com/Article/6995.shtml
- http://http://www.read.usuhx.com/Article/8138.shtml
- http://http://www.mobile.xqnqq.com/Article/3206.shtml
- http://http://www.mobile.xqnqq.com/Article/184962.shtml
- http://http://www.read.usuhx.com/Article/242876.shtml
- http://http://www.read.usuhx.com/Article/55853.shtml
- http://http://www.mobile.xqnqq.com/Article/8325796.shtml
- http://http://www.mobile.xqnqq.com/Article/881621.shtml
- http://http://www.read.usuhx.com/Article/9320194.shtml
- http://http://www.read.usuhx.com/Article/7993.shtml
- http://http://www.mobile.xqnqq.com/Article/6433.shtml
- http://http://www.read.usuhx.com/Article/20052.shtml
- http://http://www.mobile.xqnqq.com/Article/2483551.shtml
- http://http://www.mobile.xqnqq.com/Article/53118.shtml
- http://http://www.read.usuhx.com/Article/49781.shtml
- http://http://www.mobile.xqnqq.com/Article/6276.shtml
- http://http://www.mobile.xqnqq.com/Article/384608.shtml
- http://http://www.mobile.xqnqq.com/Article/9137729.shtml
- http://http://www.read.usuhx.com/Article/33936.shtml
- http://http://www.mobile.xqnqq.com/Article/7940.shtml
- http://http://www.read.usuhx.com/Article/4226999.shtml
- http://http://www.mobile.xqnqq.com/Article/048040.shtml
- http://http://www.mobile.xqnqq.com/Article/572918.shtml
- http://http://www.read.usuhx.com/Article/28060.shtml
- http://http://www.read.usuhx.com/Article/586517.shtml
- http://http://www.mobile.xqnqq.com/Article/2068684.shtml
- http://http://www.read.usuhx.com/Article/9226665.shtml
- http://http://www.mobile.xqnqq.com/Article/70694.shtml
- http://http://www.mobile.xqnqq.com/Article/3873951.shtml
- http://http://www.mobile.xqnqq.com/Article/327122.shtml
- http://http://www.mobile.xqnqq.com/Article/6760514.shtml
- http://http://www.read.usuhx.com/Article/1956.shtml
- http://http://www.mobile.xqnqq.com/Article/5427.shtml
- http://http://www.read.usuhx.com/Article/537028.shtml
- http://http://www.read.usuhx.com/Article/0049.shtml
- http://http://www.mobile.xqnqq.com/Article/0820962.shtml
- http://http://www.read.usuhx.com/Article/3555.shtml
- http://http://www.mobile.xqnqq.com/Article/39612.shtml
- http://http://www.mobile.xqnqq.com/Article/73959.shtml
- http://http://www.read.usuhx.com/Article/479788.shtml
- http://http://www.mobile.xqnqq.com/Article/56437.shtml
- http://http://www.mobile.xqnqq.com/Article/0905081.shtml
- http://http://www.read.usuhx.com/Article/84141.shtml
- http://http://www.mobile.xqnqq.com/Article/04732.shtml
- http://http://www.read.usuhx.com/Article/6901155.shtml
- http://http://www.mobile.xqnqq.com/Article/963052.shtml
- http://http://www.read.usuhx.com/Article/460399.shtml
- http://http://www.read.usuhx.com/Article/0637.shtml
- http://http://www.mobile.xqnqq.com/Article/878140.shtml
- http://http://www.read.usuhx.com/Article/7462197.shtml
- http://http://www.mobile.xqnqq.com/Article/32493.shtml
- http://http://www.mobile.xqnqq.com/Article/7808.shtml
- http://http://www.read.usuhx.com/Article/751227.shtml
- http://http://www.read.usuhx.com/Article/47950.shtml
- http://http://www.read.usuhx.com/Article/4293391.shtml
- http://http://www.mobile.xqnqq.com/Article/13662.shtml
- http://http://www.read.usuhx.com/Article/748679.shtml
- http://http://www.mobile.xqnqq.com/Article/4835530.shtml
- http://http://www.mobile.xqnqq.com/Article/166743.shtml
- http://http://www.mobile.xqnqq.com/Article/6761792.shtml
- http://http://www.read.usuhx.com/Article/4337.shtml
- http://http://www.read.usuhx.com/Article/154559.shtml
- http://http://www.mobile.xqnqq.com/Article/490288.shtml
- http://http://www.read.usuhx.com/Article/1960.shtml
- http://http://www.read.usuhx.com/Article/75603.shtml
- http://http://www.mobile.xqnqq.com/Article/8588613.shtml
- http://http://www.mobile.xqnqq.com/Article/9352.shtml
- http://http://www.read.usuhx.com/Article/7792882.shtml
- http://http://www.read.usuhx.com/Article/7360305.shtml
- http://http://www.read.usuhx.com/Article/5980.shtml
- http://http://www.mobile.xqnqq.com/Article/8165.shtml
- http://http://www.read.usuhx.com/Article/920681.shtml
- http://http://www.read.usuhx.com/Article/785371.shtml
- http://http://www.read.usuhx.com/Article/311054.shtml
- http://http://www.mobile.xqnqq.com/Article/5872542.shtml
- http://http://www.read.usuhx.com/Article/9955.shtml
- http://http://www.mobile.xqnqq.com/Article/1620.shtml
- http://http://www.mobile.xqnqq.com/Article/506024.shtml
- http://http://www.read.usuhx.com/Article/68434.shtml
- http://http://www.read.usuhx.com/Article/948368.shtml
- http://http://www.read.usuhx.com/Article/6100548.shtml
- http://http://www.read.usuhx.com/Article/094521.shtml
- http://http://www.mobile.xqnqq.com/Article/3041971.shtml
- http://http://www.mobile.xqnqq.com/Article/2965.shtml
- http://http://www.read.usuhx.com/Article/7561376.shtml
- http://http://www.mobile.xqnqq.com/Article/000801.shtml
- http://http://www.read.usuhx.com/Article/658741.shtml
- http://http://www.read.usuhx.com/Article/46464.shtml
- http://http://www.read.usuhx.com/Article/1830.shtml
- http://http://www.read.usuhx.com/Article/8565285.shtml
- http://http://www.mobile.xqnqq.com/Article/109308.shtml
- http://http://www.read.usuhx.com/Article/967569.shtml
- http://http://www.read.usuhx.com/Article/17794.shtml
- http://http://www.read.usuhx.com/Article/0956.shtml
- http://http://www.mobile.xqnqq.com/Article/25685.shtml
- http://http://www.mobile.xqnqq.com/Article/6005.shtml
- http://http://www.read.usuhx.com/Article/09024.shtml
- http://http://www.read.usuhx.com/Article/9173.shtml
- http://http://www.mobile.xqnqq.com/Article/8429.shtml
- http://http://www.read.usuhx.com/Article/6524.shtml
- http://http://www.mobile.xqnqq.com/Article/187759.shtml
- http://http://www.mobile.xqnqq.com/Article/4915.shtml
- http://http://www.mobile.xqnqq.com/Article/9374799.shtml
- http://http://www.read.usuhx.com/Article/7004.shtml
- http://http://www.mobile.xqnqq.com/Article/562386.shtml
- http://http://www.read.usuhx.com/Article/6709175.shtml
- http://http://www.mobile.xqnqq.com/Article/77187.shtml
- http://http://www.mobile.xqnqq.com/Article/4652.shtml
- http://http://www.read.usuhx.com/Article/37283.shtml
- http://http://www.read.usuhx.com/Article/6413637.shtml
- http://http://www.mobile.xqnqq.com/Article/991633.shtml
- http://http://www.mobile.xqnqq.com/Article/851641.shtml
- http://http://www.read.usuhx.com/Article/7875.shtml
- http://http://www.read.usuhx.com/Article/733072.shtml
- http://http://www.read.usuhx.com/Article/00764.shtml
- http://http://www.mobile.xqnqq.com/Article/1501.shtml
- http://http://www.read.usuhx.com/Article/1190.shtml
- http://http://www.read.usuhx.com/Article/4008.shtml
- http://http://www.mobile.xqnqq.com/Article/71225.shtml
- http://http://www.read.usuhx.com/Article/477762.shtml
- http://http://www.mobile.xqnqq.com/Article/83077.shtml
- http://http://www.read.usuhx.com/Article/0085638.shtml
- http://http://www.mobile.xqnqq.com/Article/66558.shtml
- http://http://www.mobile.xqnqq.com/Article/5196.shtml
- http://http://www.mobile.xqnqq.com/Article/5433.shtml
- http://http://www.read.usuhx.com/Article/91357.shtml
- http://http://www.mobile.xqnqq.com/Article/13428.shtml
- http://http://www.read.usuhx.com/Article/2463.shtml
- http://http://www.mobile.xqnqq.com/Article/616093.shtml
- http://http://www.read.usuhx.com/Article/7857902.shtml
- http://http://www.mobile.xqnqq.com/Article/49226.shtml
- http://http://www.mobile.xqnqq.com/Article/11941.shtml
- http://http://www.mobile.xqnqq.com/Article/015575.shtml
- http://http://www.read.usuhx.com/Article/7367060.shtml
- http://http://www.read.usuhx.com/Article/0490304.shtml
- http://http://www.read.usuhx.com/Article/2251485.shtml
- http://http://www.read.usuhx.com/Article/698792.shtml
- http://http://www.read.usuhx.com/Article/1548.shtml
- http://http://www.mobile.xqnqq.com/Article/3577228.shtml
- http://http://www.mobile.xqnqq.com/Article/60595.shtml
- http://http://www.read.usuhx.com/Article/5740.shtml
- http://http://www.mobile.xqnqq.com/Article/5014.shtml
- http://http://www.read.usuhx.com/Article/32104.shtml
- http://http://www.mobile.xqnqq.com/Article/2376680.shtml
- http://http://www.read.usuhx.com/Article/6009.shtml
- http://http://www.read.usuhx.com/Article/22043.shtml
- http://http://www.mobile.xqnqq.com/Article/672455.shtml
- http://http://www.read.usuhx.com/Article/6440381.shtml
- http://http://www.read.usuhx.com/Article/4461436.shtml
- http://http://www.read.usuhx.com/Article/66736.shtml
- http://http://www.read.usuhx.com/Article/8108949.shtml
- http://http://www.read.usuhx.com/Article/767506.shtml
- http://http://www.mobile.xqnqq.com/Article/4057505.shtml
- http://http://www.mobile.xqnqq.com/Article/385807.shtml
- http://http://www.read.usuhx.com/Article/512372.shtml
- http://http://www.mobile.xqnqq.com/Article/2382.shtml
- http://http://www.mobile.xqnqq.com/Article/10138.shtml
- http://http://www.mobile.xqnqq.com/Article/52448.shtml
- http://http://www.mobile.xqnqq.com/Article/72920.shtml
- http://http://www.mobile.xqnqq.com/Article/1531740.shtml
- http://http://www.mobile.xqnqq.com/Article/85672.shtml
- http://http://www.read.usuhx.com/Article/90852.shtml
- http://http://www.mobile.xqnqq.com/Article/510545.shtml
- http://http://www.mobile.xqnqq.com/Article/7329.shtml
- http://http://www.read.usuhx.com/Article/7441330.shtml
- http://http://www.mobile.xqnqq.com/Article/9483.shtml
- http://http://www.read.usuhx.com/Article/0087301.shtml
- http://http://www.mobile.xqnqq.com/Article/76526.shtml
- http://http://www.mobile.xqnqq.com/Article/89665.shtml
- http://http://www.read.usuhx.com/Article/3029709.shtml
- http://http://www.read.usuhx.com/Article/0949683.shtml
- http://http://www.read.usuhx.com/Article/337635.shtml
- http://http://www.mobile.xqnqq.com/Article/10133.shtml
- http://http://www.read.usuhx.com/Article/0102.shtml
- http://http://www.read.usuhx.com/Article/1563.shtml
- http://http://www.mobile.xqnqq.com/Article/2438.shtml
- http://http://www.mobile.xqnqq.com/Article/1197394.shtml
- http://http://www.mobile.xqnqq.com/Article/4652070.shtml
- http://http://www.read.usuhx.com/Article/556939.shtml
- http://http://www.mobile.xqnqq.com/Article/3218782.shtml
- http://http://www.mobile.xqnqq.com/Article/3477.shtml
- http://http://www.read.usuhx.com/Article/343793.shtml
- http://http://www.read.usuhx.com/Article/4432588.shtml
- http://http://www.read.usuhx.com/Article/0803.shtml
- http://http://www.mobile.xqnqq.com/Article/231377.shtml
- http://http://www.read.usuhx.com/Article/86276.shtml
- http://http://www.read.usuhx.com/Article/1243483.shtml
- http://http://www.mobile.xqnqq.com/Article/007372.shtml
- http://http://www.mobile.xqnqq.com/Article/88509.shtml
- http://http://www.mobile.xqnqq.com/Article/6401578.shtml
- http://http://www.read.usuhx.com/Article/237031.shtml
- http://http://www.read.usuhx.com/Article/960068.shtml
- http://http://www.mobile.xqnqq.com/Article/8881229.shtml
- http://http://www.mobile.xqnqq.com/Article/282163.shtml
- http://http://www.read.usuhx.com/Article/2934155.shtml
- http://http://www.read.usuhx.com/Article/369334.shtml
- http://http://www.mobile.xqnqq.com/Article/0277337.shtml
- http://http://www.mobile.xqnqq.com/Article/7929148.shtml
- http://http://www.mobile.xqnqq.com/Article/77485.shtml
- http://http://www.mobile.xqnqq.com/Article/3706006.shtml
- http://http://www.read.usuhx.com/Article/6975.shtml
- http://http://www.read.usuhx.com/Article/9490222.shtml

## 项目结构

```
linkbridge/
├── src/                                 # 核心源代码目录
│   ├── api/                             # 公开 API 路由与序列化器
│   │   ├── endpoints/                   # 按资源类型划分的接口端点
│   │   └── serializers/                 # 请求/响应数据校验与转换
│   ├── core/                            # 业务逻辑核心模块
│   │   ├── link_manager.py              # 链接增删改查与去重逻辑
│   │   ├── tag_engine.py                # 标签树维护与关联计算
│   │   └── health_checker.py            # 异步健康检查任务实现
│   ├── models/                          # 数据模型定义（Django ORM）
│   │   ├── link.py                      # 链接实体字段与索引
│   │   ├── tag.py                       # 标签层级结构
│   │   └── user_profile.py              # 用户收藏与偏好
│   ├── tasks/                           # Celery 异步任务声明
│   │   ├── periodic.py                  # 定时任务（健康检查、统计）
│   │   └── export.py                    # 数据导出任务
│   └── utils/                           # 通用工具函数
│       ├── validators.py                # URL 校验与规范化
│       └── cache.py                     # Redis 缓存操作封装
├── config/                              # 环境配置与启动脚本
│   ├── settings/                        # 多环境配置（开发/测试/生产）
│   └── gunicorn.conf.py                 # WSGI 服务器参数
├── tests/                               # 单元测试与集成测试
│   ├── unit/                            # 核心模块单测
│   └── integration/                     # API 与数据库交互测试
├── frontend/                            # 管理控制台前端源码（Vue 3）
│   ├── src/                             # 组件与状态管理
│   └── dist/                            # 生产构建输出目录
├── docs/                                # 完整项目文档
│   ├── user-guide/                      # 用户操作手册
│   ├── admin-guide/                     # 管理员运维手册
│   └── api-reference/                   # API 详细参考
├── scripts/                             # 运维辅助脚本
│   ├── init_db.sql                      # 数据库初始化
│   └── backup.sh                        # 数据备份脚本
├── docker-compose.yml                   # 容器化编排文件
├── requirements.txt                     # Python 依赖清单
└── README.md                            # 项目简介（本文件）
```

## 贡献指南

1. 复刻主仓库并创建功能分支  
   访问 GitHub 项目主页，点击 Fork 按钮将仓库复制到个人账号下，随后使用 `git checkout -b feature/your-feature-name` 创建独立开发分支。

2. 编写或修改代码并确保测试通过  
   遵循项目现有的代码风格（PEP 8 与 ESLint 配置），新增功能需附带对应的单元测试，运行 `pytest tests/` 确认全部用例通过。

3. 提交变更说明并推送至远程分支  
   使用 `git commit -m "类型: 简短描述（如 fix: 修复健康检查超时处理）"` 格式提交，推送至个人复刻仓库的对应分支。

4. 发起合并请求并等待评审  
   在 GitHub 页面从个人分支向主仓库的 main 分支发起 Pull Request，填写模板中所需的变更描述、测试覆盖范围和影响面评估。

5. 根据评审意见修改并同步主分支最新代码  
   评审人提出修改意见后，在本地完成调整并再次推送，分支会自动更新 PR。最终由项目维护者合并。

## 常见问题

Q：导入大量链接时页面无响应或超时，如何解决？  
A：导入操作会触发后台异步任务，前端仅接收任务 ID 后即返回，不阻塞界面。若单次导入超过 500 条，建议使用脚本通过 API 批量提交，并开启 Celery 的并发 worker 提高处理速度。可在管理后台的“任务中心”查看导入进度与失败明细。

Q：健康检查报告显示某些链接状态异常，但手动访问浏览器可以打开，原因是什么？  
A：健康检查默认使用 HEAD 方法且超时时间为 5 秒，部分服务端对 HEAD 请求返回 405 或 403，但允许 GET 请求。可在系统设置中将检查方法切换为 GET，或增加超时时间至 10 秒。同时检查网络环境是否允许出口请求。

Q：能否将私有收藏夹与团队成员共享？  
A：当前版本暂不支持收藏夹共享功能，但您可以导出收藏夹为 JSON 文件，其他用户通过导入功能重建相同的收藏集合。团队级共享功能已列入后续版本计划。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-07 23:37:50
