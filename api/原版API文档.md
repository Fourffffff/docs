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

## POST 用户登录

POST /api/user/login

> Body 请求参数

```yaml
email: ""
password: ""

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明                 |
| ----------- | ------ | ---- | ---- | ------ | -------------------- |
| » userId    | string | true | none |        | none                 |
| » username  | string | true | none |        | none                 |
| » email     | string | true | none |        | none                 |
| » token     | string | true | none |        | none                 |
| » expiresIn | string | true | none |        | Token 过期时间（秒） |

## POST 用户注册

POST /api/user/register

> Body 请求参数

```yaml
username: ""
password: ""
email: ""
avatar: ""

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ----------- | ------ | ---- | ---- | ------ | ---- |
| » userId    | string | true | none |        | none |
| » username  | string | true | none |        | none |
| » email     | string | true | none |        | none |
| » createdAt | string | true | none |        | none |

## GET 用户信息获取

GET /api/user/{userId}

> Body 请求参数

```yaml
{}

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ----------- | ------ | ---- | ---- | ------ | ---- |
| » userId    | string | true | none |        | none |
| » username  | string | true | none |        | none |
| » email     | string | true | none |        | none |
| » avatar    | string | true | none |        | none |
| » bio       | string | true | none |        | none |
| » createdAt | string | true | none |        | none |

## PUT 用户信息更新 

PUT /api/user/{userId}

> Body 请求参数

```yaml
username: ""
email: ""
avatar: ""
bio: ""

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

## POST 添加收藏

POST /api/user/{userId}/collect

> Body 请求参数

```yaml
postId: 0

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称     | 类型   | 必选 | 约束 | 中文名 | 说明 |
| -------- | ------ | ---- | ---- | ------ | ---- |
| » postId | string | true | none |        | none |

## GET 获取收藏列表

GET /api/user/{userId}/collect

> Body 请求参数

```yaml
{}

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称          | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------- | -------- | ----- | ---- | ------ | ---- |
| » collections | [object] | true  | none |        | none |
| »» collectId  | string   | false | none |        | none |
| »» postId     | string   | false | none |        | none |
| »» title      | string   | false | none |        | none |
| »» category   | string   | false | none |        | none |
| »» createdAt  | string   | false | none |        | none |

## DELETE 取消收藏

DELETE /api/user/{userId}/collect/{postId}

> Body 请求参数

