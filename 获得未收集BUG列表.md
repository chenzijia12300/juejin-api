### 获得未收集BUG列表

#### 请求信息

> https://api.juejin.cn/user_api/v1/bugfix/not_collect

**请求方式：POST**

**认证方式：cookie**

**请求头参数：**

| 参数名       | 类型   | 必传 | 内容             |
| ------------ | ------ | ---- | ---------------- |
| cookie       | string | 是   | 用户凭证         |
| content-type | string | 否   | application/json |

**URL参数：**

| 参数名 | 类型   | 必传 | 内容 |
| ------ | ------ | ---- | ---- |
| aid    | string | 否   | 未知 |
| uuid   | string | 否   | 未知 |
| spider | string | 否   | 未知 |

#### 响应信息

**响应格式：application/json; charset=utf-8**



**根对象:**

| 字段    | 类型   | 内容     |
| ------- | ------ | -------- |
| err_no  | num    | 响应码   |
| err_msg | string | 响应消息 |
| data    | object | 响应内容 |

**data对象:**

| 字段          | 类型    | 内容        |
| ------------- | ------- | ----------- |
| bug_type      | number  | bug类型     |
| bug_time      | number  | bug生成时间 |
| bug_show_type | number  | bug展示类型 |
| is_first      | boolean | 是否第一    |



**请求例子：**

```
curl --location --request POST 'https://api.juejin.cn/user_api/v1/bugfix/not_collect?aid=2608&uuid=7108619669951841822&spider=0' \
--header 'content-type: application/json' \
--header 'cookie: 你滴cookie' \
--data-raw '{}'
```



**响应成功例子：**

```
{
    "err_no": 0,
    "err_msg": "success",
    "data": [
        {
            "bug_type": 8,
            "bug_time": 1661443200,
            "bug_show_type": 1,
            "is_first": false
        }
    ]
}
```



**响应失败例子：**

```
{
    "err_no": 403,
    "err_msg": "must login",
    "data": null
}
```

