---
title: 个人项目
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.29"

---

# 个人项目

Base URLs:

* <a href="http://localhost:8080">测试环境: http://localhost:8080</a>

# Authentication

# 我的商小/用户管理

本项目后端接口遵循RESTful设计理念，致力于设计简洁、规范、易用的API接口，确保前后端协作高效稳定。具体设计原则如下：

### 1.1 RESTful设计原则

- **资源导向**：接口以资源为核心，使用HTTP方法表达操作语义，例如：

  - `GET` 查询资源

  - `POST` 创建资源

  - `PUT` 更新资源

  - `DELETE` 删除资源

- **无状态性**：服务器不保存客户端状态，每次请求都包含所有必要信息，提高系统可扩展性。

- **统一接口**：采用统一的请求格式和响应格式，简化客户端调用。

- **分层架构**：通过不同层次分离接口职责，便于扩展和维护。

### 1.2 命名规范

- 使用**小写字母**和**连字符（-）**分隔路径单词，例如：`/api/user-profile`。

- 资源名称一般使用**复数形式**表示资源集合，例如：`/api/users`。

- 使用路径参数表示具体资源，例如：`/api/users/{userId}`。

- 查询操作可使用查询参数，例如：`/api/posts?author=123`。

### 1.3 版本控制策略

- API路径中明确版本号，例如 `/api/v1/users`，便于未来接口升级和兼容旧版本。

- 遵循语义化版本管理，主要版本号变化时可能破坏兼容性，次版本号用于增加功能，补丁版本用于修复问题。

- 保持旧版本接口一段时间，保证客户端平滑迁移。

## 2 接口文档

分模块进行介绍，并通过APIfox或Swagger介绍API的设计理念，使用、测试方法等。用列表和文档对所有的API进行详细的列举和描述。

### 2.1 用户管理接口

#### POST 用户登录

POST /api/user/login

> Body 请求参数

```yaml
email: ""
password: ""

```

#### 请求参数

| 名称       | 位置 | 类型   | 必选 | 说明           |
| ---------- | ---- | ------ | ---- | -------------- |
| body       | body | object | 否   | none           |
| » email    | body | string | 否   | none           |
| » password | body | string | 否   | 密码（未加密） |

> 返回示例

> 200 Response

```json
{
  "userId": "string",
  "username": "string",
  "email": "string",
  "token": "string",
  "expiresIn": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明                 |
| ----------- | ------ | ---- | ---- | ------ | -------------------- |
| » userId    | string | true | none |        | none                 |
| » username  | string | true | none |        | none                 |
| » email     | string | true | none |        | none                 |
| » token     | string | true | none |        | none                 |
| » expiresIn | string | true | none |        | Token 过期时间（秒） |

#### POST 用户注册

POST /api/user/register

> Body 请求参数

```yaml
username: ""
password: ""
email: ""
avatar: ""

