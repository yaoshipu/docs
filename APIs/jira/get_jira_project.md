## 获取jira project列表

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/jira/project
```

##### 请求参数

无

##### 参数说明

| 参数 | 说明 |
| --- | --- |
| key | 用于寻找jira board |


##### 正常返回

```json
[
    {
        "id": "11114",
        "key": "APM",
        "name": "APM"
    },
    {
        "id": "10307",
        "key": "APPS",
        "name": "APPS"
    },
    {
        "id": "11901",
        "key": "ARGO",
        "name": "ARGO"
    },
    {
        "id": "10217",
        "key": "ASLAN",
        "name": "Aslan"
    }
]
```

##### 错误返回
