## 拉取消息

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
|receiver|用户名|
|content|消息内容|


##### 错误返回