```yaml
{}

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

# 我的商小/帖子管理

## GET 获取用户发布的动态

GET /api/user/{userId}/posts

### 请求参数

| 名称   | 位置 | 类型   | 必选 | 说明 |
| ------ | ---- | ------ | ---- | ---- |
| userId | path | string | 是   | none |

> 返回示例

> 200 Response

```json
{
  "posts": [
    {
      "postId": "int",
      "title": "string",
      "content": "string",
      "images": [
        "string"
      ],
      "likes": "int",
      "comments": "int",
      "createdAt": "string"
    }
  ]
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称         | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------ | -------- | ----- | ---- | ------ | ---- |
| » posts      | [object] | true  | none |        | none |
| »» postId    | string   | false | none |        | none |
| »» title     | string   | false | none |        | none |
| »» content   | string   | false | none |        | none |
| »» images    | [string] | false | none |        | none |
| »» likes     | string   | false | none |        | none |
| »» comments  | string   | false | none |        | none |
| »» createdAt | string   | false | none |        | none |

## PUT 发布动态

PUT /api/post

> Body 请求参数

```yaml
userId: ""
title: ""
content: ""
images: ""
category: ""

```

### 请求参数

| 名称       | 位置 | 类型   | 必选 | 说明          |
| ---------- | ---- | ------ | ---- | ------------- |
| body       | body | object | 否   | none          |
| » userId   | body | string | 否   | none          |
| » title    | body | string | 否   | none          |
| » content  | body | string | 否   | none          |
| » images   | body | string | 否   | 图片 URL 列表 |
| » category | body | string | 否   | 分类          |

> 返回示例

> 200 Response

```json
{
  "postId": "int",
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » postId  | string | true | none |        | none |
| » message | string | true | none |        | none |

## GET 获取动态列表（参数不清楚该怎么写） 

GET /api/post

### 请求参数

| 名称     | 位置  | 类型    | 必选 | 说明     |
| -------- | ----- | ------- | ---- | -------- |
| category | query | string  | 否   | 筛选分类 |
| page     | query | integer | 否   | 每页数量 |

> 返回示例

> 200 Response

```json
{
  "posts": [
    {
      "postId": "int",
      "userId": "int",
      "username": "string",
      "title": "string",
      "content": "string",
      "images": [
        "string"
      ],
      "likes": "int",
      "comments": "int",
      "createdAt": "string"
    }
  ],
  "total": "int"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称         | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------ | -------- | ----- | ---- | ------ | ---- |
| » posts      | [object] | true  | none |        | none |
| »» postId    | string   | false | none |        | none |
| »» userId    | string   | false | none |        | none |
| »» username  | string   | false | none |        | none |
| »» title     | string   | false | none |        | none |
| »» content   | string   | false | none |        | none |
| »» images    | [string] | false | none |        | none |
| »» likes     | string   | false | none |        | none |
| »» comments  | string   | false | none |        | none |
| »» createdAt | string   | false | none |        | none |
| » total      | string   | true  | none |        | none |

## GET 获取动态详情

GET /api/post/{postId}

> Body 请求参数

```yaml
{}

```

### 请求参数

| 名称   | 位置 | 类型   | 必选 | 说明 |
| ------ | ---- | ------ | ---- | ---- |
| postId | path | string | 是   | none |
| body   | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "postId": "int",
  "userId": "int",
  "username": "string",
  "title": "string",
  "content": "string",
  "images": [
    "string"
  ],
  "likes": "int",
  "comments": "int",
  "createdAt": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称        | 类型     | 必选 | 约束 | 中文名 | 说明 |
| ----------- | -------- | ---- | ---- | ------ | ---- |
| » postId    | string   | true | none |        | none |
| » userId    | string   | true | none |        | none |
| » username  | string   | true | none |        | none |
| » title     | string   | true | none |        | none |
| » content   | string   | true | none |        | none |
| » images    | [string] | true | none |        | none |
| » likes     | string   | true | none |        | none |
| » comments  | string   | true | none |        | none |
| » createdAt | string   | true | none |        | none |

## DELETE 删除动态

DELETE /api/post/{postId}

> Body 请求参数

```yaml
{}

```

### 请求参数

| 名称   | 位置 | 类型   | 必选 | 说明 |
| ------ | ---- | ------ | ---- | ---- |
| postId | path | string | 是   | none |
| body   | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

## POST 点赞动态

POST /api/post/{postId}/like

> Body 请求参数

```yaml
userId: 0

```

### 请求参数

| 名称     | 位置 | 类型    | 必选 | 说明 |
| -------- | ---- | ------- | ---- | ---- |
| postId   | path | string  | 是   | none |
| body     | body | object  | 否   | none |
| » userId | body | integer | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string",
  "likes": "int"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明     |
| --------- | ------ | ---- | ---- | ------ | -------- |
| » message | string | true | none |        | none     |
| » likes   | string | true | none |        | 点赞总数 |

## DELETE 取消点赞动态

DELETE /api/post/{postId}/like

> Body 请求参数

```yaml
userId: ""

```

### 请求参数

| 名称     | 位置 | 类型   | 必选 | 说明 |
| -------- | ---- | ------ | ---- | ---- |
| postId   | path | string | 是   | none |
| body     | body | object | 否   | none |
| » userId | body | string | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string",
  "likes": "int"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |
| » likes   | string | true | none |        | none |

## POST 收藏动态

POST /api/post/{postId}/collect

> Body 请求参数

```yaml
userId: 0

```

### 请求参数

| 名称     | 位置 | 类型    | 必选 | 说明 |
| -------- | ---- | ------- | ---- | ---- |
| postId   | path | string  | 是   | none |
| body     | body | object  | 否   | none |
| » userId | body | integer | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

## DELETE 取消收藏动态

DELETE /api/post/{postId}/collect

> Body 请求参数

```yaml
userId: ""

```

### 请求参数

| 名称     | 位置 | 类型   | 必选 | 说明 |
| -------- | ---- | ------ | ---- | ---- |
| postId   | path | string | 是   | none |
| body     | body | object | 否   | none |
| » userId | body | string | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

# 我的商小/评论管理

## POST 发表评论

POST /api/post/{postId}/comment

> Body 请求参数

```yaml
userId: 0
content: ""

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称        | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ----------- | ------ | ---- | ---- | ------ | ---- |
| » commentId | string | true | none |        | none |
| » message   | string | true | none |        | none |

## GET 获取动态评论

GET /api/post/{postId}/comments

> Body 请求参数

```yaml
{}

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称         | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------ | -------- | ----- | ---- | ------ | ---- |
| » comments   | [object] | true  | none |        | none |
| »» commentId | string   | false | none |        | none |
| »» userId    | string   | false | none |        | none |
| »» username  | string   | false | none |        | none |
| »» content   | string   | false | none |        | none |
| »» createdAt | string   | false | none |        | none |

## DELETE 删除评论

DELETE /api/comment/{commentId}

> Body 请求参数

```yaml
{}

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

# 我的商小/校园评价

## POST 发布评分和评价

POST /api/review

> Body 请求参数

```yaml
userId: 0
target: ""
targetId: 0
rating: ""
comment: ""

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称       | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ---------- | ------ | ---- | ---- | ------ | ---- |
| » reviewId | string | true | none |        | none |
| » message  | string | true | none |        | none |

## GET 获取评分和评价列表

GET /api/review

> Body 请求参数

```yaml
{}

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

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

## GET 获取单个对象评分详情

GET /api/review/{reviewId}

> Body 请求参数

```yaml
{}

```

### 请求参数

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

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

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

## DELETE 删除评价

DELETE /api/review/{reviewId}

> Body 请求参数

```yaml
userId: ""

```

### 请求参数

| 名称     | 位置 | 类型   | 必选 | 说明 |
| -------- | ---- | ------ | ---- | ---- |
| reviewId | path | string | 是   | none |
| body     | body | object | 否   | none |
| » userId | body | string | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

# 我的商小/课程管理

## POST 导入课程表

POST /api/timetable/import

> Body 请求参数

```yaml
userId: 0
courseName: ""
courseTime: ""
teacher: ""
dayOfWeek: 0
time: ""
location: ""

```

### 请求参数

| 名称         | 位置 | 类型    | 必选 | 说明              |
| ------------ | ---- | ------- | ---- | ----------------- |
| body         | body | object  | 否   | none              |
| » userId     | body | integer | 否   | none              |
| » courseName | body | string  | 否   | none              |
| » courseTime | body | string  | 否   | none              |
| » teacher    | body | string  | 否   | none              |
| » dayOfWeek  | body | integer | 否   | 1=周一, 2=周二... |
| » time       | body | string  | 否   | "08:00-09:30"     |
| » location   | body | string  | 否   | none              |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

## GET 获取课程表

GET /api/timetable/{userId}

> Body 请求参数

```yaml
{}

```

### 请求参数

| 名称   | 位置 | 类型   | 必选 | 说明 |
| ------ | ---- | ------ | ---- | ---- |
| userId | path | string | 是   | none |
| body   | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称          | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------- | -------- | ----- | ---- | ------ | ---- |
| » courses     | [object] | true  | none |        | none |
| »» courseId   | string   | false | none |        | none |
| »» courseName | string   | false | none |        | none |
| »» courseCode | string   | false | none |        | none |
| »» teacher    | string   | false | none |        | none |
| »» dayOfWeek  | string   | false | none |        | none |
| »» time       | string   | false | none |        | none |
| »» location   | string   | false | none |        | none |

## PUT 更新课程信息

PUT /api/timetable/{courseId}

> Body 请求参数

```yaml
courseName: ""
courseCode: ""
teacher: ""
dayOfWeek: 0
time: ""
location: ""

```

### 请求参数

| 名称         | 位置 | 类型    | 必选 | 说明 |
| ------------ | ---- | ------- | ---- | ---- |
| courseId     | path | string  | 是   | none |
| body         | body | object  | 否   | none |
| » courseName | body | string  | 否   | none |
| » courseCode | body | string  | 否   | none |
| » teacher    | body | string  | 否   | none |
| » dayOfWeek  | body | integer | 否   | none |
| » time       | body | string  | 否   | none |
| » location   | body | string  | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

## DELETE 删除课程

DELETE /api/timetable/{courseId}

### 请求参数

| 名称     | 位置 | 类型   | 必选 | 说明 |
| -------- | ---- | ------ | ---- | ---- |
| courseId | path | string | 是   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

# 我的商小/兼职招聘

## POST 发布兼职招聘

POST /api/job

> Body 请求参数

```yaml
userId: 0
title: ""
description: ""
salary: ""
location: ""
contact: ""
workTime: ""

```

### 请求参数

| 名称          | 位置 | 类型    | 必选 | 说明 |
| ------------- | ---- | ------- | ---- | ---- |
| body          | body | object  | 否   | none |
| » userId      | body | integer | 否   | none |
| » title       | body | string  | 否   | none |
| » description | body | string  | 否   | none |
| » salary      | body | string  | 否   | none |
| » location    | body | string  | 否   | none |
| » contact     | body | string  | 否   | none |
| » workTime    | body | string  | 否   | none |

> 返回示例

> 200 Response

```json
{
  "jobId": "int",
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » jobId   | string | true | none |        | none |
| » message | string | true | none |        | none |

## GET 获取兼职招聘列表

GET /api/job

> Body 请求参数

```yaml
{}

```

### 请求参数

| 名称 | 位置  | 类型    | 必选 | 说明 |
| ---- | ----- | ------- | ---- | ---- |
| page | query | integer | 否   | none |
| body | body  | object  | 否   | none |

> 返回示例

> 200 Response

```json
{
  "jobs": [
    {
      "jobId": "int",
      "userId": "int",
      "title": "string",
      "salary": "string",
      "location": "string",
      "workTime": "string",
      "createdAt": "string"
    }
  ],
  "total": "int"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称         | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------------ | -------- | ----- | ---- | ------ | ---- |
| » jobs       | [object] | true  | none |        | none |
| »» jobId     | string   | false | none |        | none |
| »» userId    | string   | false | none |        | none |
| »» title     | string   | false | none |        | none |
| »» salary    | string   | false | none |        | none |
| »» location  | string   | false | none |        | none |
| »» workTime  | string   | false | none |        | none |
| »» createdAt | string   | false | none |        | none |
| » total      | string   | true  | none |        | none |

## GET 获取兼职招聘详情

GET /api/job/{jobId}

> Body 请求参数

```yaml
{}

```

### 请求参数

| 名称  | 位置 | 类型   | 必选 | 说明 |
| ----- | ---- | ------ | ---- | ---- |
| jobId | path | string | 是   | none |
| body  | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "jobId": "int",
  "userId": "int",
  "title": "string",
  "description": "string",
  "salary": "string",
  "location": "string",
  "contact": "string",
  "workTime": "string",
  "createdAt": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称          | 类型   | 必选 | 约束 | 中文名 | 说明 |
| ------------- | ------ | ---- | ---- | ------ | ---- |
| » jobId       | string | true | none |        | none |
| » userId      | string | true | none |        | none |
| » title       | string | true | none |        | none |
| » description | string | true | none |        | none |
| » salary      | string | true | none |        | none |
| » location    | string | true | none |        | none |
| » contact     | string | true | none |        | none |
| » workTime    | string | true | none |        | none |
| » createdAt   | string | true | none |        | none |

## DELETE 删除兼职招聘

DELETE /api/job/{jobId}

> Body 请求参数

```yaml
{}

```

### 请求参数

| 名称  | 位置 | 类型   | 必选 | 说明 |
| ----- | ---- | ------ | ---- | ---- |
| jobId | path | string | 是   | none |
| body  | body | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

## POST 应聘兼职

POST /api/job/{jobId}/apply

> Body 请求参数

```yaml
userId: 0
contactInfo: ""

```

### 请求参数

| 名称          | 位置 | 类型    | 必选 | 说明 |
| ------------- | ---- | ------- | ---- | ---- |
| jobId         | path | string  | 是   | none |
| body          | body | object  | 否   | none |
| » userId      | body | integer | 否   | none |
| » contactInfo | body | string  | 否   | none |

> 返回示例

> 200 Response

```json
{
  "message": "string"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称      | 类型   | 必选 | 约束 | 中文名 | 说明 |
| --------- | ------ | ---- | ---- | ------ | ---- |
| » message | string | true | none |        | none |

## GET 获取兼职申请列表

GET /api/job/{jobId}/applications

### 请求参数

| 名称  | 位置 | 类型   | 必选 | 说明 |
| ----- | ---- | ------ | ---- | ---- |
| jobId | path | string | 是   | none |

> 返回示例

> 200 Response

```json
{
  "applications": [
    {
      "userId": "int",
      "username": "string",
      "contactInfo": "string",
      "appliedAt": "string"
    }
  ]
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称           | 类型     | 必选  | 约束 | 中文名 | 说明 |
| -------------- | -------- | ----- | ---- | ------ | ---- |
| » applications | [object] | true  | none |        | none |
| »» userId      | string   | false | none |        | none |
| »» username    | string   | false | none |        | none |
| »» contactInfo | string   | false | none |        | none |
| »» appliedAt   | string   | false | none |        | none |

# 我的商小/其他

## GET 获取动态（首页）

GET /api/feed

### 请求参数

| 名称 | 位置  | 类型    | 必选 | 说明 |
| ---- | ----- | ------- | ---- | ---- |
| page | query | integer | 否   | none |

> 返回示例

> 200 Response

```json
{
  "feed": [
    {
      "type": "string",
      "data": {}
    }
  ],
  "total": "int"
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称    | 类型     | 必选  | 约束 | 中文名 | 说明 |
| ------- | -------- | ----- | ---- | ------ | ---- |
| » feed  | [object] | true  | none |        | none |
| »» type | string   | false | none |        | none |
| »» data | object   | false | none |        | none |
| » total | string   | true  | none |        | none |

## GET 搜索帖子/用户/招聘信息

GET /api/search

> Body 请求参数

```yaml
{}

```

### 请求参数

| 名称  | 位置  | 类型   | 必选 | 说明 |
| ----- | ----- | ------ | ---- | ---- |
| query | query | string | 否   | none |
| body  | body  | object | 否   | none |

> 返回示例

> 200 Response

```json
{
  "posts": [],
  "users": [],
  "jobs": []
}
```

### 返回结果

| 状态码 | 状态码含义                                              | 说明 | 数据模型 |
| ------ | ------------------------------------------------------- | ---- | -------- |
| 200    | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none | Inline   |

### 返回数据结构

状态码 **200**

| 名称    | 类型     | 必选 | 约束 | 中文名 | 说明     |
| ------- | -------- | ---- | ---- | ------ | -------- |
| » posts | [string] | true | none |        | 帖子结果 |
| » users | [string] | true | none |        | 用户结果 |
| » jobs  | [string] | true | none |        | 兼职结果 |

# 数据模型

<h2 id="tocS_Pet">Pet</h2>

<a id="schemapet"></a>
<a id="schema_Pet"></a>
<a id="tocSpet"></a>
<a id="tocspet"></a>

```json
{
  "id": 1,
  "category": {
    "id": 1,
    "name": "string"
  },
  "name": "doggie",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 1,
      "name": "string"
    }
  ],
  "status": "available"
}

```

### 属性

| 名称      | 类型                        | 必选 | 约束 | 中文名 | 说明         |
| --------- | --------------------------- | ---- | ---- | ------ | ------------ |
| id        | integer(int64)              | true | none |        | 宠物ID编号   |
| category  | [Category](#schemacategory) | true | none |        | 分组         |
| name      | string                      | true | none |        | 名称         |
| photoUrls | [string]                    | true | none |        | 照片URL      |
| tags      | [[Tag](#schematag)]         | true | none |        | 标签         |
| status    | string                      | true | none |        | 宠物销售状态 |

#### 枚举值

| 属性   | 值        |
| ------ | --------- |
| status | available |
| status | pending   |
| status | sold      |

<h2 id="tocS_Category">Category</h2>

<a id="schemacategory"></a>
<a id="schema_Category"></a>
<a id="tocScategory"></a>
<a id="tocscategory"></a>

```json
{
  "id": 1,
  "name": "string"
}

```

### 属性

| 名称 | 类型           | 必选  | 约束 | 中文名 | 说明       |
| ---- | -------------- | ----- | ---- | ------ | ---------- |
| id   | integer(int64) | false | none |        | 分组ID编号 |
| name | string         | false | none |        | 分组名称   |

<h2 id="tocS_Tag">Tag</h2>

<a id="schematag"></a>
<a id="schema_Tag"></a>
<a id="tocStag"></a>
<a id="tocstag"></a>

```json
{
  "id": 1,
  "name": "string"
}

```

### 属性

| 名称 | 类型           | 必选  | 约束 | 中文名 | 说明       |
| ---- | -------------- | ----- | ---- | ------ | ---------- |
| id   | integer(int64) | false | none |        | 标签ID编号 |
| name | string         | false | none |        | 标签名称   |