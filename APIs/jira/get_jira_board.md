## 获取jira board列表

#### 注意事项

- 需要`user`权限
- 只返回有sprint的board

#### 请求

```
GET /api/jira/board/:key
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
        "id": 234,
        "self": "https://jira.qiniu.io/rest/agile/1.0/board/234",
        "name": "Aslan  Sprint Board",
        "type": "scrum"
    }
]
```

##### 错误返回