```

#### 请求参数

| 名称       | 位置 | 类型   | 必选 | 说明             |
| ---------- | ---- | ------ | ---- | ---------------- |
| body       | body | object | 否   | none             |
| » username | body | string | 否   | none             |
| » password | body | string | 否   | none             |
| » email    | body | string | 否   | none             |
| » avatar   | body | string | 否   | 头像 URL（可选） |

> 返回示例

> 200 Response

```json
{
  "userId": "int",
  "username": "string",
  "email": "string",
  "createdAt": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ----------- | ------ | ---- | ---- | ------ | ---- |
| » userId    | string | true | none |        | none |
| » username  | string | true | none |        | none |
| » email     | string | true | none |        | none |
| » createdAt | string | true | none |        | none |

#### GET 用户信息获取

GET /api/user/{userId}

> Body 请求参数

```yaml
{}

```

#### 请求参数

| 名称   | 位置 | 类型   | 必选 | 说明 |
| ------ | ---- | ------ | ---- | ---- |
| userId | path | string | 是   | none |
| body   | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "userId": "int",
  "username": "string",
  "email": "string",
  "avatar": "string",
  "bio": "string",
  "createdAt": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ----------- | ------ | ---- | ---- | ------ | ---- |
| » userId    | string | true | none |        | none |
| » username  | string | true | none |        | none |
| » email     | string | true | none |        | none |
| » avatar    | string | true | none |        | none |
| » bio       | string | true | none |        | none |
| » createdAt | string | true | none |        | none |

#### PUT 用户信息更新 

PUT /api/user/{userId}

> Body 请求参数

```yaml
username: ""
email: ""
avatar: ""
bio: ""

```

#### 请求参数

| 名称       | 位置 | 类型   | 必选 | 说明 |
| ---------- | ---- | ------ | ---- | ---- |
| userId     | path | string | 是   | none |
| body       | body | object | 否   | none |
| » username | body | string | 否   | none |
| » email    | body | string | 否   | none |
| » avatar   | body | string | 否   | none |
| » bio      | body | string | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

#### POST 添加收藏

POST /api/user/{userId}/collect

> Body 请求参数

```yaml
postId: 0

```

#### 请求参数

| 名称     | 位置 | 类型    | 必选 | 说明 |
| -------- | ---- | ------- | ---- | ---- |
| userId   | path | string  | 是   | none |
| body     | body | object  | 否   | none |
| » postId | body | integer | 否   | none |

> 返回示例

> 200 Response

```json
{
  "postId": "int"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称     | 类型   | 必选 | 约束 | 中文名 | 说明 |
| -------- | ------ | ---- | ---- | ------ | ---- |
| » postId | string | true | none |        | none |

#### GET 获取收藏列表

GET /api/user/{userId}/collect

> Body 请求参数

```yaml
{}

```

#### 请求参数

| 名称   | 位置 | 类型   | 必选 | 说明 |
| ------ | ---- | ------ | ---- | ---- |
| userId | path | string | 是   | none |
| body   | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "collections": [
    {
      "collectId": "int",
      "postId": "int",
      "title": "string",
      "category": "string",
      "createdAt": "string"
    }
  ]
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称          | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------- | -------- | ----- | ---- | ------ | ---- |
| » collections | [object] | true  | none |        | none |
| »» collectId  | string   | false | none |        | none |
| »» postId     | string   | false | none |        | none |
| »» title      | string   | false | none |        | none |
| »» category   | string   | false | none |        | none |
| »» createdAt  | string   | false | none |        | none |

#### DELETE 取消收藏

DELETE /api/user/{userId}/collect/{postId}

> Body 请求参数

```yaml
{}

```

#### 请求参数

| 名称   | 位置 | 类型   | 必选 | 说明 |
| ------ | ---- | ------ | ---- | ---- |
| userId | path | string | 是   | none |
| postId | path | string | 是   | none |
| body   | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |



### 2.2 帖子管理接口  

#### POST 发表评论

POST /api/post/{postId}/comment

> Body 请求参数

```yaml
userId: 0
content: ""

```

#### 请求参数

| 名称      | 位置 | 类型    | 必选 | 说明 |
| --------- | ---- | ------- | ---- | ---- |
| postId    | path | string  | 是   | none |
| body      | body | object  | 否   | none |
| » userId  | body | integer | 否   | none |
| » content | body | string  | 否   | none |

> 返回示例

> 200 Response

```json
{
  "commentId": "int",
  "message": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ----------- | ------ | ---- | ---- | ------ | ---- |
| » commentId | string | true | none |        | none |
| » message   | string | true | none |        | none |

#### GET 获取动态评论

GET /api/post/{postId}/comments

> Body 请求参数

```yaml
{}

```

#### 请求参数

| 名称   | 位置 | 类型   | 必选 | 说明 |      |
| ------ | ---- | ------ | ---- | ---- | ---- |
| postId | path | string | 是   | none |      |
| body   | body | object | 否   | none |      |

> 返回示例

> 200 Response

```json
{
  "comments": [
    {
      "commentId": "int",
      "userId": "int",
      "username": "string",
      "content": "string",
      "createdAt": "string"
    }
  ]
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称         | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------ | -------- | ----- | ---- | ------ | ---- |
| » comments   | [object] | true  | none |        | none |
| »» commentId | string   | false | none |        | none |
| »» userId    | string   | false | none |        | none |
| »» username  | string   | false | none |        | none |
| »» content   | string   | false | none |        | none |
| »» createdAt | string   | false | none |        | none |

#### DELETE 删除评论

DELETE /api/comment/{commentId}

> Body 请求参数

```yaml
{}

```

#### 请求参数

| 名称      | 位置 | 类型   | 必选 | 说明 |
| --------- | ---- | ------ | ---- | ---- |
| commentId | path | string | 是   | none |
| body      | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |


### 2.3 评论管理接口

#### POST 发表评论

POST /api/post/{postId}/comment

> Body 请求参数

```yaml
userId: 0
content: ""

```

#### 请求参数

| 名称      | 位置 | 类型    | 必选 | 说明 |
| --------- | ---- | ------- | ---- | ---- |
| postId    | path | string  | 是   | none |
| body      | body | object  | 否   | none |
| » userId  | body | integer | 否   | none |
| » content | body | string  | 否   | none |

> 返回示例

> 200 Response

```json
{
  "commentId": "int",
  "message": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ----------- | ------ | ---- | ---- | ------ | ---- |
| » commentId | string | true | none |        | none |
| » message   | string | true | none |        | none |

#### GET 获取动态评论

GET /api/post/{postId}/comments

> Body 请求参数

```yaml
{}

```

#### 请求参数

| 名称   | 位置 | 类型   | 必选 | 说明 |
| ------ | ---- | ------ | ---- | ---- |
| postId | path | string | 是   | none |
| body   | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "comments": [
    {
      "commentId": "int",
      "userId": "int",
      "username": "string",
      "content": "string",
      "createdAt": "string"
    }
  ]
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称         | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------ | -------- | ----- | ---- | ------ | ---- |
| » comments   | [object] | true  | none |        | none |
| »» commentId | string   | false | none |        | none |
| »» userId    | string   | false | none |        | none |
| »» username  | string   | false | none |        | none |
| »» content   | string   | false | none |        | none |
| »» createdAt | string   | false | none |        | none |

#### DELETE 删除评论

DELETE /api/comment/{commentId}

> Body 请求参数

```yaml
{}

```

#### 请求参数

| 名称      | 位置 | 类型   | 必选 | 说明 |
| --------- | ---- | ------ | ---- | ---- |
| commentId | path | string | 是   | none |
| body      | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

### 2.4 校园评价接口

#### POST 发布评分和评价

POST /api/review

> Body 请求参数

```yaml
userId: 0
target: ""
targetId: 0
rating: ""
comment: ""

```

#### 请求参数

| 名称       | 位置 | 类型    | 必选 | 说明        |
| ---------- | ---- | ------- | ---- | ----------- |
| body       | body | object  | 否   | none        |
| » userId   | body | integer | 否   | none        |
| » target   | body | string  | 否   | 评价对象    |
| » targetId | body | integer | 否   | 对应对象 ID |
| » rating   | body | string  | 否   | none        |
| » comment  | body | string  | 否   | none        |

> 返回示例

> 200 Response

```json
{
  "reviewId": "int",
  "message": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称       | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ---------- | ------ | ---- | ---- | ------ | ---- |
| » reviewId | string | true | none |        | none |
| » message  | string | true | none |        | none |

#### GET 获取评分和评价列表

GET /api/review

> Body 请求参数

```yaml
{}

```

#### 请求参数

| 名称     | 位置  | 类型    | 必选 | 说明        |
| -------- | ----- | ------- | ---- | ----------- |
| target   | query | string  | 否   | 评价类型    |
| targetId | query | integer | 否   | 具体对象 ID |
| page     | query | integer | 否   | 页码        |
| body     | body  | object  | 否   | none        |

> 返回示例

> 200 Response

```json
{
  "reviews": [
    {
      "reviewId": "int",
      "userId": "int",
      "username": "string",
      "category": "string",
      "targetId": "int",
      "rating": "float",
      "content": "string",
      "createdAt": "string"
    }
  ],
  "total": "int"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称         | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------ | -------- | ----- | ---- | ------ | ---- |
| » reviews    | [object] | true  | none |        | none |
| »» reviewId  | string   | false | none |        | none |
| »» userId    | string   | false | none |        | none |
| »» username  | string   | false | none |        | none |
| »» category  | string   | false | none |        | none |
| »» targetId  | string   | false | none |        | none |
| »» rating    | string   | false | none |        | none |
| »» content   | string   | false | none |        | none |
| »» createdAt | string   | false | none |        | none |
| » total      | string   | true  | none |        | none |

#### GET 获取单个对象评分详情

GET /api/review/{reviewId}

> Body 请求参数

```yaml
{}

```

#### 请求参数

| 名称     | 位置 | 类型   | 必选 | 说明 |
| -------- | ---- | ------ | ---- | ---- |
| reviewId | path | string | 是   | none |
| body     | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "reviewId": "int",
  "userId": "int",
  "username": "string",
  "category": "string",
  "targetId": "int",
  "rating": "float",
  "content": "string",
  "createdAt": "string"
}
```

#### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

#### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ----------- | ------ | ---- | ---- | ------ | ---- |
| » reviewId  | string | true | none |        | none |
| » userId    | string | true | none |        | none |
| » username  | string | true | none |        | none |
| » category  | string | true | none |        | none |
| » targetId  | string | true | none |        | none |
| » rating    | string | true | none |        | none |
| » content   | string | true | none |        | none |
| » createdAt | string | true | none |        | none |
