## 获取jira module列表

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/jira/project/:key/field/:field
```

##### 请求参数

| 参数 | 说明 |
| --- | --- |
| key | jira project key |
| field | ["epic","component"] |


##### 参数说明

| 参数 | 说明 |
| --- | --- |
| module_key | 返回的key |
| module_name | 展示的name |





##### 正常返回

```json
[
    {
        "module_key": "Service",
        "module_name": "Service"
    },
    {
        "module_key": "Spock",
        "module_name": "Spock"
    },
    {
        "module_key": "产品化",
        "module_name": "产品化"
    },
    {
        "module_key": "安全&性能",
        "module_name": "安全&性能"
    },
    {
        "module_key": "流程",
        "module_name": "流程"
    }
]
```

##### 错误返回
