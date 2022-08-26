### 收集BUG

#### 请求信息

> https://api.juejin.cn/user_api/v1/bugfix/collect

**请求方式：POST**

**认证方式：cookie**

**请求头参数：**

| 参数名       | 类型   | 必传 | 内容             |
| ------------ | ------ | ---- | ---------------- |
| cookie       | string | 是   | 用户凭证         |
| content-type | string | 是   | application/json |

**请求体参数：**

| 参数名   | 类型   | 必传 | 内容        |
| -------- | ------ | ---- | ----------- |
| bug_type | number | 是   | bug类型     |
| bug_time | number | 是   | bug生成时间 |

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

**请求例子：**

```
curl --location --request POST 'https://api.juejin.cn/user_api/v1/bugfix/collect?aid=2608&uuid=7108619669951841822&spider=0' \
--header 'content-type: application/json' \
--header 'cookie: 你滴cookie' \
--data-raw '{
    "bug_type": 8,
    "bug_time": 1661443200
}'
```



**响应成功例子：**

```
{
    "err_no": 0,
    "err_msg": "success",
    "data": null
}
```



**响应失败例子：**

```
{
    "err_no": 20004,
    "err_msg": "bug already collect",
    "data": null
}
```

