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
        "sender": "*",
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
        "sender": "guoyu",
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





##### 错误返回
