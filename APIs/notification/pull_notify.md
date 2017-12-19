## 拉取通知

#### 注意事项

- 需要`user`权限

#### 请求

```
GET /api/notify/pull
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
```json
[
   {
        "id": "5a373c68acd01000019bedbd",
        "type": 2,    
        "receiver": "guoyu",
        "content": {
        "task_id": 1,
        "pipeline_name":"pipline",
        "status":"success"
    },
    "create_time": 1513569384,
    "is_read": false
}
]
```

##### 参数说明

|参数|描述|
|---|---|
|type|`1`对应系统通知，`2`对应pipline提醒|
|receiver|用户名（当用户名为*时为系统通知）|
|content|消息内容|


##### 错误返回
