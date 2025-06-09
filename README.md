# 我的商小

## 项目介绍

本项目是一个学生校园生活社交软件。前端使用uniapp+javascript+scss+vue.js,后端使用python+FastAPI，数据库使用MySQL+Navicat。主要功能有：

- 发布具有标题，文字内容，配图的帖子，进行校园生活分享或者二手物品买卖。
- 对帖子进行点赞，评论收藏。
- 发布对于老师，课程，食堂等校园模块的评分和评价留言。
- 导入课程表，对课程信息进行查询。
- 进行兼职工作的招聘。

## 小组成员与分工

| 姓名                                    | 学号       | 分工                  |
| --------------------------------------- | ---------- | --------------------- |
| [李坤](https://github.com/applekkkk)    | 2223040529 | 前端核心开发+扩展模块 |
| [刘群](https://github.com/liuqun579367) | 2212190233 | 后端服务+基础设施     |

## 项目结构

```mermaid
mindmap
	root((我的商小))
		技术栈
			前端
				uniapp
				Vue.js
				uni-ui
				javascript
				Dcloud
			后端
				Python
				Fastapi
				MySQL
				Redis
				ORM
		功能模块
			帖子管理
				发布帖子
				点赞帖子
				收藏帖子
				删除帖子
				添加评论
			校园评价
				发布主题
				进行打分
				统计分数
				进行排名
				添加评论
			
		测试方案
			后端测试
				Postman
				Pytest
			集成测试
				selenium
		第三方服务
			界面设计
				即时设计
			文档编写
				markdown
				typora
			版本管理
				git
				github
```



## 项目计划

```mermaid
gantt
    title 我的商小 - 项目开发计划 (2025/03/04 - 2025/06/01)
    dateFormat  YYYY-MM-DD
    axisFormat %m/%d

    section 需求与设计
    需求分析 (李坤 & 刘群)  :a1, 2025-03-04, 7d
    技术方案评审 (李坤 & 刘群) :a2, after a1, 5d
    UI/UX 原型设计 (李坤) :a3, after a2, 7d
    数据库结构设计 (刘群) :a4, after a2, 7d
    API 设计 (刘群)       :a5, after a4, 5d

    section 基础架构
    前端项目搭建 (李坤) :b1, 2025-03-20, 7d
    后端基础设施搭建 (刘群) :b2, 2025-03-20, 10d
    数据库初始化 (刘群) :b3, after b2, 5d
    登录/注册功能 (刘群) :b4, after b3, 7d

    section 核心功能开发
    帖子管理 (发布/点赞/评论) (李坤 & 刘群) :c1, 2025-04-05, 10d
    校园评价 (评分/排名/评论) (李坤 & 刘群) :c2, after c1, 10d
    课程管理 (课程导入/查询) (李坤 & 刘群) :c3, after c2, 10d
    招聘管理 (发布/接受) (李坤 & 刘群) :c4, after c3, 10d

    section 扩展与优化
    UI 细节优化 (李坤) :d1, 2025-05-10, 7d
    后端性能优化 (刘群) :d2, 2025-05-10, 7d
    前端动画与交互优化 (李坤) :d3, after d1, 5d

    section 测试与部署
    后端 API 测试 (刘群) :e1, after c4, 7d
    前端页面测试 (李坤) :e2, after c4, 7d
    集成测试 (李坤 & 刘群) :e3, after e1, 5d
    服务器环境搭建 (刘群) :e4, after e3, 3d
    版本发布 (李坤 & 刘群) :e5, after e4, 2d

```
