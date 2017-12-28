## 拉取全部系统通知

#### 注意事项

- 需要`admin`权限

#### 请求

```
GET /api/notify/all
```

##### 正常返回

```json
[
    {
        "id": "5a372ca8acd01000019bedbc",
        "type": 1,
        "receiver": "*",
        "content": {
            "title": "test",
            "priority":1,
            "content":"dajiahao",
            "start_time":"1513565352",
            "end_time":"1513569384"
        },
        "create_time": 1513565352,
        "is_read": false
    }
]
```

##### 参数说明

|参数|描述|
|---|---|
|content|消息内容|


